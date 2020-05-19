+++
title = "GSoCpedia: Chapter One"
description = ""
type = ["blogs","blog"]
tags = [
    "Google Summer of Code",
    "WebdriverIO",
]
date = "2020-05-17"
categories = [
    "Google Summer of Code",
    "WebdriverIO",
]
series = ["Google Summer of Code"]
[ author ]
  name = "Vidhi Mody"
+++

> *“The mission of the Wikimedia Foundation is to empower and engage people around the world to collect and develop educational content under a free license or in the public domain, and to disseminate it effectively and globally."*

I am pleased to share that I have been [accepted](https://summerofcode.withgoogle.com/projects/#5417756675014656) into [Google Summer of Code 2020](https://summerofcode.withgoogle.com/) under [Wikimedia Foundation](https://wikimediafoundation.org/)! 

I believe that Open source projects are a great way of developing quality products by working together with other developers. I have always wanted to contribute to projects that I myself use to give back to the Community. 

Back in my school days, I remember using Wikipedia extensively for assignments and projects. Now to be working for Wikimedia feels like such a privilege. 

## Getting started

The project I will be working on is [Upgrade WebdriverIO to the latest version for all repositories](https://phabricator.wikimedia.org/T247844). My Google Summer of Code Proposal can be found [here](https://phabricator.wikimedia.org/T248868). My project is concerned mainly with the [Selenium Tests](https://www.mediawiki.org/wiki/Selenium). I will be following a breadth-first approach of first [upgrading all the repositories to v5](https://phabricator.wikimedia.org/T234314) and then [upgrading them to v6](https://phabricator.wikimedia.org/T247254). 

#### Week 1 (4th-10th May)
**Highlights:**
> - Accepted Projects announced!
> {{<center src="/img/accepted_projects.jpeg" alt="Accepted Projects">}}
> - Learnt more about the community.
> - Co-ordinated with my mentor and fixed meetings for the coming week.
> - The week ended with the Wikimedia Welcome Party. It was great meeting and interacting with the community and fellow students. I also learnt that I share similar interests with a few of them. ( *How awesome is that?* :v:)
> {{<center src="/img/welcome_party.jpeg" alt="Wikimedia Welcome Party">}}

#### Week 2 (11th-18th May)
I had daily meetings with my mentor [Željko Filipin](https://wikimediafoundation.org/profile/zeljko-filipin/). These meetings set a direction, a route which helped me learn more about my organization's structure, practices and work flow. My mentor showed me what skills and coding practices I needed to familiarize myself with which would lead my project to the best possible destination.

**Highlights:**
> - Read the [Technical contributor onboarding](https://phabricator.wikimedia.org/T250830) and completed the micro tasks mentioned.
> - Went through the [Code Review Developer Guide](https://google.github.io/eng-practices/review/) for a better understanding and making the code review process faster and convinient for the reviewers.
> - I read the [CL Author's Guide](https://google.github.io/eng-practices/review/developer/). My learnings can be summarized as follows: 
>   1. The first line should be a short, focused, and to the point summary of what is being done by the CL.
>   2. The rest should be an informative description of the problem and the approach followed. \
:pushpin: *Note: Any shortcomings to the approach, should also be mentioned.*
>   3. Background information such as bug numbers, benchmark results, and links to design documents (if relevant) should be included.
> - Learnt that CLs should be as small as possible. Additionally, read about this [here](https://google.github.io/eng-practices/review/developer/small-cls.html).
> - Gained knowledge on the [continuous integration](https://www.mediawiki.org/wiki/Continuous_integration) infrastructure. CI is managed by the [Release Engineering Team](https://wikimediafoundation.org/role/staff-contractors/) of MediaWiki. The applications used are:
>   1. [Gerrit](https://gerrit.wikimedia.org/r/#/q/status:open) (code review)
>   2. [Jenkins](https://integration.wikimedia.org/ci/)
>   3. [Zuul status](https://integration.wikimedia.org/zuul/) (Gerrit/Jenkins gateway)
> - Started implemenation on the [ContentTranslation](https://phabricator.wikimedia.org/T252521) repository.
> - Sometimes the most minimal change comes by making no [change](https://gerrit.wikimedia.org/r/#/c/mediawiki/extensions/ContentTranslation/+/596488/) at all!
> - Started implemenation on the [WikibaseCirrusSearch](https://phabricator.wikimedia.org/T252885) repository.
> - Last meeting of the week ended with a smile! :smiley::purple_heart:
> {{<center src="/img/gsoc_meeting.png" alt="Daily Meeting">}}

In the coming week, I might have a coding session with my mentor where I can learn more about his coding process. I'm really looking forward to it! To an amazing week coming up :beers:!
