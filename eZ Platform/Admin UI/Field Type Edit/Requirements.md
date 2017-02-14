# Content editing

# Objective

The objective of this spike which should be, supported by prototype(s) or example(s), to identify and decide on the best approach to implement CRUD (create, read, update and delete) operations on field types within the user interface(s) and APIs exposed by eZ Platform in v2.x.

The underlying goals are:

Simplify how to create a new field type (wether it is for eZ Systems own needs when creating field types in the core platform, or developers customizing the platform by creating custom field types)
Reduce risk of errors and simplify maintenance by limiting the number of places where U.I. behavior are defined
Increase speed for developers to develop and maintain field types with a similar efficiency level as what was offered by eZ Publish legacy or better.

# Firm requirements

The solution should enable CRUD operations on fields in the exact same way in eZ Platform UI (cf. Hybrid application prototype) and in any Website directly powered by eZ Platform Web framework (as opposed to a Website decoupled, simply using eZ Platform APIs)
The solution should enable CRUD operations on field in a remote Web site / Web application (in any programming language) using the REST API and should minimize the U.I. logic that will have to be implemented for that (e.g. moving in the API as much as possible of the UI logic such as validation rules or others or exposing Web UI through the API)

# Preferred requirements

The solution should enable CRUD operations on fields in a non-Web application (e.g. native mobile apps, digital signage, i-tv...) using the REST API and should minimize the U.I. logic that will have to be implemented for that too

# Candidates

The repository-form solution is a strong candidate for the Web UI as it solve the first firm requirement by design. Repository-form was however created as a complement of Platform U.I. and this spike should validate (by examples) that it's a viable solution standalone and should benchmark other solutions too.

Other approaches either complementary or alternative might be good candidates too, such as

exposing part of the UI via REST API calls (answers the 2nd requirement)
using Web components instead of pure Twig based U.I. (answers the 1st and 2nd requirements and reduces dependencies to Symfony for the future)
evolving repository-form : based on repository forms but adding additional capabilities to better define U.I. behaviors in the API
...?

# Outcome

This spike should provide a final recommendation and a draft of specification so that rewrite of edit UI of all default field types for 2.x could start.
