# S2I Builder with Play and Java

A very simple S2I builder which builds Java Play applications.

## Assembling

The assemble script runs `sbt stage` and moves the built artifacts to
`/opt/app-root/bin`.

It also supports incremental builds, so if there are already artifacts
available, they will be restored before calling the build command.

Directories saved during `save-artifacts`:

* `.ivy2`
* `target`
* `.sbt`

### Environment Variables

| Name       | Description              | Default value  |
| ----       | ------------------------ | -------------- |
| RUN_TESTS  | Runs "sbt test" if true  | false          |
| TASK_CLEAN | Runs "sbt clean" if true | false          |

## Running

To execute the built application the script will be searched under
`/opt/app-root/bin/bin` and if found executed. Customization can be done using
the `PLAY_START_PARAMETER` environment variable.

### Environment Variables

| Name                 | Description                         | Default value  |
| ----                 | ------------------------            | -------------- |
| PLAY_START_PARAMETER | Parameters passed to the run script |                |
| USER_NAME            | Username for the random uid         | play           |

## Ideas

* Runtime image
