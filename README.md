# Delphi

Interpreting Small Language Models Across Time and Scale

# Setup

1. Clone this repo and submodules: `git clone https://github.com/delphi-suite/delphi.git --recurse-submodules`
2. make python 3.10 virtual env in `.venv`
3. install dependencies `pip install -r requirements.txt`
4. install the project in editable state `pip install -e .`
5. run tests `pytest`

## Submodule Setup
If you cloned without `--recurse-submodules`, you can still install the submodules later with:
```bash
git submodule init
git submodule update
```

# Formatting

We're using black & isort to format the code. To make sure your changes adhere to the rules:

1. follow setup instructions above
2. install pre-commit `pre-commit install`
3. install recommended vscode extensions

When you save a file vscode should automatically format it. Otherwise, pre-commit will do that, but you will need to add the changes and commit again.

# Pull Requests

1. make a branch
   - if it relates to an existing issue
     - go to the issue page and click _Create a branch_ under _Development_
     - if the default name is not very long, keep it; otherwise, make it shorter, but keep the issue number in the front
   - otherwise pick a short but descriptive name, a few hyphen-separated-words
2. make your changes
   - include unit tests
   - update README if needed
   - if new huggingface datasets/models are added to testing, increment the cache number in `.github/workflows/checks.yml`
3. make a pull request
   - if it isn't ready for review yet, mark it as draft
   - check if CI is passing
   - if the change is big, try to keep the commit history clean using interactive rebase
   - don't push more often than it's needed, we're running github actions on a free tier
   - if there were any changes to the main branch, rebase on top of it
   - explain the change
     - provide short description; focus on things that were not mentioned in the relevant issue
     - comment important sections of the code in _Files changed_ tab
   - when it's ready, add the relevant stakeholders as reviewers
4. after the comments are resolved and PR is approved, merge it using _Squash and merge_
