# Firefox the "Privacy" browser

I have an interest in compiling my web browser from scratch to remove telemetry and other nasty goodies from the source altogether. Both Chromium and Firefox make web requests every time they're started and every time you visit a webpage.

Picking a web browser nowadays is less about picking which one is the best and more about picking which one is the lesser evil. Each new version removes long loved features and instead introduces unwanted changes. Each version also becomes harder and harder to build yourself.

My expectation from an Open Source Web Browser is that it doesn't collect any data from me whatsoever. No matter how anonymized it may be. Even the disabling of telemetry doesn't fully stop this from happening.

This post will focus primarily on Firefox as Chromium makes no claims to caring about your privacy whatsoever and it's well, Google.


## Table of Contents

<!-- vim-markdown-toc GFM -->

* [Telemetry](#telemetry)
    * [Organic Search](#organic-search)
    * [Firefox Health Report](#firefox-health-report)
    * ["optout" ping](#optout-ping)
    * [Environment ping](#environment-ping)
    * [Ad click measurement](#ad-click-measurement)
* [Sources](#sources)

<!-- vim-markdown-toc -->


## Telemetry

### Organic Search

Firefox sends the number of searches you make in the browser to Mozilla.

> Last year we launched the in-content search probe, which counts the number of queries Firefox users issue to our search partners. ...

Source: [\[0\]](#sources)

### Firefox Health Report

FHR is a Firefox feature which collects a series of technical indicators which are sent to Mozilla "periodically".

> ... For example, FHR sends data to Mozilla on things like: operating system, PC/Mac, number of processors, Firefox version, the number and type of add-ons. ...

Source: [\[1\]](#sources)

### "optout" ping

Firefox sends data to Mozilla when you disable Firefox Health Report.

> This ping is generated when a user turns off FHR upload from the Preferences panel, changing the related datareporting.healthreport.uploadEnabled preference.

Source: [\[2\]](#sources)


### Environment ping

Firefox periodically sends a large amount of data about your environment to Mozilla. This includes and is not limited to the following information.

- All available OS locales.
- Your search engine.
- Your `prefs.js` settings.
    - For some privacy-sensitive preferences a `<user-set>` value is given.
- Your devices specifications.
    - This includes data like CPU, GPU, Memory, Cores, Device model, Operating System name, Kernel version, Model of HDD where Firefox is installed, Display Resolution, **Currently enabled Addons** and a lot lot more.

I would recommend reading through what kind of data is sent in the link below. I can't cover it all in this post and it's far too long to embed here.

Source: [\[3\]](#sources)


### Ad click measurement

Firefox will (*The source is over 6 months old so this may have landed.*) track the number of times you click on an advertisement on a search page.

> We also plan to count the number of times a search page displays ads and the number of times users click ads. These will be counts by user. Mozilla will not know the content of the search nor the content of the ads. This helps us both forecast Mozilla revenue and also understand the impact of ad blocking on the larger web ecosystem.

Source: [\[0\]](#sources)

## Sources

- \[0\] <https://blog.mozilla.org/data/2018/08/20/effectively-measuring-search-in-firefox/>
- \[1\] <https://blog.mozilla.org/metrics/fhr-faq/>
- \[2\] <https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/telemetry/data/optout-ping.html>
- \[3\] <https://firefox-source-docs.mozilla.org/toolkit/components/telemetry/telemetry/data/environment.html>
