# stack-templates

Project templates for stack new http://haskellstack.org

<img src="logo.jpg" alt="logo"/>

## Prerequisites

- [Stack](http://haskellstack.org)
- [Docker](https://www.docker.com)

## Usage

```bash
stack new hello-world \
  github:tkachuk-labs/nix-app \
  -p organization:tkachuk-labs \
  -p env-prefix:HELLO_WORLD \
  --resolver lts-14.27

cd ./hello-world

chmod a+x ./*.sh

./nix-shell.sh

stack test

vi .
```

<br>
<p align="center">
  <tt>
    Made with ❤️ by
    <a href="https://tkachuklabs.com" target="_blank">tkachuk.labs</a>
  </tt>
</p>
