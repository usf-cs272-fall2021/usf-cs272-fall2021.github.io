---
title: Project 4 Search Engine
navbar: Guides
layout: guides
key: 4.2
bump: false

tags:
  - text: 'Pending'
    type: 'is-muted'

assignments:
  - text: 'Project 4 Search Engine'
    link: 'https://usfca.instructure.com/courses/1602551/assignments/7118300'
---

For this project, you will extend your [previous project](project-4a.html) to create a search engine web interface using embedded Jetty and servlets.

**This writeup is for the search engine functionality only.** See the general [Project 4 Writeup](project-4.html) for more details.

## Eligibility
{: .page-header }

The eligibility requirements for this project are the same [design eligibility](design.html#eligibility) requirements of the previous projects. Specifically:

  - You must have a non-zero design grade for [project 3](project-3.html) on [Canvas]({{ site.data.info.links.canvas.link }}).

  - You must have a non-zero functionality grade for [project 4a](project-4a.html) on [Canvas]({{ site.data.info.links.canvas.link }}).

If you are missing a grade you should already have, please reach out to us on the [course forums]({{ site.data.info.links.forums.link }}).

## Functionality
{: .page-header }

Pending

### Core Functionality

Pending

### Additional Functionality

Pending

### Potential Deductions

Pending

### Extra Credit

Pending

## Input
{: .page-header }

Your main method must be placed in a class named `Driver`. The `Driver` class should accept the following **additional** command-line arguments:

  - `-server port` where `-server` indicates a search engine web server should be launched and the next argument `port` is the port the web server should use to accept socket connections. Use `8080` as the default value if it is not provided.

    If the `-server` flag is provided, your code should **enable multithreading** with the default number of worker threads even if the `-threads` flag is not provided.

The command-line flag/value pairs may be provided in any order, and the order provided is not the same as the order you should perform the operations (i.e. always build the index before performing search, even if the flags are provided in the other order).

Your code should support all of the command-line arguments from the [previous project](project-4a.html) as well.

## Output
{: .page-header }

The output of your inverted index and search results should be the same from the [previous project](project-4a.html). As before, you should **only generate output files if the necessary flags are provided**.

## Testing
{: .page-header }

**There are no functionality tests for this project.** Instead, you will demonstrate your search engine functionality to the instructor during your [final code review](final-review.html) appointment during finals week.

## Related Content
{: .page-header }

Pending
