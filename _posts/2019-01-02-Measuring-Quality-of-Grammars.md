---
layout: post
title:  "Measuring Quality of Grammars for Procedural Level Generation"
date:   2019-02-01 15:00:00 +0100
author: Riemer van Rozen, Amsterdam University of Applied Sciences
categories: project update
---
*Updated Wednesday February 7th 2019*

## Improving Debuggers for Procedural Game Levels
Quinten Heijn and Riemer van Rozen participated in the International Conference on the Foundations of Digital Games (FDG), in Malmö, Sweden in August 2018.

Their talk at the Procedural Content Generation in Games (PCG) workshop, a part of FDG, was for a paper on Measuring Quality of Grammars for Procedural Level Generation [1].
It was written in the context of Quinten's MSc project, which was in collaboration with Joris Dormans of Ludomotion.

Following a very interesting related topic presented by Tom Smith on generating graphs for Zelda-style levels via Answer-Set Programming,
Riemer gave an introduction into Software Evolution which framed the talk, an unusual perspective for games research.
According to Antonios Liapis, Joris was virtually present too.

<blockquote class="twitter-tweet" data-conversation="none" data-lang="en"><p lang="en" dir="ltr">Feels like Joris &amp; <a href="https://twitter.com/PlayUnexplored?ref_src=twsrc%5Etfw">@PlayUnexplored</a> have a special virtual seat in this session. 2nd talk is on judging code quality of grammar-based dungeon generation. It&#39;s a Software Evolution approach for root-cause analysis in PCG, cool for explainable AI for white-box PCG? Shoutout <a href="https://twitter.com/jichenz?ref_src=twsrc%5Etfw">@jichenz</a> <a href="https://t.co/udCCbDA9aL">pic.twitter.com/udCCbDA9aL</a></p>&mdash; Antonios Liapis (@SentientDesigns) <a href="https://twitter.com/SentientDesigns/status/1026763935079251970?ref_src=twsrc%5Etfw">August 7, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

Analyzing the output of content generators is a key challenge, but determining root-causes of quality issues in the source code of the generators is another.

