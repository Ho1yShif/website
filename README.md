# Sure Marketing Site

This is the marketing site for [Sure](https://sure.am), an OS for your personal finances.

## Local Development Setup

### Requirements

- Ruby 3.4.9 (see `.ruby-version`)
- PostgreSQL >9.3 (ideally, latest stable version)

After cloning the repo, the basic setup commands are:

```sh
cd website
cp .env.example .env
bin/setup
bin/rails db:seed
bin/dev
```

### AI-assisted development

We fully support AI-assisted development. As a team, we typically use [Cursor](https://cursor.com) for that. As such, we've included files with some rules for Cursor and Claude Code, along with prompts for certain tasks.

## Deploy

[![Deploy to Render](https://render.com/images/deploy-to-render-button.svg)](https://render.com/deploy?repo=https://github.com/we-promise/website)

`render.yaml` at the repo root defines the whole stack: the web service, a Sidekiq worker, Postgres, and two Key Value instances. Applying the Blueprint creates everything, including an environment group named `sure-secrets`.

No API key values live in the repo. The group declares its keys with `sync: false`, which Render ignores inside an environment group, so the keys start out unset. Set them in the Dashboard under the `sure-secrets` group.

## Copyright & license

Sure is distributed under an [AGPLv3 license](https://github.com/we-promise/sure/blob/main/LICENSE). "Sure" and the "S" logo are pending trademarks of Sure Finances, LLC
