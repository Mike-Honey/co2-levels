# co2-levels
Project to analyse data on CO2 levels, using data files from Aranet4 devices

[Link to interactive infographic - Decomposition Tree](https://app.powerbi.com/view?r=eyJrIjoiNTllMTliNjktNWVlYy00YTk5LWFhYjItMjUwYzMxZjQwY2Y2IiwidCI6ImRjMWYwNGY1LWMxZTUtNDQyOS1hODEyLTU3OTNiZTQ1YmY5ZCIsImMiOjEwfQ%3D%3D&pageName=ReportSection874449a5dc80e84560dc)

[![Click to view and interact with the report](https://github.com/Mike-Honey/gates/raw/main/BMGF-Grants-Decomposition-Tree.png)](https://app.powerbi.com/view?r=eyJrIjoiNTllMTliNjktNWVlYy00YTk5LWFhYjItMjUwYzMxZjQwY2Y2IiwidCI6ImRjMWYwNGY1LWMxZTUtNDQyOS1hODEyLTU3OTNiZTQ1YmY5ZCIsImMiOjEwfQ%3D%3D&pageName=ReportSection874449a5dc80e84560dc)


**Reference:**

Dataviz using data from CO2 monitors to analyse CO2 levels. The first file format supported is that output by the [Aranet4](https://aranet.com/products/aranet4/) device, in CSV file format. Multiple CSV files can be collected and aggregated together for analysis across monitors.

An Excel template is provided to ease the manual collection of data, where that is preferred.

**Summary**

This project presents a series of interactive dashboard pages to help analyse and understand the data collected on CO2 levels.  The page navigation control is at the centre-bottom, e.g. **< 1 of 4 >**. Click the centre of that control for a menu of the pages.

On every page, slicer controls allow the selection of a range of dates. There is a Play control immediately below to let you "play" through the selected dates in an animation.  There are also slicers to filter by the Monitor (device ID), Day of the week and Hour of the day. In combination, many different analyses are possible.  Each visual element e.g. a point on a line chart can be selected, then it will act as a "cross-filter" to filter every other visual on that page.

On most pages, a detailed table at the bottom lists the individual CO2 readings within the scope of the current slicer settings. The table can be resorted by clicking any column header, and the **Focus mode** button (which appears at the top-right corner of the table on hover) will expand the table to fill the browser window.

The page: **Scatter** presents a scatter chart showing a dot for every CO2 level measurement. When there are over 10,000 readings, an automatic sampling algorithm kicks in. It aims to mostly hide the points that overlap with others. The X-Axis is the time of day, expressed in decimal fractions of hours. The actual hour and minute shown is available in the tooltip for any point.  The Y Axis is the CO2 level. A **CO2 Yellow Range** slicer at the right controls which levels of CO2 are coloured Red-Yellow-Green.

There is a hidden page using the [Key Influencers visual](https://learn.microsoft.com/en-us/power-bi/visuals/power-bi-visualization-influencers?tabs=powerbi-desktop), which is a very powerful no-code, AI-powered analysis engine for understanding the relationships within the data. After every interactive filter you choose, the engine re-runs it's analysis to explore which factors are the Key Influencers for a variable - in this project the CO2 level. That visual is not supported by this publishing method, but you can install the free Power BI Desktop tool, download the .PBIX file from this project and open it to explore that page.

![Key Influencers page](https://github.com/Mike-Honey/gates/raw/main/BMGF-Grants-Key-Influencers.png)]

The data visualisation engine is [Power BI](https://powerbi.microsoft.com), featuring the Custom Visuals:
- [HTML Content (Lite)](https://appsource.microsoft.com/en-us/product/power-bi-visuals/coacervolimited1596856650797.htmlcontent_certified?tab=Overview)
- [Play Axis](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104380981?tab=Overview)
- [Violin Plot](https://appsource.microsoft.com/en-us/product/power-bi-visuals/WA104381947?tab=Overview)
