
# Global Transshipment Behaviour

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


