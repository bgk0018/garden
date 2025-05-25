---
{"dg-publish":true,"permalink":"/references/articles/web-clipper-can-extract-the-transcript-from-a-you-tube-video-then-run-it-through-interpreter-to-summarize-the-key-points-r-obsidian-md/","title":"Web Clipper can extract the transcript from a YouTube video then run it through Interpreter to summarize the key points : r/ObsidianMD","tags":["📰"],"created":"2025-05-12T22:56:55.118-05:00","updated":"2025-01-09T15:03:58.000-06:00"}
---

# Web Clipper can extract the transcript from a YouTube video then run it through Interpreter to summarize the key points : r/ObsidianMD

>[!summary]- Description
> 

## Concepts
| Name | Weight |
| ---- | ------ |

{ .block-language-dataview}

## Content

[![u/kepano avatar](https://styles.redditmedia.com/t5_1xobzo/styles/profileIcon_ub8lrjjcsr981.jpeg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=de2e5a82b87253c1cd94e515de29e6ca690c7ed6)](https://www.reddit.com/user/kepano/)

Any content that you can extract you can pass to [Interpreter](https://help.obsidian.md/web-clipper/interpreter), e.g. highlights, or any page content you want — and run templates based on URL patterns.

Here's the Interpreter context I used:

```
{{description}}

{{selectorHtml:ytd-engagement-panel-section-list-renderer[visibility$=\"EXPANDED\"] #segments-container|strip_tags:"h2,ytd-transcript-segment-renderer"|replace:"ytd-transcript-segment-renderer":"li"|markdown}}
```

For this to work, I need to manually open the transcribe pane right ?

[![u/kepano avatar](https://styles.redditmedia.com/t5_1xobzo/styles/profileIcon_ub8lrjjcsr981.jpeg?width=64&height=64&frame=1&auto=webp&crop=64:64,smart&s=de2e5a82b87253c1cd94e515de29e6ca690c7ed6)](https://www.reddit.com/user/kepano/)

Yes, Web Clipper can only access data that is available in the page

Thanks seems to work well!

[More replies](https://www.reddit.com/r/ObsidianMD/comments/1hbejjo/comment/m1fwi0x/) [More replies](https://www.reddit.com/r/ObsidianMD/comments/1hbejjo/comment/m1ftmh1/) [More replies](https://www.reddit.com/r/ObsidianMD/comments/1hbejjo/comment/m1fnrcv/)

[![u/wasansn avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_0.png)](https://www.reddit.com/user/wasansn/)

[![u/Manifestor64 avatar](https://www.redditstatic.com/avatars/defaults/v2/avatar_default_7.png)](https://www.reddit.com/user/Manifestor64/)

Proud to support excellent software. Keep up the good work!