# Notes

## Background Checks

- There's a need to avoid bycatch of Chinook salmon
- One way to do this would be through being aware of depth occupancy
- What does the modeling look like today? 
- What are we adding in?

1. Bering Sea Salmon Bycatch Update


## Introduction (Draft)

### Bullets

---

- The walleye pollock fishery in Alaska is the largest in the United States by volume and in 2008 the wholesale gross value of the fishery was 1.4 billion 
- Chinook salmon are a prohibited species catch for this fishery. 
- Specifically for this fishery Ammendment 91 indicates that there is a 60,000 fish limit on the entire fishery (divided by sector and season A and B) that cannot be exceeded or the entire fishery is closed.
- Under the same ammendment there is a 47,591 limit that is distributed amongst the seasons and sectors of the fishery and if any of these sectors exceed that limit in 3 years for any 7 consecutive years then they are limited to their share of the 47,591 indefinitely from there on out. 
- This is to provide an incentive to reduce bycatch while allowing for years of unusually high salmon bycatch
- This policy was followed by Ammendment 110 in response to low levels of Chinook abundance where according to an index of abundance the performance limit previously described (the 47,591) would be reduced in times of especially low abundance. 
- To allow for the monitoring and enforcement of these policies, each vessel in the pollock fishery is required to have 100% observer coverage. 

---

- The methods used to combat bycatch are varied but include such things as closure areas, short term closures in areas of high incidental bycatch, and using salmon bycatch excluders in pollock trawls.
- However fixed time area closures may not always encompass the core habitat of species of concern and may unnecessarily restrict fishing activity when bycatch risk is low
- Furthermore it can concentrate fishing activity in other areas and affect species whose habitat occupancy or behavior is different from the species being protected by a specific closure. 
- Experience over time has shown that the industry, working cooperatively, can more effectively avoid salmon bycatch by sharing data
- And Dynamic ocean management (an example of an ecological informatics (“eco-informatics”) approach that uses near real-time data streams to support sustainable use of marine resources) is a good example of how data can be fed to an industry to allow for real time adaptation that can effectively take into account changes due to environmental variability or species behavior. 
- Ammendment 91 and 110 are already intended to incentivize the fleet to find and incorporate measures that reduce bycatch, providing eco-informatics to this end can only be helpful. 
- To this end incorporating providing the industry with modeling that can incorporate environmental covariates to help predict species distribution across longitude, latitude, and depth would provide a tooling the industry could use to further inform their efforts to avoid Chinook salmon bycatch.

---

- Of particular interest is depth as walleye pollock are found on or near the sea bottom as well as at mid water and near-surface depths, although most catches are found between 50 and 300 m and those catches are made using pelagic trawls. 
- This overlaps the 0 - 500m range observed for Chinook salmon in a tagging study mean that being able to differentiate between the two would be quite useful as clearly there is overlap in their geospatial distribution in order to cause bycatch issues. 

--- 

- There have been a series of studies on depth occupancy in Chinook salmon however all of them have focused on trying to understand what effects depth occupancy as opposed to providing inferential tools. 
- Machine learning has also been applied to this problem, but once again only to provide a sense of how covariates mattered to depth occupancy.
- Fish behavior with regards to environmental covariates is ultimately stochastic and so instead of predicting specific depths there is need for a model that predicts the relative occurence rates across the depth column available to the fish. this would mean predicting the likelihood of occupying specific depths as opposed to the specific depth occupied. 
- This is a perfect opportunity for probabilistic deep learning. 

### Draft

The walleye pollock fishery in Alaska is the largest in the United States by volume and generated a wholesale gross value of $1.4 billion in 2008 (2). Chinook salmon are classified as a prohibited species catch in this fishery, meaning their incidental capture is strictly regulated (1). In response to record high bycatch in 2007, Amendment 91 established a hard cap of 60,000 Chinook salmon for the entire fishery, divided by sector and season (A and B), with the consequence that exceeding this limit results in a complete fishery closure. Additionally, a performance limit of 47,591 salmon is allocated across seasons and sectors, with a rule that if any sector exceeds its share in three out of seven consecutive years, it is permanently restricted to that limit (2). This approach balanced the need to incentivize bycatch reduction while accounting for natural variability in salmon encounters. However, while the bycatch in the fisheries was reduced, in response to low Chinook abundance Amendment 110 was introduced to add an adaptive mechanism where the performance limit is further reduced during periods of low salmon abundance based on an established index (1). To enforce these rules, 100% observer coverage is mandated on all vessels within the pollock fishery, ensuring compliance and accurate monitoring of bycatch levels (1).

Efforts to reduce Chinook salmon bycatch in the pollock fishery employ a variety of strategies, including fixed closure areas, short-term closures in high-bycatch zones, and salmon bycatch excluders in trawl nets (1). While these measures have contributed to bycatch reduction, they can also have unintended commercial and ecological consequences. For example, time-area closures designed to protect one species may concentrate fishing effort elsewhere, potentially impacting other species (4), and they often restrict fishing in areas where bycatch risk is low, as they are typically based on historical rather than real-time data (3). In contrast, dynamic ocean management leverages eco-informatics and near real-time data streams to support adaptive fishing practices, allowing for a more responsive and precise approach to bycatch mitigation (3). This strategy aligns with industry experience, which has shown that cooperative data-sharing is a highly effective method for reducing salmon bycatch (1). To this end, providing the industry with models that incorporate environmental covariates to predict species distribution across longitude, latitude, and depth would offer a valuable resource for further refining bycatch avoidance strategies.

