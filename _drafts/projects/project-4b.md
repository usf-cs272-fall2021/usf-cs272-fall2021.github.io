---
title: Project 4 Search Engine
navbar: Guides
layout: guides
key: 2.6

tags:
  - text: 'Updated'
    type: 'is-primary'

assignments:
  - text: 'Project 4 Search Engine'
    link: 'https://usfca.instructure.com/courses/1597848/assignments/7043816'

---

For this project, you will extend your [previous project](project-4a.html) to include a [search engine web interface](project-4b.html) using [embedded Jetty](https://www.eclipse.org/jetty/) and servlets to search that index. You fully must pass the [web crawler functionality](project-4a.html) to be eligible to earn credit for this project.

**This writeup is for the search engine functionality only.** See the general [Project 4 Writeup](project-4.html) for more details.

## Functionality

The functionality for this project is broken into 2 parts: core functionality and extra features. **You must complete the core functionality before attempting extra functionality.**

### Core Functionality

In addition to maintaining the functionality of the [previous project](project-4a.html), your code must support the following core features using embedded Jetty and servlets for a total of 40 points:

  - **10 points:** Display a webpage with a text box where users may enter a multi-word search query and click a button that submits that query to a servlet in your search engine.

  - **10 points:** Process the queries to match how the data is stored by your inverted index and get the partial search results of those queries.

  - **10 points:** Display the search results as dynamically generated HTML with sorted and clickable links.

  - **10 points:** Support multi-user search. Users conducting search simultaneously should see results relevant to their own queries only. (Be careful how storing results are stored. Static data, as usual, will not be multi-user friendly.)

You cannot earn credit for additional features until the core functionality is working properly.

### Additional Functionality

Once the core functionality is complete, you may implement up to 60 points worth of additional features. These features are broken into several categories. You may choose any combination of features from these categories.

Have a feature idea? You can propose an extra feature in a public post on the course forums. If approved, the instructor will post the number of points that feature will be worth on the final project.

##### User Tracking

The following features requires your search engine to track user data. There are two options: single user support via storing data in memory, or multi-user support via storing per-user data using session tracking or cookies. The possible features are:

<style>
.features th:nth-child(1) {
  vertical-align: bottom !important;
}

.features th:nth-child(n+2) {
  white-space: nowrap;
}

.features em {
  display: block;
  padding-top: 1.5ex;
}
</style>

| Feature Description | Single User<br/>(via memory) | Multi User (via<br/>sessions/cookies) |
|:--------|:------:|:-------:|
| **Search History:** Store a history of all search queries. Allow users to view and clear that history. | 5 | 10 |
| **Visited Results:** Store a history of all visited search results (i.e. results clicked on). Allow users to view and clear that history. *Hint: Modify the search result links to direct back to your search engine, so that it may first store that the link was visited and then redirect the user to the link selected.* | 5 | 10 |
| **Favorite Results:** Allow users to save favorite search results. Allow users to view and clear those favorites. *Hint: Add a special link to each result that saves it as a favorite.* | 5 | 10 |
| **Time Stamps:** Add timestamps to each item stored. Implement this for all related features to earn full credit. *For example, if you implement search history and visited results, timestamps should be added to BOTH features for full credit.* | 2.5 | 5 |
| **Private Search:** Allow users to set an option that turns off all tracking of user data. Implement this for all related features to earn full credit. *For example, if you implement search history and visited results, tracking should be turned off for BOTH features for full credit.* | 2.5 | 5 |
| **Last Login Time:** Track and display the last time a user visited your search engine. | 2.5 | 5 |
{: .table .is-hoverable .features }

You may implement any number of these features, but must do so using the same strategy: either single user via memory or multi-user via sessions/cookies. For example, if you implement search history using sessions, you should also implement visited results using sessions.

##### Database Support

The following features requires your search engine to track additional data (not specific to users). There are two options: storing data in memory, or storing data in an SQL database. The possible features are:

| Feature Description | Via Memory | Via Database |
|:--------|:------:|:-------:|
| **Page Snippets:** During a crawl, store short snippets of every webpage and display these snippets whenever that page is returned as a result. | 10 | 15 |
| **Last Crawled:** This feature requires you implement the "Page Snippets" feature. When crawling pages and storing page snippets, also store a timestamp of when that page was crawled. Whenever that page and snippet is returned as a result, display the crawled date as well. | 2.5 | 5 |
| **Most Visited and/or Favorited Results:** This feature requires you implement at least one of the "Visited Results" or "Favorite Results" features. When storing a visited or favorite result, also track the number of times that page has been visited or favorited by any user. When displaying the visited or favorited history, also show the top 5 visited or favorited pages overall. Implement this for all related features to earn full credit. *For example, if you implement visited results and favorited results, counters should be added to BOTH features for full credit.* | 5 | 10 |
| **Popular Queries**: Store the number of times each multi-word query has been searched for. Allow users to see the top 5 most popular queries on your search page. | 5 | 10 |
| **Clickable Popular Queries** This feature requires you to implement the "Popular Queries" feature. Make the queries displayed clickable such that when clicked, the results for that query is displayed (i.e. clicking a popular query conducts a search for that query). | 2.5 | 5 |
| **Reset Counter Data:** This feature requires you implement at least one the above features that stores counter data (most visited/favorited, or popular queries). Allow users with an administrator password to clear all the counter data stored. | 2.5 | 5 |
{: .table .is-hoverable .features }

You may implement any number of these features, using either of the available approaches. Unlike the user data features, you do not need to use the same approach for all features in this category. For example, you could implement page snippets via a database but popular queries in memory.

##### Multi-Option Functionality

The following miscellaneous features may also be implemented. These features have base functionality and extra functionality that can be implemented; however, the base functionality must be implemented first.

| Functionality Description | Base | Extra |
|:--------------------------|:----:|:-----:|
| **New Seed:** Allow a user to specify a new seed URL that should be added to the existing inverted index. If the URL has already been crawled, skip crawling that URL and output a warning to the user. <em></em>**Max Support:** In addition to entering a new seed URL, allow the user to also specify a maximum number of pages to crawl. This is the maximum number of new pages to crawl in addition to the pages already crawled. URLs that are already included in the inverted index should be skipped and should not contribute to this maximum count. | 5 | 5 |
| **Index Browser:** Allow users to browse your inverted index as an HTML page with all of the words stored, clickable links to all of the indexed URLs for those words, and the number of positions stored for that word and location (but not list all of the positions). <em></em>**Subindex Browser:** Allow users to enter a specific word and display the data stored in your inverted index for that specific word. | 5 | 5 |
| **Location Browser** Allow users to browse all of the locations and their word counts stored by your inverted index as an HTML page with clickable links to all of the indexed URLs. <em></em>**Partial Location Search:** Allow users to browse all of the locations and their word counts for locations that start with the same text. For example, browse all locations that start with "http://www.cs.usfca.edu/~cs212". | 5 | 5 |
{: .table .is-hoverable .features }

Each part is worth 5 points. For example, implementing the "New Seed" feature is worth 5 points and implementing the "Max Support" extra feature is worth another 5 points.

##### Miscellaneous Functionality

The following miscellaneous features may also be implemented:

| Feature Description | Points |
|:--------------------|:------:|
| **Graceful Shutdown:** Allow an administrator to trigger a graceful shutdown of your search engine without calling `System.exit()`. You will need to create a special servlet combined with the [ShutdownHandler](https://www.eclipse.org/jetty/javadoc/jetty-11/org/eclipse/jetty/server/handler/ShutdownHandler.html) in Jetty for this feature. | 10 |
| **Page Statistics:** In addition to providing a clickable link for each search result (i.e. web page), display the page title (via the `<title>` tag in HTML), word count, and content length (via the `Content-Length` HTTP header). This information can be stored in-memory (no database connectivity required) by your web crawler, except word count is already stored by your inverted index. | 10 |
| **Search Statistics:** Display the total number of results along with the time it took to calculate and fetch those results, and display the score and number of matches per search result listed. | 5 |
| **Server Statistics:** As a footer on every page, display the server uptime (i.e. time since the server was started), total number of words stored, total number of locations stored, and total number of queries conducted. This information can be stored in memory by the server. | 5 |
| **I’m Feeling Lucky Button:** Add a new button to your search form (in addition to the normal search button) that automatically redirects the user to the first search result instead of listing all of the search results. This is similar to the Google Search "I'm Feeling Lucky" button. Output a warning if there are no search results! | 5 |
| **Reverse Sort Order:** Allow the user to select an option to reverse the sort order of the search results using a checkbox on the search form. | 5 |
| **Partial/Exact Search Toggle:** Allow the user to toggle on/off partial versus exact search using a checkbox on the search form. | 5 |
| **Web Framework:** Design a search engine using any popular CSS/style framework to create a consistent style for all the web pages. For example, consider using [Bulma](https://bulma.io/), [Bootstrap (Twitter)](https://getbootstrap.com/), [Pure.css](https://purecss.io/), [Material (Google)](https://material.io/develop/web/), [Semantic UI](https://semantic-ui.com/), and many more. | 5 |
| **Search Brand:** Design a search engine with a distinct brand, logo, and tagline. This includes creating a logo and tagline, and including it on all of the web pages. **Do not use unlicensed unattributed media on your website.**{: .has-text-danger } | 5 |
| **Light/Dark Mode Toggle:** Allow users to toggle between light mode (light colored background with dark text) and dark mode (dark colored background with light text) styles for your website. | 5 |
{: .table .is-hoverable .features }

### Potential Deductions

There will be a brief review of your code for this project. If your code has any of the following issues, points may be deducted from your the project grade:

| Deduction Description | Points |
|:----------------------|:------:|
| **Cross-Site Scripting (XSS) Vulnerabilities:** Your grade will lose up to 5 points if your code do not protect against cross-site scripting (XSS) attacks. Your code must escape or sanitize any data it uses from a user (either via the HTTP request or a database) prior to using it on an HTML page. | -5 |
| **SQL Injection Vulnerabilities:** Your grade will lose up to 5 points if your code does not protect against SQL injection attacks. (This only applies to search engines using a database.) Specifically, your code must use prepared statements anytime it stores data in a database. | -5 |
| **Poor Encapsulation:** Your grade will lose up to 5 points if your code breaks encapsulation. | -5 |
| **Poor Code Style:** Your grade will lose up to 5 points if your code is not professionally styled and documented. This includes the formatting, variable names, Javadoc, warnings, and exception handling. | -5 |
{: .table .is-hoverable .features }

While there are many ways to lose points, the total possible deduction is capped such that no more than 10 points total will be removed from your project grade due to the above issues.

### Extra Credit

You may complete additional functionality as extra credit. There is no cap on how much extra credit you can earn for this specific project, however the overall project category grade will be capped to 110% at the end of the semester.

For example, suppose you lost 10% because you submitted project 1 functionality late and completed 130% worth of extra credit on the search engine project. Instead of earning 130% &ndash; 10% = 120% in the project category, your overall project category grade will be capped to 110% instead. This is a great way to make up missed points from late submissions, as well as boost your score if you struggled in the other grade categories.

<article class="message is-warning">
  <div class="message-body"><i class="far fa-exclamation-triangle"></i>&nbsp;Regardless of what you implemented, you will NOT earn points for the search engine core functionality if you are not passing all of the web crawler tests, and will NOT earn points for extra functionality if you have not fully implemented the core functionality!</div>
</article>

## Input

Your main method must be placed in a class named `Driver`. The `Driver` class should accept the following **additional** command-line arguments:

  - `-server port` where `-server` indicates a search engine web server should be launched and the next argument `port` is the port the web server should use to accept socket connections. Use `8080` as the default value if it is not provided.

    If the `-server` flag is provided, your code should enable multithreading with the default number of worker threads even if the `-threads` flag is not provided.

The command-line flag/value pairs may be provided in any order, and the order provided is not the same as the order you should perform the operations (i.e. always build the index before performing search, even if the flags are provided in the other order).

Your code should support all of the command-line arguments from the [previous project](project-4a.html) as well.

## Output

The majority of the output for this project will be in the form of HTTP responses to a browser. Only output the inverted index or search results to a file if the necessary flags are provided.

## Testing

No tests will be provided for this project. Instead, you will demonstrate your search engine functionality to the instructor during your final code review appointment during finals week.
