Emma Kaufman
Fall 2024
erk25@duke.edu

Notes from when data were shared:

I put the FIM vector outline in a shared G-folder here. I also added a small slide deck of some of my first-glance observations of how the FIM performed. The FIM data I'm giving you is from the Latest Analysis run of the National Water Model (aka Analysis and Assimilation, aka AnA). This configuration is based on observed data like radar-indicated rainfall amounts and assimilated flows at gaged locations. Therefore, it's considered the closest to what's happening at the given timestep – in this case 22:49Z (GMT). I was using this FIM because I'm mainly interested in removing as much uncertainty from the rainfall and streamflow forecast as possible so that I can just focus on the FIM performance. Rainfall forecasting is one of our biggest sources of error, which makes this event perfect for this analysis since all of the rain had ended 2 days prior in the Ozarks and was traveling downstream.

Here's a link to our web and data service catalog where you can download the rainfall data if you'd like. NWPS can also give you a quick look by turning on the precip estimate layer and selecting Nov 8.
image.png

NDWI is a pretty standard practice, you'll just need to dial in the threshold you use for identifying water pixels. This image may not be the easiest for automatically pulling the flood because there are a few high clouds and some cloud shadows, which can affect the light reflected back to the optical sensor. Nevertheless, I would definitely try to see what you can get out of it. I'm cc'ing the author of that paper, Mike – feel free to ask him about his methods.

Here's a few things to keep in mind:
No matter how good your algorithm is for identifying water pixels, this area has quite a bit of tree cover which is always going to give you false negatives. There are some "region grow" algorithms that can try to fill in the gaps caused by vegetation, but I've been told by Dr. Sagy Cohen that evaluating FIM performance in areas where you've filled-in is a fallacy because you're essentially evaluating our FIM model on another model. Bottom line: only do your analysis over pixels that you can identify without modelling the vegetation gaps.
There will inevitably be wet pixels that are not floods, like reservoirs and ponds. It's a good idea to remove these areas of "permanent water" from your analysis, especially because our FIM won't have ponds identified as flooded unless they are close to the river. You can find this data from the USGS NHD.
Noise is always an issue. There are ways to reduce it, the most common I know of is to use a sieve, but ArcPro might have something easier. Nothing is ever going to be one-size-fits-all for remote sensing, so you're going to have to do a little trial-and-error.

NHD Dataset: https://apps.nationalmap.gov/downloader/#/