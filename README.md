# eZ Platform Requirements Repository

Welcome to our new Requirements repository for eZ Platform development! eZ's
Product Management team shares our collaborative work here, storing feature
requirements in Markdown documents for easy access. You may also find PDF files,
Word Docs, BDD, RAML... :)

## Take a Look Around

There are only a few files here while we ramp up this new approach (this
  repository was born on February 8, 2017). The `v2.0` branch is where you'll
  find most of our initial activity, PRs, and discussion:

https://github.com/ezsystems/specs/tree/v2.0

### What are all these empty folders?

As we have discussed a logical structure to organize files for requirements, we
created _empty folders_ to form a sort of skeleton with placeholders where
requirements will be dropped in as we work. This can be tweaked and updated as
we find ways to improve.

Here's an example: eZ Platform has an Administration UI, and the Administration
UI has a feature we call the Universal Discovery Widget that allows you to
discover content items. In a widget. Universally. ;)

You'd find an overview of its requirements here:
/eZ Platform/Admin UI/Universal Discovery Widget/README.md

And, until we get to it (likely when we next specify requirements related to
improvements of that feature), the folder just has a basic boilerplate message
holding its place for the future. Got ideas you'd like to drop in there? Read
on.

## Contributing
Do you have some ideas you'd like to contribute to these requirements? It's
easy! Simply fork this repository to your own GitHub account, checkout the
branch you want to work with (e.g., `git checkout v2.0`), then make your own
branch (with a useful and informative name, e.g.
`git checkout -b v2.0/feature/udw-suggestions`) from that.

Make any changes or additions you'd like to propose, add, and commit. Push to
your fork, then send a Pull Request back here to the branch you're targeting
where we can discuss things together.

### Target the Right Version!
The master branch will always represent eZ's _current_ recommended product.
Right now, that's eZ Platform v1.7 LTS. If you submit a Pull Request to master,
you're asking for the requirements and specifications to be updated for v1.7
(probably not the one you meant, unless your Pull Request is just fixing a typo
for that version). For example, if you're excited about the v2.0 project and
want to contribute, you'd check out the v2.0 branch and make your working
branch based on that one.

Start by checking out the branch representing the version you _do_ want to work
with, and send your Pull Request back to that branch so it goes into the right
place. For example, if you want to propose edits to the requirements and
specifications for v2.0, you would make _your_ branch _based on_ this
repository's v2.0 branch: https://github.com/ezsystems/requirements/tree/v2.0
and send your PRs there.

### Naming your working branch

Your Pull Request will show that it comes from your fork, so you don't need to
add your name or initials to the branch. Try to give it a name that describes
what you're working on. For example, one might create a branch called
`v2.0/feature/raml` or `v2.0/feature/rest-api-improvements` if one wanted to
contribute requirements for implementing the use of RAML with our REST API. The
files would probably make sense in the `/eZ Platform/APIs/REST/` folder. When
you send your PR, we'll help you make sure it is aimed at the right branch
(v2.0, the one you created yours from), and then everyone can review and comment
to discuss.

### Editing Your Files

#### Editors

If you'd like a good browser-based Markdown editor that can import, edit, and
save MD files on GitHub, check out http://dillinger.io/

There are also plugins available for your favorite editor or IDE. For example,
here's one for Atom: https://github.com/atom/markdown-preview

#### Other Formats
You don't _have_ to use Markdown, but we encourage you to; it's what we'll use,
but share files that express your vision for the feature clearly.

#### Starting Templates
You can start with one of the templates we're cultivating here if you like:



## Epics
We're using GitHub Projects to track the status of features, so you can follow
along too: https://github.com/ezsystems/requirements/projects

We have a label, "Epic", to signify epics we're working on. Each Epic tracks a
feature. You can track along as the issues are moved through the different
columns in the boards. Click an issue on the board to view and comment.

## About eZ Platform
eZ Platform is the Symfony CMS, written in PHP and released under the GPLv2 open
source license.
- https://ezplatform.com/
- https://github.com/ezsystems/ezplatform

eZ Platform _Enterprise Edition_ is available with additional features and full
support from https://ez.no/Products/eZ-Platform-Enterprise-Edition
If you are an existing eZ Enterprise customer and would like to report an issue
with the Enterprise Edition, please use: https://support.ez.no/

Copyright (c) 1999-2017 eZ Systems
Repository contents are licensed under the Creative Commons
Attribution-ShareAlike 4.0 International Public License
