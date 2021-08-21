---
title: Project Functionality
navbar: Guides
layout: guides
key: 1.3

blurb: |
  <p>Each project grade is split into two components: functionality (passing tests) and design (passing code review). This guide details both the process for getting credit for project functionality.</p>
---

This guide assumes you have already [setup your project](project-setup.html) and [tested your project](project-testing.html). This includes making a release of your project that passes the verification process on Github.

## Eligibility
{: .page-header }

Before making a request, make sure your project is eligible to earn the functionality grade:

  - **Do you have credit for the functionality of the previous project?** You can check your grades on [Canvas]({{ site.data.info.links.canvas.link }}). If you are missing a grade you should already have, please reach out to us on [CampusWire]({{ site.data.info.links.forums.link }})

      *For example, if you are on project 3, you must already have a non-zero functionality grade for project 2. If you are on project 1, you can skip this check.*

  - **Are you working only 1 project ahead?**

      *For example, if you are on project 3, you must already have completed project 1 (both functionality and design) and have a non-zero functionality grade for project 2. If you are on project 1 or 2, you can skip this check.*

  - **Do you have a release for this project that passed the verification action on Github?** If not, see the [Creating Releases](project-testing.html#creating-releases) section of the testing guide.

If you answered yes to all of the above, you can request to have your functionality grade updated.

## Requesting Grade
{: .page-header }

**You only need to do this once per project.**

After verifying your project is eligible for the functionality grade, follow these steps:

  1. Browse to your private project repository on Github and click the "Actions" tab.

  2. Click on the "Request Project Grade" action on the side.

  3. Click the "Run workflow" button.

      a. Enter the project release, e.g. `v1.0.0`, that passed the tests.

      b. Enter `f`, `fun`, or `functionality` to indicate you are requesting a functionality grade.

  4. Wait for the action to finish running. When it is complete, click the "Request Project Grade" link until you see the run details.

  5. If the run was successful, click the link to visit the issue that was created. If everything worked properly, the issue should be assigned to a teacher assistant, have the `functionality` and `project#` labels, and belong to the `Project #` milestone (where `#` is a project number). It should also have information about your project release and expected grade.

  6. Follow the instructions on the issue. When done, click the "Reopen issue" button.

  7. Wait 2 business days. If you have not heard a response by then, double check your issue is "Open" and reach out privately on [CampusWire]({{ site.data.info.links.forums.link }}) with a link to your issue asking for a status update.

When the issue is closed by the instructor or teacher assistant, verify your grade was updated on Canvas.

*If the run was not successful, the log should state why. If you are unsure how to fix the problem, reach out privately on [CampusWire]({{ site.data.info.links.forums.link }}) with a link to your run asking for help.*

## Functionality Grading
{: .page-header }

The functionality grade is based on the created date of your **first passing release** on Github. This is *not* when you first passed those tests locally or a commit that passed those tests.

There is a **10% late penalty per week** that your project is late. For example, you will earn a 90% functionality grade if the first passing release is 1 day late. You will earn an 80% functionality grade if the first passing release is 8 days late.

See the [Schedule](schedule.html) for the functionality deadlines.
