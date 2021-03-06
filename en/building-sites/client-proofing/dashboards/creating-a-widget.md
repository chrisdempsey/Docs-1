---
title: "Creating a Dashboard Widget"
_old_id: "69"
_old_uri: "2.x/administering-your-site/dashboards/creating-a-dashboard-widget"
---

This article describes how to create a custom Dashboard Widget, including a short description of the different Dashboard Widget types and how they work.

## Creating a Basic Widget

Go to the Dashboards page (Dashboard -> Dashboards in the top menu), and click on the "Widgets" tab. Then, click on "Create New Widget", and this will load the Widget creation screen. You'll see a few new fields:

- **Name** - The name of your new widget. Let's call ours "Hello World".
- **Description** - A short description of your widget, used internally.
- **Widget Type** - The type of Widget. We'll get into this more later, but for now, just select "HTML".
- **Size** - Widgets come in 3 sizes - half, full, and double. A half-sized widget takes up half of one row. A full takes up one whole row. A double takes up 2 rows.
- **Namespace** - The Namespace to associate the widget with. Useful for Extras developers; but for us, let's keep it at "core".
- **Lexicon** - Adds an ability to load a lexicon with this widget. Let's go ahead and leave ours at "core:dashboards", the default setting.

You'll note that as you type the name of the widget, text appears below it following what you type. This is the automatic translation tool for Widget names; if you were to type a Lexicon Entry key, it would translate it (try typing "widget\_create" for kicks to see what it does).

Now, in your dashboard widget content, go ahead and put this:

``` php
<p>Hello, world!</p>
```

Our widget should look like this:

![](dashboard-create1.png)

Go ahead and save the Widget.

### Assigning the Widget to the Default Dashboard

Now that we've got our widget, let's assign it to the Default Dashboard, by going back to the main Dashboards page, clicking on the "Dashboards" tab, and finding the default Dashboard. Right-click on it, and click "Update Dashboard". This will load the Default Dashboard editing page.

From here, click the "Place Widget" button above the Widgets grid on this page. Select our "Hello World" widget from the dropdown, and click save. Now our Widget is on the Dashboard! Let's go ahead and place it in position #2 by dragging it between the "Configuration Check" widget and the "MODX News Feed" widget:

![](dashboard-create2.png)

Save your Dashboard.

### Viewing the Widget

Now, if you click the "Dashboard" top menu item on the page, you can see your new dashboard widget in place!

![](dashboard-create3.png)

## Other Widget Types

Obviously, there are more widget types to create. See the [Dashboard Widget Types](building-sites/client-proofing/dashboards/widget-types "Dashboard Widget Types") section for more information on creating different types of widgets.

## See Also

1. [Managing Your Dashboard](building-sites/client-proofing/dashboards/managing)
2. [Assigning a Dashboard to a User Group](building-sites/client-proofing/dashboards/usergroups)
3. [Creating a Dashboard Widget](building-sites/client-proofing/dashboards/creating-a-widget)
4. [Dashboard Widget Types](building-sites/client-proofing/dashboards/widget-types)
    1. [Dashboard Widget Type - File](building-sites/client-proofing/dashboards/widget-types/file)
    2. [Dashboard Widget Type - HTML](building-sites/client-proofing/dashboards/widget-types/html)
    3. [Dashboard Widget Type - Inline PHP](building-sites/client-proofing/dashboards/widget-types/inline-php)
    4. [Dashboard Widget Type - Snippet](building-sites/client-proofing/dashboards/widget-types/snippet)
