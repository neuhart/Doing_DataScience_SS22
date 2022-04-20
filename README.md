# Doing_DataScience_SS22
Link to Kaggle: https://www.kaggle.com/datasets/sayansh001/global-transshipment-behaviour
## Context
Vessels meet at sea for multiple reasons, such as refueling and exchanging crew, but in the commercial fishing industry, they also meet to transfer catch, or transship. Using machine learning, we processed more than 32 billion Automatic Identification System (AIS) signals broadcast from ships at sea to identify vessels capable of receiving transshipments and analyze their movements. Those vessels include fish tenders, live fish carriers, factory/processors and refrigerated cargo vessels. Verifying our results with confirmed fishery registries and open source online resources, we identified vessels capable of transshipping fish at sea between 2012 and December 2017, and incidents in which one of these vessels exhibited telltale transshipment behavior patterns such as drifting slowly enough and long enough to receive a transfer of catch.<br>
Source: Kaggle
## Content
This dataset includes data on transshipment. Included are data on the following:<br>
List of vessels involved in transshipment - Includes transshipment capable vessels (fish tenders, live fish carriers, factory/processors and refrigerated cargo vessels).
Loitering events - Occurrences of transshipment-capable vessels drifting slowly enough and long enough to receive a transfer of catch, but during which time no fishing vessels are observed on AIS meeting with the vessel.
Potential transshipment events (encounters) - Occurrences of transshipment-capable vessels drifting slowly enough and long enough to receive a transfer of catch and meeting with one or more fishing vessel that is actively broadcasting AIS. <br>
Source: Kaggle
## Files description
* **encounter-events.csv**     - data of two-vessel encounter - 11682 rows x 9 columns
* **loitering-events.csv**     - data of single-vessel loitering - 46570 rows x 9 columnes
* **transshipment-vessels.csv** - data of transshipment vessel - 1125 rows x 7 columns 
* **data_description.txt**     - full description of each column
## Data fields
### transshipment-vessels.csv
* **mmsi**: Maritime Mobile Service Identity wih nine-digit of the transshipment vessel, issued by that object's current flag state
* **shipname**: Normalized name of the ship
* **callsign**: Callsign of the ship in broadcasting and radio communications assigned by a government agency
* **flag**: The flag of the nationality conferred by the State upon ships registered under its national law
* **imo**:  Unique and unchaged seven-digit number linking to all the vessel's names, flags and owners
* **first_timestamp**: Timestamp of the MMSI's first known AIS position
* **last_timestamp**: Timestamp of the MMSI's last known AIS position

### encounter-events.csv
* **fishing_vessel_mmsi**: Maritime Mobile Service Identity wih nine-digit of the fishing vessel, issued by that object's current flag state
* **transshipment_vessel_mmsi**: Maritime Mobile Service Identity wih nine-digit of the transshipment vessel, issued by that object's current flag state
* **start_time**: Timestamp of the encounter's first position
* **end_time**: Timestamp of the encounters's last position
* **mean_latitude**: Mean latitude of the encounter event
* **mean_longitude**: Mean longitude of the encounter event
* **duration_hr**: Duration (hours) of the encounter event
* **median_distance_km**: Median distance (km) between the transshipment vessel and fishing vessel during the encounter event
* **median_speed_knots**: Median speed (knots) of the transshipment vessel during the encounter event

### loitering-events.csv
* **transshipment_mmsi**: Maritime Mobile Service Identity wih nine-digit of the transshipment vessel, issued by that object's current flag st
* **starting_latitude**:Latitude of the loitering event's first position
* **starting_longitude**: Longitude of the loitering event's first position
* **ending_latitude**: Latitude of the loitering event's last position
* **ending_longitude**: Longitude of the loitering event's last position
* **starting_timestamp**: Timestamp of the loitering event's first position
* **ending_timestamp**: Timestamp of the loitering event's last position
* **median_speed_knots**: Median speed (knots) of the transshipment vessel during the loitering event
* **total_event_duration**: Total duration (hours) of the loitering event

## Sources
1. <a href="https://api.vesselfinder.com/docs/ref-flags.html">Country Flag Code</a>
2. <a href="https://www.imo.org/en/OurWork/MSAS/Pages/IMO-identification-number-scheme.aspx#:~:text=The%20Number%20consists%20of%20seven,company%20and%2For%20registered%20owner">IMO Numbers</a>
3. <a href="https://shiptracks.com/updates/2019/07/01/mmsi-imo-and-call-sign-what-is-the-difference/">Difference of MMSI, IMO and Callsign</a>




