# Project Understanding:

## What is the problem, what are the expected benefits?

* Transhipment, i.e. ship to ship transactions involving goods, personnel etc., is a global phenomenon that often takes places in international waters 

* Good faith actors have no incentive to report their activities and often do not have GOs and NGOs they could report to

* This enables bad actors to hide activities like human rights abuses, tax evasion and supply chain obfuscation

## How would a solution look like?

* To gain and present an understanding of the underlying mechanisms of transshipment behavior

* To identify patterns in transshipping behavior that enable stakeholders to target only the relevant sub-samples for further analysis and action

## What is known about the domain?

* The original research paper that created the dataset, the kaggle description and further research by our own team (readme and data description)

  - Identifying Global Patterns of Transshipment Behavior <a href="https://www.frontiersin.org/articles/10.3389/fmars.2018.00240/full#:~:text=Transshipment%20behaviors%20were%20identified%20using,single%2Dvessel%20loitering%E2%80%9D%20events">Miller et al. (2018)</a> 

  - <a href="https://www.kaggle.com/datasets/sayansh001/global-transshipment-behaviour">Data Source</a>

  - <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/draft_goals/README.md">README</a>

  - <a href="https://github.com/neuhart/Doing_DataScience_SS22/blob/draft_goals/data_description.md">Data description</a>

# Data Understanding:

## What data is available?

* A dataset featuring pre-identified encounter events between larger vessels( > 300 GT) related to the fishing industry

* A similar dataset featuring loitering events of a single larger vessel related to the fishing industry, but no other vessels with active AIS systems nearby

* A list of transshipment capable vessels and a list of their respective features(flag etc...) 

## Is it relevant to the problem at hand?

* Highly: We have the geographic distribution, time intervals, timestamps of events and additional features at the transshipment vessel level 

## Is it valid, does it reflect our expectations?

* The dataset complies with its description, including metadata, the original research is published and peer reviewed and also external sources

## Is the data quality, quantity and recency sufficient? 

* There are some slight issues with data quality that can be easily alleviated via standard methods

* Data quantity is well beyond the need of most standard approaches

* Recency will require some further investigation during evaluation

  - While the data is from within the last decade, there could be some shifts in behavior during the 5 years included in the datasets

  - We do however include time related data in our models to counter this issue early on

# Data Preparation:

* ...

# Modeling:

* ...

# Evaluation:

* ...