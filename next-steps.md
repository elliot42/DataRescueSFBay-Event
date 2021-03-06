# Next Steps Track: Tech for Monitoring and Continued Access

Even though we're nowhere near done collecting data, events are pushing us to think about what we do next. We're already seeing changes to government websites, and we need to be able to:

1. [monitor websites](#monitoring-websites) (work with @titaniumbones in the [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli) repo)
1. [filter changes](#filtering-changes) (work with @titaniumbones in the [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli) repo)
1. [audit resiliency](#auditing-resiliency) (work with _@librlaurie (??) or @dcwalk (??)_ in _Google Docs??_)
1. [understand data](#understanding-data) (needs a leader, preferably someone w/ semantic analysis or similar bacground)
1. [~~disseminating~~](#disseminating) (moved to storytelling!)

## Monitoring Websites

[Page Freezer](http://www.pagefreezer.com) has generously donated use of their tracking service for the next four years. We are setting up a server which will provide a testbed for their API's and allow us to query changes to individual pages or domains. We need to familiarize ourselves with the API and write docs that allow organization members to quickly make sense of its most important features.

Current materials:
* Docs and issues are in [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli)

### Goal

To create tools that work with Page Freezer's API to show changes to individual pages or domains

### Deliverable

* Proof-of-concept code that queries the server and returns human-usable results in tabular form. This can be CSV, HTML, whatever.
* Documentation outlining the main challenges and next steps in this project.

### Priority
**High**, Time Sensitive


## Filtering Changes

The vast majority of web page changes are of limited interest to us, and so we need to write filters that allow us to prioritize changes. Our analysts are currently drowning in false positives. Here are some examples:

* A substantial percentage of pages on [climate.nasa.gov](http://climate.nasa.gov) include a `Latest Resources` box on the right-hand side of the main page. Every page that contains this box will be marked as a "changed page" by our version tracking software. The relevant change can be seen on `line 1305` of [this diff](https://gist.github.com/va-client/c25c6def28b760f25e3190b1e986d2e3/revisions#diff-8a777b7cd35d6141f393542135beb397R1306). A simple ad-hoc filter that discards changes from `<aside class='list_view_module'>` would cut out about [30%*](# "Made Up Number.") of our positives from `climate.nasa.gov`.
* Many domains update their "Last Updated" date at random. Again, cutting these out would help.
* Other examples?

Current materials:
* [versionista-outputter](https://github.com/edgi-govdata-archiving/versionista-outputter) implements similar goals for our current (deprecated) monitoring process
* [sample html pages](https://github.com/edgi-govdata-archiving/pagefreezer-cli/tree/master/archives) for testing filters are provided in the [pagefreezer-cli](https://github.com/edgi-govdata-archiving/pagefreezer-cli) repo

### Goal

To reduce the amount of noise in our website change results and reduce the length of time of our change review process

### Deliverable

* 2-3 example filters that can be applied to the queries [described above](#monitoring-websites) to improve results. Language and coding practices of the two projects should be compatible
* Documentation suggesting improvements/next steps

### Priority

**High**, Time Sensitive


## Auditing Resiliency

As we move into supporting the use and ongoing access to the data we have saved we are beginning to have questions about the

Current materials:
* [datarefugephilly/ckan](https://github.com/datarefugephilly/ckan)
* [datarefugephilly/ckanext-extrafields](https://github.com/datarefugephilly/ckanext-extrafields)
* [Overview Issue #27 on IPFS](https://github.com/edgi-govdata-archiving/overview/issues/27)

### Goal

To ensure that as we develop our tools to store data for future use we are creating secure, redundant, and resilient storage

### Deliverable

* Documentation with 5-10 suggested best practises as well as considerations and resources as we develop our tools
* Potential milestones for our projects to hit in the near and long term

### Priority

Medium, Less Time Sensitive


## ~~Disseminating~~

**This work has been moved to the "Storytelling" track!**

~~Our work is only relevant if people hear about it. How should we make our work public? What will it take to build public-facing tools to allow citizens to investigate the archive we have assembled?~~

### ~~Goal~~

~~To decide on the next milestones for outreach and engagement with archived materials~~

### ~~Deliverable~~

* ~~Strategy document for communications and citizen research~~

### ~~Priority~~

~~Medium, Less Time Sensitive~~

## Understanding Data

This is a very large set of data (10^5 pages already, hopefully 10^6 pages in the future). Most of our analysis team has limited experience extracting semantically relevant information from these kinds of archives. What meaningful information can we expect to find, and what tools will we need to find it?

### Goal

To have a preliminary set of approaches and tools identified for analyzing web page data

### Deliverable

* Brief report on appropriate statistical/digital humanities tools for this work.

### Priority

Low, Less Time Sensitive
