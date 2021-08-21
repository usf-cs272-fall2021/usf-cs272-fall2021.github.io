---
layout: guides
navbar: Guides
title: Homework Setup
key: 1
---

This guide will walk you through the process of setting up your homework repository and importing it into Eclipse.

### One-Time Setup

Before you begin, you need to make sure to go through the other setup guides first:

  - [General Guides](/guides/general/)
  - [Eclipse Guides](/guides/eclipse/)

If you do not yet have a Github account, [sign up for a free account](https://github.com/join). I recommend choosing a professional username and signing up for the [Student Developer Pack](https://education.github.com/pack)  when you get a chance.

### Per-Homework Setup

For every homework assignment, you will need to repeat these steps:

  1. **Setup your Github repository.**

      1. Find the homework assignment on Canvas. For example, go to the [ArgumentMap](https://usfca.instructure.com/courses/1597848/assignments/7043821) assignment on Canvas for the first homework of the semester.

      1. Click the Github Classroom invitation link and follow the instructions.

      1. If this is your first time using Github Classroom, you will be prompted to select your USF username from the list. This makes sure we can associate your Github username with your grades in Canvas. You only need to complete this step once.

      This process will create a private Github repository with the homework starter code that only you, the teacher assistants, and the instructor can access.

  2. **Setup your Eclipse project.**

      Once your repository is setup, you must import the homework as a Java Maven Project in Eclipse. See the [Importing Eclipse Projects from Github](/guides/eclipse/importing-eclipse-projects-from-github.html) guide for detailed steps.

      When done, the "Package Explorer" view of your homework should look something like this:

      ![Screenshot]({{ "/images/homework-imported.png" | relative_url }}){: style="width: calc(654px * 0.5);"}

      Make sure you are in the "Java" perspective before moving on. This perspective allows you to run Java code. The "Git" perspective lets you view, but not run, Java code.

  - **Verify you can run the JUnit tests on Eclipse locally.**

      The tests will be in the `src` » `test` » `java` subfolder. Right-click the test file and select "Run As" » "JUnit Test" from the menu.

      That should open up the "JUnit" view automatically, which will look similar to this:

      ![Screenshot]({{ "/images/homework-junit.png" | relative_url }}){: style="width: calc(734px * 0.5);"}

      These are the tests you will need to pass for the homework. Most of the tests will fail the first time.

  - **Commit and push changes to Github.**

      In Eclipse, make a minor change and [commit and push](http://wiki.eclipse.org/EGit/User_Guide#Committing_Changes) that change to Github. I recommend placing the [Git Staging View](http://wiki.eclipse.org/EGit/User_Guide#Git_Staging_View) somewhere on your Eclipse layout to make this process more convenient.

      Make sure to drag files from the "Unstaged" to the "Staged" box and add a commit message. For example:

      ![Screenshot]({{ "/images/homework-staging.png" | relative_url }}){: style="width: calc(654px * 0.5);"}

      Click "Commit and Push" to make a checkpoint and push that checkpoint to Github. If you click "Commit" you only make a local checkpoint on your system.

  - **Verify the Autograder Github Action ran properly.**

      Visit your repository on Github. Click the "Actions" tab to view all of the runs. There should be a run with the same name as your last commit.

      Make sure the action finishes running. Here is an example of what a completed action looks like:

      <https://github.com/usf-cs212-spring2021/homework-ArgumentMap-template/actions/runs/520215983>

      Scroll down in the "Summary" view to see the "Annotations" section. That will report the number of points your homework has earned so far:

      ![Screenshot]({{ "/images/homework-annotation.png" | relative_url }}){: style="width: calc(1162px * 0.5);"}

      For details on which tests failed, you need to drill into the "Autograding" output.

At this point, you should be able to start filling in the missing code, committing changes, and pushing those changes to Github.

### Completing Homework

Refer to the `TODO` comments in the template code for specifics on what code to fill in or modify for the assignment. When modifying this code, keep in mind the following:

  - **Do not modify any method or class declarations.** For example, you cannot add or remove keywords like `static` or add a `throws` keyword to a method if one was not already included.

  - **Do not modify methods that are already fully defined.** For example, if a method is provided and has no `TODO` comments within the method definition, you may not modify that method.

  - **Do not modify the test code.** This includes any input or output files utilized by the test code.

  - You MAY add additional members, methods, and classes as needed to the code.

  - You MAY add comments to clarify code for yourself. You can add comments to already defined methods if you want.

  - You MAY change a `return` statement in a method with a `TODO` comment as needed. (You may *not* change the return type in the method declaration, however.)

  - Remove the `TODO` comments when you are done. This removes them from the "Tasks" view in Eclipse. If you want to keep the comment around, you can change the text `TODO` to `DONE` instead.

To receive full credit on any homework assignment, you must:

  - **Pass all of the unit tests remotely.** See the [Homework Testing](/guides/homework/homework-testing.html) guide detailed steps. You will not receive full points if you are passing the tests locally but not remotely.

  - **Commit your work often.** Some assignments require a minimum number of commits! Consider making a commit after you complete every `TODO` in the code or after you pass a new test. <i class="fas fa-star has-text-warning"></i>

  - **Avoid warnings.** Some assignments require the code to compile with no warnings to earn full points. Try to make sure your code is warning-free in Eclipse before testing your code remotely!

  - **Follow the `TODO` directions.** For example, if the `TODO` comment stated you must use a `HashSet` and your code does not, you could lose points even if you are passing all of the unit tests.

  - **Properly submit your homework on time.** Remember, there are [no late homework](/syllabus.html#late-policy) submissions unless you apply for a [policy exception](/syllabus.html#policy-exceptions).

Post on [CampusWire]({{ site.data.info.links.forums.link }}) if you have any questions regarding what must be done for a homework assignment or a question about your homework grade.
