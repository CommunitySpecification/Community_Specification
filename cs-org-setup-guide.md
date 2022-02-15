# Setting up Community Specification for a GitHub Organization

## Overview and Scope

This guide describes the steps to take within GitHub to implement the [Community Specification 1.0](https://github.com/CommunitySpecification/1.0) license and governance process for a new project, where multiple specification documents can each be developed in their own repositories.

This is intended as a supplement and extension to the [Getting Started document](https://github.com/CommunitySpecification/1.0/blob/master/..Getting%20Started.md) included in the Community Specification 1.0 repo.

This guide assumes the following:

* You are creating a new specification, without pre-existing public content
* Your project has set up a GitHub organization account
* Your project might develop multiple specification documents in multiple repositories
* You have minimal experience with Git and GitHub
* You'll use the GitHub web interface to edit files for this initial setup process

Some modifications to the steps below might be needed if the assumptions above don't apply to you and your project.

This guide does _not_ address the following:

* reasons why a project might (or might not) decide to implement the Community Specification process
* legal interpretations of the Community Specification license or other aspects of its governance
* modifications that might be desirable when implementing Community Specification for a project with a pre-existing specification or community

## Setup Procedure

In the steps below, the following placeholders are used. Be sure to replace these with the applicable values for your project:

* **`MYORG`** -- your GitHub organization's account name
* **`MYSPEC`** -- your specification's repository name

### Objective

After completing the following steps, your project's GitHub organization will have the following repositories:

* `governance`: contains the Community Specification 1.0 license text and other documents
* `MYSPEC`: contains the substance of the first specification that you're developing
* You could create additional specification repositories with other names using the same process as for MYSPEC.

### Step 1: Setting up the "governance" Repository

1) **Fork the upstream Community Specification repo**:

  * Go to the Community Specification repo on GitHub: [https://github.com/CommunitySpecification/1.0](https://github.com/CommunitySpecification/1.0)
  * Click the "Fork" button in the upper right of the page
  * GitHub should ask you which organization you want to fork the repo into.
  * You should see MYORG listed -- if so, click on it.
  * If you didn't see MYORG listed, you may need to adjust the organization's settings -- go to the organization's main page and check the "People" tab to confirm who has ownership access.

2) **Adjust the repo's name to `governance`**:

  * When you forked the repo, it retained the name `1.0`; we'll want to change that.
  * On the GitHub page for your forked repo, click "Settings"
  * Under "Repository name", it will say "1.0"; change that to "governance" and click "Rename"

3) **Change the branch name from `master` to `main`**:

  * Click on "Settings", then select "Branches" on the left side of the page
  * One branch called `master` will be listed. Edit the name by clicking the pencil icon to the right of `master`, enter `main` for the new name, and click "Rename branch".

### Step 2: Adjust the "governance" Repository's files

The `MYORG/governance` repository now contains a copy of the original template Community Specification documents.

You'll want to make some changes to them, to fill in some of the template options, as well as to adjust some assumptions that they make.

For each of the following files, you'll take the following steps to make the changes described below:

* click on the filename in the `governance` repo
* on the file's page, click the Edit button (looks like a pencil on the right side of the screen)
* edit the file's text contents
* after editing the text, in the "Commit changes" box at the bottom:
  * in the first text box, fill in a short description with a few words, such as `Edited governance document`
  * in the second text box, where it says "Add an optional extended description...", add a DCO sign-off line with the following, using your name and email address: `Signed-off-by: NAME <EMAIL ADDRESS>`
  * make sure the "Commit directly to the `main` branch" button is selected
  * click the "Commit changes" button

Using the process above for each one, edit the files as follows:

