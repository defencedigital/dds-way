# Software development

## How to name software products
Read this guide when you need to name components for your software product, for example applications, software libraries, plugins or frameworks. Your users should understand what something does from its name.

### User needs
Users should to be able to infer a basic understanding of what a given thing does from its name.

### Your product name should be self-descriptive
Names should be self-descriptive – you should be able to infer a basic understanding of what something does from its name. 

Avoid naming things using puns, uncommon acronyms, version numbers, or with a brand. All of these make it difficult for others to understand what the thing does. Puns and acronyms (unless they’re very widely understood outside government, like API) probably won’t be understood by anyone coming to your thing later. Version numbers and brand names (including names of parts of government) are likely to change over time as the thing adapts to changing user needs and policies.

If your service is an instance of a well-known type of system (like an intranet or help desk), it is appropriate to include the name of the government body it’s associated with so people can understand the context it applies to. Where possible, avoid exposing that name to people (usually citizens or organisations outside government) who shouldn’t have to understand how government is structured to do what they’re trying to do.

Ensure you use the same name consistently whenever you’re referring to the same thing. For example, in most cases the name of an application’s git repository should match its hostname. Similarly, the team responsible for an application should probably be called something related to the application and its git repositories.
Make sure you use the same name consistently whenever you’re referring to the same product. 

### Other resources
The [GOV.UK Service Manual](https://www.gov.uk/service-manual) has good guidance for [naming services](https://www.gov.uk/service-manual/design/naming-your-service), a lot of which will also be relevant when naming applications or packages.

## Programming languages

We use a range of programming languages at DDS because we think using the right tool for the job gives us the best chance of building services that best meet users’ needs. This document does not apply to choosing ‘off the shelf’ software (open source or not).

We focus on using a small number of programming languages for core software development tasks.

This should make it easier for developers to:

- move around the organisation
- develop shared components
- improve their personal development
- master how they operate applications

### Frontend development

The GOV.UK Service Manual has information on [using client-side JavaScript](https://www.gov.uk/service-manual/technology/using-progressive-enhancement). 

### Backend development

Our core languages for backend development are:

- Python
- Go

We’ve chosen these languages because they are successfully used by teams at the moment, and we are confident in how to host and operate applications written in them. You should carry out new development in one of these languages.

#### Python
You should write new Python projects in Python 3. [Python 2 is end of life](https://www.python.org/doc/sunset-python-2/). Python 3 is now well-supported by application frameworks and libraries, and is commonly used in production.

#### Go
Go is an appropriate language for systems programming, like proxying, routing, and transforming HTTP requests. However you should only write these sorts of components if there is no alternative maintained open source tool available.

Go has a feature complete standard library, good concurrency primitives and is a memory safe language. These features make it a good choice for backend application which aggregate or transform APIs, or have performance requirements.

## Style Guides

### Code style guides
Developers read code much more often than they write it. These guidelines are intended to improve the readability of code and make it consistent across DDS projects.

A style guide is about consistency. Consistency with this style guide is important. Consistency within a project is more important. Consistency within one module or function is most important.

But most importantly: know when it’s ok to be inconsistent. Sometimes the style guide just does not apply. When in doubt, use your best judgement. Look at other examples and decide what looks best. And do not hesitate to ask if you’re unsure.

Some good reasons to ignore a particular guideline include:

- when applying the guideline would make the code less readable, even for someone who is used to reading code that follows this style guide
- to be consistent with surrounding code that also breaks it (maybe for historic reasons) – although this is also an opportunity to clean up the existing code
 - when the code in question is older than the introduction of the guideline and there is no reason to modify that code
- when the code needs to remain compatible with older versions that do not support the feature recommended by the style guide

## How to manage third party software dependencies
When you develop and operate a service, it’s important to keep any third party dependencies you use up-to-date. By doing this, you can avoid potential security vulnerabilities.

Any automated tools you use to manage third party dependencies should be compatible with DDS supported programming languages. The tools you use should neither slow down your development process nor disclose potential security vulnerabilities to the public.

You can read more about [managing software dependencies in the Service Manual](https://www.gov.uk/service-manual/technology/managing-software-dependencies), where you will find a list of common dependency management tools.

### Update dependencies frequently
Update your dependencies frequently rather than in ‘big bang’ batches. This works well with continuous delivery principles and makes sure the changes introduced are small and can be automatically tested.

There are tools which scan GitHub repositories and raise PRs when they find dependency updates. 

- [Dependabot](https://github.blog/2020-06-01-keep-all-your-packages-up-to-date-with-dependabot/) 

### Rebuild container base images
Like dependencies, container base images are also frequently updated. If you run containers as part of your service, you should regularly rebuild your images (and base images) to include the latest updates. Automate this process where possible.

### Specifying container image tags
The DDS Way container guidance contains advice on how to use container image tags to specify the exact container image version to use.

## Building accessible services

## Supporting different browsers
Test your service in [the browsers listed in the Service Manual](https://www.gov.uk/service-manual/technology/designing-for-different-browsers-and-devices).

## How to optimise frontend performance
You should focus on [frontend performance](https://www.gov.uk/service-manual/technology/how-to-test-frontend-performance) when developing your service’s website. This will improve the user experience of your service by making your website respond faster and work better on all devices.

## Documenting architecture decisions
You should record decisions that affect the architecture of your service, in order to preserve the context of your choices.

As agile projects age, it is sometimes hard to keep track of the reasoning behind the decisions made. This is especially true as new people join the projects when those involved in the early stages are no longer around.

It is important to preserve the reasoning so the current team can include it as context when making their own decisions about changes they need to make. For example, understanding whether a particular choice was made for the sake of expediency and can therefore be changed with little impact, or whether there were external reasons behind that decision that need to be factored in.

### How to document decisions
Architecture/Technical decisions should be stored in version control so there is a record of what was changed, who by, and when. Decisions that affect a specific application should be in that application’s code repository. You may also want to store larger-scale decisions in a central documentation repository.

A suggested format is the Architecture Decision Record, proposed by [Michael Nygard in a blog post](http://thinkrelevance.com/blog/2011/11/15/documenting-architecture-decisions) and since adopted widely. That post describes the format in full, but as a summary it consists of the following sections:

Title: A description of the decision (not the problem)

Status: eg Proposed, Accepted, Superseded

Context: The facts behind the need to make the decision

Decision: What the team has decided to do

Consequences Both positive and negative consequences of the decision

Example Architecture Decision Records across HM Government:

 - [GOV.UK RFCs](https://github.com/alphagov/govuk-rfcs)