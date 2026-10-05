---
layout: article-toc
---
## Request Catalog

The Request Catalog is an Employee Portal page that lists all the catalog items a user can raise in one place. Users don't have to open each service in turn to find the right form; they can browse or search everything from a single page.

### What users see

- **All requests:** Every catalog item the user can raise, shown as cards or a list. Users can search, sort, and filter by service.
- **Quick access:** Shortcuts to the user's recently used items and the items most popular across your organization across the last 90 days.
- **Request cards:** Each card shows the catalog item's name, its service, and its description. Clicking a card opens the request form.

Tip: The Request Catalog uses the names and descriptions you've set on your catalog items. Clear, task-based names (such as *Request remote access* rather than *Remote Access*) and descriptions that add detail beyond the name make it much easier for users to choose the right item. Consider the clarity of catalog item names and descriptions when they are viewed across multiple services.

### Which catalog items appear

Services and their catalog items belong to the Service Manager application. Users only see catalog items from services they're entitled to raise requests against, so the Request Catalog shows each user a different list.

### How to enable the Request Catalog

1. Open [Configuration](/esp-config/getting-started/using-configuration) and select `Service Manager`.
2. Select `Application Settings`.
3. Search for `guest.app.selfService.requestCatalog.enabled`.
4. Set the setting to **On**.

### How to provide access to the Request Catalog

Once enabled, your Request Catalog is available at 'https://live.hornbill.com/<your-instance-id>/servicemanager/selfservice/requestcatalog'.

You can provide users with the direct link, or add a hyperlink within a widget on the Employee Portal to direct users to the catalog.