* `2._Scope.md`:
  * Replace the first main sentence ("[Include a detailed description...") with a description of the substance of what the specification's scope will include.
  * The link to ISO's guidance (see page 5 of the linked PDF) may be useful in drafting the scope.
  * For an example, see [SPDX's Scope document](https://github.com/spdx/governance/blob/main/2._Scope.md).

* `3._Notices.md`:
  * Under "Code of Conduct", fill in the blank with names and email addresses for at least _two different individuals_ from the project who will be designated to receive Code of Conduct inquiries or issues.
  * Note that these should be individual persons, and not general mailing list addresses. Ideally select two or more people from different employers / organizations.
  * After filling in the blank, delete the following sentence ("[Ideally list two different individuals...")
  * Do not fill in the blanks for the remainder of the file, unless your organization is designating exclusions from the Community Specification License's patent license grant. If so, consult with your legal counsel about what should be filled in here.

* `4._License.md`:
  * Under "Specification License", change "repository" to "GitHub organization".
  * Under "Source Code License", the default license for software source code is MIT. If a license other than MIT will be used for software source code, then change each instance of `MIT` to the [SPDX License Identifier](https://spdx.org/licenses) for the chosen software license.

* `5._Governance.md`:
  * The Governance Policy document describes a default Working Group process which is generally usable by projects without modification.
  * You will want to review the process closely and confirm that your project community is comfortable with the proposed process.
  * If appropriate changes are desired, they can be reflected in edits to this document. However, it is strongly recommended _NOT_ to edit the principles reflected in Section 3 (Ways of Working).
    * An example of a heavily modified governance process can be seen in [SPDX's Governance Policy](https://github.com/spdx/governance/blob/main/5._Governance.md). The process document was modified here to reflect SPDX's pre-existing processes and team structures.
  * If you revise the contents of the policy, also change the title in the first line of the document, to replace "Community Specification" with "MYORG" in the name of the policy.

* `6._Contributing.md`:
  * As with `5._Governance.md` above, review this policy for the actual process of specification development and contributions, and make any appropriate changes for the way your project community will work.
  * If you revise the contents of the policy, also replace "Community Specification" with "MYORG" in the name of the policy.

* `.0_CS_Contributor_License_Agreement.md`:
  * In the title of the document (in the first line), change "Community Specification Contributor License Agreement 1.0" to "MYORG Contributor License Agreement 1.0".
  * Replace the first main sentence ("By making a Contribution...") with the following text: "By making a Contribution to a repository in the MYORG GitHub organization, I agree to the terms of the following documents located at https://github.com/MYORG/governance:"
  * If you changed the contents and names of the Governance Policy or the Contribution Policy as described in files 5 and 6 above, also change their names in the references under (b) and (c) of the Contributor License Agreement document.

* `Readme.md`:
  * Replace the generic Community Specification Readme file with a brief description of the project's governance repo, such as the following:

```
# MYORG Governance

This repo contains documents that describe the governance practices for the MYORG Working Group.

The MYORG Working Group oversees development of the MYORG materials in the [MYORG GitHub org](https://github.com/MYORG). Specifications developed by the MYORG Working Group are developed in their own repositories, and are subject to the licensing and governance policies described in this repo.

The MYORG Governance process is based on the [Community Specification model and license](https://github.com/CommunitySpecification/1.0) from the [Joint Development Foundation](https://www.jointdevelopment.org).
```

* `..Getting Started.md`:
  * Consider deleting this file (by clicking the trash can icon on the right side of the screen when viewing the file), since it will no longer be relevant after the repo is set up.

### Step 3: Create the MYSPEC repo

* Click the "+" button on the upper right of the GitHub page, and select "New repository"
* Make sure that "Owner" is set to MYORG, and fill in the MYSPEC name for "Repository name"
* Under "Description", fill in a short description of the specification in a few words
* Make sure "Public" is selected
* Under "Initialize this repository with:", select "Add a README file" and make sure the other options are left unchecked
* Click the "Create repository" button

### Step 4: Set up the starting files for the MYSPEC repo

* Edit the `README.md` file to add a brief description of the specification.
  * You will want to include a reference back to the governance repo, such as the following (making appropriate substitutions):

```
# MYSPEC Specification

This repo is used for collaboration and development of the MYSPEC specification.

The MYSPEC Specification is developed pursuant to the [MYORG Governance practices](https://github.com/MYORG/governance) and licensed pursuant to the [Community Specification License 1.0](hhttps://github.com/CommunitySpecification/1.0/blob/master/.0_CS_Contributor_License_Agreement.md).

Contributions to the MYSPEC Specification are required to be submitted pursuant to the [MYORG Contributor License Agreement 1.0](https://github.com/MYORG/governance/blob/main/.0_CS_Contributor_License_Agreement.md).
```

* Add a "LICENSE" file:
  * Click "Add file" => "Create new file"
  * For the filename, enter "LICENSE"
  * Fill in the following text:

```
The MYSPEC Specification is licensed pursuant to the Community Specification License 1.0, a copy of which is available at https://github.com/CommunitySpecification/1.0/blob/master/.0_CS_Contributor_License_Agreement.md.
```
  * Commit the new file as previously described.

* Create the starting template for your specification:
  * Click "Add file" => "Create new file"
  * For the filename, enter "Specification.md"
  * Copy the contents of the default specification template from [the Community Specification repo](https://raw.githubusercontent.com/CommunitySpecification/1.0/master/7._CS_Template.md), and paste it into the new file's text box
  * Adjust the default text to refer to your project and specification:
    * Delete the initial lines (everything prior to `## Title`)
    * Fill in the Title, Version and Status of the specification where indicated
    * Fill in the copyright blank with an appropriate copyright notice for your project
    * Under "Foreword":
      * **NOTE**: In the current version, there is a typo in the first paragraph under "Foreword". If the second sentence states "No party shall not be held responsible...", delete "not" so that it reads "No party shall be held responsible..."
      * Fill in the name of the specification working group where indicated.
      * Delete the lines referring to prior editions, if they do not apply to your specification.
      * In the next line ("Known patent licensing exclusions..."), replace "the specification's repository's Notices.md file" with "the Notices.md file in the MYORG governance repo".
      * In the next line ("Any feedback of questions...", fill in the blank with a link to the MYSPEC repo's issue submission URL.
    * The remainder of the document will contain the actual substance of your specification.
  * Commit the new file as previously described.

