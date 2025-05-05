---
{"dg-publish":true,"permalink":"/references/articles/limits-to-growth-1972/","title":"Limits to Growth (1972)","tags":["📰"],"created":"2025-02-22T11:20:09.253-06:00","updated":"2024-12-30T09:36:22.000-06:00"}
---


# Limits to Growth (1972)

>[!summary]- Description

## Concepts

| Name | Weight |
| ---- | ------ |

{ .block-language-dataview}

## Content

"Computation and the Human Predicament," in the May–June issue of *American Scientist*, discusses the World3 computer model, introduced in the 1972 book *The Limits to Growth*. As a way of better understanding the inner structure of the model, I have been working to re-implement it as a web application. The current state of this project is on exhibit [here](http://bit-player.org/limits/ltg.html).

This is a work in progress and may well have serious bugs. I expect to continue improving it, but any serious investigation of the World3 model should be done with one of the more reliable simulation packages, such as [Stella II](http://www.iseesystems.com/) or [Vensim](http://www.vensim.com/). This one is a toy.

The program relies on some fairly recent additions to the HTML markup language. In my casual tests I have found that it works well in recent releases of Google Chrome, Opera and Safari; it also runs in Firefox, though more grudgingly. As far as I know, even the latest versions of Internet Explorer do not support all the features needed.

The controls for the model include four "sliders." Two of them allow for adjustments in the total duration and time resolution of the model. A third slider determines the initial quantity of nonrenewable resources, which has a major impact on the fate of the simulated world. The measure of resources displayed in the graph is the fraction remaining, so the curve will always begin at the maximum point of the *y* axis; but changing the setting of the resources slider alters the rate of depletion. The final slider adjusts the proportion of industrial output diverted away from investment and into consumption. Small changes in this parameter can have dramatic—and perhaps counterintuitive—effects.

I've described a few more details on the implementation of the model in a blog post: [World3, the public beta](http://bit-player.org/2012/world3-the-public-beta).

Brian Hayes

## [Try it!](http://bit-player.org/extras/limits/ltg.html)
