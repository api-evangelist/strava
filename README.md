# Strava

Strava is a popular fitness tracking app and social network for runners, cyclists, swimmers, and athletes across 200+ sport types. The Strava API enables developers to access athlete profiles, activities, segments, routes, clubs, gear, and time-series data streams. OAuth 2.0 provides granular scope-based access control. Rate limits: 100 requests/15 minutes, 1000/day.

**Human URL:** [https://developers.strava.com/](https://developers.strava.com/)  
**Base URL:** `https://www.strava.com/api/v3`

## Links

- [Developer Portal](https://developers.strava.com/)
- [API Documentation](https://developers.strava.com/docs/reference/)
- [Authentication](https://developers.strava.com/docs/authentication/)
- [Getting Started](https://developers.strava.com/docs/getting-started/)
- [Rate Limits](https://developers.strava.com/docs/rate-limits/)
- [Webhooks](https://developers.strava.com/docs/webhooks/)
- [Community Forum](https://communityhub.strava.com/developers)
- [App Registration](https://www.strava.com/settings/api)
- [Terms of Service](https://www.strava.com/legal/api)

## APIs

### Strava API

The Strava API v3 provides access to athlete profiles, activities, segments, routes, clubs, gear, and time-series data streams. Uses OAuth 2.0 authorization code flow with fine-grained scopes.

- [OpenAPI Spec](openapi/strava-openapi.yml)
- [Documentation](https://developers.strava.com/docs/reference/)

## Artifacts

### OpenAPI Specifications

| File | Description |
|---|---|
| [strava-openapi.yml](openapi/strava-openapi.yml) | Strava API v3 — athletes, activities, segments, routes, clubs, gear, streams |

### JSON Schema

| File | Description |
|---|---|
| [strava-activity-schema.json](json-schema/strava-activity-schema.json) | JSON Schema for Strava activity objects |

### JSON Structure

| File | Description |
|---|---|
| [strava-activity-structure.json](json-structure/strava-activity-structure.json) | Field structure documentation for Strava activities |

### JSON-LD Context

| File | Description |
|---|---|
| [strava-context.jsonld](json-ld/strava-context.jsonld) | JSON-LD context mapping Strava vocabulary to schema.org ontology |

### Examples

| File | Description |
|---|---|
| [strava-list-activities-example.json](examples/strava-list-activities-example.json) | List athlete activities with pagination |
| [strava-get-athlete-example.json](examples/strava-get-athlete-example.json) | Get authenticated athlete profile |
| [strava-get-segment-leaderboard-example.json](examples/strava-get-segment-leaderboard-example.json) | Get segment leaderboard |

### Spectral Rules

| File | Description |
|---|---|
| [strava-rules.yml](rules/strava-rules.yml) | Spectral ruleset enforcing Strava API conventions |

### Naftiko Capabilities

#### Shared Definitions

| File | Description |
|---|---|
| [capabilities/shared/strava-api.yaml](capabilities/shared/strava-api.yaml) | Strava API — athletes, activities, segments, routes, gear, streams |

#### Workflow Capabilities

| File | Description |
|---|---|
| [capabilities/fitness-tracking.yaml](capabilities/fitness-tracking.yaml) | Fitness tracking and performance analysis workflow (13 tools) |

### Vocabulary

| File | Description |
|---|---|
| [vocabulary/strava-vocabulary.yml](vocabulary/strava-vocabulary.yml) | Strava domain vocabulary and fitness terminology |

## Tags

- Cycling
- Fitness
- Fitness Tracking
- Running
- Sports

## Maintainers

**FN:** Kin Lane  
**Email:** kin@apievangelist.com
