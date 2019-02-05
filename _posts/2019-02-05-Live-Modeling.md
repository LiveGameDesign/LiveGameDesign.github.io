---
layout: post
title:  "Exploring the Design Space with Live Modeling"
date:   2019-02-05 14:00:00 +0100
author: Riemer van Rozen, Amsterdam University of Applied Sciences
categories: draft of a short position paper
---

*Draft -- February 5th 2019*

**Abstract.**
Live Modeling is a research area in Model-Driven Engineering that studies how to improve the affordances of languages, tools and techniques by providing immediate and continuous feedback about how visual changes to the source code (or model) affect running programs.
Instead of long edit-compile-run cycles, every update to the model is immediately visible in the running application and its programming environment.
Here we share our perspective on how these tools support interactive design space exploration.
We motivate our research and give and account on our progress on enabling technology constructed in the context of an applied project called Live Game Design.
We demonstrate two live programming environments we created for 1) a simple State Machine Language; and 2) Micro-Machinations, a Domain-Specific Language for game economies.

### Introduction
Imagination is at the root of every improvement. We see how something is lacking, we imagine an improvement, set out to achieve a new goal and find new solutions with varying degrees of success. Making improvements often goes wrong because our imagination did not accurately predict the outcomes of our actions.

Practitioners and researchers have invented *iterative design processes* to gather early feedback on the qualities of our work and improve solutions step by step, gradually improving our insight, constantly checking if we are still on track with respect to changing goals. On the one hand we rely on our imagination to take the right course of action, and on the other hand we do not know yet what that should be because we still have to learn what the solution can become.

Experienced software engineers construct *mental models* of the systems they built. They can predict with uncanny accuracy how a program works, how it is failing and how it can be improved. Programming is mostly done by imagining improvements and then implementing them, finding out how you were wrong during a lengthy debugging sessions and fixing bugs, repairing mistakes, and of course improving your predictions in the mean time.

To achieve the highest possible quality, *understanding* how programming changes affect systems under development with respect to a goal is paramount. However, the changes themselves are not often explicitly represented. Instead, engineers create a new version of the source code of a program by making changes here and there, but commonly only see the effects when they recompile or reinterpret and run that code again. This is especially complicated for novice programmers who lack the mental model needed to make correct and meaningful changes to the source code. Instead, novices are left to guess and are forced to take a stab in the dark. This makes learning how to program a frustrating and difficult thing to do. How can you build your mental model if everything you try blows up in your face?

Imagine that we do explicitly represent change, that all changes we make to program models have meaning, and that we can study the effect of changes immediately and continuously. This enables checking with every little change if it had the effect what we imagined or learning how it did not, and combining lots of little changes for steering towards improvements of complete systems. This style of incremental updates with immediate feedback is called *live programming*.

In live programming we do not assume that you already know what you are doing. Program, go forward, discover your imagination was wrong, learn and reimagine. Go back and try again, observe an improvement, enjoy the endorfines rushing through your brain and continue. Fail, that is ok, it's never a straight line to a goal, just model sideways and *'explore the failure space'*, you will get there in the end. 

Our research focusses on explicitly representing changes of program models that help programmers and game designers quickly learn what their changes mean, enabling them to gradually improve both their insight and their programs [1].

### Live Programming for State Machines
A key research challenge in live modeling is to determine how to migrate the application's run-time state with the changes to the source code.
In van Rozen and van der Storm [1], we describe first steps towards general, reusable and maintainable solutions, which entails *differencing* models and *patching* the run-time state to reflect the changes. 
The following movie demonstrates how this works for a simple State Machine Language.

<figure class="video_container">
  <video controls="true" allowfullscreen="true"  width="800">
    <source src="/assets/sml_live.mp4">
  </video>
</figure>

### Live Game Design with Machinations
The project Live Intelligent Visual Environments for Game Design, or Live Game Design for short, envisions LIVE game design tools that have the following qualities:
	
* **Visual.** includes visual programming languages especially attuned to the expertise of game designers

* **Live.** provides immediate and continuous (live) results that are understandable and help gain insight

* **Feedback.** shows precise and intelligent feedback on mechanics, related dynamics (interaction and run-time), resulting aesthetics (gameplay), in order to make informed decisions.

* **Feed-forward** offers alternatives that can be inspected, picked and applied to focus the creative design process

* **Applicable.** examples and material to learn how to apply the tools

Here we demonstrate a new live programming environment for Machinations, a Domain-Specific Language for game economies.
The tool supports simultaneously editing and running models, which enables immediate prototyping and continuous play testing.
Ferdy van den Hoed (a bachelor student at the AUAS) built the front-end in Unity,
while Riemer van Rozen built the back-end, a new C#-based library which is also embeddable in games that is based on prior research [1].
As a result, games developed in Unity might profit from a built-in editor, though the final goal is platform independent remote manipulation.

**Simple Model.**
We show a simple diagram that uses only global variables, like the Machinations tool by Joris Dormans.
On the left we see the *edit view* and on the left the *run-time view*. As soon as an interactive node is added, it can be activated to see how the resources flow.

<figure class="video_container">
  <video controls="true" allowfullscreen="true" width="800">
    <source src="/assets/mm_simple.mp4">
  </video>
</figure>

**Farmville Model.**
More complex models consist of more than just global variables. Instead, the name space consists of objects, which are instances of definitions.
A first attempt at modeling a version Farmville also works surprisingly well.
We now see the definitions in the *edit view* on the left have running instances at run time in the *run-time view* on the right, which are updated every time we edit.
The engine that drives this tool not yet published, but requires a rather different way of programming. This will be a subject of a future research paper.

<figure class="video_container">
  <video controls="true" allowfullscreen="true" width="800">
    <source src="/assets/mm_objects.mp4">
  </video>
</figure>


### Conclusions
We described progress on enabling technology for languages and tools for live programming and game design, and shared our perspective on how they support an interactive exploration of the design space.
We motivated our research and gave and account on our progress by demonstrating live programming environments for State Machines and Micro-Machinations.

### Bibliography

1. R. van Rozen and T. van der Storm. Toward Live Domain-Specific Languages: From Text Differencing to Adapting Models at Run Time. Pre-print of an article that appeared in Software & Systems Modeling, Springer, August 2017. [[pdf]](https://homepages.cwi.nl/~storm/publications/vRozenvdStorm2017_sosym_v3.pdf)