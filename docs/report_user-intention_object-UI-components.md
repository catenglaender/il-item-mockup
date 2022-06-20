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

For example, if the user intent is to pick a course from a category that interests them, they might apply the mental model of navigation they know from a file manager: They expect that they can distinguish categories from other objects and that clicking on the category's title brings them one level deeper in the hierachy.

Ideally, the mental model of the user aligns with the interface model provided. Issues arise when these models clash e.g. an important button or information cannot be found when and how the user expects it.

Because ILIAS offers many different user roles, dozens of different object types and a variety of vastly different possible actions, guessing the current user intent and matching their mental model at a given moment can be challenging.

Therefore many places in ILIAS default to supporting many possible mental models at once. This often leads to screens and objects filled with so many properties and options that finding a specific one might feel cumbersome and overwhelming especially to new users.

Consequently, we explored if we can meet the user intent a bit more closely, ideally reducing the amount of properties shown without accidentally cutting important information.

We identified 3 general types of models, where closely matching a user's mental model while accordingly controlling the selection of information shown seems feasible in ILIAS:

* Making a quick choice
* Comparing before choosing
* Managing multiple objects

### Making a quick choice

In this case, a user intent is so focused that they only want to **quickly make the one clear choice for one expected object** by glancing at one or two of its properties. The item action shown as the most prominent is usually the reason why the user came to this view.

A good example is the contact or member gallery in ILIAS. If a user sets out with the intent to get in touch with a specific person they already know, then a name and profile picture of that person is all they need to make the choice to initiate contact.

When a user expects to be making such a quick choice, a number of irrelevant properties and a hard to find main action are especially frustrating. A visual priority given to the element that allows the quickest identification is very welcomed.

However, the reduction of properties can also prove problematic e.g. if the wanted user in the member gallery isn't identifiable just by the name or profile picture.


### Comparing before choosing

Sometimes a user wants to compare a selection of relevant properties of multiple objects before making a choice between them. The properties seen as relevant help the user to make the decision for the action presented as the most prominent.

For example, a user might be offered a choice of sessions to attend in the ILIAS repository. Besides the session title, they will most likely be interested in multiple other properties like the time and date, the description, the location and the remaining available seats before attending. Ideally, irrelevant information (like the creation date of the session) wouldn't be shown at all.

When a user expects to compare objects, they do not like to find the relevant details only displayed in a subsequent view. Out of the array of potentially most relevant properties some can become more important than others (e.g. if there are no more seats available for a session, all other properties are no longer important).

### Managing multiple objects

It's mostly administrators or users with a special role who want to **collect, compare and modify many objects and their properties for sorting and bulk processing actions.**

The user management table in ILIAS supports many filtering, sorting and view options, so the administrator can choose dynamically which relevant properties to display and what (bulk) actions to perform.

The quality of this user experience is mostly based on how intuitive and quick the provided sorting, view controls and filter systems are. When working with such an intent, a pre-filtered and visually weighted presentation is often seen as an unnecessary obstacle.

## UI components to match user intent

We already have a range of different UI components that each lean towards different user intents:

A UI Card with an apropriately selected image offers the simplicity and quick identification that a user wishing to make a quick choice would like to see.

The legacy repository object, the UI item and the UI Presentation Table offer room for some selected properties and bits of content to guide an informed decision when a user prefers to explore and compare.

The legacy table and the UI Data Table are meant for dealing with large amount of data and offer the functions for dynamic filtering and processing that a person managing multiple objects requires.

However, there are instances where those UI components are not embracing the user intent that they are best at, which sometimes forces the mental model to shift. For example, some repository items can end up displaying so many properties that finding the relevant bit to compare becomes time consuming. In this case one might wish for a table view with customizable property columns instead or a carefully set up presentation table which hides cartain details when collapsed.

With the three distinct types of user intent presented here we would like to make identifying mismatches easier and encourage further discussions and explorations of how the ILIAS UI can lead the user with minimal friction and distraction.

