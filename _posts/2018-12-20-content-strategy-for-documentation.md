---
title: "A content strategy to manage web services documentation"
layout: post
categories: ["Content design", "Content strategy", "Process"]
tags: ["Content design", "Content strategy", "Documentation", "Technical writing", "Reflective writing", "ISTCCPD", "University of Warwick"]
---

In late 2017 I was asked to write a strategy on how to manage and produce support documentation for the University of Warwick's web publishing team, which develops web and mobile applications in-house.

The number of web applications had increased since I joined Warwick in 2012. Help pages were in large banks of FAQs (frequently asked questions). Over time, they had become difficult to navigate and keep up to date. After a successful trial to incorporate documentation work with the development cycle for one application during 2016-17, there was a successful model to follow. The challenge was to identify the scope of documentation work and how to scale up the trial to a full service of 17 applications.

One year later, I cannot say that the strategy is fully realised and that the work is complete. Far from it, there's a long way to go. The new model is working well though, and more applications are now in the fold.

In this post, I break down how I:

- audited the scope and volume of the team's documentation
- researched the factors involved in creating high-quality documentation
- introduced best practice from the [Write the Docs](https://www.writethedocs.org/) community and GOV.UK's [Service Design Manual](https://www.gov.uk/service-manual)
- wrote the strategy

To respect confidentiality, I have omitted product names, made job titles generic and paraphrased the strategy's actual content.

## Why write a content strategy

It's quick to write a help article and post it online, right? ‘Write once, publish and forget’ is cheap and fast. It's a poor experience for customers though when ungoverned content grows out of date. When a product evolves, but the support documentation does not, the result is bloated legacy articles that are:

- inaccurate or obsolete
- difficult for customers to navigate and use
- difficult for writers to maintain

In an agile development environment where product features change frequently, this decay in documentation accelerates.

Each year or so you hit a bump. Without a content strategy for governance and maintenance – by that I mean [Kristina Halvorson's original definition](https://www.braintraffic.com/blog/what-is-content-strategy) of the discipline, not the term co-opted by content marketers – you generate [content debt](https://18f.gsa.gov/2016/05/19/content-debt-what-it-is-where-to-find-it-and-how-to-prevent-it-in-the-first-place/).

Resolving the problem with a content audit and rewrite, for example, is expensive. It's labour intensive to review legacy documentation, decide what to delete, what to rewrite, then do the actual writing. Also, there's an opportunity cost. The review diverts writers from current or new products.

Publishing quality documentation to help people use web applications is a significant investment. While writing may be the most visible element (the published page), accurate and timely documentation tailored to an audience is a collaborative effort.

It relies on:

- a culture of user-centred design and continuous improvement
- a culture that values documentation
- a commitment to making design, development and support information open and findable
- [technical acuity](https://idratherbewriting.com/2018/10/24/technical-aptitude/) of non-programmers to learn, contextualise and explain how to use a product
- dependable, efficient and appropriate publishing tools

These require investment in leadership, skills and infrastructure, which all have a cost. If you intend to help people to use your products through quality documentation, you may as well plan how to do that rather than leaving it to chance.

## Benefits and outcomes

I started the strategy with a statement of intent:

> For each service, we will produce and maintain support documentation that is: accurate; relevant; timely; appropriate to the audience; concise; accessible; and usable.

Next, I outlined the benefits beyond providing a good user experience. These are the benefits that can potentially save money. The benefits include:

- reducing the number of support calls
- increasing capacity to refer customers to accurate, high-quality information
- increasing capacity in the support team to reference information when responding to calls
- making the workload to maintain documentation sustainable
- reducing dependency on individuals and their availability
- removing the need for periodic labour-intensive jobs to revise out-of-date documentation

## Discovery part 1: scope and volume

Like a quantitative content audit, I started by identifying all the supported products, what documentation existed for each product and the number of help pages. The documentation included user guides, manuals and embedded help for user interfaces. To keep the scope sensible and to prioritise, I limited the research to user-facing documentation (material for students, staff and the public).

I wanted to get a realistic sense of how often product features changed. The 2016-17 academic year _felt_ busy, mainly due to launching a redesigned coursework management system and upgrading the University's CMS user interface, but I wanted to check anecdotes against data.

I reviewed historical data in [Jira](https://www.atlassian.com/software/jira), the team's platform for development, for the supported products for a full academic year. Between October 2016 and September 2017 there were 133 version releases with an average of 11 version releases per month.

An interesting fact from this analysis was that 80% of all bug fixes, improvements and feature changes were for two of the 17 supported products. One of these products was part of the trial for the new documentation model, a product that dominated the collaborative effort across development, support and documentation. Knowing that most of the other products changed less often, I felt more confident about scaling up the documentation model to the remaining products.

Writing this post one year later, my confidence was premature. Scaling has turned out to be the most challenging part of implementing the strategy!

## Discovery part 2: mapping information flow

Technical writers or content designers need writing skills. That's a given. What job descriptions do not always reflect or value appropriately, in my experience, is the ability to seek information from different sources, to make sense of it all and to keep track methodically.

Writing support documentation is a messy environment. Sometimes there are no definitive answers. There may not be an agreed, coherent picture for a writer to start work. Requirements and features change.

Writers need to be able to:

- hunt down information, verify statements and cross-check information sources
- have enough technical acuity to learn how to use a product for themselves
- connect with the right people to confirm their understanding
- navigate internal politics
- seek constructive criticism

It's crucial for a documentation writer to connect to sources of information for the requirements and future development. Without it, they risk not having enough domain knowledge to write about a product in the user's context or add value from a position of expertise. I'm lucky at Warwick in that I work in the same team as those who design, build and support the products. I sympathise with writers located in teams far from where product design decisions happen.

For the strategy, I mapped the flow of product information through the web publishing service from its origins, through UX design, development, testing and launch.

![Information flow diagram](/assets/2018/12/information-flow-generic.png)

Writing down each source helped me to identify situations where:

- I was already involved
- I was not involved but should take part
- I was not involved and needed to connect with the relevant person at that level

Seeing the process visually helped to identify where and when to incorporate the documentation tasks. The diagram shows where the information for support documentation work comes from, how it's captured in Jira and how support material gets published.

The flow should ensure that:

- relevant information is available to developers and documentation writers
- documentation creators can collaborate with developers in a shared environment (Jira)
- changes to existing functionality have an accompanying documentation task
- user interface copy and documentation are consistent in content and tone
- documentation reviews do not delay releases unnecessarily
- the quality of information for customers improves continuously

## Discovery part 3: identifying documentation job types

To get a sense of the different natures of content jobs for the service's documentation, I plotted job types against volume in a typical academic year and the complexity of writing.

![Documentation job types](/assets/2018/12/job-types-genericised.png)

By following the strategy, my intentions were for:

- ‘Audit and refresh out of date or legacy content’ to move to the ‘Low volume’ side
- ‘Maintain documentation in line with version releases’ to become the norm for all supported products

As a result, there would be more capacity to put effort into creating high-quality, original material for new products or significant updates. Killing off those bi-annual, labour-intensive projects (paying down the content debt) would release time to focus elsewhere. It also boosts writers’ morale!

## Content purpose

In this new strategy, every item of content must have a purpose. It must pass the following tests:

- does the content enable the user to complete their task?
- does the content solve a problem?
- does the content increase the user's understanding of the task and its context?

Otherwise, there's no need to write new content, which needs maintaining, or to keep existing content that does not serve a purpose. Stop, delete, move along.

## Context and value

The documentation needs to do more than describe _how something works_. It should provide context and add value for users by:

- explaining information that users may not discern on their own
- describing the effects of one action beyond what the user may intend
- highlighting issues for consideration such as prerequisites
- offering tips on how to complete a task efficiently when there is more than one way to do it

## Content depth

Next, I wanted to define the level of detail required for each product's documentation. For example, manuals document every feature. User guides help people to complete a task. This work still needs doing, but the aim is to:

- commit resources on creating documentation that serves a purpose  
- reduce time spent on documentation that is of low value to customers or the team

## Content types

Much of the legacy documentation was in the form of FAQs. While some content is a short answer to a common question, it's rare that an [FAQ is the appropriate content type](https://alistapart.com/article/infrequently-asked-questions-of-faqs#section3). In most cases, the FAQ format causes problems and frustration for customers.

In 2013 Sarah Richards blogged about [why the UK Government Digital Service don’t have FAQs](https://gds.blog.gov.uk/2013/07/25/faqs-why-we-dont-have-them/). Lisa Wright wrote _No More FAQs_ for [A List Apart](https://alistapart.com/article/no-more-faqs-create-purposeful-information-for-a-more-effective-user-experi) in 2018, in which she advocated for purposeful information instead. Gerry McGovern called FAQs the &lsquo;[dinosaurs of web navigation](http://gerrymcgovern.com/faqs-are-the-dinosaurs-of-web-navigation/)&rsquo;, and renowned usability expert Jakob Nielsen included FAQs in [top 10 web design mistakes of 2002](https://www.nngroup.com/articles/top-ten-web-design-mistakes-of-2002/).

For me, the problems with Warwick's FAQs were:

- increasing difficulty for customers to find information
- pages that documented features without context, rather than focusing on a task
- a maintenance overhead to periodically review and update large banks of FAQs

In the strategy, I defined the content types to use for help documentation. Each type accounts for the audience's needs and technical skill level. For example:

- **UI help text** - ‘show don’t tell’ with an example in microcopy instead of a detailed explanation
- **Help article** - a single page of step-by-step instructions that helps the user to complete a task or solve a problem
- **User guide** - a linear sequence of pages to walk the reader through a process

## Roles

I mapped the roles necessary for producing documentation against the activities involved. The aim was to get clarity on who is responsible for activities. The role map could potentially help define skills for any future recruitment. (This table does not list all the activities and I've made the role titles generic.)

| Activity                                                                                                     | Product manager | Lead developer | Developer | Senior writer | Writer |
|--------------------------------------------------------------------------------------------------------------|-----------------|----------------|-----------|-------------|--------|
| Manage the service. Communicate changes and developments to developers and writers.                          | x               |                |           |             |        |
| High-level technical knowledge of the product.                                                               |                 | x              | x         |             |        |
| Medium-level technical knowledge of the product.                                                             | x               |                |           | x           | x      |
| Scope the documentation requirements.                                                                        | x               |                |           | x           |        |
| Design and maintain the information architecture for documentation.                                          |                 |                |           | x           |        |
| Create a significant volume of new documentation.                                                                 |                 |                |           | x           |        |
| Write new pages or update existing pages to be technically accurate and follow the house style, as assigned. |                 |                |           | x           | x      |
| Answer technical queries and take part in content critiques.                                                      |         x       | x              | x         | x           | x      |

## Processes

This section makes the following activities concrete and specifies the role responsible for each activity:

- what to do for a product version release
- what to do each week and month to maintain the documentation
- what to do for large projects such as documenting a new product from scratch

## Knowledge transfer and reference materials

This section listed Warwick's internal guides for documentation writers:

- a glossary of agreed terms
- guidance on how to write for the web
- training notes on how to write a help article

Rather than recreate style guides from scratch, the team uses these external resources:

- [Microsoft Writing Style Guide](https://docs.microsoft.com/en-gb/style-guide/welcome/)
- [Google Developer Documentation Guide](https://developers.google.com/style/)
- [GOV.UK's ‘Writing for User Interfaces’](https://www.gov.uk/service-manual/design/writing-for-user-interfaces)
- [English Oxford Dictionary](https://en.oxforddictionaries.com/)

Microsoft's _Writing Style Guide_ is a great resource and it's comprehensive. It replaces the _Microsoft Manual of Style_, a 20-year-old print publication. While the _Google Developer Documentation Guide_ considers API documentation for a developer audience, it contains lots of examples on how to write for non-developer audiences.

The GDS team at GOV.UK have published their design thinking and references online for years. Their [Service Design Manual](https://www.gov.uk/service-manual), which _Writing for User Interfaces_ is part of, contains useful information for any organisation to produce their documentation in a modern, user-centred way.

## One year later

The biggest challenge I'm thinking about now is how to scale the successful documentation model to more products. Writing a strategy is one thing. Putting it into practice is another.

Another aspect not covered in the strategy is how to evaluate the documentation's quality or gaps through user research and feedback. Mechanisms do exist to capture feedback through the web publishing service's approach to continuous improvement, which tends to be feedback when someone gets stuck. It's unusual to hear about the times when someone used a help article successfully or where the gaps lie.

There's plenty more to do. After using the strategy for one year though, the documentation is in a much better position.
