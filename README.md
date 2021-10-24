# Data_viz-Python

Data format: Json.

Data file name: tech_test_3000.json.

Data contains: Information about 3000 call records.

Samples to work on: Top 2500 records from the data.

Design Assumptions: We have the raw dataset. I have created two visuals from the data. Before that we have to process the data accordingly.
i)	The first one will be showing the count of unique agents per hour in a selected time frame. 
ii) Second graph will filter 35 Agents based on least seconds spent on the call values of column on a Bar Graph.


Designing Decisions:
#Graph - 1

Steps: 
1.	Process the data to have the columns regarding agent names.
2.	Take the time range to visualize as input. Here I took 2 inputs: 1 for start time and another for end time. The time format will be %Y-%m-%d %H:%M:%S.
Example input:
Enter Start Date Time: 2021-08-14 20:30:00
Enter End Date Time: 2021-08-28 20:30:00

3.	Process the date-time column to extract hours from them.
4.	Count the number of agents for each hour inside time range.
5.	Plot using different libraries like matplotlib, seaborn, plotly. But I will prefer ‘plotly’ for its interactive and saving as a html file.
6.	Here I have used line plot.

#Graph - 2

Steps:
1.	Take the name of the metrics to visualize as input.
Example input:
Column to Visualize (interaction.totalDurationSec/interaction.talkingDurationSec/interaction.onHoldDurationSec/interaction.onMuteDurationSec): interaction.totalDurationSec
2.	Sort the data in ascending order as per the input metrics’ column. In this case, it's interaction.totalDurationSec
3.	Filter 35 Agents based on least seconds spent on the call values of column.
4.	Visualize this data on bar graph in an ascending order
5.	Here I used bar graph.

Operation support consideration:
As our main challenge is to read and process the data file correctly, I have provided the solution using pandas library of python to process the json data properly.

For visualization support, To make the visuals interactive I have provided the visuals by using "Plotly" library of python.
And to make the visuals as per input, I have input option inside it.



Issues encountered: There were to main issue that I encountered while doing these 2 visualizations.
1.	Data Processing: The initial dataset was too much nested in structure. I had to first analyze the structure properly and then extracted the proper data for the visualizations.
2.	Visualization: Firstly, I tried to use D3.js but as I have not dealt with data visualization in JavaScript/React before I was unable learn D3.js in short time. But in python, there are several manners that I was confident about using different python packages like pandas, matplotlib, seaborn, plotly and plotly express for its interactive feature. Finally, I choose python for visualizing this Data.


#Run

1.) Before we plot a graph we need run this particular cell where put input date or/and time that we want accordingly AND it will determine the graph with in accordance to the input later.

#determing based on input start_datetime and end_datetime
start_datetime=input('Enter Start Date Time (YYYY-MM-DD) & (HH-MM-SS): ')
end_datetime=input('Enter End Date Time (YYYY-MM-DD) & (HH-MM-SS): ')

2.) To plot the 2nd Graph, we need to run the last cell which takes different options and we have type one of the following options from it that are

( interaction.totalDurationSec / interaction.talkingDurationSec / interaction.onHoldDurationSec / interaction.onMuteDurationSec )

and it will plot the graph accordingly.
