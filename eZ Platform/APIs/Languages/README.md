# v2: Updated API Language behaviour

## Objective

Simplify usage of the product for developers, avoid common mistakes when dealing with multi language installs,
and make sure to cover needs for future UI needs.

### Use Cases
The identified new behaviour:
- As a Developer, I want to get API entities in prioritised language of the given SiteAccess,
  so I don't need to specify language in API Service calls
- As a Developer, I want to get API entities in one Translation at a time,
  so I don't need to specify language or use helpers when using the API entities

##### Related use cases
- As an Editor, in UI I want to be able to select languages of API entities to view and edit translation independently
  of the current SiteAccess, _so I don't need to deal with several variants of backend to do that_
- As an Editor, I want to be able to pick language for translation of the UI itself independently of the
  current SiteAccess, _so I don't need to deal with several variants of backend to do that_
- As a Developer, I want to be able to handle translations across the API entities, including being able to delete
  single translations

#### Existing use cases
- As a Developer, when enabling on a per entity basis always available language feature, I expect to get entities in
  it's main language if not translated to language(s) provided by either me or automatically set from SiteAccess.

## Firm
The feature MUST:
- Not break BC on the 99% use of the API Repository Services usage:
  - If developer specified custom language, API should still respect that
  - If languages is not specified it is assumed we can safely _change_ to return the prioritised one as that is what
    helpers on top would later pick anyway, so we need to make sure the helpers will still work with only one language.
- Use languages arguments as a priority list consistently across the API, as is the case with search today
- Automatically inject the list of SiteAccess defined languages unless developer provided one specifically

## Preferred
The feature SHOULD:
- Provide a way for the 1% use case to be able to easily adopt to still work:
  - If languages are not specified and developer intended to load all languages for further processing, this should still
    be possible somehow
- Be consistent across all the different API entities and Services in Repository API
- **v1:** Features being added as part of this change should be done in v1, and the change in behaviour should be done
  in v2, allowing v1 users to start to be forward compatible.

## Bonus
The feature MAY:
- Give better performance by reducing amount of code needed to deal with languages, reduce the size of entities
  placed in cache and transferred from database


## Open Question:
In the case where A. an editor select a given contextual language to edit a given entity (e.g. a content object)
and/or
the case where B. an editor select a language for the user interface (e.g. languages of the menus)

Should this affect language **global** priority when API calls are made for _(A: other)_ entities?

Example:
 Given I am a Editor
 When I edit Content in language fre-FR
 I expect to see relations and items in UDW in language taken from Z << ??


Suggestion, updated requirements above to reflect:
- Case A should be left up to UI if language when editing entity X, should also affect loading of entity Y
  So this behavour will not be defined here, as it will be defined when needed on a given specific UI behaviour.
- Case B should be injected into the language priority logic, so the user specified UI language will also reflect on
  the entities being displayed by default, hence Platform UI takes "Z" from this selection instead of using config.
