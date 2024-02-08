# Configuring a Custom Domain for your Customer Portal

:::warning
This document provides preliminary information that is not yet production ready, both the functionality and this content is under active development
:::

## Custom Domain Overview

The customer portal is a feature of the Hornbill solution designed to allow your external contacts interact with your Hornbill instance. Typically this is used in the context of you, as the owner of the Hornbill instance, providing support services to your external customers.   Please note, external customers are identified in the Hornbill solution as "contacts" and these are a distinctly separate from your employees, where you may be providing internal support.  The Customer portal is designed for external users only. 

Because the Customer Portal is designed to provide you with a portal that gives your customers access to the support services you provide, an important element of the portal is the ability to customize its appearance in order to blend the portal into your companies own brand design language.  Every aspect of the portal is customizable, including logo, color scheme and aspects of layout and content.   Beyond appearance of the pages that make up the portal its self, its often highly desirable to have the portal presented on your own brands domain name, making it easier for your customer to locate the portal and identify its from you by the URL/link you may provide to it.   The Custom Domain capabilities allows you to achieve this. 

## What You Need to Know Before Configuring a Custom Domain

The first thing to understand about configuring a custom domain is there is a lot to know and understand.  Its not a case of configuring Hornbill and it will just work, in fact, the configuration in Hornbill is as simple as telling Hornbill the custom domain you want to use, by doing this, Hornbill will accept traffic from that domain and present the portal on that domain.  However, before you configure Hornbill (basically the last step), you need to do the following: -

:::note
It is well beyond the scope of Hornbill's normal support services to assist you through the process of configuring a custom domain for your service porta.  This is because most of the work involves systems that have nothing to do with Hornbill. Typically this means your own DNS services, most likely your own front-end content delivery network, proxy services etc... 

This document will tell you everything you need to know from a Hornbill perspective because configuring Hornbill is very simple, but it assumes that you have expert knowledge of web application infrastructure, DNS, SSL and so on, so you will either need that knowledge, or have access to your own experts to deal with the planning and implementation of the DNS changes, SSL Certificates, CDN and proxy configurations

If you do need our help, we do have access to experts that can help configure, guide, troubleshoot and assist with this type of configuration, but this assistance would be provided on a chargeable basis, which will vary depending on the complexity of your particular systems, security requirements and so on
:::

## Understanding How Custom Domains Work

The high-level operating principle of a custom domain is quite simple.  The web server that serves the portal pages is known as an origin server.  This is the master source of the web pages, images and other content that makes up the portal.  The origin server only serves encrypted traffic so always has a valid SSL certificate, this certificate relates to the *.hornbill.com domain.  

The origin server is __NOT__ the web server that your user will connect to when you enter the portal URL into your browser. The Origin server is not directly accessible, it only serves traffic when originating from a specific domain.  In the case of Hornbill, the general portal URL is https://customer.hornbill.com/ and this is the normal domain Origin these servers are configured to serve traffic.   The host customer.hornbill.com host resolves to a load balancer and a group of proxy servers, these servers are owned and operated by our web application front end content delivery network partner, in our case this is a company called Cloudflare. 

![customer portal default](_books/esp-config/customize/customer-portal/images/customer-portal-default.png)

The important thing to note here is the role of the SSL certificate.  The connection between the users browser and the front end services uses a TLS connection that is secured with a Hornbill owned SSL certificate.  An SSL certificate is implicitly bound to a specific domain, so that SSL certificate can only secure network traffic that is served on the hornbill.com domain.  The certificate must be hosted on the servers at the "arrow end" of the traffic lines shown in the diagram, so the SSL certificates __2b__ are hosted on __2c__, which means we have given specific permission to our web front end partner (Cloudflare at the time of this writing) to host and use our verified SSL certificates for traffic related to our *.hornbill.com domain.

You will also see that traffic between the front end services and our Origin servers is also encrypted traffic using an SSL certificate bound to the .hornbill.com domain, this is because we also host our verified SSL certificates for traffic served by our own Origin servers. 

When your user enters service.hornbill.com/your_instance_id into their browser, the browser will resolve that URL to the Cloudflare service via DNS __2a__, this DNS server is under our control, its the DNS service we use for .hornbill.com.   The browser connects to the front end services using our SSL certificate __2b__ which is hosted on the front end servers __2c__.  The front end proxy servers __2c__ know the traffic for this domain needs to be forwarded on to our origin servers __3c__ so lookup the origin servers IP address using the DNS service controller by looking up the host addresses from our DNS service __3a__, again, which is a service Hornbill controls in relation to our .hornbill.com domain. 

In summary, Hornbill controls the configuration of all elements of columns __2__ and __3__ in the diagram, this is important to understand when it comes to configuring a custom domain.

When using a custom domain, things work a little bit differently. 

![customer portal default](_books/esp-config/customize/customer-portal/images/customer-portal-custom.png)

In this configuration, it is important to note that Hornbill only controls the configuration of column __3__ in the revised diagram, and, it should be noted that Hornbill does not need to configure anything specific in column __3__ in order for you to configure, and make use of, a custom domain for your Hornbill customer portal instance. 

