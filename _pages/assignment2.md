---
permalink: /Assignment-2/
title: "Assignment-2"
---

# **Luxury Trade in Zanzibar 1915 \- 1919**

## **Source and data**

The data for our map was sourced from the Zanzibar Gazette, a colonial government publication that included monthly statements of Zanzibar’s imports and exports. Specifically, we picked the statements from 1915 to 1919 for this project and focused on commodities often associated with luxury such as beer, wine, spirits, and tobacco, quantities of which were recorded in packages (pounds for native tobacco). The monetary values of these commodities in rupees were also available from the source. All figures are organized by month, direction of trade, and regions.  
The regions that traded with Zanzibar include the United Kingdom, continental Europe, America, India, other Asian ports, and the African mainland. The Gazette records these by region rather than by the names of specific ports. One interesting thing we noticed was the distinction between “European” and “native” tobacco, as it was the only commodity from our chosen list with this distinction. 

## **Direct and inferred data**

The statements from the Gazette give us the month, the direction of trade, the commodity, the region, the number of packages, and the value in rupees. In addition to these, we needed the coordinates of the geographic regions named in the statements, as the purpose of this assignment is to visualize the data on a map. Because the Gazette only names very generalized geographic regions instead of specific cities, we took the capitals of each region as stand-ins on the map: London was used as a stand-in for the United Kingdom, Paris for continental Europe, New York for America, Bombay for India, Aden for other Asian ports, and Mombasa for the African mainland. 

## **Prompt engineering**

We used Claude to turn the Gazette data into a CSV file. The prompt was:  
i need to make csv file on the data, but i’d need only the information for tobacco, wine, spirits, beer, (maybe other luxury goods that you may see fit), professor wants us to aim for around 300 data points. id want the rows to be the location (go location by location, like all of europe then all of etc), id like the columns to be by the goods, and also the lat long of the location, and the date, add a column for notes, and also if uncertain about anything, mark it with \[?\]  
We believe that this prompt worked well because it gave Claude a clear scope as well as an output format. Rather than simply asking the model to read the data, our prompt defined the CSV structure, defined both the list of commodities to consider and requested geographic coordinates, and established a rule for uncertainty. The instruction to use \[?\] in place of uncertainties was crucial because it prevented the model from fabricating data. Claude also pointed out some things that we failed to notice, such as the Gazette’s inconsistencies in naming regions (ex: the switch from “Bombay / Calcutta” in 1915 to “India / Other Countries” in 1916 and then “India and Burmah / Other Ports of Asia” in 1919). 

## **Automation and cleaning**

We feel like automation was most useful for organizing our screenshots of the statements into a more readable table. However, it was less reliable in reading parts of the statements that were tilted or misaligned. A lot of the tables had columns that do not line up neatly with their row labels, so in certain cases a number may appear to belong to one commodity but actually belongs to another. Instructing Claude to mark \[?\] for these uncertainties helped a lot with the process, but we also had to double check whether the regional package and value totals matched the original data as well as standardizing the names of the differing regional categories across the years. For example, the CSV includes notes such as “value blurred,” “figures sit one row above their labels,” and “parts add to the printed total.” The dataset was also missing data from 1917, 1918, and August 1919, so we could not show a continuous timeline of trade in our visualization as we had initially hoped, not to mention all the cells that were marked with \[?\].

## **Mapping the data**

We used Claude to create an interactive Leaflet map from the CSV. The map includes a toggle for imports and exports, a slider for progressing to the years, a selector for individual commodities, and visual flags for uncertain figures. The map reveals several concentrations of activity: the African mainland had a strong presence in both imports and exports, especially for beer, spirits, and native tobacco. India/Bombay was another important concentration, particularly for imports. Europe, especially the United Kingdom, appeared to be a major source of beer, wine, spirits, and European tobacco. These clusters suggest that Zanzibar was connected to several overlapping commercial networks, from a regional East African network to an Indian Ocean network centered partly on Bombay and a more sparse European and American network. However, these clusters should not be taken as absolute historical facts because the map uses major cities as stand-in points for entire regions. The map is therefore most useful for visualizing Zanzibar’s trading partnerships but not the exact shipping routes. 

## **On a larger scale**

If the project were expanded to include a longer series of Gazette trade statements, the expanded dataset would likely reduce the impact of individual uncertainties and make it easier to identify patterns that repeat across months or years. With more data, it would also be possible to examine seasonal patterns, wartime disruption, and other changes in Zanzibar’s trade activity that reflected historical circumstances. For example, we can try to see if European imports declined during the First World War. If we could use another source for this assignment, the ideal source would be a record of ports in Zanzibar that lists individual vessels, their ports of departure/destination and descriptions of their cargo. This would allow us to map actual trading routes rather than broadly assigning regions to representative cities. It would also make it possible to distinguish between goods that merely passed through Zanzibar and goods that were actually consumed by the local population.

## **Conclusion**

This assignment showed that Claude can be very effective for both data extraction and visualization when prompted correctly with specific instructions. At the same time, it became clear that automation needs to be complemented with historical judgment. The Gazette’s changing regional names and misaligned tables required additional cleaning and interpretation. The ideal workflow was to let the model automate the first pass while noting uncertainties, pointing us to places where we needed to double check categorizations and numbers.

<div style="width:100%; height:70vh;">
  <iframe
    src="{{'daah/assets/maps/Zanzibar.html'}}"
    style="width:100%; height:100%; border:0;"
    loading="lazy">
  </iframe>
</div>