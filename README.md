# Doing Data Science SS2022

![CRISP DIAGRAM](https://github.com/neuhart/Doing_DataScience_SS22/blob/9d0145dc1b2806f7ee67366fe8f2775c9be777cc/graphics/Screen%20Shot%202022-05-04%20at%2020.40.24.png)


# Sources
<details><summary>Dataset</summary>

* <a href="https://www.kaggle.com/datasets/sayansh001/global-transshipment-behaviour">Kaggle Data Source</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/main/data_description.md">Global Transshipment Behaviour Dataset Discription</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/main/data_description.md">Specified Data Description</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/tree/main/data">Modified and Original Dataset</a>




</p>
</details>

<details><summary>Codes</summary>
  
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/main/maps.ipynb">Global Map</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/main/EDA.ipynb">Data Cleaning</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/main/transformation.ipynb">Data Transformation</a>
* <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/Clustering/Clustering_p.ipynb">Dimensional Reduction</a>

</p>
</details>






# Project Understanding:

<details><summary> What is the problem, what are the expected benefits? </summary>

* Transhipment, i.e. ship to ship transactions involving goods, personnel etc., is a global phenomenon that often takes places in international waters 

* Good faith actors have no incentive to report their activities and often do not have GOs and NGOs they could report to

* This enables bad actors to hide activities like human rights abuses, tax evasion and supply chain obfuscation
  
</p>
</details>

<details><summary> How would a solution look like? </summary>

* To gain and present an understanding of the underlying mechanisms of transshipment behavior

* To identify patterns in transshipping behavior that enable stakeholders to target only the relevant sub-samples for further analysis and action

</details>

<details><summary> What is known about the domain? </summary>

* The original research paper that created the dataset, the kaggle description and further research by our own team (readme and data description)

  - Identifying Global Patterns of Transshipment Behavior <a href="https://www.frontiersin.org/articles/10.3389/fmars.2018.00240/full#:~:text=Transshipment%20behaviors%20were%20identified%20using,single%2Dvessel%20loitering%E2%80%9D%20events">Miller et al. (2018)</a> 

  - <a href="https://www.kaggle.com/datasets/sayansh001/global-transshipment-behaviour">Data Source</a>

  - <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/draft_goals/README.md">README</a>

  - <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/draft_goals/data_description.md">Data description</a>
  
</details>

# Data Understanding:

<details><summary> What data is available? </summary>

* A dataset featuring pre-identified encounter events between larger vessels( > 300 GT) related to the fishing industry

* A similar dataset featuring loitering events of a single larger vessel related to the fishing industry, but no other vessels with active AIS systems nearby

* A list of transshipment capable vessels and a list of their respective features(flag etc...) 
  
 </details>

<details><summary> Is it relevant to the problem at hand? </summary>

* Highly: We have the geographic distribution, time intervals, timestamps of events and additional features at the transshipment vessel level 
  
   </details>

<details><summary> Is it valid, does it reflect our expectations? </summary>

* The dataset complies with its description, including metadata, the original research is published and peer reviewed and also external sources
  
   </details>

<details><summary> Is the data quality, quantity and recency sufficient? </summary>

* There are some slight issues with data quality that can be easily alleviated via standard methods

* Data quantity is well beyond the need of most standard approaches

* Recency will require some further investigation during evaluation

  - While the data is from within the last decade, there could be some shifts in behavior during the 5 years included in the datasets

  - We do however include time related data in our models to counter this issue early on
  
   </details>

# Data Preparation:

## Data Cleaning

<details><summary> Removing invalid values </summary>
  
  - Remove the tuples whose wrong mmsi format (must be 8-digit number)
  - Remove all tuples whose null values
  - Remove duplicates
    </details>
    
 <details><summary> Detect and Remove Outliers </summary>
  
  * **encounter-events**
    - duration_hr: remove encouters lasted > 65h (96.7% remain)
    - median_distance: 5.282% of data whose median distance equals 0 (have not yet decided to remove or not)
  
  * **loitering-events**
    - loitering_duration: remove 1% of the data whose loitering event longer than 200 hours 
  
  * **transshipment_vessels**
    - Unchanged
   </details>   
   
  <details><summary> Change data format </summary>
  
  - Change the format of start_time and end_time from object to datetime
  - 
    </details>
    

    
## Data Transformation
* **New features**
  * Calculate the distance of each transshipment to the nearest coast
  * Calculate the mean of longitude and latitude during the event 
  
* **Merge dataset**
  * Merges the aggregated datasets with the vessel data on the key pair 'transshipment_vessel_mmsi' and 'mmsi'

* ...

# Modeling:

* ...

# Evaluation:

* ...




## References
* Vessels Flag Code.
  <a href="https://api.vesselfinder.com/docs/ref-flags.html">Vessel Finder</a>
* IMO Ship
  <a href="https://wwwcdn.imo.org/localresources/en/OurWork/IIIS/Documents/A%2030-Res.1117%20-%20Imo%20Ship%20Identification%20Number%20Scheme.pdf">Identification Number Scheme</a>
* Miller NA, Roan A, Hochberg T, Amos J and Kroodsma DA (2018) Identifying Global Patterns of Transshipment Behavior. Front. Mar. Sci. 5:240. doi: 10.3389/fmars.2018.00240
  https://doi.org/10.3389/fmars.2018.00240
* South America’s ocean problems
<a href="https://news.mongabay.com/2019/04/weak-governance-undermines-south-americas-ocean-ecosystems/">Weak Government Problem</a>
<a href="https://www.aa.com.tr/en/americas/illegal-fishing-threatens-stocks-in-south-america/2182404">Illegal Fishing Problem</a>

* China and South Korea ocean problems
<a href="https://foreignpolicy.com/2020/11/30/china-beijing-fishing-africa-north-korea-south-china-sea/">Illegal Fishing Problem</a>


