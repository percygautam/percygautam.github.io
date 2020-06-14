---
layout: post
title: Journey to GSoC
description: This post is going to describe my journey of being selected as the student developer for Signac under Google summer of code an overview of my project.
image: assets/images/GSoC-2020.png
show_tile: false
---


I am Piyush Gautam, a senior undergraduate from NIT Hamirpur with the major in Electronics and Communication Engineering. I started programming in my sophomore year of the college, but did not have any experience with open-source till my junior year. I got introduced to open-source by my friend. I first started contributing to another NumFOCUS affilated organisation YellowBrick, which is plotting library for ML algorithms. I have been an active contributor for the same since then.

I got introduced to ArviZ through a Professor in my university. He teaches us the Statitics course an drecommended ArviZ for the visualisation of Bayesian statitics models. Although being a new subject, I begin trying out examples and reading about Bayesian algorithms. I started out with reading the documentation and getting myself used to the modules used in the library.

The ArviZ developer team was very friendly and assigned me various beginner issues and also solved all of my queries. After solving some issues, the community encouraged me to try some of the harder issues. This provides me with deep understanding of the library and other modules used in the library. InferenceData are central to ArviZ but it is still in development phase. There are only few selective methods present, which limits the full capabilities of the InferenceData object. So, I started working on enhancing its usability. I also made my Google Summer of Code's proposal based on this. I started breaking the problem into smaller chunks and solve them one by one. I formed a plan to tackle the issue in the 3 month duration and created the proposal for the same. As my project was still in discussion phase, so I faced many queries when I was writing my proposal, but the team of ArviZ helped me along the whole process.

## Project

ArviZ is a Python package for exploratory analysis of Bayesian models, intending to provide backend-agnostic tools for diagnostics and visualizations of Bayesian inference in Python. Generally, Bayesian inference generates numerous datasets that represent different aspects of the model. To simplify the handling, referencing, and serialization of data generated during Bayesian analysis, ArviZ uses a couple of data structures: xarray.Dataset, arviz.InferenceData and netCDF.

InferenceData objects are central to ArviZ and most ArviZ functions take InferenceData as input. However, its functionality is still quite limited. The main aim of the project is to extend some methods from xarray.Dataset and to create specific InferenceData methods.<br> 
You can view my project's proposal [here](https://docs.google.com/document/d/1Z9eMwFKQXyyYBEpp7WEGaJQPFxN_lILO9P0xHAdTLFw/edit?usp=sharing)

## For new contributors

Open-source is whole new world in itself and any one can contribute to it, even if you do not have much experience with programming. There are whole lot of different types of work in open-source like: solving issues, adding features, documentation etc. Every library on GitHub has some issues labelled for beginners, start with them and learn new technologies being used one step at a time. In <b>ArviZ</b>, we have `good first issues` for beginners. They mainly consist of documentation change, minor code fix etc. You can contact the ArviZ developers on [Gitter](https://gitter.im/arviz-devs/community?at=5c67a7755095f6660c018018) for live support. We’ll be sure to help you in any way we can. <br> SO, stop thinking an start contributing.

