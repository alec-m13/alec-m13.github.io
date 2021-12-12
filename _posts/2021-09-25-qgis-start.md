---
category: gis
title:  "File Format Issues"
---

The first day was mostly lost trying to open a specific file (actually a folder of related files) before ultimately resigning myself to the fact that it was in a format unavailable to QGIS. QGIS is perfectly capable of opening Esri shapefiles, though, and those are the standard in geopspatial data. Therefore most data in the tutorial loaded just fine. After skipping that one part of the opening task I made it halfway through the entire tutorial before encountering the formatting problem again.

The second time I couldn't open a file it was a street map. Supposedly the file contained data on the streets nationwide and address locations on their street. It was intended for geocoding, which is transforming address strings (like "3002 Mt Angeles Rd, Port Angeles, WA 98362") to geographic coordinates. I got around this file incompatibility by using a network-based geocoding feature in QGIS. Basically it sent the addresses to a server somewhere on the internet dedicated to this task and processed the results which the server returned. It was a slow process because there were lots of addresses and I would want a networkless approach if I were to do it for real.

After that I consistently had trouble opening street data files. The sections of the tutorial involving street networks (where the goal is to find the shortest distance by road) invariably had incompatible street data. I circumvented these incompatibilities by finding alternate sources of street data. Most large cities, states, and other municipalities publish street data in several different formats freely online. I learned how to find and utilize these data for the tasks.