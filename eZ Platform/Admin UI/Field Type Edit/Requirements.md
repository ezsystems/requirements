# Content Editing

## Objective

The objective (which may be supported by prototypes or examples), is to identify and decide on the best approach to implement CRUD (create, read, update and delete) operations on Field Types within the user interface(s) and APIs exposed by eZ Platform in eZ Platform v2.x.

The underlying goals are:

- Simplify how to create a new Field Type (wether it is for eZ Systems' own needs when creating Field Types in the core platform, or developers customizing the platform by creating custom Field Types)
- Reduce risk of errors and simplify maintenance by limiting the number of places where UI behavior is defined
- Increase speed for developers to develop and maintain Field Types with a similar efficiency level as what was offered by eZ Publish Legacy, or better.

## Firm requirements

- The solution must enable CRUD operations on fields in the exact same way, in both eZ Platform UI (cf. Hybrid application prototype), and in any website directly powered by eZ Platform Web Framework (as opposed to a decoupled website, simply using eZ Platform APIs)
- The solution must enable CRUD operations on fields in a remote website / web application (in any programming language) using the REST API, and should minimize the UI logic that will have to be implemented for that (e.g. moving as much as possible of the UI logic in the APIs, such as validation rules, etc., or exposing the Web UI through the API)

## Preferred requirements

- The solution should enable CRUD operations on fields in a non-web application (e.g. native mobile apps, digital signage, iTV...) using the REST API and should minimize the UI logic that will have to be implemented

### Candidates

The repository-form solution is a strong candidate for the Web UI as it solves the first firm requirement by design. Repository-form was, however, created as a complement of Platform UI, and this spike should validate (by examples) that it's a viable standalone solution, and should benchmark other solutions too.

Other approaches (either complementary or alternative) might be good candidates too, such as:

- Exposing part of the UI via REST API calls (answers the 2nd requirement)
- Using webcomponents instead of pure Twig-based UI (answers the 1st and 2nd requirements and reduces dependencies on Symfony for the future)
- Evolving repository-form: based on repository forms, but adding additional capabilities to better define UI behaviors in the API

## Outcome

The spike allocated for this requirement should provide a final recommendation and a draft specification so that a rewrite of the edit UI of all default Field Types for 2.x can start.
