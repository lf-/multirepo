# repo.py

A script to manage multiple Git repositories in a single directory.

## Usage

### `./repo.py init [--https]`

Clone all the tracked repositories. Use `--https` to clone with the https
protocol rather than using ssh.

### `./repo.py pull`

Runs a pull on all of the repositories to grab the latest version. This does
not perform merges. This only performs fast-forwards. If there is both new
content locally and remotely, pull will fail on the repository where this is
the case and you should pull or fetch+merge manually.

### `./repo.py forall <cmd>`

Runs the given shell command in each repository in parallel.

### `./repo.py status`

Checks whether all of the repos here are up to date: fetches and checks the
status of the master branch.

## Configuration

`repo.py` reads a list of repositories line-by-line from `repos.txt` relative
to where it is installed. Each line is `<The URL> <Local Name>`. Spaces are
supported in the local name.
