# git-private

A `bash` cli command to download Github releases from private repositories.

## Requirements

* [jq](https://stedolan.github.io/jq/) - a lightweight and flexible command-line JSON processor
* [curl](https://curl.haxx.se/) - command line tool and library for transferring data with URLs
* [ENV:GITHUB_TOKEN](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) created - a personal access token and use it in place of a password when performing Git operations over HTTPS with Git on the command line or the API.

## Example usage: 

Securely set the `GITHUB_TOKEN` in the ENV. Then execute `git-private`

```bash
$> export GITHUB_TOKEN=${GITHUB_TOKEN} 
$> git-private "${git_tag}" myorg private-repo "${filename}" "${archive:?}/${filename}"
```

Reference: https://security.stackexchange.com/q/20282

###  less secure option

You can pass the ENV directly on the same line, but this **will end up in the process list, exposing your `GITHUB_TOKEN`** to other users on the system.

```bash
GITHUB_TOKEN=ABCDEFGHIJ0123456789 git-private v0.0.1 myorg private-repo foo.tar.gz /var/tmp/foo.tar.gz
```

## Download & Install

```bash
curl --silent --show-error --no-buffer --request GET https://raw.githubusercontent.com/shadowbq/git-private/master/git-private --output git-private
chmod +x ./git-private
(sudo) mv ./git-private /usr/local/bin/.
```

## Original Fork (gist)

https://gist.github.com/nikosev/24d1a784aee16966c91a9ebe341b8388/revisions
