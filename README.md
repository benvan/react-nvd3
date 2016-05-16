This is a fork of https://github.com/NuCivic/react-nvd3 . You probably want to go there instead.

#Why this fork exists
nvd3 v1.8.1 introduced a rendering bug for (at least) scatterCharts whereby transition durations were no longer configurable. This made it impossible to render certain charts updating in real-time since they would require a transition duration of 0.

This fork reverts nvd3 to 1.1.15, and directly sets transition / duration in the d3 call chain.

#Why you would use this fork
You want to animate the nvd3 scatterChart

#Why the hell didn't you just fix nvd3 v1.8.1+ ?
I did have a look into it, but the solution was not a simple case of tracking down a lost parameter. I just want to animate a single graph in another project of mine. This got me moving.

I have submitted a bug report to nvd3.

#Why are you writing this README then?
Courtesy. It bothers me to see forks with the same README as the original. What do you do, fork? What do you do??!

#Changes in this fork
- nvd3 dependency reverted to 1.1.15
- nvd3 accessed via global (window) context since 1.1.15 does not export any modules :(
- transition + duration calls added to chart rendering to compensate for outdated API (but fixing current nvd3 transition bug)
