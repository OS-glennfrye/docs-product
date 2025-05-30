---
tags: ui patterns, user interface design, progress tracking, outsystems ui, widget implementation
summary: OutSystems 11 (O11) features a Progress Circle UI Pattern for visually representing operation flow progress in Traditional Web Apps.
locale: en-us
guid: 8f2233e3-6e6d-46b0-bdb9-ea3fa1d813b3
app_type: traditional web apps
platform-version: o11
figma: https://www.figma.com/file/iBD5yo23NiW53L1zdPqGGM/Developing-an-Application?type=design&node-id=245%3A12&mode=design&t=u4ANW5BJS7Flsdmg-1
audience:
  - frontend developers
  - full stack developers
outsystems-tools:
  - service studio
coverage-type:
  - apply
---

# Progress Circle

<div class="info" markdown="1">

Applies only to Traditional Web Apps.

</div>

You can use the Progress Circle UI Pattern to show the current progress of an operation flow. The progress is incremented in fractions of the circular badge. 

 ![Screenshot of the Progress Circle UI Pattern in a Traditional Web App](images/progresscircle-2-ss.png "Progress Circle UI Pattern")

**How to use the Progress Circle UI Pattern**

In this example, we display the percentage of shipped orders from an existing Customer Order Database.

1. In Service Studio, in the Toolbox, search for `Progress Circle`.

    The Progress Circle widget is displayed.

    ![Screenshot showing the Progress Circle widget in the Service Studio toolbox](images/progresscircle-8-ss.png "Progress Circle Widget in Service Studio")

    If the UI widget doesn't display, it's because the dependency isn't added. This happens because the Remove unused references setting is enabled. To make the widget available in your app:

    1. In the Toolbox, click **Search in other modules**.

    1. In **Search in other Modules**, remove any spaces between words in your search text.
    
    1. Select the widget you want to add from the **OutSystemsUIWeb** module, and click **Add Dependency**. 
    
    1. In the Toolbox, search for the widget again.

1. From the Toolbox, drag the Progress Circle widget into the Main Content area of your application's screen.

    ![Screenshot of dragging the Progress Circle widget into the Main Content area of an application screen](images/progresscircle-9-ss.png "Dragging Progress Circle Widget")

1. Right-click your screen name and select **Add Preparation**.

1. From the Toolbox, drag an Aggregate onto the screen preparation, and enter a name for the aggregate. In this example, we call the aggregate **GetTotalOrders**.

    ![Screenshot of adding an aggregate named GetTotalOrders in the screen preparation](images/progresscircle-10-ss.png "Adding Aggregate for Total Orders")

1. To add a database entity, double-click the aggregate you just created and click on the aggregate screen.

1. From the **Select Source** pop-up, choose the source entity and click **OK**. In this example, we select the **Order** database.

    ![Screenshot of selecting the Order database entity as the source for the GetTotalOrders aggregate](images/progresscircle-11-ss.png "Selecting Source Entity for Aggregate")

1. Return to the screen preparation, and add another aggregate (See step 4). In this example we call the second aggregate **GetShippedOrders**.

    ![Screenshot of adding a second aggregate named GetShippedOrders in the screen preparation](images/progresscircle-12-ss.png "Adding Aggregate for Shipped Orders")

1. To add the relevant database entity, repeat steps 5 and 6.

1. On the aggregate screen, click **Filters**, then **Add Filter**.

1. In the **Filter Condition** pop-up, add the relevant logic for the filter and click **Close**. In this example, to get all of the shipped orders, we add the following logic:

    `Order.Status = Entities.OrderStatus.Shipped`

    ![Screenshot showing the addition of a filter condition to the GetShippedOrders aggregate](images/progresscircle-14-ss.png "Adding Filter to Aggregate")

1. Double-click your screen name, and on the **Properties** tab, from the **Progress** drop-down, select **Expression Editor**. Enter the logic for the progress circle and click **Close**. This displays the percentage value as the stroke on the Progress Circle.

    In this example, to show the percentage of shipped orders, we add the following:

    `GetShippedOrders.Count / GetTotalOrders.Count * 100`

    ![Screenshot of the Expression Editor with logic for the Progress Circle to display the percentage of shipped orders](images/progresscircle-16-ss.png "Setting Progress Circle Logic")

1. From the Toolbox, drag an Expression widget into the Progress Circle's **Content** placeholder, and on the **Properties** tab, from the **Value** drop-down, select **Expression Editor**.

1. In the Expression Editor, enter the same logic as in step 11 (`GetShippedOrders.Count / GetTotalOrders.Count * 100`), and click **Close**. This displays the percentage value inside the Progress Circle.

    ![Screenshot of an Expression widget inside the Progress Circle showing the percentage of shipped orders](images/progresscircle-15-ss.png "Displaying Percentage Value Inside Progress Circle")

1. On the **Properties** tab, you can also change the Progress Circle's look and feel by setting the (optional) properties, for example, the color and animation settings.

    ![Screenshot of the Properties tab where the Progress Circle's appearance settings like color and animation are adjusted](images/progresscircle-17-ss.png "Customizing Progress Circle Appearance")

After following these steps and publishing the module, you can test the pattern in your app.

## Properties

| Property                                   | Description                                                                                                                                                                                                                                                                                                                                  |
|--------------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| Progress (Integer): Mandatory              | Percentage to display. You can use functions or local variables.                                                                                                                                                                                                                                                                             |
| ProgressColor (Color Identifier): Optional | The color of the stroke on progress circle. Red, orange, yellow, lime, green, blue, violet, and pink are just some of predefined colors available. <p>Examples <ul><li>_Blank_ - The stroke color displays in the color you chose when creating the app (default value).</li><li>Entities.Color.Red - The stroke color is red.</li></ul></p> |
| TrailColor (Color Identifier): Optional    | The color of the empty part of the progress circle. <p>Examples <ul><li>Blank - The empty part of the circle is a light gray (Entities.Color.Neutral5). This is the default value.</li><li>Entities.Color.Blue - The empty part of the progress circle is blue.</li></ul></p>                                                                |
| CircleThickness (Integer): Optional        | The thickness of the circle that marks the progress. <p>Examples <ul><li>_lank - The circle thickness is 4px. This is the default value.</li><li>8 - The circle thickness is 8px.</li></ul></p>                                                                                                                                              |
| AnimateInitialProgress (Boolean): Optional | If set to True, the progress from zero to the progress value is animated. This is the default value. If set to False, the progress is not animated.                                                                                                                                                                                          |
| IsSemiCircle (Boolean): Optional           | If True, the Progress Circle is changed from a circle to semi circle. If False, it remains a circle. This is the default value.                                                                                                                                                                                                              |
| AdvancedFormat (Text): Optional            | Allow for more options beyond what is provided through the input parameters. For more information, visit: <https://kimmobrunfeldt.github.io/progressbar.js/>. Example: `{ easing: 'bounce' }`                                                                                                                                                |
