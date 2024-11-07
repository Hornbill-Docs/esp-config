---
layout: article-toc
---
# Slideshows
Slideshows provide a way of automatically presenting a number of dashboards one after another, and against definable transitions periods. These dashboards are great for large-screen displays within your support center; they can also be accessed by individuals via a web browser.

**To access Slideshows:**
1. Select the **Configuration** cog at the bottom of the left-hand application menu bar.
1. In Configuration, from the navigation dropdown, select **Platform Configuration**.
1. In the navigation panel, scroll to locate the *Advanced Analytics* section.
1. Click **Slideshows**.

## Creating a new slideshow
You must have dashboards already created and available for use before you can create a slideshow.

**To create a slideshow:**
1. In Slideshows, click **Create New Show**.
1. In the + panel, click to add a slide.
1. For additional slides, click again in the + panel.
1. From the **Show** dropdown, select the dashboard you want in each slide.
1. From the **For** dropdown, select the duration you would like the slide to show for before moving to the next.

## Editing a slideshow
It is possible to edit existing slideshows to add additional slides, remove slides, change the order in which the slides appear, change the dashboard that appears on each slide, and change the period for which each slide will be displayed.

**To add additional slides:**
1. Click the + button and add a dashboard, as well as the duration for which the dashboard will be displayed.

**To remove an existing slide:**
1. Click the delete button (the bin icon) on a slide to remove it from the slideshow.

**To reorder slides:**
1. Drag and drop slides to reorder them in the sequence in which they will display.

**To change the dashboard being displayed on each slide:**
1. From the dropdown list, select a different dashboard from the dropdown list. (Only dashboards marked as *Available for Use* will be displayed.)

**To change the duration each slide will display before transitioning to the next slide:**
1. Select a different time period for which the slide will be displayed.

**To create a clone:**
1. Select the dropdown control next to the Save icon and choose  **Save As**. Give the slideshow a new name. This creates a complete copy of the existing slideshow.

## Running a slideshow
When a slideshow is ready to be presented, there are two display options to choose from:
* **Run Show.** Click the Play button, and the slides will run in the order they have been configured.
* **Run Randomized.** Select this option from the dropdown control next to the Play button, and the slide will ignore the configured sequence and will display the slides in a random order.

## Auto-play a slideshow
You can create a slideshow and have it set to auto-play.

**To set a slideshow to auto-play:**
1. Use this URL:
    `https://live.hornbill.com/<INSTANCENAME>/admin/app/com.hornbill.servicemanager/advanced-analytics/slideshows/<SLIDESHOWID>/play`

1. Replace `<INSTANCENAME>` with your instance name.
1. Replace `<SLIDESHOWID>` with the ID of the slideshow you want to auto-play. You can see the ID of the slideshow in the URL bar of your browser once you are viewing a slideshow in Configuration.

:::tip
If you are intending to share the auto-play URL with other Hornbill users:

* Ensure the users have the Dashboard Viewer role.
* If you have applied access controls on the dashboards in the slideshow, ensure that the users have had the dashboards shared with them, their group, or their role.
:::

## Deleting a slideshow
**To delete one or more slideshows:**
1. Select (tick) the slideshow(s) you wish to delete.
1. From the dropdown next to the **Create New Show** button, click **Delete Selected Slideshow**.

<!-- https://wiki.hornbill.com/index.php?title=Slideshows -->