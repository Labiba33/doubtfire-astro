---
title: Projects Endpoint - New Query Parameters
description: Documents new query parameters added to the GET /projects endpoint
---

## Overview

This document describes the new query parameters introduced to the `GET /projects`
endpoint as part of the cross-unit dashboard feature.

## Endpoint

`GET /projects`

## New Query Parameters

### `include_task_definitions`

| Property | Value   |
|----------|---------|
| Type     | Boolean |
| Required | No      |
| Default  | false   |

When set to `true`, the response will include task definitions for each
project's unit. Task definitions are exposed inside the `unit` object of
the project response.

**Example request:**
This was introduced to support the cross-unit dashboard, allowing the
frontend to display task definitions without making additional API calls.
Including task definitions improves response time compared to separate
requests (~200ms vs ~800ms).

### `include_inactive`

| Property | Value   |
|----------|---------|
| Type     | Boolean |
| Required | No      |
| Default  | false   |

When set to `true`, inactive projects are included in the response
alongside active ones.

**Example request:**
## Combined Usage

Both parameters can be used together:
## Related

- [Pull Request #100 - feature: new endpoint for crossunit team](https://github.com/thoth-tech/doubtfire-api/pull/100)