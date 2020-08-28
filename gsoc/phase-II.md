---
layout: post
title: Completion of Phase-II
description: This post is going to describe the goals achieve during the second phase of my project.
image: assets/images/phase-II.jpg
date: 4 August 2020
show_tile: false
---

<p align = "justify">Hi everyone, this is Piyush and I am here with the 5th iteration of my series of blogs depicting my journey in the GSOC program. If you haven’t read my previous blogs, you can do so <a href="/../gsoc.html">here</a> and keep up.</p>


<p align = "justify">The phase-II of the coding period has been completed. During these two months most of the coding work has been completed. During this phase, some of my work PR has also been merged after many rounds of review process by mentors. It's thanks to their timely and detailed review that much of the project work has already been completed.</p>

<p align = "justify">In this phase, apart of completing the wrapper to extend <i>xr.Dataset</i> methods, the custom methods to InferenceData object has been added. The work can been seen in this <a href="https://github.com/arviz-devs/arviz/pull/1300">PR</a>. In this PR, follwing methods has been added:
<ul>
    <li><b>add_groups</b>: Add new groups to InferenceData object</li>
    <li><b>extend</b>: Extend InferenceData with groups from another InferenceData.</li>
</ul>

It has been decided to add further custom methods as the need arises.
</p>

<p align = "justify">By the end of this phase, the  <a href="https://github.com/arviz-devs/arviz/pull/1223">PR</a> on <i>io_dict</i> also got merged. This enabled us to finally implement the <i>JSON converter</i> just like the <i>NetCDF</i> one. In this PR, I implemented the two methods <i>from_json</i> and <i>to_json</i>. The work can be seen in the <a href="https://github.com/arviz-devs/arviz/pull/1349">PR</a>. The next phase will deal with documentationa and wrapping up the project.</p>

<p align = "justify">During this whole time, the mentors were very helpful and cleared all my doubts on channel or on the PR itself. They regularly reviewed my work and suggested changes. This motivated me to remain focussed on my work. The phase II of coding period is also over and I am enjoying my work. Peace out.</p>