Quinten presented the main contributions of the paper, showing movies of LudoScope Lite, a prototype level generator and analyzer he built (currently limited to tile maps), which is available on [[github]](https://github.com/visknut/LudoscopeLite).

In good company, we see Rafaël Bidarra on the left and Julian Togelius on the right.
<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr">.<a href="https://twitter.com/VisKnut?ref_src=twsrc%5Etfw">@VisKnut</a> explaining declarative game level properties for measuring the quality of grammars for procedural level generation <a href="https://twitter.com/PcgWorkshop?ref_src=twsrc%5Etfw">@PcgWorkshop</a> <a href="https://twitter.com/hashtag/FDG18?src=hash&amp;ref_src=twsrc%5Etfw">#FDG18</a> <a href="https://t.co/JVxAVyMSRO">pic.twitter.com/JVxAVyMSRO</a></p>&mdash; Riemer van Rozen (@rvrozen) <a href="https://twitter.com/rvrozen/status/1026770246655504384?ref_src=twsrc%5Etfw">August 7, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

The movie below demonstrates a simple example game level of a dungeon room.
The player has to traverse the room without being burnt by fire pillars.
However, luckily players can use water from a pond to extinguish the flames.

<figure class="video_container">
  <video controls="true" allowfullscreen="true" width="320">
    <source src="/assets/PCG2018_demo_level.mp4">
  </video>
</figure>

The movie below shows how LudoScope Lite generates the tile map of this level.

<figure class="video_container">
  <video controls="true" allowfullscreen="true" width="100%">
    <source src="/assets/PCG2018_generate_level.mp4">
  </video>
</figure>

LudoScope Lite is a prototype that demonstrates two techniques that developers can use to analyse the root causes of quality issues in generated levels.
First, the Metric of Added Detail (MAD) raises flags for grammar rules that remove detail with respect to their position in the transformation pipeline.
Second, Specification Analysis Reporting (SAnR), analyzes level generation histories against level properties and reports problematic grammar rules.

The movie below demonstrates how SAnR finds broken levels given a set of simple properties. SAnR facilitates debugging and can be used to prevent bad levels from being generated.

<figure class="video_container">
  <video controls="true" allowfullscreen="true" width="100%">
    <source src="/assets/PCG2018_inspect_level.mp4">
  </video>
</figure>

### Conclusions
Specification Analysis Reporting (SAnR) in particular may prove very useful, since debugging grammar rules in level generation histories is an important requirement for improving the quality of grammar-based content generators.

Are MAD and SAnR odd names? Well, yes, but simultaneously debugging grammar rules and potentially countless levels feels MAD, and therefore becoming SanR must be urgent.
In that light, the results game developers achieve using generative grammars are not just good, but astonishing. Apparently one can develop an intuition of effects that enables steering for quality, even if debugging facilities are lacking or completely missing.
This cutting-edge technology explores the limits of procedural content generation, and it deserves the attention of researchers who can help developers push those limits forward.

* **Symposium.** In case you wish to learn more, Quinten will give a talk at the [Symposium on Live Game Design](/project/update/2019/02/01/Live-Game-Design-Symposium.html) in Amsterdam on February 27th.

### Bibliography
1. R. van Rozen and Q. Heijn. Measuring Quality of Grammars for Procedural Level Generation. Chapter revision. In Proceedings of the 13th International Conference on Foundations of Digital Games, FDG, as part of the 9th Workshop on Procedural Content Generation, PCG, Malmö, Sweden, August 7--10, 2018. [[pdf]]({{ site.url }}/assets/vRozenHeijn2018.pdf)
2. Q. Heijn. Improving the Quality of Grammars for Procedural Level
Generation: A Software Evolution Perspective. MSc Thesis. University of Amsterdam, Master of Software Engineering, August 30, 2018. [[pdf]](http://www.scriptiesonline.uba.uva.nl/document/661986)
3. R van Rozen and Q. Heijn. Measuring Quality of Grammars for Procedural Level Generation. Presentation slide deck. In Proceedings of the 13th International Conference on Foundations of Digital Games, FDG, as part of the 9th Workshop on Procedural Content Generation, PCG, Malmö, Sweden, August 7--10, 2018. [[pdf]]({{ site.url }}/assets/PCG2018_slides_vRozenHeijn.pdf)

**Proceedings.**
The full proceedings (the collection of papers) of FDG 2018 can be found here at dblp [[url]](https://dblp.uni-trier.de/db/conf/fdg/fdg2018.html).
The papers are available on the ACM digital library [[url]](https://dl.acm.org/citation.cfm?id=3235765).
In case you don't have access, most authors share a pre-print you might find via Google Scholar.

**Thanks.**
The city council of Malmö warmly welcomed the  conference participants to a reception and a dinner at the historical city hall, as recorded by the conference chair Jose Font.
We thank the organizers for a great conference!

<blockquote class="twitter-tweet" data-lang="en"><p lang="en" dir="ltr"><a href="https://twitter.com/hashtag/fdg18?src=hash&amp;ref_src=twsrc%5Etfw">#fdg18</a> gala dinner at the Town Hall thanks to <a href="https://twitter.com/malmostad?ref_src=twsrc%5Etfw">@malmostad</a> &#39;s support. <a href="https://t.co/hSTAD7IKZx">pic.twitter.com/hSTAD7IKZx</a></p>&mdash; Jose Maria Font (@erfont) <a href="https://twitter.com/erfont/status/1027642451329200129?ref_src=twsrc%5Etfw">August 9, 2018</a></blockquote> <script async src="https://platform.twitter.com/widgets.js" charset="utf-8"></script> 

Finally, we thank Joris Dormans for his continued collaboration with us in applied research on PCG and Automated Game Design.
