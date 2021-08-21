---
title: Project Extra Credit
navbar: Guides
layout: guides
key: 4.0
bump: true

tags:
  - text: 'New'
    type: 'is-primary'

---

Recall from the [syllabus](/syllabus.html#extra-credit-request) that:

> You may request one extra credit/makeup opportunity for assignments in the participation, homework, or **project** categories. You may earn up to 50% of the amount of points missed on that assignment. For example, suppose you earned 70 out of 100 points on an assignment, you can request an extra credit opportunity to make up 15 points. There is no time limit on when this request may be made.

You can only make this request for one specific project. Regardless of how much extra credit you do, it will be capped at 50% of the points lost on that project.

You do not need to make requests for project 4, which already has extra credit opportunities built-in.

Below are some options and the projects they apply. For example, "Projects 2+" means the extra credit can be completed for Projects 2, 3, or 4.

  - **5 points, Projects 1+:** Update and polish all of your Java documentation, then use the `javadoc` tool to generate a documentation website. Place the generated html in a [docs](https://github.blog/2016-08-22-publish-your-project-documentation-with-github-pages/) subfolder in your `main` branch. Ask the instructor or TA to enable Github Pages for your repository so that your documentation is viewable as a website.

  - **5 points, Project 1+:** Reduce the duplicate logic in your `Driver` class for outputting data to a JSON file using lambda expressions, such that Code Climate no longer complains about (most of) this code. This can be done in multiple different ways---ask the instructor for suggestions specific to your implementation.

  - **5 points, Project 1+:** Reduce the duplicate logic in your JSON writing and stemming classes using lambda expressions, such that Code Climate no longer complains about (most of) this code. This can be done in multiple different ways---ask the instructor for suggestions specific to your implementation.

  - **5 points, Projects 2+**: Create a Comparator that will sort your custom search result object by score, total number of words in the file (instead of the number of matches), and then the path. Create test code to demonstrate this Comparator works. This test code can be a simple class with hard-coded arguments and console output; it does not need to be a unit test using JUnit.

  - **5 points, Project 3+**: Add a flag, `-verbose`, that enables logging `DEBUG` messages and above to the console. Add `DEBUG` messages at the start and end of each `if` block in your `Driver`, at the start and end of every task `run()` method, and finally in the work queue class to indicate when a work queue is created and shutdown. Create test code to demonstrate this feature works. This test code can be a simple class with hard-coded arguments and console output; it does not need to be a unit test using JUnit.

You are encouraged to ask for clarification on any of these you are interested in completing in a public anonymous Piazza post.
