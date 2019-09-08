# Broader Feedback Blog Post

## Background
It is widely accepted that the Javascript community now has a sustainability issue. The number of package
dependencies within the ecosystem is large. Many important packages are struggling with support issues. It 
is recognized that events in the live's of many maintainers can lead to important packages going without 
the necessary support they need.

The [package maintenance team](https://github.com/nodejs/package-maintenance) has been formed to address these issues. 
The team meet bi-weekly as one of the many Node.js committees with meetings recorded on 
[you tube](https://www.youtube.com/playlist?list=PLfMzBWSH11xYuROYr6Z9TpS0Wb9lRIldn). 
The committee falls under the supervision of the [OpenJS Foundation](https://openjsf.org/).

This group seeks to provide a framework to offer support to key packages within the ecosystem that may need
assistance with maintenance. The package maintenance group is offering guidelines covering many aspects of 
package support and publishing. These include but are not limited to:

- versioning
- licensing
- tooling (@eomm)
- support levels
- backing
- soliciting help
- publishing best practices

### For Package Maintainers

If you are maintaining a significant package and require assistance the package maintenance team may be able to
assist your project. 

### For Package Consumers
The package maintenance team seeks to provide clear guidelines for the level of support that a package can expect
to receive from its maintainers. The team are offering guidance upon licensing and funding so that consumers can have 
baseline expectations about the package. 

## Ongoing Discussions

- Support file format JSON or MD ?
- Support json in package.json or not
- external reference or within package

## Overview of Key Elements
Overview of key elements

The new support level information that we are recommending has 3 main dimensions:

* target: the platform versions that the package maintainer aims to support. 
* response: how quickly the maintainer chooses to, or is able to, respond to issues and
   contacts for that level of support
* backing: how the project is supported

The goal is to allow the package maintainers to clarify what versions  they plan to support, how quickly a consumer can 
expect to get help and both the existing support for the packages as well as ways that consumers can support the package.

The `target` field which covers which versions the package maintainers plan to support is not just the currently supported 
versions, but the model that can be used to predict which versions will be supported in the future.  In the context of 
Node.js, for example, `lts` would indicate that any given time the package maintainers intend to support the current LTS 
version of Node.js and that consumers won't be forced to update their Node.js version in order to get essential fixes.

The `response` field allows the package maintainer to communicate the levels of support that are available (or not), as 
well as contact information for being able to get or pay for that support.

The `backing` field allows the package maintainer to communicate the outside support/funding that the package is currently 
receiving, as well as the channels through which consumers can support the package.  

These fields allow package maintainer to clearly set expectations with consumers, reducing the friction/stress/self-imposed 
guilt when consumers make and express expectations that don't match those of the package maintainer.

For the consumer, these fields allow consumers to:
* better understand which versions of Node.js may be supported in the future
* the risk associated with packages that they consume
* understand how/if they can get help if they have problems
* options/channels for helping both reduce their own risk as well as how to be a `good consumer` by 
  helping to support packages which are important to them.



## Contentious Issues

With all discussions there will be areas of contention the following is a discussion of some of the thornier issues that 
have been discussed and resolved by the package maintenance group.

### Package Size
There are 2 schools of thought about what should go into a package the **minimalist** which basically is only the code 
which is run when using the package and the **all inclusive** school of thought which prefers to ship everything that could 
be useful in the package.

```
Note: Glenn Hinks 20190901
the names minimalist and all inclusive can be changed but 
we have to decide what to call the 2 schools
```

With these two schools there is not much of overlap. So the package maintenance team accepts both with the following reasoning.


#### Minimalist
It has been a practice not to include source code that is not run. Things such as tests or with transpiled code only the 
distribution folder containing the result of the transpilation is included. | The package size should be as small as possible 
and installation time fast. 
#### All inclusive
All source code, tests and configuration files should be included in the package. | Github repositories are not imutable 
whereas packages are. If everything that is in the repository is in the package offline debugging is possible. Future tooling 
such as **Tink** ( to be confirmed with a conversation with them) will make it possible to install selected parts of the package. |

## Case Study

The package maintenance team has been looking at suitable candidates for first case study. We have been engaging the
[express](https://github.com/expressjs/express) team. The [express](https://www.npmjs.com/package/express) package is a widely
used package for both APIs and static hosting. When the package maintenance team look at package it is not just the top of the
tree that concerns us. It is all of the dependencies that are depended upon that make up the entire collection of 
packages that go into making that one package work. For express there are many dependencies. If any of these dependencies
are in jeopardy then maybe so is the main package. 

It is understood that mature packages can be difficult for a newcomer to enter into. The package maintenance team have
been in discussion with the express team to see how newcomers can assist without being overwhelmed or causing unintentional
harm.

There are ways that help can be given without jumping straight into complex problems. There has been a request to help 
**triage** new incoming issues. Often what the maintainers need is help with the ofter **less glamorous** work so that 
they can be freed to work on tricky bugs.

This can simply be responding to issues and making sure that they can be reproduced. That a suitable example of the issue
is pushed to a repository so that it may be reproduced. In this first case study the package maintenance team is learning
too and we will be morphing as we learn.


## Call to action
Within the community as a whole we have now recognized that the package ecosystem has 
reached a level of maturity that requires guidelines. Whether a maintainer can no longer 
commit to support an essential package or if the maintainers can no longer commit to 
supporting older versions or engines for a package. 

We need an agreement that serves both the maintainers and the consumers of packages. The
agreements may cover [financial commitments](https://blog.npmjs.org/post/187382017885/supporting-open-source-maintainers)
or may be a commitment to follow the guidelines presented by the [package maintenance team](https://github.com/nodejs/package-maintenance).

The package maintenance team is offering a place for maintainers that provides guidelines and assistance
for the maintenance of their package. It is also a place for consumers who wish to support widely used 
packages that need some help a bit of support. 

We would welcome feedback from developers who wish to offer support and from package maintainers who wish 
to get some assistance with their packages. 

Please give us feedback at 

- name@address.com
- github.com/nodejs/package-maintenance/...

Please tell us if you are interested in 

- general enquiries
- licensing 
- support levels
- dependencies upon unmaintained but critical packages
- wish to notify us of important ghosted packages
- joining the package maintenance team
- ideas for the package maintenance team
