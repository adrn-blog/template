# adrian.pw blog post template

*Note: This is a fork of [dfm](https://github.com/dfm)'s blog post template. You probably want to check out [his template](https://github.com/dfm-io/template) instead!*

These are mostly notes to self.

## Creating a new repo

To create a new post, install [copier](https://copier.readthedocs.io):
```bash
python -m pip install pipx
pipx install copier
```

then run:
```bash
copier gh:adrn-blog/template post--URL_SLUG_FOR_POST
cd post--URL_SLUG_FOR_POST
git init .
python -m pip install pre-commit
pre-commit install
git add .
git commit -am "Initial commit"
```

This should push to a remote repo called `post--URL_SLUG_FOR_POST` under the `adrn-blog`
organization. [Create a new empty repository](https://github.com/organizations/adrn-blog/repositories/new) with the same name (post--URL_SLUG) (i.e., don't check any boxes!), and:
```bash
git remote add origin git@github.com:adrn-blog/post--URL_SLUG.git
git branch -M main
git push -u origin main
```

## Setting up Python environment

To set up your environment, in the root directory of the post repo, run:

```bash
python -m venv env
source env/bin/activate
python -m pip install -U pip
python -m pip install -U pip-tools
python -m piptools sync
```

To add new dependencies, add them to `requirements.in` then run

```bash
python -m piptools compile
python -m piptools sync
```
