# Strava GraphQL Schema

## Overview

This is a conceptual GraphQL schema for the Strava API. Strava is a fitness tracking app and social network enabling athletes to track and analyze workouts including running, cycling, swimming, and 200+ sport types. The Strava REST API at `https://www.strava.com/api/v3` provides access to athlete profiles, activities, segments, routes, clubs, gear, and time-series data streams via OAuth 2.0.

This GraphQL schema is derived from the [Strava API Reference](https://developers.strava.com/docs/reference/) and models the underlying REST resources as a typed graph.

## Schema Source

- **Provider:** Strava
- **REST API Base:** `https://www.strava.com/api/v3`
- **Documentation:** https://developers.strava.com/docs/reference/
- **Authentication:** OAuth 2.0 with scopes (`read`, `activity:read`, `activity:write`, `profile:read_all`, etc.)
- **Rate Limits:** 100 requests / 15 minutes, 1000 requests / day

## Types

### Athlete Types

| Type | Description |
|------|-------------|
| `Athlete` | Full authenticated athlete profile including stats, clubs, and gear |
| `AthleteProfile` | Summary view of an athlete for display in lists and feeds |
| `AthleteZones` | Heart rate and power training zones configured for an athlete |
| `AthleteStats` | Aggregated totals for recent rides, runs, and swims |
| `FollowerStats` | Counts of followers and following for an athlete |
| `FollowerSummary` | Summary of a follower or following relationship |

### Activity Types

| Type | Description |
|------|-------------|
| `Activity` | A full workout record including sport type, distance, time, and streams |
| `ActivityStats` | Aggregated statistics across all activities for an athlete |
| `ActivityZone` | Distribution of time spent in training zones during an activity |
| `ActivityLap` | A lap segment within an activity with distance, time, and pace |
| `ActivitySegmentEffort` | An effort on a named segment within an activity |
| `HeartRateZone` | A heart rate training zone defined by BPM range |
| `PowerZone` | A power training zone defined by watt range |
| `PaceZone` | A pace training zone defined by min/km or min/mile range |
| `HeartRate` | A heart rate measurement or summary |
| `Power` | A power output measurement or summary |
| `Cadence` | A cadence measurement or summary |

### Segment Types

| Type | Description |
|------|-------------|
| `Segment` | A named portion of road or trail tracked by Strava |
| `SegmentLeaderboard` | Ranked list of efforts on a segment |
| `SegmentLeaderboardEntry` | A single entry (athlete + time) on a segment leaderboard |
| `StarredSegment` | A segment that an athlete has starred for quick access |
| `SegmentPR` | An athlete's personal record on a segment |

### Route Types

| Type | Description |
|------|-------------|
| `Route` | A planned path for an activity, with distance and elevation |
| `RouteSegment` | A segment that is part of a route |

### Club Types

| Type | Description |
|------|-------------|
| `Club` | A Strava club grouping athletes by shared interest or team |
| `ClubMember` | An athlete who is a member of a club |
| `ClubAnnouncement` | An announcement posted within a club |
| `ClubActivities` | A paginated collection of recent activities from club members |

### Gear Types

| Type | Description |
|------|-------------|
| `Gear` | Generic gear item associated with an athlete |
| `Shoes` | Running shoes with distance tracking |
| `Bike` | A bicycle with components and distance tracking |
| `Helmet` | A cycling helmet piece of gear |

### Social Types

| Type | Description |
|------|-------------|
| `Kudos` | A kudos (like) given to an activity |
| `Comment` | A comment left on an activity |
| `Photo` | A full photo attached to an activity |
| `PhotoSummary` | A lightweight summary of a photo reference |

### Map and Location Types

| Type | Description |
|------|-------------|
| `Map` | A polyline map associated with an activity or route |
| `PolyLine` | An encoded Google polyline string |
| `LatLng` | A geographic coordinate pair (latitude and longitude) |
| `Location` | A named place with coordinates |
| `Elevation` | An elevation value with unit |
| `ElevationSummary` | Summary of elevation gain, loss, and min/max for an activity |

### Stream Types

| Type | Description |
|------|-------------|
| `Stream` | A single time-series data channel for an activity |
| `StreamSet` | All available stream channels for a given activity |
| `StreamData` | The data array within a stream channel |
| `StreamType` | Enum of available stream types (time, distance, heartrate, etc.) |

### Achievement and Record Types

| Type | Description |
|------|-------------|
| `Achievement` | An achievement earned on a segment effort |
| `PersonalRecord` | A personal best record for a distance or effort type |
| `AthletePR` | A personal record belonging to a specific athlete |
| `KOMRecord` | A King/Queen of the Mountain record on a segment |

### Upload and Webhook Types

| Type | Description |
|------|-------------|
| `Upload` | An activity file upload in progress or completed |
| `UploadStatus` | Status of an activity file upload (processing, error, ready) |
| `Webhook` | A registered webhook subscription for activity events |
| `WebhookEvent` | An event payload delivered to a webhook endpoint |
| `WebhookAspect` | The aspect type (create, update, delete) of a webhook event |
| `SubscriptionEvent` | A subscription-level event notification |

### Analytics Types

| Type | Description |
|------|-------------|
| `AnalyticsSegment` | An analytics view of segment traffic and trends |

## Queries

```graphql
type Query {
  # Athlete
  athlete: Athlete
  athleteById(id: ID!): AthleteProfile
  athleteStats(athleteId: ID!): AthleteStats
  athleteZones: AthleteZones

  # Activities
  activity(id: ID!): Activity
  athleteActivities(before: Int, after: Int, page: Int, perPage: Int): [Activity!]!
  activityLaps(activityId: ID!): [ActivityLap!]!
  activityZones(activityId: ID!): [ActivityZone!]!
  activityComments(activityId: ID!, page: Int, perPage: Int): [Comment!]!
  activityKudoers(activityId: ID!, page: Int, perPage: Int): [AthleteProfile!]!
  activityPhotos(activityId: ID!): [Photo!]!
  relatedActivities(activityId: ID!): [Activity!]!

  # Segments
  segment(id: ID!): Segment
  starredSegments(page: Int, perPage: Int): [StarredSegment!]!
  segmentLeaderboard(segmentId: ID!, gender: String, ageGroup: String, weightClass: String, following: Boolean, clubId: ID, dateRange: String, contextEntries: Int, page: Int, perPage: Int): SegmentLeaderboard!
  segmentEfforts(segmentId: ID!, athleteId: ID, startDateLocal: String, endDateLocal: String, perPage: Int): [ActivitySegmentEffort!]!
  exploreSegments(bounds: [Float!]!, activityType: String, minCat: Int, maxCat: Int): [Segment!]!

  # Routes
  route(id: ID!): Route
  athleteRoutes(athleteId: ID!, page: Int, perPage: Int): [Route!]!

  # Clubs
  club(id: ID!): Club
  athleteClubs: [Club!]!
  clubMembers(clubId: ID!, page: Int, perPage: Int): [ClubMember!]!
  clubActivities(clubId: ID!, page: Int, perPage: Int): ClubActivities!
  clubAdmins(clubId: ID!, page: Int, perPage: Int): [AthleteProfile!]!
  clubAnnouncements(clubId: ID!): [ClubAnnouncement!]!

  # Gear
  gear(id: ID!): Gear

  # Streams
  activityStreams(activityId: ID!, keys: [StreamType!]!, keyByType: Boolean): StreamSet!
  segmentEffortStreams(effortId: ID!, keys: [StreamType!]!, keyByType: Boolean): StreamSet!
  routeStreams(routeId: ID!): StreamSet!

  # Uploads
  upload(uploadId: ID!): UploadStatus
}
```

## Mutations

```graphql
type Mutation {
  # Activities
  createActivity(input: CreateActivityInput!): Activity!
  updateActivity(id: ID!, input: UpdateActivityInput!): Activity!
  deleteActivity(id: ID!): Boolean!

  # Kudos and Comments
  createComment(activityId: ID!, text: String!): Comment!
  deleteComment(activityId: ID!, commentId: ID!): Boolean!

  # Segments
  starSegment(segmentId: ID!): StarredSegment!
  unstarSegment(segmentId: ID!): Boolean!

  # Athlete
  updateAthlete(input: UpdateAthleteInput!): Athlete!

  # Gear
  createGear(input: CreateGearInput!): Gear!
  updateGear(id: ID!, input: UpdateGearInput!): Gear!

  # Uploads
  uploadActivity(input: UploadActivityInput!): Upload!

  # Webhooks
  createWebhook(input: CreateWebhookInput!): Webhook!
  deleteWebhook(subscriptionId: ID!): Boolean!
}
```

## Relationships

- An `Athlete` has many `Activity` records, `Club` memberships, and `Gear` items.
- An `Activity` contains `ActivityLap` segments, `ActivitySegmentEffort` instances, `Photo` attachments, `Comment` threads, and `Kudos`.
- A `Segment` has a `SegmentLeaderboard` with many `SegmentLeaderboardEntry` items.
- A `Route` is composed of `RouteSegment` references.
- A `Club` has `ClubMember` athletes, `ClubAnnouncement` posts, and `ClubActivities`.
- An `Activity` produces a `StreamSet` containing multiple `Stream` channels.
- `Athlete` training zones are split into `HeartRateZone` and `PowerZone` bands within `AthleteZones`.

## Notes

- This schema is conceptual and intended to represent the Strava REST API surface as a typed GraphQL graph.
- Strava does not currently offer a public GraphQL endpoint; this schema is a design artifact.
- All queries map to REST endpoints under `https://www.strava.com/api/v3`.
- OAuth 2.0 Bearer token authentication is required for all operations.
