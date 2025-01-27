The *area* series type is useful when you need to emphasize a change in values. With this series type, data is displayed by a line that joins points, and the shaded area between this line and the zero value. This line is a border and is invisible by default.

![AreaPolarSeriesType ChartJS](/images/ChartJS/PolarArea.png)

To understand how polar charts are built, imagine how a chart in a rectangular coordinate system is transformed by rounding its argument axis.

![Transformation from Rectangular to Polar Coordinates PolarAreaSeriesType ChartJS](/images/ChartJS/PolarArea_TransformationFromStandardChart.png)

To use the *area* series type, assign *'area'* to the **type** property of the **series** configuration object.

    <!--JavaScript-->var polarChartOptions = {
        // ...
		series: {
			type: 'area'
		}
	};

To learn how to specify data for a series, refer to the [Data Binding](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Local_Array/) topic. Note that you can use DateTime and Numeric types for points in the data source, as well as the String type. By default, the data of the DateTime and Numeric types is displayed on continuous axes, while string values are displayed on discrete axes (you can manage the axes types using their **type** property). When continuous axes are used in the UI component, the area chart is displayed using a smooth border line.

![Smooth PolarAreaSeriesType ChartJS](/images/ChartJS/PolarArea_Smooth.png)

When either the argument or value axis is discrete, the area chart joins data points by straight lines.

![Discrete PolarAreaSeriesType ChartJS](/images/ChartJS/PolarArea_Discrete.png)

Note that you can use a spider web for polar charts displaying discrete data. For this purpose, set the UI component's [useSpiderWeb](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/useSpiderWeb.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/#useSpiderWeb') property to **true**.

![SpiderWeb PolarAreaSeriesType ChartJS](/images/ChartJS/PolarArea_useSpiderWeb.png)

To change the series default appearance, set the properties of the **series** configuration object. For instance, you can change the following.

*   **Area Color**  
    A color from the chart's [palette](/concepts/60%20Themes%20and%20Styles/20%20SVG-Based%20Components%20Customization/10%20Palettes/00%20Palettes.md '/Documentation/Guide/Themes_and_Styles/SVG-Based_Components_Customization/#Palettes') is used by default. Set a custom color using the series' [color](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/commonSeriesSettings '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/commonSeriesSettings/') property. This color will be used for the series' border. The color of the series area will be the same, but a specified capacity will be applied.
    
*   **Border Properties**  
    Make a border visible by setting the **visible** property of the series' [border](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/border '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/commonSeriesSettings/border/') object. When the border is visible, you can change its width and color, using the **width**, **color** and **dashStyle** properties of the series' **border** object. In addition, you can change the border settings when the series is hovered or selected. To do this, set the properties of the **border** object within the series' [hoverStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/hoverStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/AreaSeries/hoverStyle/') or [selectionStyle](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/selectionStyle '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/AreaSeries/selectionStyle/') configuration object.
    
*   **Point Properties**  
    Make points visible by setting the **visible** property of the series' [point](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/point '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/commonSeriesSettings/point/') object. For details on other point properties, refer to the [Series Points](/concepts/05%20UI%20Components/PolarChart/10%20Visual%20Elements/020%20Series%20Points/10%20Series%20Points.md '/Documentation/Guide/UI_Components/PolarChart/Visual_Elements/#Series_Points') topic.
    
*   **Point Label Properties**  
    Make point labels visible by setting the **visible** property of the series' [label](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/CommonPolarChartSeries/label '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/AreaSeries/label/') object. For details on other label properties, refer to the [Series Point Labels](/concepts/05%20UI%20Components/PolarChart/10%20Visual%20Elements/030%20Series%20Point%20Labels.md '/Documentation/Guide/UI_Components/PolarChart/Visual_Elements/#Series_Point_Labels') topic.

These and other properties that can be set for series of the *area* type are explained in the [AreaSeries](/api-reference/10%20UI%20Components/dxPolarChart/5%20Series%20Types/AreaSeries '/Documentation/ApiReference/UI_Components/dxPolarChart/Series_Types/AreaSeries/') Reference section. Set the required series properties within the [series](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/series '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/series/') object of the chart's configuration object.