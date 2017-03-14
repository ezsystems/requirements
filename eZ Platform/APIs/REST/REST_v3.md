# REST API v3: content management

This specification defines the next iteration of the REST API in eZ Platform known as V3. The API aims to be backwards compatible but will also introduce new capabilities.

As a developer the overall vision of V3 is that the API should create simpler endpoints that can get me started quicker with the API. The endpoints will more default to values like language, draft, versions and misc options in order to make the threshold to use the API lower.

The overall vision is: simple by default and still making the advanced capabilities efficient.

The goal of the API defined here is to manage object fetch, create update and deletion. For read only and content heavy uses the GraphQL endpoints should be used.

*Question:* Should we drop XML support in the REST API? Other than specific field types like RichText there are no real needs to support XML. We could focus on V3 being just JSON for simplification.

## Typical use case

As a front-end developer I would like to:
* Define a content type in eZ Platform
* Manage the content via the REST API:
    * Use the REST endpoints to quickly create a new object
    * Use the REST endpoints to quickly update an already created object

# Creating content POST
The create content endpoint should be simplified to default most values and the simplest possible.

This call should create:
* A new content object (not a draft) and publish
* Assign ownership to the current user
* Create the object in the default language if not set
* Location can be defined either with ID or URL

## Example: creating a new object

__Resource__: _/content/object_

__Accept__: _application/vnd.ez.api.Content+json_

__Content-Type__: _application/vnd.ez.api.SimpleContentCreate+json_

__Method__: _POST_

__Body__:
```json
{
    "ParentLocation": <ID> or <URL>,
	"contentType": <CONTENT_TYPE_IDENTIFIE>,
	"fields": {
		"title": "My blog title",
		"author": "Bård Farstad",
		"body": "Body text, ideally simple but also with <b>formatting</b>. Perhaps supporting simple form and docbook.",
		"image": "/path/to/image.jpg"
	}
}
```

__Return__: _HTTP/1.1 201 Created_
```json
Location: /content/object/<newID>
```

# Fetching content GET

Fetching an object by location. Location can be either a location ID (42) or a relative url (/Blog/My_Post)

## Example: fetching an object

__Resource__: _/content/object/<LOCATION_ID>_

__Method__: _GET_

__Return__: _HTTP/1.1 200 Success_
```json
{
    TODO: add default fields: id, published, modified, version, language etc.
    "content-location": "/blogs",
    "content-type": "blog_post",
    "content-type-name": "Blog Post",
    "fields": {
        "title": "My blog title",
        "author": "Bård Farstad",
        "body": "Body text, ideally simple but also with <b>formatting</b>. Perhaps supporting simple form and docbook.",
        "image": "/path/to/image.jpg"
        }
}
```
OR
__Return__: _HTTP/1.1 404 Not found_

# Patching content PATCH

The following call patches an object and updates complete object or the defined fields only.

## Example: object's full update

__Resource__: _/content/object/<LOCATION_ID>_

__Method__: _PATCH_

__Body__:
```json
{
    "fields": {
        "title": "My Updated title",
        "author": "Bård Farstad",
        "body": "Body text, ideally simple but also with <b>formatting</b>. Perhaps supporting simple form and docbook.",
        "image": "/path/to/image.jpg"
        }
}
```

__Return__: _HTTP/1.1 200 Success_ OR _HTTP/1.1 404 Not found_

## Example: partially updating an object

__Resource__: _/content/object/<LOCATION_ID>_

__Method__: _PATCH_

__Body__:
```json
{
    "fields": {
        "title": "My Updated title",
    }
}
```

__Return__: _HTTP/1.1 200 Success_ OR _HTTP/1.1 404 Not found_

# Deleting content DELETE

Same as current REST API behaviour.

## Field types

TODO: define the interface for the currently available field types to create and update/create.
