# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to
[Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [Unreleased](https://github.com/JuptiterOne/graph-jira/compare/v1.9.8...HEAD)

### Added

- Added support for Jira API Version 2 (Jira Data Center)
- Added support for specifying the port in the `jiraHost` configuration value
  (i.e. `example.com:8080`)
- Added optional bulk ingestion feature to allow for collecting every single
  Issue in a Jira project. This is activated by setting
  `config.bulkIngestIssues: true`.
- Added `Issue` class to `jira_issue` entities
- Added error handling for Issue ingestion to avoid one bad Issue causing the
  step to fail
- Added retry functionality that respects Jira `Retry-After` header

### Changed

- Process issues and users per page instead of fetching all before processing

### Fixed

- Fix bug limiting per-project issue ingestion to 500 issues
- Fix bug limiting issues page size to 50

## [2.1.3] - 2021-08-17

### Removed

- Removed default `jira_user.email` property of `donotemail@example.com`

## [2.1.2] - 2021-08-12

### Added

- an `IntegrationProviderAuthorizationError` will be thrown on 403 responses to
  the `getUsers` endpoint.

## [2.1.1] - 2021-08-12

### Fixed

- Do not throw an error when a issue creator or reporter user is no longer in
  this Jira instance.

## [2.1.0] - 2021-08-12

### Fixed

- Only ingest `issues` from projects specified in the integration config.

## [2.0.0] - 2021-08-11

### Changed

- Rewrite on new SDK.
- Loosened the hostname validating regex to allow example.atlassian.net/jira

## [1.11.4] - 2021-07-027

### Changed

- Loosened the hostname validating regex to allow example.atlassian.net/jira

## [1.11.0] - 2021-06-04

- Add the functionality to create an issue with a specific class.

## [1.10.0] - 2021-05-21

### Added

- Ingestion for all Jira custom field types.

### Changed

- Validate `projects` config variable in `invocationValidation` and expose
  better errors.

## [1.9.8](https://github.com/github.com/JuptiterOne/graph-jira/compare/v1.9.7...v1.9.8) - 2020-09-18

### Changed

- Validate `projects` config variable in `invocationValidation` and expose
  better errors.