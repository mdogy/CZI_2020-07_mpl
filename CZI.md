## Progress Report

> Provide a short summary of progress towards the deliverables in your
> currently funded proposal (maximum of 250 words)

> 95 words

While hiring took longer than expected, since Elliott Sales de Andrade
started (mid-March) we have hit our target of a net reduction of open
PRs by 50/quarter, and are making progress on reducing the number of
open issues.  Our initial estimates of the effort per issue closed was
[this sentence needs to be completed]
to Several mid-sized high-impact projects (documentation, js
modernization, and semantic Axes layout) have been merged that would
not have happened without this support.  In addition to the above work
we have done 2 feature release and 5 bug-fix releases since January
2020.

We created a discourse to facilitate conversations with users and drafted new code and community contributor onboarding guidelines and (have seen an increase in new contributors?)

While building the initial prototype, our priority shifted from reviewing the architecture of other libraries to developing the theoretical underpinnings of the new architecture Subsequent iterations have tightly coupled the prototype implementation to the developing architecture to avoid drifting due to immediate technical needs. We prioritized structured 2D array like data to ensure we do not break existing functionality. 


## Proposal Purpose

> One sentence (maximum of 255 characters including spaces)

> 245 characters

​​To enable Matplotlib to continue as the core plotting library of the
Scientific Python Ecosystem, we will address the maintenance backlog
and begin Matplotlib's evolution to meet the community’s visualization
challenges for the next decade.


## Abstract/Proposal Summary
> A short summary of the application ​(maximum of 250 words)

> - keep up level of effort on maintenance
> - start to implement design work planned this year
> - engage with down-stream packages

> 191 words

​​Matplotlib is the foundational data visualization library for the
​​Scientific Python Ecosystem, used by over a million users, including
​​scientists in bio-medical imaging, microscopy, and genomics.  It has
​​been actively developed and maintained by a vibrant, primarily
​​volunteer community for the past 17 years.  Given the current scale,
​​scope, and importance of the project, it is critical that we continues
​​to support professional developers to maintain the project and
​​community.

With supported developers we have been able reduce our backlog of open
Issues and Pull Requests, a marked change from the previous year when
both were increasing.  We propose to dedicate three-quarters of a
developers time to maintenance and user support.  This work has the
direct effect of improving the library for our users, bit it also has
improves the experience of contributors and the community.

A core strength of Matplotlib is our large and vibrant community of
contributors, down stream library developers, and users.  We propose
committing the rest of the developer to maintaining and fostering this
community.

Building on the theoretical and design work we have done in the past
year we will continue to re-implement the core of Matplotlib using the
new architecture.  Simultaneously we will continue to unify and extend
the user facing API and collaborate with domain specific libraries to
build highly tuned plotting tools.  We propose committing a developer
year to this effort.

## Work Plan

> A description of the proposed work the applicants are requesting
> funding for, including resources the applicants will provide that
> are not part of the requested funding. For software development
> related work (e.g., engineering, product design, user research),
> specify how the work fits into the existing software project
> roadmap. For community outreach related activities (e.g., sprints,
> training), specify how these activities will be organized, the
> target audience, and expected outcomes (maximum of 750 words)

A core component of the proposed work is the continued maintenance of
the library. This is a very broad scope of work that includes every
thing from fixing critical bugs, reviewing Pull Requests, triaging and
addressing bug reports, tagging release, and keeping the continuous
integration services running.  While critical to keeping the project
healthy and individually small, it is difficult to accomplish them in
a timely manner with only volunteer effort.  These tasks are
frequently reactive, you can not plan for a critical bug to be found
or a dependency to change, time critical, and not always fun.  By
making sure these tasks are done we will improve the experience for
both new and existing contributors and improve the rate at which we
onboard new contributors to the project.  We propose to devote three
quarters of a developers time to handling these tasks.

In addition to the reactive work there are incremental improvements
that are bigger in scope that can easily be done with volunteer
effort.  These projects can range from fixing long standing rendering
artifacts, deep-dive documentation into the why of the API design,
improving performance, to new user facing features.  For example
these are projects at the scale of adding color-blind filters to all of
the user interfaces so users can preview their visualizations.  In addition
to the technical work of adding the filter and UI code we also need to
do research to make sure we are doing it correctly.  We propose devoting
a quarter of a developer to these small projects.

