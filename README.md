[![Create Release][release-badge]][release-url]
[![Import Labels][import-labels-badge]][import-labels-url]
[![Sync Labels][sync-labels-badge]][sync-labels-url]
[![PR AutoLabeler][autolabeler-badge]][autolabeler-url]
[![Assigner][assigner-badge]][assigner-url]

Notify slack channels when a production release has completed

### Inputs
#### `SLACK_WEBHOOK`
Slack webhook for notification action
Required.

#### `CHANNEL1`
First channel to notify

#### `CHANNEL2`
Second channel to notify

#### `CHANGELOG_CHANNEL`
Channel to send changelog to

#### `TOKEN`
GitHub token with API access
Required.

#### `MATRIX`
matrix of jobs to get status of from previous jobs
Required.

#### `FAILURE_ICON`
Icon for slack messages if to be used in future actions
Default: `:dumpsterfire:`

#### `SUCCESS_ICON`
Icon for slack messages if to be used in future actions
Default: `:white_check_mark:`

### Example usage
```yaml
      - name: action
        uses: CumulusDS/notify-release-end-action@v1
        with:
          TOKEN: ${{ secrets.TOKEN }}
          SLACK_WEBHOOK: ${{ secrets.SLACK_WEBHOOK }}
          MATRIX: ${{ toJson(needs.job.outputs.matrix) }}
```

[release-badge]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/release.yml/badge.svg
[release-url]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/release.yml
[import-labels-badge]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/labels_import.yml/badge.svg
[import-labels-url]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/labels_import.yml
[sync-labels-badge]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/labels_sync.yml/badge.svg
[sync-labels-url]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/labels_sync.yml
[autolabeler-badge]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/autolabeler.yml/badge.svg
[autolabeler-url]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/autolabeler.yml
[assigner-badge]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/assign.yml/badge.svg
[assigner-url]: https://github.com/CumulusDS/notify-release-end-action/actions/workflows/assign.yml
