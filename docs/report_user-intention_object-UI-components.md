# Proposal: Optimize Information Architecture for object properties on UI components

We propose implementing more general rules and best-practices for the Information Architecture of object properties displayed on UI components, as well as the views that they are presented in.

A calculated and contextual Information Architecture will assist users and administrators when they work with many objects in large repositories without getting overwhelmed and distracted by data and actions irrelevant to their intent.

This project and our research focused on properties displayed on repository objects specifically, but many points directly apply to content structure and object hierachy in general.

## What is Information Architecture?

Information Architecture describes how data is organized across multiple pages and objects of an app.

Good Information Architecture guides a user through layers, branches or funnels (with varying information density) to the content or action they intended to find. Relevant data is provided when and where it is expected, while data irrelevant to the current user intent is minimized.

While it should heavily influence the interface design of pages and UI components, it focuses purely on semantic grouping, hierachies and the current context of data.

## Why revise the Information Architecture of meta-data?

As we [transition the Legacy Container Object to the UI Standard Listing Panel](https://docu.ilias.de/goto_docu_wiki_wpage_6409_1357.html) (and the UI item it contains) many requests came up to replicate all features of this legacy object especially with regards to the data shown.

A feature request to [Streamline Object Properties](https://docu.ilias.de/goto_docu_wiki_wpage_7399_1357.html) already exists. It contains an extensive collection of properties that the Legacy Container Items will display when the conditions are met with little to no regard for the context or user intent.

There also is a proposal to create a [Catalogue Presentation for repository items](https://docu.ilias.de/goto_docu_wiki_wpage_6990_1357.html) that displays even more properties.

Feature requests like these demonstrate that there is a lot of activity and requirements around object properties and their placement. However, many discussions often focus on single, specific use cases.

Therefore, we would like to propose general guidelines for the Information Architecture of such properties that can be applied as a starting point for organizing object properties in many situations.

This guideline aims to make decisions about displaying object properties easier for concept designers and developers. It provides a more focused and contextually sensitive experience for the users while browsing through a repositiory.

## User intent should guide data presentation

When a user interacts with an interface, they approach it with expectations and methods they learned from previous experiences. This is often referred to as the user's mental model. The user intent describes the goal, the mental model describes how they think they will get there.

For example, if the user intent is to pick a course from a category that interests them, they apply the mental model of navigation they know from a file manager. They expect that they can distinguish categories from other objects and that clicking on the category's title brings them one level deeper in the hierachy.

Ideally, the mental model of the user aligns with the interface model provided. Issues arise when these models clash e.g. an important button or information cannot be found when and how the user expects it.

Because ILIAS offers many different user roles, dozens of different object types and a variety of vastly different possible actions, guessing the current user intent and matching their mental model at a given moment can be challenging.

Many potentially possible options and properties need to be displayed at once to support many possible mental models at once. This often leads to screens and objects filled with so many properties and options that finding a specific one might feel cumbersome.

However, we did identify 3 general types of models in ILIAS, where closely matching a user's mental model while accordingly controlling the selection of information shown seems very feasible:

* Making a quick choice
* Comparing before choosing
* Managing multiple objects

### Making a quick choice

In this case, a user intent is so focused that they only want to **quickly make the one clear choice for one expected object** by glancing at one or two of its properties. The action shown as the most prominent is the reason why the user came to this view.

A good example is the contact or member gallery in ILIAS. If a user sets out with the intent to get in touch with a specific person they already know, then a name and profile picture of that person is all they need to make the choice to initiate contact.

When a user expects to be making such a quick choice, a number of irrelevant properties and a hard to find main action are especially frustrating. A visual priority given to the element that allows the quickest identification is very welcomed.

The reduction of properties can also prove problematic e.g. if the wanted user in the member gallery chose a pseudonym and didn't add a profile picture.


### Comparing before choosing

Sometimes a user intent requires them to compare a selection of relevant properties of multiple objects before making a choice between them. The properties seen as relevant help the user to make the decision for the action presented as the most prominent.

For example, a user might be offered a choice of sessions to attend in the ILIAS repository. Besides the session title, they will most likely be interested in multiple other properties like the time and date, the description, the location and the remaining available seats before attending.

When a user expects to compare objects, they do not like to find the relevant details only displayed in a subsequent view. Out of the array of potentially most relevant properties some can become more important than others (e.g. if there are no more seats available for a session).

### Managing multiple objects

It's mostly administrators or users with a special role who want to **collect, compare and modify many objects and their properties for sorting and bulk processing actions.**

The user management table in ILIAS supports many filtering, sorting and view options, so the administrator can choose dynamically which relevant properties and objects to display and what (bulk) actions to perform.

The quality of this user experience is mostly based on how intuitive and quick the provided sorting and filter systems are. When working with such an intent, a pre-filtered and visually weighted presentation is often seen as an unnecessary obstacle.

## UI components to match user intent

We already have a range of different UI components that each lean towards different user intents:

A UI Card with an apropriately selected image offers the simplicity and quick identification that a user wishing to make a quick choice would like to see.

The legacy repository object, the UI item and the UI Presentation Table offer room for some selected properties and bits of content to guide an informed decision when a user prefers to explore and compare.

The legacy table and the UI Data Table are meant for dealing with large amount of data and offer the functions for dynamic filtering and processing that a person managing multiple objects requires.

However, there are instances where those UI components are not embracing the user intent that they are best at, which sometimes forces the mental model to shift. For example, some repository items can end up displaying so many properties that finding the relevant bit to compare becomes time consuming. In this case one might wish for a table view with customizable property columns instead.

With the concepts presented here we would like to make identifying mismatches like this easier and encourage further discussions and explorations of how the ILIAS UI can lead the user with minimal friction and distraction from their current intent.

## Strategies to meet user intent

There are multiple ways to accomodate a user's wish to focus on specific data properties or operations. The following list goes from the strategy that requires the least knowledge about the user intent to the one that requires the most:

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