Building on what we have learned in the past year working on re-designing the
low-level architecture we will :

- Finish architecture development & start to implement in core library
- start to re-design user API in a way that can make the most of the
  improved internal structure


The most common visualizations in a domain need to be fluid for the
end-practitioners, with the "obvious" customization options exposed.
Much of the domain-specific specialization is carried in the
structure, semantics and assumptions of the data, and in the standard
visualizations of the domain.  These specializations can vary widely,
in contradictory ways, between domains.  Because no high-level API can
simultaneously satisfy all of the visualization needs, there will
always be a need for domain-specific visualization libraries.  We will
continue to work with down-stream libraries to make sure that we are
able to support them to support their users both in terms of
implementing data sources, artists, and user API.

- continue maintenance work
  - review work
  - bug triage
- improve new contributor on-boarding
- Finish architecture development & start to implement in core library
- start to re-design user API in a way that can make the most of the
  improved internal structure
- mid-sized new features
  - color blind filter
  - rendering accuracy improvements
  - performance

- work with down-stream libraries to use data sources

## Milestones and Deliverables

> List expected milestones and deliverables, and their expected
> timeline. Be specific and include (where possible) any goals for
> metrics the software project(s) are expected to reach upon
> completion of the grant (maximum of 500 words)

- Initial response to all issues / new PRs in < 3 days
- Resolve 90% of new issues / PRs within 1 month
- ​​Reduce backlog of issues by 50 / quarter
- ​​Reduce backlog of PRs by 50 / quarter

- initial implementation of data-source backed artists merged to core Matplotlib
- initial implementation of data-source backed artists in domain specific libraries
- design documentation about new user-facing API
- ??


## Landscape Analysis

> Briefly describe the other software tools (either proprietary or open
> source) that the audience for this proposal is primarily using. How
> do the software projects in this proposal compare to these other
> tools in terms of size of user base, usage, and maturity? ​How do
> existing tools and the project(s) in this proposal interact? (maximum
> of 250 words)

> 191 words


Matplotlib is the mostly widely used and de-facto standard
visualization library in Python (over 1M monthly users) and is a
mature library (17+ years old) with over 1,000 individual code
contributors.  In addition to being directly used by scientist, there
are many libraries and applications that use Matplotlib, including
scikit-learn, CellProfiler, scanpy, starfish, nipy, and sickit-image
(all of been funded by CZI), to provide domain-spcefiic plotting.  To
aid users in discovering these extensions we have recently been
assigned a Trove classifier on pypi [1].

Given the centrality of visualization to data analysis across all
domains no single tool is going to be suited to fit all needs.  There
are a range of tools, see https://pyviz.org/tools.html for a long but
not exhaustive list, not built on Matplotlib that target use cases
(such as client-side rendering in a web browser or high-performance
GPU accelerated rendering) that Matplotlib is not well suited for.  A
goal of our work is to increase the degree to which the tools can
interoperate letting users switch tools as needed to use the right
tool for the job.

[1] https://pypi.org/search/?q=&o=&c=Framework+%3A%3A+Matplotlib


## Diversity, Equity, and Inclusion (DEI) Statement

> Advancing DEI is a core value for CZI, and we are requesting
> information on your efforts in this area. Describe any efforts the
> software project(s) named in this proposal have undertaken to
> increase diversity, equity, and inclusion with respect to their
> contributors and audience. Please see examples from successful second
> cycle applications ​(maximum of 250 words)

The Matplotlib project is committed to being an open and welcoming
project.  It is critical that all contributors, independent of
experience level both in general and with the project, feel safe to
make mistakes, be wrong, and learn. We embody these values in our 
interactions on github, our community discussion forum (discourse) 
and in our social media. In our effort to be welcoming, we have also 
worked at being more explicit about how the project operates and our 
norms and values. To this end, we have put major effort into documenting 
our governance, defining leadership roles, and specificying expectations 
for new code and community contributors. We hope this explicitness will 
empower people to make more informed decisions about participating in open source. 