In order to set up a custom domain, you need to configure the following things: - 

|Item|Name|Description|
|:--|:--|:--|
|2a|DNS|Your chosen custom domain must be hosted on a DNS service somewhere. Typically your corporate domain, like `yourcompany.com` will be configured for your web site, typically www.yourcompnay.com, there is a large variation of DNS hosting and setups generally, so trying to explain how to configure DNS is out of scope for the purpose of this document.  What you need to do is decide what your custom domain for the portal will be, a common use might be `support.yourcompany.com` for example.  You then need to add a [CNAME](https://en.wikipedia.org/wiki/CNAME_record) entry into your DNS server, that maps your chosen custom domain to hornbill's origin server domain name, often referred to as creating an alias. Here is an example of a [CNAME](https://en.wikipedia.org/wiki/CNAME_record) configuration: - <br><br> ![dns cnam config](_books/esp-config/customize/customer-portal/images/dns-cname-example.png)|
|2b|SSL Certificate|It is your responsibility to obtain a valid SSL certificate for your chosen custom domain. You may already have a usable wildcard certificate for *.yourcompany.com or you may decide to have a specific certificate just for your chosen custom domain.  This is really a choice you/your team will make based on your own policies around managing and hosting SSL certificates. From a Hornbill standpoint, the details of your SSL certificate is not relevant, the only requirement Hornbill has is your traffic is encrypted, unencrypted traffic will not work because the domain origin for anything other than https:// is not supported|
|2c|Proxy| Your SSL certificate needs to be hosted on a proxy server in order to serve encrypted traffic using your own SSL certificates.  This can take many forms, from proxies you host yourself in your own data centers to using 3rd Party front end CDN type providers, like we do with Cloudflare for example.  The odds are very good that you already have these things in place, so your experts need to plan and decide on the specifics of your own configuration. The only thing that is mandatory is your hosting provider must be able to act as a proxy service with support for SSL certificates.|


## It May Be Really Simple

If your domain is already hosted on Cloudflare, Akamai, Amazon Cloudfront or one of the many other major front end services, your SSL certs may already be in place and usable. If this is the case, all you really need to do is choose your custom sub-domain and add a single CNAME record into your DNS, then add the custom domain to your portal configuration in Hornbill and thats it. 

![dns cnam config](_books/esp-config/customize/customer-portal/images/dns-cname-example.png)


## Origin Servers

|Server|Description|
|:--|:--|
|https://mdh-p01-customer-portal.hornbill.com/|This is the origin server used for custom domain [CNAME](https://en.wikipedia.org/wiki/CNAME_record) targets.  These servers are hosted in the UK but work for custom domains in all regions because front end proxy servers will cache content as required.|

The is one final step and that is to configure your Hornbill instance in order that the Hornbill servers will allow traffic to be served to your custom domain.  This step is simple. Navigate to: -

`Administration` -> `Platform Configuration` -> `Customize` -> `Customer Portal` 

And in the properties, go to the __Domain Settings__ section and set the __Custom Domain Name__ field. The format you enter here has to be accurate and in the exact same format as shown here: -

https://custom.yourcompany.com

Please ensure what you enter here follows these requirements exactly

- You __MUST__ use only lower-case letters
- The custom domain __MUST__ start with https:// because only encrypted traffic is allowed
- The domain name part custom.yourcompany.com __MUST NOT__ include a trailing forward-slash

Assuming everything is configured correctly, you should now be able to enter your custom domain into a browser and see your Hornbill customer portal instance.

## Current Limitations
- Only a single custom domain is supported for your customer portal.
- Hornbill does not have any ability to host or manage your SSL certificates, you either need to host these yourself or use a front end network provider like Cloudflare for that. 
- Hornbills origin servers are not designed for high traffic volumes for direct traffic serving, if we detect that type of traffic we may well block it, these servers are specifically for use Origin duties only, and should be used for the sole purpose of acting as the origin source for front end content delivery networks or caching proxy servers. 

## Troubleshooting

As mentioned above, it is beyond the scope of Hornbill's normal support services or expertise to provide technical support or assistance with troubleshooting the configuration of your custom domain configuration.  This is because most of the configuration effort goes into systems that are completely outside of Hornbill and these external systems can be configured in many different ways, using many different software tools, packages and services, and much of the configuration in these ares are generally dictated by your own companies security and web hosting policies and practices. It is incredibly important that you have the support of your people/team/experts in planning and configuring a custom domain name for the Hornbill Customer Portal. 

Hornbill does have specialist expert services capabilities, but we have limited resources and charge for these services.  So if you really do need Hornbill to get involved and assist you in configuring this, we can do that, but it will be chargeable work, and will likely involve subject matter experts that do not sit within our support or expert services teams.  Contact us if you need help.  Otherwise, we have aimed to set out everything you/your experts need to know in order to configure this successfully. 

If you have questions/clarifications about anything in this document, please use our [Hornbill Community Forums](https://forums.hornbill.com) in the first instance, we will mostly answer most questions that need clarifying by updating this document. 



