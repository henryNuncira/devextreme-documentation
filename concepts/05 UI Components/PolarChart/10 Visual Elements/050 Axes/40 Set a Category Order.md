When specifying [data for a series](/Documentation/Guide/Data_Binding/Specify_a_Data_Source/Local_Array/) in a chart with a [discrete axis](/concepts/05%20UI%20Components/PolarChart/10%20Visual%20Elements/050%20Axes/10%20Argument%20Axis.md '/Documentation/Guide/UI_Components/PolarChart/Visual_Elements/#Axes/Argument_Axis'), the order of categories on this axis is determined by the order in the series defined first. You can set a specific order of the categories. For this purpose, use the axis' [categories](/api-reference/10%20UI%20Components/dxPolarChart/1%20Configuration/argumentAxis/categories.md '/Documentation/ApiReference/UI_Components/dxPolarChart/Configuration/argumentAxis/#categories') property.

	<!--JavaScript-->var polarChartOptions = {
		argumentAxis: {
			categories: ['January', 'February', 'March']
		},
		// ...
	};