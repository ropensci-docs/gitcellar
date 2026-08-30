# Download archives of GitHub repositories within an account

Download archives of GitHub repositories within an account

## Usage

``` r
download_organization_repos(
  organizations = NULL,
  extra_repos = NULL,
  keep = character(0),
  dest_folder = getwd()
)
```

## Arguments

- organizations:

  Account username(s) (vector)

- extra_repos:

  Named vector of extra repository names where names are account names.

- keep:

  a character vector of repository names to explicitly archive and
  download. If this vector is length zero, all account repositories are
  archived and downloaded.

- dest_folder:

  Where to save the folders with the archives.

## Details

You will need a [GitHub Personal Access
Token](https://usethis.r-lib.org/articles/git-credentials.html).

If `organizations` is a personal account username, the PAT needs to be
from that account.

As long as you're an owner of the organisation you're trying to back up,
absolutely no permissions are required for your PAT. You will only need
to add the `repos` scope if you wish to automatically include private
repositories in the list of repos to back up. Note however that there is
a workaround using the `extra_repos` argument, as documented below.

The reason why you might need `extra_repos` is if you want to download
archives of private repositories, while using a GitHub Personal Access
Token with no scope.

[GitHub documentation on
archives](https://docs.github.com/en/repositories/archiving-a-github-repository/backing-up-a-repository).

## Examples

``` r
if (FALSE) { # \dontrun{
download_organization_repos(c("maelle-test", "maelle-test"))
download_organization_repos("maelle-test", keep = "testy2") # only keep the testy2 repo
} # }
```
