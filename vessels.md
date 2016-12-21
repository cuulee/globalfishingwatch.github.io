---
layout: default
---

# Vessel Identity

Over the course of a year, around 300,000 vessels broadcast their location via AIS. Several tens of thousands of these vessels are industrial fishing vessel, and we identify these vessels through three methods. 

### 1. Likely Fishing Vessels
AIS messages include a field `shiptype`, which is a two digit number corresponding to the activity that the vessel is engaged in. The full list of these possible activities is listed [here on Marine Traffic](https://help.marinetraffic.com/hc/en-us/articles/205579997-What-is-the-significance-of-the-AIS-SHIPTYPE-number-). About seventy thousand vessels per year report that they are fishing. The user of the AIS device, though, has to manually enter this information, meaning that while this information is mostly accurate, in some cases the shiptype is entered incorrectly, and some reported fishing vessels are not actually fishing vessels, and some fishing vessels don't report as such. We call vessels that self report as fishing `likely` fishing vessels.

### 2. Known Fishing Vessels
To identify fishing vessels we also match mmsi numbers to vessel registries, such as the [European Union's vessel registry](http://ec.europa.eu/fisheries/fleet/index.cfm), or the [Consolidated List of Authorized Authorized Vessels](http://www.tuna-org.org/vesselpos.htm). Many of these vessels also self-report as fishing, and thus are also `likely` vessels. These matches, though, give us a higher degree of confidence, and we call these vessels `known` fishing vessels.

### 3. Suspected Fishing Vessels
The third method involves using machine learning techniques to identify vessels that behave like fishing vessels. This method is still under development. We call these `suspected` fishing vessels. Visit our page on our [neural net]({{ site.url }}{{site.baseurl}}/neural-net.html) to learn more about .


# Version 0.1 of Vessel Lists
This is the lists of fishing vessels that we included in the initial public release of Global Fishing Watch in September of 2016. We included vessels that incorporated the following criteria:

 - At least 1000 position messages broadcast in any given year (thus ignoring vessels that had very
 little activity).
  - Vessels that broadcast they were fishing vessels 100 percent of the time ('likely' fishing vessels), or were matched with one of the fishing vessel registries ('known' fishing vessels).

 We also excluded some mmsi numbers that we knew were not fishing vessels, such as some helicopters that were using AIS and self-reporting as "fishing" because they work with fishing vessels. 

These lists of mmsi numbers can be accessed [here](https://github.com/GlobalFishingWatch/treniformis/tree/0.1/treniformis/_assets/GFW/FISHING_MMSI/KNOWN_AND_LIKELY), and more details for how they were were developed are in [this GitHub repo](https://github.com/GlobalFishingWatch/treniformis/tree/0.1/), version 0.1.

Future versions of these lists will include flag state, gear type, and other information about the vessels. 

![Vessels]({{ site.url }}{{site.baseurl}}/images/vessel.jpg)
