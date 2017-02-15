# v2: Symfony 3 Hybrid Prototype: Admin UI Requirements

## Prototype Objective
"As an eZ Engineer, I want...

To create a functioning, experimental combination of Symfony3, eZ Platform, and
a mix of existing elements (in YUI) and rewritten elements (in a new framework),
for the purpose of research and development (prototype), so that I can get a
better picture of how such a hybrid approach may work."

The underlying main goals are:
- By adopting Symfony 3, we will provide developers (especially the ones who are
  experienced with eZ Publish or Symfony) a substantially faster and easier way
  to develop, extend, and customize eZ Platform.
- By ensuring a hybrid architecture that reuses existing elements relying on
  YUI, we will speed up availability of 2.x by not having to re-develop all
  features. Candidates for reuse are UDW, Sub-Items View, Content views. If this
  reuse is not possible, expectations and plans for 2.x will have to be
  re-adjusted.

### Definitions
- "Hybrid Approach": A Multi-Page App (MPA) approach, replacing current SPA
  - Uses Symfony routing, and ensures that we can have an application URL that
    can use Content IDs, Location IDs, Content Fields (name)
  - Allows extending Admin UI via Symfony/Twig
  - Includes JavaScript enhancements utilizing modern framework(s) &
    librar(y/ies)

### Use Cases

#### Stories

##### As a developer I want to simply reuse Admin Panel functionalities present in 1.x
- ex: content type view

##### As a developer I want to simply reuse existing YUI-based modules present in 1.x
- ex1: universal discovery widget
- ex2: landing page editor
- ex3: sub-item views in the repository

##### As a developer I want to extend the hybrid app with a React-based module.
- ex: a module in a tab in the content repository that would deal specifically with content

##### As a developer I want to extend the hybrid app with a Polymer-based module.
- ex: a module in a main tab or sub tab of the app navigation

##### As a developer I want to extend the hybrid app with a Angular-based application
- ex: a module on the dashboard

## Requirements:

### Firm
Prototype *must*:
- Demonstrate routing in Symfony3
- Demonstrate PHP API usage in Symfony3
- Demonstrate re-use of at least one existing YUI component within new solution
- Demonstrate re-use of an existing non-YUI component such as Content Type View
  (which is Symfony based)

### Preferred
Prototype _should_:
- Demonstrate use of a non-YUI JavaScript enhancement within Admin UI
- Use the Universal Discovery Widget as the test subject to Demonstrate re-use
  of existing YUI component within new solution

### Bonus
Prototype may:
- Demonstrate encapsulation of existing YUI elements, as well as others, in
  webcomponents if practical.

### Exclusions
Prototype *must not*:
- Rely on YUI for Admin UI

Prototype _should not_:
- Be pretty. This is just to test, play, and learn. Nothing fancy.
