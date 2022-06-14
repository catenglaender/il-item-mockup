# Proposal: Optimize Information Architecture for meta-data on UI components and their views

We propose implementing more general rules and best-practices for the Information Architecture of meta-data properties displayed on UI components as well as the views that they are presented in.

A calculated and contextual Information Architecture will assist users and administrators to work with even large magazine repositories without getting overwhelmed and distracted by data and actions irrelevant to their intent.

## What is Information Architecture?

Information Architecture describes how data is organized across multiple pages and objects of an app.

Good Information Architecture guides a user through layers, branches or funnels (with varying information density) to the content or action they intend to find. Relevant data is provided when and where it is expected while data irrelevant to the current user intent is minimized.

While it should heavily influence the interface design of pages and UI components, it focuses purely on semantic grouping, hierachies and context of data.

## Why revise the Information Architecture of meta-data?

As we [transition the Legacy Container Object to the UI Standard Listing Panel](https://docu.ilias.de/goto_docu_wiki_wpage_6409_1357.html) (and the UI item it contains) many requests came up to replicate all features of this legacy object especially with regards to the meta-data properties shown.

A feature request to [Streamline Object Properties](https://docu.ilias.de/goto_docu_wiki_wpage_7399_1357.html) already exists. It contains an extensive collection of meta-data that the Legacy Container Items will display when the conditions are met with little to no regard for the context or user intent.

There also is a proposal to create a [Catalogue Presentation for repository items](https://docu.ilias.de/goto_docu_wiki_wpage_6990_1357.html) that displays even more properties.

Feature requests like these demonstrate that there is a lot of activity and requirements around meta-data properties and their placement. However, many discussions often focus on single, specific use cases.

Therefore, we would like to propose general guidelines for the Information Architecture of such properties that can be applied as a starting point for organizing meta-data in many different use cases.

This guideline aims to make decisions about displaying meta-data easier for developers and provides a more focused and contextually sensitive experience for the users while browsing through a repositiory.

## Challenges

Because ILIAS offers many different user roles, dozens of different objects and a variety of vastly different possible actions, guessing a user's intent at a given moment while browsing the repository is challenging.

The following methods can be applied to have users focused on the data that matches their intent:

* Providing a pattern: The user directs their attention to a section where they expect to consistently find the currently relevant data
* Changing the view themselves: The user sets filters and sorting according to their current intent
* Curating a view for others: Someone builds a view choosing to include, exclude, highlight and deemphasize data to support the user with an anticipated intent

