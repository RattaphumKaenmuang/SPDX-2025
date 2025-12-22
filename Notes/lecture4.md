# Git
**An Open Source "Version Control" System**

## Branch
Developers create "branches" to develop and test new features before it is merged into the main, working branch, this merging action is intuitively called "merge". Allegedly not CI/CD-friendly.

Other than separating working code from a work-in-progress feature, branching out the code also provides the benefit of allowing multiple team members to develop at the same time with minimal worry about code conflicts.

### Merging
After each branch finishes its own respective task, the developer may attempt to merge said branch into the main branch. This aforementioned main branch may either be a "dev" branch which is the common main branch for developers, or an actual "main" branch which is the actual main branch conventionally facing the clients/users.

Merging can be done directly by a command or the UI, but conventionally in a team project you would file a "Pull Request" for your team to approve instead.

## Commit
And on every branch, the developers "commit" and create a checkpoint of the code every time a significant milestone is reached. All commits can (must) be named with a commit message.

## Gitignore
There are some files (mostly library-generated files or private credentials) which shouldn't be uploaded to the repository, these files can be blacklisted in a ".gitignore" file which can untrack the directories or files automatically.

## CLI Commands
### git status
* For checking the status of the local files in comparison to last commit
### git add [file_name]
* For staging changed files for the next commit
  * Can use . in place of file_name to add all changed files
### git commit -m [commit_message]
* For committing the staged changes onto the local branch
### git push [alias] [branch]
* Pushing the local committed changes onto the remote branch

# Pytest
* Everything related to the testing itself must start with "test"
  * test_transformation.py
  * def test_normalize_column()
* If the project files aren't all flattened (everything in the root directory) then add the following into pyproject.toml file somewhere

    ```
    [tool.pytest.ini_options]
    pythonpath = ["."]
    ```

    * After which, importing files will follow this pattern:
      * folder1.folder2.source_code_file