# git-private

A `bash` cli command to download Github releases from private repositories.

## Requirements

* [jq](https://stedolan.github.io/jq/) - a lightweight and flexible command-line JSON processor
* [curl](https://curl.haxx.se/) - command line tool and library for transferring data with URLs
* [GITHUB TOKEN](https://help.github.com/en/github/authenticating-to-github/creating-a-personal-access-token-for-the-command-line) created - a personal access token and use it in place of a password when performing Git operations over HTTPS with Git on the command line or the API.

## Example usage: 

```bash
$> git-private "${GITHUB_TOKEN}" "${git_tag}" myorg private-repo "${filename}" "${archive:?}/${filename}"
$> git-private ABCDEFGHIJ0123456789 v0.0.1 myorg private-repo foo.tar.gz /var/tmp/foo.tar.gz
```

## Original Fork (gist)

https://gist.github.com/nikosev/24d1a784aee16966c91a9ebe341b8388/revisions
