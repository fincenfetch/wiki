# Release Guidelines
### For new features and refactors

---

This process is for ensuring we have smooth transitions and a fully informed user base when we release new minor versions of the portal software to production.

#### Semantic versioning

**Minor Version Upgrade**

Example: Upgrading from **1.15.2** to **1.16.0**

**1** is the major version, **16** is the minor version, **0** is the patch version.

A minor version upgrade means we have breaking changes between front end and API code - usually due to large features being introduced, or a big refactor that changes the way the front end communicates with the API. 

Patch version updates can simply be categorized as bug fixes.

An example of a major release would be coding a brand new front end in a new framework.

For this write-up, we are only concerned about the practices around minor releases. Patches are simple, and non breaking. Major releases are a totally different animal - we can cross that bridge when we get to it.

---

#### Step 1

Define a milestone.

A milestone is simply a label named as the next semantic version with a **due date**. We can mark PRs with a milestone label - indicating that we intend to include the PR in that version.

We should only mark a PR with a milestone label if we expect that the project will be completed by the **due date**. If not, then it should be included in the next release after.

#### Step 2

The three day rule.

Once the **due date** has been reached, we separate what's been collected in the dev server for that release and deploy it to stage. The team should then focus on bug hunting in the current state of the code. During the next three business days, if bugs are found, they can simply be tested on dev initially, then merged into the rest of the milestone in stage - until the stage behaves as intended (bug free..hopefully).

#### Step 3

Customer preparedness.

Write user-friendly release notes based on the Github diff wiki and our Jira board. Send out a broadcast disclosing the new upgrades and changes coming so that our user base can become aware of them and adjust their processes accordingly.

We can use this 3 days to continue battle testing and bug hunting.

#### Step 4

Release and wait.

Merge stage to production and announce the release. Keep the pipeline clear for an additional 3 business days to ensure it remains easy to push quick bug fixes all the way through immediately following the production push.

---

In some cases, we may want to increase the amount of time between the **due date** and the **release date**. Sometimes, instead of 3 days, a week or more may be appropriate for larger merges. The *three day rule* simply refers to a reasonable amount of time we can spend preparing so that we don't accidentally jump the gun or release too early before everything can be thoroughly tested.

The plan is to start following this process on milestone **1.17.0**, **6/27/2024**

Thank you all!
