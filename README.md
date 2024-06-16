# Athens Heat Risk Index
An interactive map illustrating the intensity of heat across various areas in Athens, Greece. Designed to aid in implementing preventative measures for cooling the city and enhancing its resilience.

**Link to project:** http://recruiters-love-seeing-live-demos.com/

![alt tag](http://placecorgi.com/1200/650)

## How It's Made:

**Tech used:** ArcGIS Pro, ArcGIS Online, ArcGIS Living Atlas of the World, ArcGIS Spatial Analyst extension

The first step is to get the land surface temperature through a Multispectral Landsat layer. It was received from ArcGIS Living Atlas.

Next up was to set the study area to Athens, Greece, zooming to the GRC_Postcodes3 layer, going into the attriubtes layer and filter out postcodes that can skew the data and removed them accordingly. I then used the Copy Features tool to reproduce a copy of the remaining postcodes into a new layer called Athens_Postcodes.



Here's where you can go to town on how you actually built this thing. Write as much as you can here, it's totally fine if it's not too much just make sure you write *something*. If you don't have too much experience on your resume working on the front end that's totally fine. This is where you can really show off your passion and make up for that ten fold.

## Optimizations
*(optional)*

You don't have to include this section but interviewers *love* that you can not only deliver a final product that looks great but also functions efficiently. Did you write something then refactor it later and the result was 5x faster than the original implementation? Did you cache your assets? Things that you write in this section are **GREAT** to bring up in interviews and you can use this section as reference when studying for technical interviews!

## Lessons Learned:

No matter what your experience level, being an engineer means continuously learning. Every time you build something you always have those *whoa this is awesome* or *wow I actually did it!* moments. This is where you should share those moments! Recruiters and interviewers love to see that you're self-aware and passionate about growing.

## Examples:
Take a look at these couple examples that I have in my own portfolio:

**Palettable:** https://github.com/alecortega/palettable
