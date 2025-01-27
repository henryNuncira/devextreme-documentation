With the *line* series type, data is displayed as points joined by a line. This series type is useful when you need to visualize a trend in data over intervals.

![PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine.png)

To understand how polar charts are built, imagine how a chart in a rectangular coordinate system is transformed by rounding its argument axis.

![Transformation from Rectangular to Polar Coordinates PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_TransformationFromStandardChart.png)

To use the *'line'* series type, assign *'line'* to the [type](/api-reference/_hidden/PolarChartSeries/type.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/series/#type') property of the **series** configuration object.

    <!--JavaScript-->var polarChartOptions = {
        // ...
        series: {
            type: 'line'
        }
    };

To learn how to specify data for a series, refer to the [Data Binding](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Local_Array/) topic. Note that, you can use DateTime and Numeric types for points in the data source, as well as the String type. By default, the data of the DateTime and Numeric types is displayed on continuous axes, while string values are displayed on discrete axes (you can manage the axes types using their **type** property). When continuous axes are used in the UI component, the line chart is displayed using a smooth curve.

![Smooth PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_Smooth.png)

When either argument or value axis is discrete, the line chart joins data points by straight lines.

![Discrete PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_Discrete.png)

Note that you can use a spider web for polar charts displaying discrete data. For this purpose, set the UI component's [useSpiderWeb](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/useSpiderWeb.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/#useSpiderWeb') property to **true**.

![SpiderWeb PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_useSpiderWeb.png)

Line polar charts are appropriate for data whose values span cyclically repeating arguments. In this instance, set the [argumentAxis](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/argumentAxis '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/argumentAxis/').[period](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/argumentAxis/period.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/argumentAxis/#period') property.

![Cyclic PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_Smooth_Cyclic.png)

In some scenarios, you may need to close the line chart by joining the first point and the last point. For this purpose, set the series' [closed](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/closed.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/#closed') property.

![Closed Cyclic PolarLineSeriesType ChartJS](/images/ChartJS/PolarLine_Smooth_Cyclic_Closed.png)

To change the series default appearance, set the properties of the **series** configuration object. For instance, you can change the following.

*   **Line Width**  
    Change the line width using the series' **width** property. To set a line width when the line is hovered or selected, set the **width** property of the [hoverStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/hoverStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/hoverStyle/') or [selectionStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/selectionStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/selectionStyle/') object defined within the **series** configuration object.

*   **Line Color**  
    A color from the chart's [palette](/concepts/60%20Themes%20and%20Styles/20%20SVG-Based%20Components%20Customization/10%20Palettes/00%20Palettes.md '/Documentation/Guide/Themes_and_Styles/SVG-Based_Components_Customization/#Palettes') is used by default. Set a custom color using the series' [color](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/commonSeriesSettings '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/commonSeriesSettings/') property.

*   **Line Dash Style**  
    Set the line's style using the series' **dashStyle** property. To set a dash style when the line is hovered or selected, set the **dashStyle** property of the [hoverStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/hoverStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/hoverStyle/') or [selectionStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/selectionStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/selectionStyle/') object defined within the **series** configuration object.

*   **Line Point Properties**  
    Set up the series' [point](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/point '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/commonSeriesSettings/point/') object (see the [Series Points](/concepts/05%20UI%20Components/PolarChart/10%20Visual%20Elements/020%20Series%20Points/10%20Series%20Points.md '/Documentation/Guide/UI_Components/PolarChart/Visual_Elements/#Series_Points') topic).

*   **Point Label Properties**  
    Make point labels visible by setting the **visible** property of the series' [label](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/label '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/label/') object. For details on other label properties, refer to the [Series Point Labels](/concepts/05%20UI%20Components/PolarChart/10%20Visual%20Elements/030%20Series%20Point%20Labels.md '/Documentation/Guide/UI_Components/PolarChart/Visual_Elements/#Series_Point_Labels') topic.

These and other properties that can be set for series of the *line* type are explained in the [LineSeries](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/LineSeries '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/LineSeries/') Reference section. Set the required series properties within the [series](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/series '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/series/') object of the chart's configuration object.