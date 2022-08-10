## UI Component HTML Template bare - layout structure done in CSS

* layout, color and bg come all from component specific CSS classes (maybe using mixins from other layers)

```html
<div class="il-c-item">
    <div class="il-c-obj__main-identifier-1">{MAIN-IDENT-1}</div>
    <div class="il-c-obj__main-identifier-2">{MAIN-IDENT-2}</div>
    <div class="il-c-obj__main-identifier-3">{MAIN-IDENT-3}</div>
    <div class="il-c-obj__main-action">{MAIN-ACTION_PROP}{MAIN-ACTION}</div>
    <div class="il-c-obj__properties__content-info">{CONTENT-INFO}</div>
    <div class="il-c-obj__properties__community-interaction">{COMMUNITY-INTACT}</div>
    <div class="il-c-obj__properties__meta-data">{META-DATA}</div>
    <div class="il-c-obj__manage-action">{MANAGE-ACTION}</div>
    <div class="il-c-obj__properties__additional">{ADDITIONAL_PROP}</div>
</div>
```

## UI Component HTML template - layout structure done in HTML

* layout comes from layout layer and tool layer classes
* colors and bg design comes from component specific classes

```html
<div class="il-c-item-2">
    <div class="il-l-section-bar il-t-flex--nowrap">
        <div class="il-c-obj__main-identifier-2 ">{MAIN-IDENT-2}</div>
        <div class="il-l-section il-t-flex--grow-1">
            <div class="il-l-section-bar il-t-flex--nowrap">
                <div class="il-l-section il-t-flex--grow-1">
                    <div class="il-c-obj__main-identifier-1">{MAIN-IDENT-1}</div>
                    <div class="il-c-obj__properties__content-info">{CONTENT-INFO}</div>
                </div>
                <div class="il-l-section-bar">
                    <div class="il-c-obj__main-action">{MAIN-ACTION_PROP}{MAIN-ACTION}</div>
                    <div class="il-c-obj__manage-action">{MANAGE-ACTION}</div>
                </div>
            </div>
            <div class="il-l-section-bar il-t-flex--nowrap">
                <div class="il-c-obj__properties__content-info il-t-flex--grow-1">{CONTENT-INFO}</div>
                <div class="il-c-obj__properties__community-interaction">{META_DATA}</div>
            </div>
        </div>
    </div>
</div>
```


Areas:
* main identifier 1 (title, object icon)
* main identifier 2 (thumbnail, main date/time)
* main action bar: 1 x primary, 1 x secondary button
* main action featured property (availability)
* properties content information (description, next appointment date, available number of seats)
* properties community interactions (star rating, comment number)
* properties meta-data (creation date, file size, version number)
* manage action featured property (e.g. file size)
* manage actions (dropdown)
* properties additional (CC License)

each area can hold 1x bar with multiple items that should fit in one single row on desktop and then fullwidth elements beyond that

Property Group UI Component

PropertiesFullRows
PropertiesColumns
PropertiesBar
PropertiesBarAlignOpposite
PropertiesBarEvenlySpaced


Weighting inside property areas:
* property highlight by top position
* grouping in bar or single line
* property highlight by inline formatting

possible depiction of a property
* value text/link
* paragraph
* icon
* icon with number badge
* image
* key text: value text/link (side by side)
* key text: icon
* key text: value text/link (with separation)
* button primary
* button secondary
* dropdown button
* input field?

layout options - container
* break for every item
* wrap when width reached
* space-between items

layout options - item size
* full width
* object width
* fixed width (e.g. to recieve columns)
* distribute available width
SHOULD result in one row with multiple items only, CAN have multiple full-width rows



* content information (next appointment date, available number of seats)
* community interactions (star rating, comment number)
* meta-data (creation date, file size, version number)

Problem: Some properties should travel into panel/group headline

Handpicked Sorting

(Course Icon)   Course Title
                18. Oct 2021 - 18. Feb 2022, 
                Registration Period:
                Availability: 18. Oct 2021 - 12. Dec 2022




Automatic Course Sorting

Panel Headline: (Icon) Courses

Item Group: No date

Item Group: July - August

Item Group: We, 06. July 2022

9:00 - 16:30