Depth is of particular interest as Chinook salmon and walleye pollock occupy overlapping ranges. Pollock are found from the seafloor to midwater and near-surface depths, with most catches occurring between 50 and 300 meters using pelagic trawls (5). This aligns with the 0–500 meter range observed for Chinook salmon in tagging studies (6), highlighting a key factor driving bycatch. However, models of salmon occupancy patterns that can take into account real-time environmental conditions could help fishers refine their operations, allowing them to target specific depths where bycatch risk is lower.

While several studies have examined depth occupancy in Chinook salmon, they have primarily focused on understanding the factors influencing depth use rather than developing inferential tools for prediction (7). Machine learning has also been applied, but mainly to analyze how environmental covariates influence depth occupancy, rather than generating practical predictive models (7). Given that fish behavior in response to environmental factors is inherently stochastic, an effective model would not aim to pinpoint exact depths, but rather estimate the likelihood of salmon occupying different depth ranges within the water column. Framed in this way, the problem becomes an ideal application for a probabilistic deep learning classifier, capable of modeling uncertainty and providing flexible, data-driven depth distribution predictions.

The goal of this study is to develop a probabilistic deep learning classifier capable of predicting Chinook salmon depth occupancy in near-real time. To achieve this, we will first identify key environmental covariates from existing literature that can be measured or predicted, and then use pop-up satellite archival tagging data from Chinook salmon in the Gulf of Alaska (7) to build and evaluate the model. This approach aims to provide a practical, data-driven tool for improving bycatch mitigation strategies in the pollock fishery.

1. Bering Sea Salmon Bycatch Update
2. Fisheries of the Exclusive Economic Zone Off Alaska; Chinook Salmon Bycatch Management in the Bering Sea Pollock Fishery
3. A dynamic ocean management tool to reduce bycatch and support sustainable fisheries
4. What are we protecting? Fisher behavior and the unintended consequences of spatial closures as a fishery management tool
5. https://www.adfg.alaska.gov/index.cfm?adfg=walleyepollock.printerfriendly
6. Behavior and thermal environment of Chinook salmon Oncorhynchus tshawytscha in the North Pacific Ocean, elucidated from pop-up satellite archival tags
7. Chinook salmon depth distributions on the continental shelf are shaped by interactions between location, season, and individual condition

## Methods (Proposal)

We will approach this study in three distinct steps: (1) identifying likely covariates, (2) building the model, and (3) evaluating the model's utility.

In the first step, we will conduct a literature review using Google Scholar, focusing on keywords such as depth, model, Chinook salmon, Gulf of Alaska, and Eastern Bering Sea. This will yield a collection of relevant studies, which we will review to extract useful covariates and modeled behaviors. We will also follow up on key citations within these papers to ensure a comprehensive selection of environmental and behavioral factors influencing depth occupancy.

For the second step, we will develop a series of probabilistic models following a log-odds modeling approach. Beginning with a null model, we will progressively incorporate covariates to assess their contribution to model performance. At each stage, we will retain intermediate models to track how covariate additions impact overall quality, evaluated by log-likelihood averaged per individual.

Finally, in the third step, we will assess the model’s ability to detect cases where Chinook salmon exhibit clear depth occupancy preferences. To do this, we will design and test a set of metrics to identify such patterns and summarize them over time and space. The goal is not to provide exhaustive spatial guidance, as the full range of fishing and environmental conditions is too large, but rather to determine the model’s effectiveness in identifying depth-based avoidance opportunities. Further validation will be required to assess whether the identified low-bycatch depth ranges align with walleye pollock hotspots.

## Looking for Features

### Great Papers

- Marine Vertical Distribution of Juvenile Chinook and Coho Salmon in Southeastern Alaska
- Chinook salmon depth distributions on the continental shelf are shaped by interactions between location, season, and individual condition

### Features Found

- Bottom Depth
- Bottom Slope
- Day of the Year
- Lunar Cycle
- Day vs Night
- Surface Temps
- Temps at Depth
- Current Direction
- Zooplankton 
- Chlorophyll
- Oxygen
- Salinity
- Thermocline Depth
- Size

Let's see what we can build with what's already in the database. 

### Results

- Model Selection 
  - A table with each of the models and the appropriate statistics to go with them 
  - Any notes on the changs in the statistics 
- What the model found (as compared to other papers)
  - Seasonal patterns 
  - Diel patterns 
  - Against the environmental variables 
  - Elevation (because folks talk about that too)
- How this helps with decision making 
  - Auxillary data and the need to inform not make decisions
  - Min maxing with constraints
  - High level (where or when)
  - Lower level (time and place)
  - Where to set a net 






