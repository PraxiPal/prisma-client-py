# usage for praxipal


## build and deployment

after you have the local dev setup working


in `src/prisma/__init__.py` change __version__ to the version you want to build. you can add .post1, .post2, etc. to the end of the version if a version is broken.

- `pip install -U -r pipelines/requirements/dev.txt`
- `python setup.py sdist bdist_wheel`
- `export TWINE_USERNAME=azure`
- `export TWINE_PASSWORD=<your PAT>`
- `twine upload --repository-url https://pkgs.dev.azure.com/praxipal/_packaging/praxipal/pypi/ dist/*`