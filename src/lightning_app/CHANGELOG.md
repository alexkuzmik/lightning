# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](http://keepachangelog.com/en/1.0.0/).


## [UnReleased] - 2022-MM-DD

### Added

- Add `load_state_dict` and `state_dict` ([#14100](https://github.com/Lightning-AI/lightning/pull/14100))


- Add `--secret` option to CLI to allow binding Secrets to app environment variables when running in the cloud ([#14612](https://github.com/Lightning-AI/lightning/pull/14612))


### Changed

-


### Fixed

-


## [0.6.2] - 2022-09-21

### Changed

- Improved Lightning App connect logic by disconnecting automatically ([#14532](https://github.com/Lightning-AI/lightning/pull/14532))
- Improved the error message when the `LightningWork` is missing the `run` method ([#14759](https://github.com/Lightning-AI/lightning/pull/14759))
- Improved the error message when the root `LightningFlow` passed to `LightningApp` is missing the `run` method ([#14760](https://github.com/Lightning-AI/lightning/pull/14760))

### Fixed

- Fixed a bug where the uploaded command file wasn't properly parsed ([#14532](https://github.com/Lightning-AI/lightning/pull/14532))
- Fixed an issue where custom property setters were not being used `LightningWork` class ([#14259](https://github.com/Lightning-AI/lightning/pull/14259))
- Fixed an issue where some terminals would display broken icons in the PL app CLI ([#14226](https://github.com/Lightning-AI/lightning/pull/14226))


## [0.6.1] - 2022-09-19

### Added

- Add support to upload files to the Drive through an asynchronous `upload_file` endpoint ([#14703](https://github.com/Lightning-AI/lightning/pull/14703))

### Changed

- Application storage prefix moved from `app_id` to `project_id/app_id` (#14583)
- LightningCloud client calls to use keyword arguments instead of positional arguments (#14685)

### Fixed

- Making `threadpool` non-default from LightningCloud client  (#14757)
- Resolved a bug where the state change detection using DeepDiff won't work with Path, Drive objects (#14465)
- Resolved a bug where the wrong client was passed to collect cloud logs (#14684)
- Resolved the memory leak issue with the Lightning Cloud package and bumped the requirements to use the latest version (#14697)
- Fixing 5000 log line limitation for Lightning AI BYOC cluster logs (#14458)
- Fixed a bug where the uploaded command file wasn't properly parsed (#14532)
- Resolved `LightningApp(..., debug=True)` (#14464)


## [0.6.0] - 2022-09-08

### Added

- Introduce lightning connect ([#14452](https://github.com/Lightning-AI/lightning/pull/14452))
- Adds `PanelFrontend` to easily create complex UI in Python ([#13531](https://github.com/Lightning-AI/lightning/pull/13531))
- Add support for `Lightning App Commands` through the `configure_commands` hook on the Lightning Flow and the `ClientCommand`  ([#13602](https://github.com/Lightning-AI/lightning/pull/13602))
- Add support for Lightning AI BYOC cluster management ([#13835](https://github.com/Lightning-AI/lightning/pull/13835))
- Add support to see Lightning AI BYOC cluster logs ([#14334](https://github.com/Lightning-AI/lightning/pull/14334))
- Add support to run Lightning apps on Lightning AI BYOC clusters ([#13894](https://github.com/Lightning-AI/lightning/pull/13894))
- Add support for listing Lightning AI apps ([#13987](https://github.com/Lightning-AI/lightning/pull/13987))
- Adds `LightningTrainingComponent`. `LightningTrainingComponent` orchestrates multi-node training in the cloud ([#13830](https://github.com/Lightning-AI/lightning/pull/13830))
- Add support for printing application logs using CLI `lightning show logs <app_name> [components]` ([#13634](https://github.com/Lightning-AI/lightning/pull/13634))
- Add support for `Lightning API` through the `configure_api` hook on the Lightning Flow and the `Post`, `Get`, `Delete`, `Put` HttpMethods ([#13945](https://github.com/Lightning-AI/lightning/pull/13945))
- Added a warning when `configure_layout` returns URLs configured with http instead of https ([#14233](https://github.com/Lightning-AI/lightning/pull/14233))
- Add `--app_args` support from the CLI ([#13625](https://github.com/Lightning-AI/lightning/pull/13625))

### Changed

- Default values and parameter names for Lightning AI BYOC cluster management ([#14132](https://github.com/Lightning-AI/lightning/pull/14132))
- Run the flow only if the state has changed from the previous execution ([#14076](https://github.com/Lightning-AI/lightning/pull/14076))
- Increased DeepDiff's verbose level to properly handle dict changes ([#13960](https://github.com/Lightning-AI/lightning/pull/13960))
- Setup: added requirement freeze for next major version ([#14480](https://github.com/Lightning-AI/lightning/pull/14480))

### Fixed

- Unification of app template: moved `app.py` to root dir for `lightning init app <app_name>` template ([#13853](https://github.com/Lightning-AI/lightning/pull/13853))
- Fixed an issue with `lightning --version` command ([#14433](https://github.com/Lightning-AI/lightning/pull/14433))
- Fixed imports of collections.abc for py3.10 ([#14345](https://github.com/Lightning-AI/lightning/pull/14345))

## [0.5.7] - 2022-08-22

### Changed

- Release LAI docs as stable ([#14250](https://github.com/Lightning-AI/lightning/pull/14250))
- Compatibility for Python 3.10

### Fixed

- Pinning starsessions to 1.x ([#14333](https://github.com/Lightning-AI/lightning/pull/14333))
- Parsed local package versions ([#13933](https://github.com/Lightning-AI/lightning/pull/13933))


## [0.5.6] - 2022-08-16

### Fixed

- Resolved a bug where the `install` command was not installing the latest version of an app/component by default ([#14181](https://github.com/Lightning-AI/lightning/pull/14181))


## [0.5.5] - 2022-08-9

### Deprecated

- Deprecate sheety API ([#14004](https://github.com/Lightning-AI/lightning/pull/14004))

### Fixed

- Resolved a bug where the work statuses will grow quickly and be duplicated ([#13970](https://github.com/Lightning-AI/lightning/pull/13970))
- Resolved a bug about a race condition when sending the work state through the caller_queue ([#14074](https://github.com/Lightning-AI/lightning/pull/14074))
- Fixed Start Lightning App on Cloud if Repo Begins With Name "Lightning" ([#14025](https://github.com/Lightning-AI/lightning/pull/14025))


## [0.5.4] - 2022-08-01

### Changed

- Wrapped imports for traceability ([#13924](https://github.com/Lightning-AI/lightning/pull/13924))
- Set version as today ([#13906](https://github.com/Lightning-AI/lightning/pull/13906))

### Fixed

- Included app templates to the lightning and app packages ([#13731](https://github.com/Lightning-AI/lightning/pull/13731))
- Added UI for install all ([#13732](https://github.com/Lightning-AI/lightning/pull/13732))
- Fixed build meta pkg flow ([#13926](https://github.com/Lightning-AI/lightning/pull/13926))

## [0.5.3] - 2022-07-25

### Changed

- Pruned requirements duplicity ([#13739](https://github.com/Lightning-AI/lightning/pull/13739))

### Fixed

- Use correct python version in lightning component template ([#13790](https://github.com/Lightning-AI/lightning/pull/13790))

## [0.5.2] - 2022-07-18

### Added

- Update the Lightning App docs ([#13537](https://github.com/Lightning-AI/lightning/pull/13537))

### Changed

- Added `LIGHTNING_` prefix to Platform AWS credentials ([#13703](https://github.com/Lightning-AI/lightning/pull/13703))
