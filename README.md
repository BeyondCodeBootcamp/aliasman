# [aliasman](https://github.com/BeyondCodeBootcamp/aliasman)

An alias manager for bash, zsh, and fish

## Install

```sh
curl -sS https://webi.sh/aliasman | sh
source ~/.config/envman/PATH.env
```

## Usage

```txt
USAGE

    # Set alias
    aliasman [--] <aliasname> <command> [flags, opts, args, pipes, etc]

    # Check alias
    aliasman [--] <aliasname>

    # Delete alias
    aliasman -d [--] <aliasname>

    aliasman help
    aliasman version

EXAMPLES

    aliasman curl curlie
    aliasman ls lsd -F
    aliasman la lsd -AF
    aliasman ll lsd -lAhF
    aliasman tree lsd -F --tree
    aliasman xrnd xxd -l24 -ps /dev/urandom

FILES

    ~/.bashrc
    ~/.config/envman/alias.env
    ~/.config/envman/load.sh
    ~/.config/envman/load.fish
    ~/.config/fish/config.fish
    ~/.profile
    ~/.zshrc

NOTES

    You may use single quotes around the alias definition, like so:

        # generate 24 random bytes, url-safe base64-encoded
        aliasman rnd 'xxd -l24 -ps /dev/urandom |
                          xxd -r -ps |
                          base64 |
                          tr -d = |
                          tr + - |
                          tr / _'

    However, the use of single quotes as part of flags, options, and arguments
    is not yet supported. Neither are newlines.
```
