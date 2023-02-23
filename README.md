# [aliasman](https://github.com/BeyondCodeBootcamp/aliasman)

> Love your *alias*es again! 🥸

A cross-shell (POSIX-compliant) _alias_ manager for `bash`, `zsh`, and `fish`

```sh
# short form
aliasman gc 'git commit -m'

# or long form
aliasman alias gc='git commit -m'
```

-   [What's an alias?](#whats-an-alias)
-   [Install](#install)
-   [Usage](#usage)
-   [Imagine the Possibilities!](#imagine-the-possibilities)
-   [Common Aliases](#common-aliases)

## What's an _alias_?

An _alias_ is just shorthand for a shell function.

Take a long command like this:

```sh
git commit -m "feat: new feature"
```

And turn it into a short command, like this:

```sh
gc "feat: new feature"
```

(that would be `aliasman gc 'git commit -m'`)

## Install

**Mac**, **Linux** via [webi](https://webinstall.dev/) (<https://webinstall.dev/aliasman>):

```sh
curl -sS https://webi.sh/aliasman | sh
source ~/.config/envman/PATH.env
```

**GitHub Releases**:

```sh
# pick version
my_version="v1.1.0"

# download and unpack
curl -o "aliasman-${my_version}.tar.gz" \
    -fL "https://github.com/BeyondCodeBootcamp/aliasman/archive/refs/tags/${my_version}.tar.gz"
tar xvf "aliasman-${my_version}.tar.gz"

# install to somewhere in your PATH
mkdir -p ~/bin
mv ./aliasman-*/aliasman ~/bin/
```

## Usage

```txt
USAGE:
    aliasman [FLAGS] [--] <aliasname>[=][command] [flags, opts, args, pipes, etc]

FLAGS:
    -d, --delete                     Delete by aliasname
    -e, --edit                       Open ~/.config/envman/alias.sh for editing
        --help                       Prints help information
    -V, --version                    Prints version information

EXAMPLES:
    Add or replace (short):
        aliasman ll 'lsd -lAhF'
    or (long):
        aliasman alias ll='lsd -lAhF'

    View current:
        aliasman ll

    Delete:
        aliasman -d ll

    Common Aliases:
        aliasman cat 'bat --style=plain'
        aliasman curl 'curlie'
        aliasman ls 'lsd -F'
        aliasman la 'lsd -AF'
        aliasman ll 'lsd -lAhF'
        aliasman tree 'lsd -F --tree'
        aliasman xrnd 'xxd -l24 -ps /dev/urandom'

FILES:

    ~/.bashrc
    ~/.config/envman/alias.env
    ~/.config/envman/load.sh
    ~/.config/envman/load.fish
    ~/.config/fish/config.fish
    ~/.profile
    ~/.zshrc

LIMITATIONS:

    You may use single quotes around the alias definition, like so:

        # Generate 24 random bytes, url-safe base64-encoded
        aliasman rnd 'xxd -l24 -ps /dev/urandom |
                xxd -r -ps |
                base64 |
                tr -d = |
                tr + - |
                tr / _'

    However, the use of single quotes as part of flags, options, and arguments
    is not yet supported. Neither are newlines.
```

## Imagine the possibilities!

1. What if you could quickly create a _command_, `ll`, \
   that does the work of `ls -lAhF`!?
2. Set an _alias_ to do just that!

    ```sh
    # short form
    aliasman ll 'ls -lAhF'

    # long form
    # (copy/paste from an alias file)
    aliasman alias ll='ls -lAhF'
    ```

3. Reload your alias config (or open a _new terminal_)
    ```sh
    source ~/.config/envman/alias.env
    ```
4. Use it!
    ```sh
    ll
    ```
    ```text
    drwxr-xr-x aj wheel 416 B  Thu Feb  9 02:08:39 2023 📂 .git/
    .rwxr-xr-x aj staff 6.2 KB Thu Feb  9 01:36:30 2023 💻 aliasman*
    .rw-r--r-- aj wheel  16 KB Wed Feb  8 21:51:06 2023 🔑 LICENSE
    .rw-r--r-- aj wheel 1.4 KB Thu Feb  9 01:47:13 2023 📄 README.md
    ```

## Common Aliases

Use *alias*es to make other tools you find around [webi](https://webinstall.dev) even _more_ convenient ⚡️ (and powerful 💪).

```sh
aliasman cat 'bat --style=plain'

aliasman curl 'curlie'

aliasman diffy 'diff -y --suppress-common-lines'

aliasman gc 'git commit -m'
aliasman gri 'git rebase -i'

aliasman la 'lsd -AF'
aliasman ll 'lsd -lAhF'
aliasman ls 'lsd -F'

aliasman rgi 'rg -i'

aliasman tree 'lsd -F --tree --group-dirs=last'

# random password generator
aliasman rnd 'xxd -l24 -ps /dev/urandom'
```
