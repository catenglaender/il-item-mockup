# Proposal: Optimize Information Architecture for meta-data on UI components and their views

We propose implementing more general rules and best-practices for the Information Architecture of meta-data properties displayed on UI components, as well as the views that they are presented in.

A calculated and contextual Information Architecture will assist users and administrators when they work with even large magazine repositories without getting overwhelmed and distracted by data and actions irrelevant to their intent.

This project and our research focused on meta-data properties on repository objects specifically, but many points directly apply to content structure and object hierachy in general.

## What is Information Architecture?

Information Architecture describes how data is organized across multiple pages and objects of an app.

Good Information Architecture guides a user through layers, branches or funnels (with varying information density) to the content or action they intend to find. Relevant data is provided when and where it is expected, while data irrelevant to the current user intent is minimized.

While it should heavily influence the interface design of pages and UI components, it focuses purely on semantic grouping, hierachies and the current context of data.

## Why revise the Information Architecture of meta-data?

As we [transition the Legacy Container Object to the UI Standard Listing Panel](https://docu.ilias.de/goto_docu_wiki_wpage_6409_1357.html) (and the UI item it contains) many requests came up to replicate all features of this legacy object especially with regards to the meta-data properties shown.

A feature request to [Streamline Object Properties](https://docu.ilias.de/goto_docu_wiki_wpage_7399_1357.html) already exists. It contains an extensive collection of meta-data that the Legacy Container Items will display when the conditions are met with little to no regard for the context or user intent.

There also is a proposal to create a [Catalogue Presentation for repository items](https://docu.ilias.de/goto_docu_wiki_wpage_6990_1357.html) that displays even more properties.

Feature requests like these demonstrate that there is a lot of activity and requirements around meta-data properties and their placement. However, many discussions often focus on single, specific use cases.

Therefore, we would like to propose general guidelines for the Information Architecture of such properties that can be applied as a starting point for organizing meta-data in many situations.

This guideline aims to make decisions about displaying meta-data easier for concept designers and developers. It provides a more focused and contextually sensitive experience for the users while browsing through a repositiory.

## Strategies to meet user intent

Because ILIAS offers many different user roles, dozens of different objects and a variety of vastly different possible actions, guessing the user intent at a given moment is challenging.

However, there are multiple ways to accomodate a user's wish to focus on specific data properties or operations. The following list goes from the strategy that requires the least knowledge about the user intent to the one that requires the most:

* Structured patterns: The user directs their attention to a section where they expect to consistently find the currently relevant data and actions.
* User adjusted views: The user sets filters and sorting according to their current intent leaving only (or mostly) the data they wish to work with.
* Curated views: Someone builds a view (or a sequence of views) choosing to include, exclude, deemphasize and highlight data to support the user by anticipating a single or a few selected intents and needs.

### Structured patterns

When there is no way to accommodate a specific user intent, properties and actions MUST at least be clearly grouped and segmented.

They MUST be placed consistently in an expected location. This often means that groups and elements SHOULDN'T switch location and appearance. 

Groups and their elements MAY switch location and appearance to gain priority when serving a user intent.

We SHOULD establish a default priority amongst these groups and their elements which SHOULD influence their order and visual formatting. If there are no specific user intents to inform this order, they SHOULD be ordered from most to least useful to the user type using this component or view the most.

The amount of properties SHOULD be as reduced as possible with rarely relevant information placed in deeper layers (e.g. an info or settings tab).

A view that meets a specific user intent MAY pull usually hidden information from inside an object to be displayed on the object.

We suggest the following categories to structure elements on an UI component

#### Quick identifiers

The quick identifier area MUST hold the pieces of information and properties that enable and benefit quick recognition. When a user knows what unique object they are loooking for (e.g. a specific course) this is what they need to decide to interact with it after just one quick glance. Usually, the most important quick identifier is the name of an object.

Recognition of an object MAY further be enhanced through selected properties that are the most relevant for this object and the current user intent e.g. a thumbnail, description, icon or tag. You SHOULDN'T add many properties in this very prominent area as each poorly used slot (like unrelated thumbnails, arbitrary tags) may waste a significant amount of space.

Depending on the context, such a property MAY be pulled from another category and given priority by displaying it in the quick identifier area instead of its usual location e.g. the time slot of a session object.

#### Important Content Properties

#### Personal Relationship

#### Analytical Properties

#### Community Relationship
