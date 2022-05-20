
# Global Transshipment Behaviour
Data Source: <a href="https://www.kaggle.com/datasets/sayansh001/global-transshipment-behaviour">Kaggle</a>
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

## Dataset Description
### transshipment_vessels dataset
* Vessels classified as "refridgerated cargo" vessels, "fish carriers", and "fish tender" vessel and were identified using the lists from International Telecommunications Union and major Regional Fisheries Management Organizations
* Vessel indentities were further corroborates via the IMO as nearly all vessel could be matched to an IMO registry

### encounter_event dataset
* Encounters were identified from AIS data as location where a fishing vessel and a transsipment were coutinuously: 
  - within 500m 
  - at least 2 hours
  - speed <2 knots
  - at least 10km from a **coastal anchorage**
  - Anchorages were identified by dividing the world into a grid with cells roughly 0.5 degrees on a side. And, identififying every cell where **at least 20 unique vessels** with **AIS (fishing and non-fishing) remained stationary for at least 12 hours** over the study period 2012-2017

### loitering_event dataset
* Loitering events were identified as location where a transshipment vessel:
  - travel at speeds of <2 knots
  - for at least 8 hours
  - at least 20 nautical miles from shore


## Features Description

### mmsi 
* For **fishing vessel**, MMSI (Marine Mobile Service Identity number is an unique identifier for each vessel
* For **transshipment**, unlike fishing vessel, transshipment can swap flag registration over time, and each time the vessel changes flag registration it acquires a new MMSI
* The goal of mmsi is communication via radio transmission

### callsign
* Maritime call signs are unique identifiers containing both characters and numbers
* An MMSI is permanently attached to a callsign

### imo
* The IMO (International Organization Number) number of transshipment is a unique seven digit number that is assigned to propelled, sea-going merchant ships of 100 GT and above upon

* When working in several countries, a single transshipment may have multiple MMSI numbers, but the IMO remains the same
* Unlike the MMSI, the IMO's goal is to prevent fraud and promote safety rather than to facilitate communication

### fla
* Under International law a Flag State means the State which has granted to a ship the right to sail under its flag

* In some countries, a ship can, for a limited period, be part of two registers, thereby sailing under two flags


| Flag code | ANT| BHS |BLZ| BMU|BRB|CAN|CHL|CHN|COK|
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |:---: |
| Flag nation| NETHERLANDS ANTILLES| BAHAMAS|BELIZE|BERMUDA|BARBADOS|CANADA|CHILE|REPUBLIC OF CHINA|COOK ISLANDS

  COL| COM |CUW| CYM |CYP | DMA | ESP| FJI |FRO | FSM| GHA
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---:
| COLUMBIA| COMOROS|CURACAO|CAYMAN ISLANDS|CYPRUS| DOMINICA | SPAIN| FIJI| FAROE ISLAND| MICRONESIA| GHANA

|HND| IDN |IRN | JPN | KHM| KIR |KNA| KOR| LBR |LTU| MDA
| :---: | :---: | :---: | :---: | :---: | :---: | :---:  | :---: | :---: | :---: | :---: 
|HONDURAS|INDONESIA|IRAN| JAPAN | CAMBODIA| KIRIBATI| SAINT KITTS AND NEVIS| SOUTH KOREA| LIBERIA|LITHUANIA|MODOLVA

|MDV | MHL | MLT| MNG |MUS | MYS| NIU |NLD| NOR |PAN 
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---:  
|MALDIVES| MARSHALL ISLANDS | MALTA| MONGOLIA| MAURITIUS|MALAYSIA| NIUE|NETHERLANDS|NORWAY|PANAMA

 | PHL| PLW| RUS |SAU|SEN|SGP|SLE| SYC| TGO | THA
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: 
| PHILIPPINES| PALAU| RUSSIA| SAUDI ARABIA|SENEGAL|SINGAPORE|SIERRA LEONE|SEYCHELLESS|TOTO|THAILAND

|TWN|TZA|UKR|USA|VCT|VUT|
| :---:| :---:| :---:| :---:| :---:| :---:
|TAIWAN|TANZANIA|UKRAINE|UNITED STATES|ST.VINCENT & GRNADNE|VANUATU


