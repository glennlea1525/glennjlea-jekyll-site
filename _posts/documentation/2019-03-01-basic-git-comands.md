---
layout: article
title: A list of basic git commands
description: As an online reference, I listed the basic git commands that I frequently use in no particular order. I update this list as required.
date: '2019-03-01'
categories: documentation
---
# {{ page.title }}

Some basic Git commands.

## File classifications

- `Tracked` - Any file already in the repository or staged in the index.
- `Ignored` - Any file that is declared invisible or ignored in the repository though present in the working directory.
- `Untracked` - Any file that is neither tracked nor ignored.

## Renaming a branch

This is from **[Renaming a branch](https://docs.github.com/en/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/renaming-a-branch)** on Github. Refer to this link for the authoritative instructions.

1. Go to the main page of the repository.
1. Click the **Branches** icon.
1. Click the **Edit** icon to the right of the branch to be renamed.
1. Type a new name for the branch in the **Rename this branch** field.
1. Review the messages. They show the implications of renaming this branch.
1. Click **Rename branch**. The branch is now renamed.
1. Run the following set of commands on a local clone of the repository to update the name of the default branch:

```bash
$ git branch -m OLD-BRANCH-NAME NEW-BRANCH-NAME
$ git fetch origin
$ git branch -u origin/NEW-BRANCH-NAME NEW-BRANCH-NAME
$ git remote set-head origin -a
```
The branch is now renamed and a local clone has been updated.

## Git command list

<table>
  <colgroup>
    <col width="50%" />
    <col width="50%" />
  </colgroup>
  <thead>
    <tr>
      <th>Command</th>
      <th>Description</th>
    </tr>
  </thead>
  <tbody>
    <tr>
      <td>$ git</td>
      <td>Git Help.</td>
    </tr>
    <tr>
      <td>$ git version</td>
      <td>Provides version of git.</td>
    </tr>
    <tr>
      <td>$ git init</td>
      <td>Create a repository. Create a directory, such as /example. cd to this directory and run git init to turn the directory into a repository.</td>
    </tr>
    <tr>
      <td>$ git add</td>
      <td>Staging a file. For example, run git add index.html to add this file to the new repository.</td>
    </tr>
    <tr>
      <td>$ git status</td>
      <td>Check the state of the repository. Shows which files need to be committed.</td>
    </tr>
    <tr>
      <td>$ git commit</td>
      <td>Commits a file to the remote repository.</td>
    </tr>
    <tr>
      <td>$ git commit - m "A comment added to the commit"</td>
      <td>Commits and adds comment.</td>
    </tr>
    <tr>
      <td>$ git commit --message</td>
      <td>Same as git commit -m.</td>
    </tr>
    <tr>
      <td>$ git commit --all</td>
      <td>Stages all known modified files and commits them.</td>
    </tr>
    <tr>
      <td>$ git log</td>
      <td>View comments.</td>
    </tr>
    <tr>
      <td>$ git checkout branch_name</td>
      <td>Switches to the branch provided in branch_name.</td>
    </tr>
    <tr>
      <td>$ git pull</td>
      <td>Pulls from origin repository to make the local repo up-to-date.</td>
    </tr>
    <tr>
      <td>$ git checkout -b new_branch_name</td>
      <td>Creates a new branch named new_branch_name.</td>
    </tr>
    <tr>
      <td>$ git rm filename</td>
      <td>Removes file from both repository and working directory.</td>
    </tr>
    <tr>
      <td>$ git commit - "Remove a file called filename"</td>
      <td>Same as git rm filename but adds a comment.</td>
    </tr>
    <tr>
      <td>$ git clone repository_directory new_repository_directory</td>
      <td>Makes a copy (a clone) of a repository</td>
    </tr>
    <tr>
      <td>$ git mv filename newfilename</td>
      <td>Moves a file to a new filename (same as renaming.</td>
    </tr>
    <tr>
      <td>$ git commit -m "renamed filename to newfilename"</td>
      <td>Renames a file.</td>
    </tr>
        <tr>
      <td>$ git remote prune origin</td>
      <td>Remove tracking references to the old branch name.</td>
    </tr>
  </tbody>
</table>
