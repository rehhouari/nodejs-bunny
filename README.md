# nodejs-bunny


run bun instead of nodejs, npm, pnpm, and yarn.

## Install

```sh
makepkg --printsrcinfo > .SRCINFO
makepkg -si
```

## Why

to make it possible to install arch packages that require nodejs, npm, pnpm, or yarn without having to install any of those.

## Lets address the rabbit in the room

<img src="https://i.imgur.com/WP8NkiF.png" width="150px"/>

### Bugs

This is just an alias, it doesn't add any compatibility layer
See: [bun's nodejs-compat page](https://bun.com/docs/runtime/nodejs-compat)
