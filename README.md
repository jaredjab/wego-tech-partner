# WeGo Public Transit Analysis
[WeGo Public Transit](https://www.wegotransit.com/) is a public transit system serving the Greater Nashville and Davidson County area. WeGo provides local and regional bus routes, the WeGo Star train service connecting Lebanon to downtown Nashville, along with several other transit services.

The data for this project is not publicly available.

# What I did

For this project, I was initially focused on analyzing the relationship between bus drivers and headway deviation. After completing that analysis and visualization work in Python, I moved to the presentation team. On the presentation team, we worked with everyone on the project to provide a clear, consistent, and concise presentation on all of the data-driven insights we discovered.

My personal python scripts are in the jupyter notebook wego_eda_jaredjab in the notebooks folder, with the wego_full_class_analysis jupyter notebook being a collection of everyone's analysis work.

The viz folder contains my exported visualizations for the presentation, and the WeGo Presentation PDF is the google slide presentation used in our final deliverable. My personal slides are slides 13-15.

The presentation was performed by various team members and given to WeGo's Cheif Operating Officer, who provided us with fantastic feedback and additional insight into the work we had done.

# Project Overview

In this project, you'll be analyzing the bus spacing to look for patterns and try to identify correlations to controllable or external factors. Specifically, you'll be using a dataset containing information on the headway, or amount of time between vehicle arrivals at a stop.

There are two main variables you will be studying in this project, headway deviation and adherence.

**Headway** is the amount of time between a bus and the prior bus at the same stop. In the dataset, the amount of headway scheduled is contained in the SCHEDULED_HDWY column and indicates the difference between the scheduled time for a particular stop and the scheduled time for the previous bus on that same stop.

This dataset contains a column HDWY_DEV, which shows the amount of deviation from the scheduled headway. **Bunching** occurs when there is shorter headway than scheduled, which would appear as a negative HDWY_DEV value. **Gapping** is when there is more headway than scheduled and appears as a positive value in the HDWY_DEV column. Note that you can calculate headway deviation percentage as HDWY_DEV/SCHEDULED_HDWY. The generally accepted range of headway deviation is 50% to 150% of the scheduled headway, so if scheduled headway is 10 minutes, a headway deviation of up to 5 minutes would be acceptable (but not ideal).

Another important variable is **adherence**, which compares the actual departure time to the scheduled time and is included in the ADHERENCE column. A negative adherence value means that a bus left a time point late and a positive adherence indicates that the bus left the time point early. Buses with adherence values beyond negative 6 are generally considered late and beyond positive 1 are considered early. However, there is some additional logic where the staff applies waivers to allow early departures, such as an express bus that has already picked up everyone at a park-and-ride lot and is only dropping people off at the remaining stops, and also allows for early timepoint records for all records where TRIP_EDGE = 2 (end of trip), since it is not a problem if a bus ends its trip early as long as it didn't pass other timepoints early along the way.
