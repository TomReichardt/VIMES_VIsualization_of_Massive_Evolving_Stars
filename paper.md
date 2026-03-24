---
title: 'VIMES: VIsualization of Massive Evolving Stars'
tags:
  - Python
  - astronomy
  - gravitational waves
  - binary evolution
authors:
  - name: Laya Binu
    affiliation: 1 # (Multiple affiliations must be quoted)
  - name: Floor Broekgaarden 
    affiliation: 1
  - name: Amedeo Romagnolo
    affiliation: 2

affiliations:
 - name: Department of Astronomy and Astrophysics, University of California San Diego, 9500 Gilman Drive, La Jolla, CA 92093, USA
   index: 1
 - name: 
   index: 2

date: xx Month 2026
bibliography: paper.bib

# Optional fields if submitting to a AAS journal too, see this blog post:
# https://blog.joss.theoj.org/2018/12/a-new-collaboration-with-aas-publishing
aas-doi: 10.3847/1538-4365/ac416c
aas-journal: Astrophysical Journal Supplements 
---

# Summary

Rapid stellar population synthesis codes are used in astronomy to simulate the evolution of binary systems, where, given initial parameters, the final product of the binary can be determined. When presenting research involving these simulations, VIMES allows the creation of an accurate animation of a binary system evolved with COMPAS, making it easily digestible to an audience. The animation uses data from any detailed output file to ensure the resulting animation is accurate in radius, separation, color, eccentricity, and evolutionary phase at any given point. 

# Statement of need

When presenting research involving rapid population synthesis codes, the output is provided as a data file with numerical values representing the evolution of the binary system, but it is difficult to translate into a visualization suitable for talks or presentations. Because each system can evolve very differently, premade visualizations are often not accurate for the exact system being studied. While Van Den Heuvel figures can be created for a given binary system, it does not fully capture the evolution of a binary system. The evolution between phases is just as important as the difference between the beginnings of two different phases, with an animation being the most effective way to ensure that no major details about the evolution is lost while being easily presentable to an audience. 
This code allows for any binary system evolved with COMPAS to be turned into an animation, with the user having a choice over the type of images used for the visualization, as well as the type of scaling used when converting the data into an animation. 

# Details

VIMES creates an animation in two different steps. When a new binary system needs to be animated, as soon as the path to the detailed file is changed, VIMES will load all necessary data from the file, and process it to have a 1:1 correspondence with the timesteps/associated parameter, and the frames of the animation. 
The data are first separated by "phase," which is determined by when the stellar type of either star in the binary changes, with mass transfer treated as an additional phase inserted later at the corresponding point in its evolution. The same number of timesteps or frames is sampled from each phase. If there is a large difference between two timesteps, either a large percentage or an absolute change in any values, then interpolated frames are added in between. This is done to ensure that the evolutionary phases that are usually more relevant are properly displayed, as having the number of frames per phase be reflective of the actual time spent in each phase, leading to excessively long main-sequence phases with nothing of note happening in the animation.
The second part of the code takes the cleaned data, now saved as a .npz file, and creates an animation with each frame corresponding to one time step from the file. 

# Acknowledgements

Multiple authors are supported by the Australian Research Council Centre of Excellence for Gravitational Wave Discovery (OzGrav), through project number CE170100004. Multiple authors were funded in part by the National Science Foundation under Grant No. (NSF grant number 2009131), the Netherlands Organization for Scientific Research (NWO) as part of the Vidi research program BinWaves with project number 639.042.728 and by the European Union’s Horizon 2020 research and innovation program from the European Research Council (ERC, Grant agreement No. 715063).  FSB is supported in part by the Prins Bernard Cultuurfonds studiebeurs. IM is a recipient of an Australian Research Council Future Fellowship (FT190100574).  AVG acknowledges funding support by the Danish National Research Foundation (DNRF132)


# References
