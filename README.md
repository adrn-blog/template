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
copier copy gh:adrn-blog/template post--URL_SLUG_FOR_POST
cd post--URL_SLUG_FOR_POST
uv venv
uv sync
git init .
uv run pre-commit install
git add .
git commit -am "Initial commit"
```

We then want to push this blog post repo to a remote called `post--URL_SLUG_FOR_POST`
under the `adrn-blog` organization. [Create a new empty
repository](https://github.com/organizations/adrn-blog/repositories/new) with the same
name (post--URL_SLUG) (i.e. don't check any boxes!), and:
```bash
git remote add origin git@github.com:adrn-blog/post--URL_SLUG.git
git branch -M main
git push -u origin main
```

## Setting up Python environment

Your python environment is managed by `uv`, so you should be all set up after the
commands above. If you want to add a dependency, add it to the `pyproject.toml` file
under "dependencies" and then run:
```bash
uv sync
```
to update the environment.