## General strategies to meet user intent

There are multiple ways to accomodate a user's wish to focus on specific data properties or operations that seem especially promising for further improving the UX in ILIAS. The following list goes from the strategy that requires the least knowledge about the user intent to the one that requires the most:

* Structured patterns: The user directs their attention to a section where they expect to consistently find the currently relevant data and actions.
* User adjusted views: The user sets filters and sorting according to their current intent leaving only (or mostly) the data they wish to work with.
* Curated views: Someone builds a view (or a sequence of views) choosing to include, exclude, deemphasize and highlight data to support the user by anticipating a single or a few selected intents and needs.

### Structured patterns

When there is no way to build the current screen around a set of selected, specific user intents, we can still support the user by giving them a specific location to look for. When properties and actions are clearly grouped and segmented, the user learns where they find the information that currently is of interest. For example, all community interactions like star rating and comments could be in the bottom right right corner of an item, all organizational meta-data like file size and version number in the bottom left.

We therefore propose to offer multiple consistently named locations on UI components to make decisions about splitting up properties easier. Instead of one property section an item could have multiple distinct ones like Community Interactions (star rating, comment number), content information (next appointment date, available number of seats) and meta data (creation date, file size, version number).

When screens are built around a specific user intent the most important property could be pulled to a prominent position. Different UI components might have different kinds of featured positions, the already existing Leading Text of the UI Item and Important Fields of the UI Presentation Table are good examples for this.

Some (or all) irrelevant properties could be hidden. Which locations and properties are shown will most likely depend on the type of object. For example, the number of recent posts in a forum object is a relevant representation of activity, while the number of recent items in a category is usually not of interest.

In views we should avoid repeating, redundant information e.g. when the magazine shows all categories grouped together, it might suffice to put the the category icon into the group panel headline instead of on every single object.

We also have yet to explore if and how we want to incorporate other elements of the interface to help display or hide information of an object outside of the item itself. For example, many file managers can display additional information in a side bar. Maybe the slate can be filled with new tools and features to aid in analyzing, comparing and managing repository items.

We also might want to more clearly and consistently decide, how a property is displayed e.g. as a key text & value text, key text & icon, icon & value text, just the value text or just an icon. For example in "Status: Offline", the word "Status" seems to be redundant as the word "Offline" alone communicates the same amount of information without it.

### User adjusted views

A user with the intent to manage multiple objects would like to use filters, display properties and sorting to shape the view to match their current focus. Currently, in the magazine repository, there is no way for the user to (temporairly) choose a specific set of of properties to be displayed while hiding others. We might want to consider adding a table view where managing users can quickly show and hide property columns and benefit from all the filter and sorting options they know from other views.

To declutter the content area, we might want to consider utilizing the slate for some of the filter and sorting tools, which on the one side keeps them in view while scrolling and on the other sides gives an option to hide them for users who don't wish to use them.

### Curated views

Very often in ILIAS, we have higher user roles managing content for lower user roles. As part of this the higher user roles craft landing pages with carefully selected repository items supllemented with information added through the page editor. If the managing user would have more control over which properties are shown they could build very focused views around the anticipated user intent.

For example, a landing page for new users offering the only three mandatory beginner courses could be completely reduced to a UI card with just a thumbnail and the course title. A catalogue of all available courses on the other hand could use the UI presentation table with focus on event dates to assist in scheduling the upcoming months.

We have seen managing users building such views manually faking a deck of cards that only contains the desired information and highlights with the page editor (see the starting page of the docu.ilias.de instance). While this is a valid workaround, these fake items do not update when the object they represent is updated. Adding, updating and removing many of such items can turn into a laborious process and is prone to user error.

Technically, every view that is developed with a specific focus also falls under this category like the badge, certificate and contacts pages which utilize a deck of cards with selected properties.

## Next steps

We hope that this documents provides some concepts and vocabularies to discuss user intent and in