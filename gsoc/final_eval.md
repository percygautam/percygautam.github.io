---
layout: post
title: Completion of Google Summer of Code
description: This post is going to describe the goals achieve during the second phase of my project.
image: assets/images/GSoC-2020.jpeg
date: 28 August 2020
show_tile: false
---

<p align = "justify">Hi everyone, this is Piyush and I am here with the final iteration of my series of blogs depicting my journey in the Google Summer of Code program. If you haven’t read my previous blogs, you can do so <a href="/../gsoc.html">here</a> and keep up.</p>

<p align = "justify">The of the coding period of <b>Google Summer of Code</b> is finally reaching its completion. During past three months, I worked closely with my mentors and brought the project to its timely completion. Most of the PRs which I opened during the coding period has been merged after many rounds of review process by mentors. It's all thanks to their timely and detailed review that the project is reaching its timely completion.</p>

<p align = "justify">The goal of the project is to define a suitable API and implement several helper methods to work with InferenceData object. This goal is further categorised into extending methods from <i>xr.Dataset</i> methods and to create custom methods for InferenceData object. During the project duration, I worked on deciding which methods to implement with the community, then on implementing those methods. Regarding extending methods from <i>xr.Dataset</i>, I custom implemented the methods which we suppose will be used frequently by the ArviZ users. For other methods, I created a wrapper which will directly extend methods from <i>xr.Dataset</i>. Apart from extending methods, I also implemented custom InferenceData object methods which will ease the handling of data with InferenceData object. <br> Following are the PRs I opened during the Google Summer of Code project duration. Most of them are merged while some are still under review process:</p>

#### [1. HTML representation for jupyter notebooks #1217 (MERGED)](https://github.com/arviz-devs/arviz/pull/1217)

This PR implements the html representation for `arviz.InferenceData` object in jupyter notebooks. This provide a visual representation for the `InferenceData` object. This is implemented first as it is crucial in implementing other methods. It eases the process of testing other methods outputs.

#### [2. Add `to_dict` method to InferenceData object #1223 (MERGED)](https://github.com/arviz-devs/arviz/pull/1223)

This PR implements `to_dict` method, which will allow the user to convert the InferenceData object to a `dict`. It also revamped the existing DictConverter (`from_dict` method) to allow attrs and warmup groups and to make it backward compatible with `to_dict`.

#### [3. Extend methods from `xr.Dataset` #1254 (MERGED)](https://github.com/arviz-devs/arviz/pull/1254)

This PR is the major PR implmenting the custom extended methods from `xr.Dataset` and the wrapper for extending other methods. Various methods being custom extended are `isel`, `stack`, `unstack`, `rename`, `rename_vars` and `rename_dims`. Various other methods are being extended using the wrapper created.

#### [4. Add custom methods for `InferenceData` #1300 (MERGED)](https://github.com/arviz-devs/arviz/pull/1300)

This PR implements the custom methods for idata object to ease out the working with idata object. The methods implemented are `extend` and `add_groups`. Also `concat` method is modified to incorporate the added methods.

#### [5. Add JSON Converter #1349 (MERGED)](https://github.com/arviz-devs/arviz/pull/1349)

This PR is an extension to `io_dict` PR and implements the method `from_json` and `to_json`. 

#### [6. Add documentation #1338 (OPEN)](https://github.com/arviz-devs/arviz/pull/1338)

This PR does documentation changes and adds examples to the methods added during GSoC period. Also this PR will add a notebook incorporating all the methods added and descibes these methods for new users.

#### [7. Add `__iter__` method #1356 (OPEN)](https://github.com/arviz-devs/arviz/pull/1356)

This PR implements the `__iter__` method used to give dict like behaviour to InferenceData object.

#### [8. Add `attrs` and `name` to InferenceData #1357 (OPEN)](https://github.com/arviz-devs/arviz/pull/1357)
This PR adds `attrs` and `name` to InferenceData object. These two attributes will add to functionality of InferenceData object.

<p align = "justify">Out of above PRs, 3 are still open and are under review process. The documentation and testing for all the methods is done. Only adding examples and finalising the notebook are remaining. These will be done in the coming week.</p>

<p align = "justify">During the whole Google Summer of Code journey, the mentors were very helpful and cleared all my doubts on channel or on the PR itself. They regularly reviewed my work and suggested changes. This motivated me to remain focussed on my work. This has been a fantastic journey and I learned a lot from this experience. Peace out.</p>