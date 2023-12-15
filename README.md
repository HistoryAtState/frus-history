# History of the Foreign Relations Series

[![exist-db CI](https://github.com/HistoryAtState/frus-history/actions/workflows/build.yml/badge.svg)](https://github.com/HistoryAtState/frus-history/actions/workflows/build.yml)

Source data for [History of the Foreign Relations Series](https://history.state.gov/historicaldocuments/frus-history)

## Build

1. Single `xar` file: The `collection.xconf` will only contain the index, not any triggers!

    ```shell
    ant
    ```

    1. Since Releases have been automated when building locally you might want to supply your own version number (e.g. `X.X.X`) like this:

    ```shell
    ant -Dapp.version=X.X.X
    ```
<!-- 
2. DEV environment: The replication triggers for the producer server are enabled in  `collection.xconf` and point to the dev server's replication service IP.

    ```shell
    ant xar-dev
    ```

3. PROD environment: Same as in 2. but for PROD destination

    ```shell
    ant xar-prod
    ``` -->

## Release

Releases for this data package are automated. Any commit to the `master`` branch will trigger the release automation.

All commit message must conform to [Angular Commit Message Conventions](https://github.com/angular/angular.js/blob/master/DEVELOPERS.md#-git-commit-guidelines) to determine semantic versioning of releases, please adhere to these conventions, like so:

| Commit message  | Release type |
|-----------------|--------------|
| `fix(pencil): stop graphite breaking when too much pressure applied` | Patch Release |
| `feat(pencil): add 'graphiteWidth' option` | ~~Minor~~ Feature Release |
| `perf(pencil): remove graphiteWidth option`<br/><br/>`BREAKING CHANGE: The graphiteWidth option has been removed.`<br/>`The default graphite width of 10mm is always used for performance reasons.` | ~~Major~~ Breaking Release |

When opening PRs commit messages are checked using commitlint.