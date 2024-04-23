# co2-levels
Project to analyse data on CO2 levels, using data files from Aranet4 devices

[Link to interactive infographic - Scatter](https://app.powerbi.com/view?r=eyJrIjoiZjRjMTFlMzgtMDQwZi00M2EwLTg2NjktNjdhZjkxZDIyZWVmIiwidCI6ImRjMWYwNGY1LWMxZTUtNDQyOS1hODEyLTU3OTNiZTQ1YmY5ZCIsImMiOjEwfQ%3D%3D&pageName=ReportSection6dc960586e2cd891bd66)

[![Click to view and interact with the report](https://github.com/Mike-Honey/co2-levels/raw/main/co2-levels-scatter-chart.png)](https://app.powerbi.com/view?r=eyJrIjoiZjRjMTFlMzgtMDQwZi00M2EwLTg2NjktNjdhZjkxZDIyZWVmIiwidCI6ImRjMWYwNGY1LWMxZTUtNDQyOS1hODEyLTU3OTNiZTQ1YmY5ZCIsImMiOjEwfQ%3D%3D&pageName=ReportSection6dc960586e2cd891bd66)


## Reference

Dataviz using data from CO2 monitors to analyse CO2 levels. The first file format supported is that output by the [Aranet4](https://aranet.com/products/aranet4/) device, in CSV file format. Multiple CSV files can be collected and aggregated together for analysis across monitors.

An Excel template is provided to ease the manual collection of data, where that is preferred.

## Summary

This project presents a series of interactive dashboard pages to help analyse and understand the data collected on CO2 levels.  The page navigation control is at the centre-bottom, e.g. **< 1 of 4 >**. Click the centre of that control for a menu of the pages.

On every page, slicer controls allow the selection of a range of dates. There is a Play control immediately below to let you "play" through the selected dates in an animation.  There are also slicers to filter by the Monitor (device ID), Day of the week and Hour of the day. In combination, many different analyses are possible.  Each visual element e.g. a point on a line chart can be selected, then it will act as a "cross-filter" to filter every other visual on that page.

On most pages, a detailed table at the bottom lists the individual CO2 readings within the scope of the current slicer settings. The table can be resorted by clicking any column header, and the **Focus mode** button (which appears at the top-right corner of the table on hover) will expand the table to fill the browser window.

The page: **Scatter** presents a scatter chart showing a dot for every CO2 level measurement. When there are over 10,000 readings, an automatic sampling algorithm kicks in. It aims to mostly hide the points that overlap with others. The X-Axis is the time of day, expressed in decimal fractions of hours. The actual hour and minute shown is available in the tooltip for any point.  The Y Axis is the CO2 level. A **CO2 Yellow Range** slicer at the right controls which levels of CO2 are coloured Red-Yellow-Green.

The page: **Violin Plot** presents a [Violin Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381947?tab=Overview) visual that elegantly aggregates data to show the shape of the data readings, combined with a box plot to show the median, mean and Inter-Quartile Range showing a dot for every CO2 level measurement. When there are over 30,000 readings, an automatic sampling algorithm kicks in using the Epanechnikov Kernel. The X-Axis is variable, driven by the **Legend Field** slicer selection. The Y Axis is the CO2 level. 

The page: **Line Chart** presents a Line chart visual that aggregates data by Time of day. The Legend is variable, driven by the **Legend Field** slicer selection. The Y Axis is the CO2 level. 

The page: **Small Multiples** presents a grid of Line charts that aggregates data by Time of day on the X-Axis. The split of data among the grid cells is variable, driven by the **Legend Field** slicer selection. The Y Axis is the CO2 level, standardised across all the grid cells. If more than 6 cells fill the grid, you can scroll down to view them all.

There is a hidden page using the [Key Influencers visual](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers?tabs=powerbi-desktop), which is a very powerful no-code, AI-powered analysis engine for understanding the relationships within the data. After every interactive filter you choose, the engine re-runs it's analysis to explore which factors are the Key Influencers for a variable - in this project the CO2 level. That visual is not supported by this publishing method, but you can install the free Power BI Desktop tool, download the .PBIX file from this project and open it to explore that page.

![Key Influencers page](https://github.com/Mike-Honey/co2-levels/raw/main/co2-levels-key-influencers.png)]

The data visualisation engine is [Power BI](https://powerbi.microsoft.com), featuring the Custom Visuals:
- [HTML Content (Lite)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/coacervolimited1596856650797.htmlcontent_certified?tab=Overview)
- [Play Axis](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981?tab=Overview)
- [Violin Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381947?tab=Overview)

## Data

Sample datasets have been shared:
- **Roaming CAIS** was provided by an anonymous user 

Any Aranet4 user can connect their monitor device to a smartphone using the Aranet app and [export their measurements](https://forum.aranet.com/all-about-aranet4/how-the-user-can-export-measurement-data-from-aranet4-application/#reply_1868). 

An ![Excel template file](https://github.com/Mike-Honey/co2-levels/raw/main/co2-levels-data-file-template.xlsx)] is available to allow those who wish to gather their data manually to provide it in an acceptable format.

If you would like to add your data to the public collection, please submit it by creating an Issue for this project using the template: **Public Data file submission**.

If you would prefer to process your data offline, just clone this project to your local drive, load your files into the **C:\Dev\co2-levels\co2-levels-data-files\aranet4** folder, then open the PBIX file using Power BI Desktop and hit the **Refresh** button.

The Ararnet4 file format is currently the only one supported for this project, but it should be relatively easy to integrate other formats.  If you would like to propose a new format, please create an Issue for this project (using the blank issue template) and attach as many sample files as possible.

## Futures

As well as including a broader range of file formats, I have imagined several directions this project could go in, including:
1. **Integrate data on locations**, e.g. the monitor was at venue X in a particular time period. Locations could be categorised e.g. cinema, shop, restaurant etc. Locations could be geocoded for a local perspective. I'm thinking the ICS Calendar file format, which can be exported from Outlook, might be a starting format for this. It already provides rich data entry features e.g. date/time, location, categorisation.
2. Automated pipeline for data updates.
