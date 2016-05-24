# Camomile documentation

## Installation

```shell
bundle install
pip install ghp-import
```

## Warning

Do **not** edit `master` branch directly. Use `source` branch instead.

```shell
git checkout source
```

## Edition

```
bundle exec middleman server
```

[http://localhost:4567](http://localhost:4567) should automagically reflect the changes you make to `source/*`

## Deployment

Once you are happy with what you are seeing at [http://localhost:4567](http://localhost:4567) , you can deploy the documentation (from the `source` branch) with this:

```shell
bundle exec middleman build
export COMMIT_MESSAGE=""
ghp-import -n -p -m $COMMIT_MESSAGE -b master build
```

This will automagically commit and push the content of the `build` directory to the repository `master` branch -- served at [camomile-project.github.io](camomile-project.github.io).
