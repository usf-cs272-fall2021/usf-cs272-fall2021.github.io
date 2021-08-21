---
title: Project Grading
navbar: Guides
layout: guides
key: 1.0
---

There are four major programming projects:

  1. **[Project 1 Inverted Index](project-1.html):** Focuses on creating the underlying data structure required for the search engine and how to build that data structure from text files.

  2. **[Project 2 Partial Search](project-2.html):** Focuses on the search algorithm to be utilized by the search engine.

  3. **[Project 3 Multithreading](project-3.html):** Focuses on improving the efficiency of building and searching using multithreading.

  4. **[Project 4 Search Engine](project-4.html):** Focuses on building and searching through web pages and a web server instead of text files and command-line arguments.

Each project is dependent on the previous. For example, you cannot work on an efficient search algorithm for project 2 until you have a well-designed underlying data structure from project 1.

## Project Grading
{: .page-header }

Each project is broken into two components: a functionality component (graded using tests) and a design component (graded using code review). See below for details.

### Functionality Grade

The functionality grade is based on remote testing using Github Actions. Your project must pass *all* of the provided tests remotely. The tests are provided in the [project-tests]({{ site.data.info.links.github.link }}/project-tests) repository in the `Project#Test.java` file (where `#` is the project number) in the [src]({{ site.data.info.links.github.link }}/project-tests/tree/main/src/test/java) subdirectory.

See the [Project Testing](project-testing.html) and [Project Functionality](project-functionality.html) guide for more details.

### Design Grade

The design grade is primarily based on code review with the instructor. The instructor will evaluate the design of your code and give you changes that must be made before the next code review. Only fully functional code may be code reviewed.

Each project takes between 2 to 4 code reviews to pass. You may have up to one synchronous code review with the instructor per week. There are no restrictions on how many asynchronous code reviews you can have per week, but each asynchronous review must be pre-approved and takes approximately 2 business days to complete. Usually asynchronous code reviews start after two synchronous code reviews.

See the [Project Design](project-design.html) guide for more details.

### Late Penalties

Since you have to fully pass both functionality and design, the project grades are based on *when* you pass each component.

  - The functionality grade is based on the created date of your **first passing release** on Github. This is *not* when you first passed those tests locally or a commit that passed those tests.

  - The design grade is based on the **first synchronous code review** of that project. This is *not* the day you requested code review, but the actually appointment time of your first synchronous code review (assuming you did not miss your appointment).

There is a **10% late penalty per week** that your project is late. For example, you will earn a 90% functionality grade if your first passing release is 1 day late. You will earn an 80% design grade if your first code review is 9 days late.

Falling behind pushes back your following projects, especially since code reviews take weeks to complete. It is critical to keep on track even if there is a sliding deadline window!

## Other Considerations
{: .page-header }

Concerned about your grade or falling behind? **Regardless, don’t cheat.**{: .has-text-danger }

I often catch it. It gets *messy*. There are consequences. You do NOT end up saving time, effort, reputation, or stress. You DO miss one of the few (if not only) one-on-one personalized learning experiences you’ll ever get in college.

Instead, please see below.

### Working Ahead

Each project is dependent on the previous project and design is dependent on functionality. However, there is room to work ahead while you are stuck in the code review process.

You can be working on the functionality and design of two **consecutive projects** at once in **SEPARATE branches**. The project being code reviewed must be in the `main` branch. Consider this diagram:

![Screenshot]({{ "/images/project-progression.svg" | relative_url }}){: style="width: 50em;"}

For example, suppose you have project 1 functionality complete. You can work on project 1 design in the `main` branch and project 2 functionality in a `project2` branch simultaneously. However, you cannot work on project 3 functionality until you have passed the design of project 1 and project 2 functionality.

Merging two development branches together can be difficult, especially for the first projects. We strongly encourage waiting until after the first code review before branching functionality for the next project.

### Extra Credit

Worried about those project points you missed due to late submissions? You can make up **missing points** by implementing additional functionality.

Below are some options and the projects they apply. For example, “Projects 2+” means the extra credit can be completed for either Projects 2, 3, or 4. Once completed for one project, it cannot be completed for another.

  - **5 points, Project 1+:** Run the [PMD Source Code Analyzer](https://pmd.github.io/) on your code with the default settings and address as many of the violations as possible. Static source code analysis tends to have high false positive rates (generating many unnecessary violations); you may choose to ignore several violations as long as you are prepared to justify that choice during code review.

  - **5 points, Project 1+:** Update and polish all of your Java documentation, then use the `javadoc` tool to generate a documentation website. Place the generated html in a docs subfolder in your main branch. Ask the instructor or TA to enable Github Pages for your repository so that your documentation is viewable as a website.

  - **5 points, Project 1+:** Reduce the duplicate logic in your Driver class for outputting data to a JSON file using lambda expressions, such that Code Climate no longer complains about (most of) this code. This can be done in multiple different ways—ask the instructor for suggestions specific to your implementation.

  - **5 points, Project 1+:** Reduce the duplicate logic in your JSON writing and stemming classes using lambda expressions, such that Code Climate no longer complains about (most of) this code. This can be done in multiple different ways—ask the instructor for suggestions specific to your implementation.

  - **5 points, Project 2+:** Create a Comparator that will sort your custom search result object by score, total number of words in the file (instead of the number of matches), and then the path. Create test code to demonstrate this Comparator works. This test code can be a simple class with hard-coded arguments and console output; it does not need to be a unit test using JUnit.

  - **5 points, Project 3+:** Add a flag, `-verbose`, that enables logging `DEBUG` messages and above to the console. Add `DEBUG` messages at the start and end of each `if` block in your `Driver` class, at the start and end of every task `run()` method, and finally in the work queue class to indicate when a work queue is created and shutdown. Create test code to demonstrate this feature works. This test code can be a simple class with hard-coded arguments and console output; it does not need to be a unit test using JUnit.

With the exception of Project 4b Search Engine, you cannot earn more than 100% within the project category. This extra credit is intended to make up for points missed due to late deductions.

However, you can apply the points to the functionality and/or design grade. For example, if you missed 10 points on the functionality grade and 20 points on the design grade, you can complete 30 points of extra credit for that project.

You are encouraged to ask for clarification on any of these you are interested in completing in a public anonymous post on our class forums.
