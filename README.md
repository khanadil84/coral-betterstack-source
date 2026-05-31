# Better Stack Coral Source

A Coral source specification for Better Stack Uptime Monitoring.

This source allows Coral to query Better Stack resources using SQL.

## Features

Exposes the following tables:

* `betterstack.monitors` — Uptime monitors and status information
* `betterstack.incidents` — Incident history and status
* `betterstack.status_pages` — Status page configuration and metadata

## Requirements

Generate a Better Stack API token from:

**Better Stack → API & Terraform → Global API Tokens**

The token requires read access to Uptime resources.

## Installation

Add the source to Coral:

```bash
coral source add --file betterstack.yaml --interactive
```

When prompted, enter:

```text
BETTERSTACK_API_TOKEN
```

## Validation

Validate the source:

```bash
coral source lint betterstack.yaml
coral source test betterstack
```

## Example Queries

List monitors:

```sql
SELECT *
FROM betterstack.monitors
LIMIT 10;
```

Show monitor status:

```sql
SELECT
  attributes__pronounceable_name,
  attributes__status
FROM betterstack.monitors;
```

List incidents:

```sql
SELECT
  id,
  attributes__status,
  attributes__started_at
FROM betterstack.incidents;
```

View status pages:

```sql
SELECT *
FROM betterstack.status_pages;
```

## Repository

Source specification created for the Coral custom source ecosystem and community source catalog.
