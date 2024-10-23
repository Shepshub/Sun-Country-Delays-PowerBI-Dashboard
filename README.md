# Sun Country Delays Dashboard
## Background and Overview

This Power BI dashboard project was developed to provide a comprehensive tool for tracking and analyzing flight delay trends at Sun Country Airlines. Every day, an Operations (OPS) briefing is held with managers from various departments to review the previous day's performance and provide insights into the current day’s operations. While this briefing provides a high-level summary, no interactive dashboard allows the Airport Coordination Center (ACC) managers, who are at the center of the entire schedule service operation, to explore flight delay data in more detail.

The dashboard addresses this gap by enabling managers to analyze flight delays across multiple dimensions, including aircraft type, arrival airports, delay codes, and the Manager on Duty (MOD) during incidents. This interactive dashboard allows users to explore patterns, identify key delay drivers, and support data-driven decision-making for operational improvements. It serves as a valuable tool for understanding and improving operational performance by visualizing delay trends and offering insights into the areas that require attention.

This Dashboard was created in tandem with the Sun Country Delays Excel project as an extra user-friendly tool to explore delay trends across multiple dimensions, such as aircraft, arrival airports, delay codes, and managers on duty (MOD), to pinpoint recurring issues. There are two dashboards in this report that show the same visuals, although one visual shows all delays while the other shows only controllable delay data.

The interactive Power BI dashboards can be downloaded [here](https://github.com/Shepshub/Sun-Country-Power-Bi/raw/refs/heads/main/Delays%20SEP%20&%20AUG.pbix)

## Data Structure Overview
![image](https://github.com/user-attachments/assets/283c4527-03a3-406c-8571-f68d2d05319c)

The data is structured across multiple tables and contains information on flight delays, delay codes, and corresponding categories, as well as performance metrics related to airline operations. The key data tables and columns used in this project are described below:

1. **Delays Table**
   
     Description: This table captures detailed information about delayed flights, including specific flight details and associated delay times.

     Key Columns:

- Date (MM/DD/YYYY): Date of the flight (formatted as a date).
- A/C (Aircraft): Aircraft identifier (formatted as a string).
- Flight #: Flight number (formatted as a number).
- ARR (Arrival Airport): Arrival airport code (formatted as a string).
- Delay Time (HH): Total delay time for the flight (formatted as time).
- Delay Code: A specific delay code signifying the reason for the delay, including codes with subcodes (formatted as string).
- Department: The department responsible for the delay (formatted as string).
- Notes: Detailed explanation of each flight's delay code (formatted as string).
- MOD (Manager on Duty): The manager on duty who was responsible at the time (formatted as a string).
- Delays (HH): Calculated column of the Delay time column. The same values were reformatted as (h:mm) (formatted as time).
  
1. **Controllable Delays Table**
   
     Description: This table captures detailed information about controllable delayed flights, including specific flight details and associated delay times. This table excludes uncontrollable delays related to late inbound arrivals and weather delays.

     Key Columns:

- Date (MM/DD/YYYY): Date of the flight (formatted as a date).
- A/C (Aircraft): Aircraft identifier (formatted as a string).
- Flight #: Flight number (formatted as a number).
- ARR (Arrival Airport): Arrival airport code (formatted as a string).
- Delay Time (HH): Total delay time for the flight (formatted as time).
- Delay Code: A specific delay code signifying the reason for the delay, including codes with subcodes (formatted as string).
- Department: The department responsible for the delay (formatted as string).
- Notes: Detailed explanation of each flight's delay code (formatted as string).
- MOD (Manager on Duty): The manager on duty who was responsible at the time (formatted as a string).
- Delays (HH): Calculated column of the Delay time column. The same values were reformatted as (h:mm) (formatted as time).

3. **Master Codes Table**

     Description: This combined table includes delay codes and subcodes, providing a comprehensive view of all possible delay reasons.

     Key Columns:

- Codes: Delay code identifiers (formatted as string).
- Department: The department responsible for the delay (formatted as string).
- Description: Detailed explanation of the delay code (formatted as string).

5. **Total Flights Table**
   
     Description: This table lists the total number of scheduled service flights for each day within the analysis period.

     Key Columns:

- Date (MM/DD/YYYY): Date of scheduled flights (formatted as date).
- Scheduled Service Flights: Number of scheduled flights on that date (formatted as number).
- Delayed Flights: Number of scheduled flights on that date (formatted as number).
- On-Time Performance (OTP): Percentage of on-time departures for that given day (formatted as a percentage).

### Relationships:
The data in these tables is interconnected, with the Delays Table being the primary source of flight delay data. Delay codes in the Delays Table reference corresponding descriptions in the Master Codes table (connected by delay codes), while the Total Flights Table provides context for total operational performance each day (connected by date).
