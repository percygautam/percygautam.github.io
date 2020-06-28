---
layout: post
title: Completion of Phase-I
description: This post is going to describe the goals achieve during the first phase of my project.
image: assets/images/journey_to_GSOC.png
date: 26 June 2020
show_tile: false
---

<p align = "justify">Hi everyone, this is Piyush and I am here with the 3rd iteration of my series of blogs depicting my journey in the GSOC program. If you haven’t read my previous blogs, you can do so <a href="/../gsoc.html">here</a> and keep up.</p>

<p align = "justify">The first phase of coding period started on June 1, 2020. I started following a fixed schedule starting from this period. I allotted a minimum of 5 to 6 hours daily and more hours during weekend. This helped me maintain the balance between my personal life and work life.</p>

<p align = "justify">I first started on the <i>html_repr</i> of the InferenceData object for jupyter notebooks. This implementation is based on xarray's. I chose this to start because this will enable me to easily check the other methods that'll be added in the future. The pull request for <i>html_repr</i> is already merged and it is up and running in the example <a href="https://arviz-devs.github.io/arviz/notebooks/InferenceDataCookbook.html#">cookbook</a>. You can check out this awesome feature <a href="https://github.com/arviz-devs/arviz/pull/1217">here</a>.</p>

Then I moved on to extend other methods from `xarray.Dataset`. I first started with converter methods to be implemented in InferenceData object. I started working on `to_dict` method, which will allow the user to convert the InferenceData object to a `dict`. As ArviZ already has `arviz.from_dict` method, the new method needs to be compatible with it. So, that we can do something like `az.from_dict(**idata.to_dict())` and still get the same `idata`. While working dual compatible `to_dict`, I also end up improving the `az.from_dict` too. I added `attrs` and `warmup` group support to `az.from_dict`. The [PR](https://github.com/arviz-devs/arviz/pull/1223) is currently active and is in the process of being reviewed.

Then I move on to extend `xarray.Dataset` methods to InferenceData object. `sel` was already implemented, so based on same structure I implemented `isel`, `rename`, `rename_dims`, `rename_vars`, `stack`, `unstack` for InferenceData object. I am also done with the testing of these methods. The [PR](https://github.com/arviz-devs/arviz/pull/1254) is open and is currently being reviewed. To extend further methods from `xarray.Dataset` to InferenceData object, I also created a wrapper function:
```
def extend_xr_method(func):

    @functools.wraps(func)
    def wrapped(*args, **kwargs):
        _filter = kwargs.pop('filter_groups', None)
        _groups = kwargs.pop('groups', None)
        _inplace = kwargs.pop('inplace', False)
        self = args[0]
        args = list(args)

        out = self if _inplace else deepcopy(self)

        groups = self._group_names(_groups, _filter)
        for group in groups:
            xr_data = getattr(out, group)
            args[0] = xr_data
            xr_data = func(*args, **kwargs)
            setattr(out, group, xr_data)

        return None if _inplace else out

    return wrapped
```
Using this wrapper, new methods `xarray.Dataset` can easily be extended to InferenceData object.

<p align = "justify">During this whole time, the mentors were very helpful and cleared all my doubts on channel or on the PR itself. They regularly reviewed my work and suggested changes. This motivated me to remain focussed on my work. The phase I of coding period is almost over and am enjoying my work. Peace out.</p>