---
layout: default
---

# Vessel Identity

Over the course of a year, over 300,000 unique vessels broadcast their location via AIS. Several tens of thousands of these vessels are industrial fishing vessels, and we identify them using three methods, listed below. With the recent publication of our paper, [Tracking the global footprint of fisheries]({{site.url}}{{site.baseurl}}/global-footprint-of-fisheries.html), we are releasing the results of our [neural net vessel classifier]({{site.url}}{{site.baseurl}}/neural-net.html). 
Visit the [Global Fishing Watch Community](https://globalfishingwatch.force.com/gfw/s/topic/0TO36000000PXJdGAO/global-fishing-watch-data) Page to download the list and results of this neural network.

Note that these lists are not the exact same as the vessels that currently appear on [globalfishingwatch.org](http://globalfishingwatch.org). Globalfishingwatch.org uses a combination of the `self-reported` and `known` fishing vessels, while the datset with our _Science_ paper uses a combination of the `known` and the `inferred` fishing lists. 

These are the three ways we identify fishing vessels:

### 1. Self-Reported Fishing Vessels
AIS messages include a field `shiptype`, which is a two digit number corresponding to the vessel's activity. The full list of these possible activities is listed [on Marine Traffic](https://help.marinetraffic.com/hc/en-us/articles/205579997-What-is-the-significance-of-the-AIS-SHIPTYPE-number-). About seventy thousand vessels per year report that they are fishing. This information is mostly accurate, but because the user of the AIS device has to manually enter this information, there is potential for human error, and in some cases the shiptype is entered incorrectly. Also some reported fishing vessels are not actually fishing vessels, and some fishing vessels don't report as such. We call vessels that self report as fishing `likely` fishing vessels.

### 2. Known Fishing Vessels
To identify fishing vessels we also match mmsi numbers to vessel registries, such as the [European Union's vessel registry](http://ec.europa.eu/fisheries/fleet/index.cfm), or the [Consolidated List of Authorized Vessels](http://www.tuna-org.org/vesselpos.htm). Many of these vessels also self-report as fishing. Matching self-reported fishing vessels with vessel registries gives us a higher degree of confidence, and we call these vessels `known` fishing vessels.

### 3. Inferred Fishing Vessels
The third method involves using machine learning techniques to identify vessels that behave like fishing vessels. This method is still under development. When vessels exhibiting fishing behavior are not also listed in registries or do not self-report, we call these `inferred` fishing vessels. Visit the page on our [neural net]({{ site.url }}{{site.baseurl}}/neural-net.html) to learn more.


# Version 0.3 of Vessel Lists 
This release is the same as version 0.2, except we have included type 19 messages, which are messages where Class B vessels broadcast their identity. These messages were accidentally not included in the previous versions of the vessel lists, which excluded some vessels. Also, these lists are updated for all of 2016, and include a list for 2017. To download lists 0.3, visit [this github release](https://github.com/GlobalFishingWatch/treniformis/tree/0.3/treniformis/_assets/GFW/FISHING_MMSI/KNOWN_AND_LIKELY).

For 2017, we include all mmsi active in the previous 12 months. We will be updating the 2017 list periodically, and posting those updates here.

# Version 0.2 of Vessel Lists
Our previous version included only vessels that had at least 1000 positions in a given year. We have changed this to 500 active positions -- positions where a vessel had a speed above 0.1 knots. We also are now including vessels that broadcast that they are fishing vessels more than 99 percent of the time (previous criteria was restricted to 100 percent). These relaxed restrictions increase the number of fishing vessels by roughly a few thousand per year.

A blog entry about this update can be found [here]({{site.url}}{{site.baseurl}}/vessel_activity/2016/12/22/New-Vessel-Lists.html).

To download lists 0.2, visit [this github release](https://github.com/GlobalFishingWatch/treniformis/tree/0.2/treniformis/_assets/GFW/FISHING_MMSI/KNOWN_AND_LIKELY).

# Version 0.1 of Vessel Lists 
These are the lists of fishing vessels that we included in the initial public release of Global Fishing Watch in September of 2016. We included vessels with the following criteria:

 - At least 1000 position messages broadcast in any given year (thus ignoring vessels that had very
 little activity).
  - Vessels that broadcast they were fishing vessels 100 percent of the time (`self-reported` fishing vessels), or were matched with one of the fishing vessel registries (`known` fishing vessels).

 We also excluded some mmsi numbers that we knew were not fishing vessels, such as some helicopters that were using AIS and self-reporting as fishing because they work with fishing vessels. 

These lists of mmsi numbers can be accessed [here](https://github.com/GlobalFishingWatch/treniformis/tree/0.1/treniformis/_assets/GFW/FISHING_MMSI/KNOWN_AND_LIKELY), and more details for how they were were developed are in [this GitHub repo](https://github.com/GlobalFishingWatch/treniformis/tree/0.1/), version 0.1.

Future versions of these lists will include flag state, gear type, and other information about the vessels. 


![Vessels]({{ site.url }}{{site.baseurl}}/images/vessel.jpg)

Page last udpated: February 22nd, 2018

