# stack-templates

- Project templates for `stack new` http://haskellstack.org
- Easy Haskell projects bootstrap
- Powered by [Stack](http://haskellstack.org), [Docker](https://www.docker.com) and [Nix](https://nixos.org/nix/)

<img src="logo.jpg" alt="logo"/>

## Features

- Pure and declarative environments
- Auto-generated CI scripts
- Automated builds of thin Docker images
- [Ultimate Haskell IDE](https://github.com/tkachuk-labs/ultimate-haskell-ide)

## Prerequisites

- Docker

- Stack (with following `~/.stack/config.yaml`)

```yaml
templates:
  params:
    author-email: tkachuk.labs@gmail.com
    author-name: Ilja Tkachuk
    category: Data
    github-username: tkachuk-labs
    organization: tkachuk-labs
```

## Templates

- `nix-yesod` classic yesod application
- `nix-concur-replica` experimental live view application

## Usage

```bash
stack new hello-world github:tkachuk-labs/nix-yesod -p env-prefix:HELLO_WORLD

cd ./hello-world

git init

chmod a+x ./nix/*.sh

./nix/shell.sh

stack test --fast

vi .
```

## Known issues

- In some cases Postgres can't use local `./postgres` directory because of permission restrictions. The fix is to manually remove directory with `rm -rf ./postgres`, and rerun command which caused the issue. Nix will create directory again with proper permissions.
- Ultimate Haskell IDE has some [known issues](https://github.com/tkachuk-labs/ultimate-haskell-ide#known-issues) as well.

<br>
<p align="center">
  <tt>
    Made with ❤️ by
    <a href="https://tkachuklabs.gitlab.io" target="_blank">tkachuk.labs</a>
  </tt>
</p>
