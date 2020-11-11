# stack-templates

- Project templates for `stack new` http://haskellstack.org
- Easy Haskell projects bootstrap
- Powered by [Stack](http://haskellstack.org), [Docker](https://www.docker.com) and [Nix](https://nixos.org/nix/)

<img src="logo.jpg" alt="logo"/>

## Features

- Pure and declarative environments
- Auto-generated CI scripts
- Automated builds of thin Docker images
- [Ultimate Haskell IDE](https://github.com/tim2CF/ultimate-haskell-ide)

## Prerequisites

- Stack
- Docker

## Environment variables

Sometimes in projects are used dependencies from private repositories.
Docker and Nix can get access to private repositories through environment variables:

```bash
vi ~/.zshrc

# hex.pm access to private Erlang/Elixir dependencies
export HEX_API_KEY="SECRET"
# hex.pm organization
export HEX_ORGANIZATION="tkachuk-labs"
# ssh access to private git dependencies
export ROBOT_SSH_KEY="$(cat ~/.ssh/id_rsa | base64)"
# git user info
export GIT_AUTHOR_NAME="tkachuk-labs"
export GIT_AUTHOR_EMAIL="tkachuk.labs@gmail.com"
# optional appearance parameters
export VIM_BACKGROUND="light" # or "dark"
export VIM_COLOR_SCHEME="PaperColor" # or "jellybeans"
```

## Templates

- `nix-yesod` classic yesod application
- `nix-concur-replica` experimental live view application

## Usage

```bash
stack new hello-world \
  github:tkachuk-labs/nix-yesod \
  -p organization:tkachuk-labs \
  -p env-prefix:HELLO_WORLD

cd ./hello-world

git init

chmod a+x ./nix/*.sh

./nix/shell.sh

stack test

vi .
```

## Known issues

- In some cases Postgres can't use local `./postgres` directory because of permission restrictions. The fix is to manually remove directory with `rm -rf ./postgres`, and rerun command which caused the issue. Nix will create directory again with proper permissions.
- Ultimate Haskell IDE has some [known issues](https://github.com/tim2CF/ultimate-haskell-ide#known-issues) as well.

<br>
<p align="center">
  <tt>
    Made with ❤️ by
    <a href="https://tkachuklabs.gitlab.io" target="_blank">tkachuk.labs</a>
  </tt>
</p>
