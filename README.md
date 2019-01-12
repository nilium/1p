# 1p

1Password fuzzy-finder utility script.

## Install

Download or clone the 1p script into your PATH.

In addition, the following software is required for 1p to function
normally:

- op: <https://support.1password.com/command-line-getting-started/>
- jq: <https://stedolan.github.io/jq/>
- fzf: <https://github.com/junegunn/fzf>
- fex: <https://github.com/jordansissel/fex>
- pbcopy or xclip: Clipboard tools.

With the exception of op, all of this software can be installed using
`xbps-install`:

    # xbps-install jq fzf fex xclip

Optionally, you can use xsel instead of xclip (it's the last resort in
the to_clipboard functon), but it's not recommended.

## Usage

Prior to using 1p, you must sign in to at least one account using `op
signin`.

```
Usage: 1p [-h|--help] [-1] [-b|-p|-c|-u|-o|-U|-j] [ACCOUNT] [QUERY...]

Searches a 1Password account (or all known accounts) for an item and
formats the item's username, password, and OTP (optional).

If -1 is passed, 1p will return as soon as it's found a match instead of
presenting an interactive fzf window. This must be the first argument.

In addition, you can pass a format specifier before the account name. By
default, the formatter is -H (clipboard).

FORMATS
-H      Print the username (and OTP, if possible) and copy the password
        to the clipboard using pbcopy.
-u      Username.
-p      Password.
-o      OTP.
-c      Username:password (colon-separated).
-b      Basic authentication. Used in HTTP authentication.
-U      1Password item UUID.
-j      1Password item JSON.
```
