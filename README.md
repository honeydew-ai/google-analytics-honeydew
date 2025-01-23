## Google Analytics Honeydew Model

This is a Honeydew model for Google Analytics GA4 data collected to Snowflake via the [Snowflake Connector for Google Analytics Raw Data](https://other-docs.snowflake.com/en/connectors/google/gard/gard-connector-about)

The Snowflake Connector for Google Analytics Raw Data enables to automatically ingest event-level Google Analytics 4 (GA4) data from BigQuery into a Snowflake account.

### Contents

Honeydew model enables analysis on raw data of a single GA4 property.

It extract all available GA4 records, including:

1. App Info
2. Collected Traffic Source
3. Device
4. ECommerce
5. Event
6. Geography
7. Privacy Info
8. Publisher
9. Traffic Source
10. User

**NOTE**: Every metric can be filtered, aggregated or slice by any attribute of any record.

Following additional metrics are defined, based on the corresponding GA4 definitions.

**Event Metrics**
1. Number of Events
2. Number of Distinct Pages

**Page Metrics**
1. Number of Page Views
1. Number of Unique Page Views
1. Average Time On Page
1. Average Engagement Time Per User

**User Metrics**
1. Number of Users
1. Number of Active Users
1. Number of New (First Time) Users
1. Number of Returning Users
1. Total User Engagement Time

**Session Metrics**
1. Average Session Duration
1. Average Engagement Time Per Session
1. Average Events Per Session
1. Average Page Views Per Session
1. Average Session Duration
1. Bounce Rate
1. Number of Bounces
1. Number of Sessions
1. Number of Engaged Sessions
1. Number of Views Per Session
1. Number of First Time User Sessions
1. Engaged Sessions Ratio (of all sessions)
1. First Time User Sessions Ratio (of all sessions)

**Session Properties**
1. Session entity (extracted from the event data)
1. Is Bounced Session
1. Is Engaged Session
1. Is First Time User Visit Session
1. Page View Count of the session
1. Duration of the session

### LLM Domain

The `llm` domain contains a subset of attributes and metrics tested with AI.

Additional metadata can be added to expand the domain.

## Installation

1. Install the Google Analytics Connector from the [Snowflake Marketplace](https://app.snowflake.com/marketplace/listing/GZSTZTP0KKC/snowflake-snowflake-connector-for-google-analytics-raw-data)
1. Configure it, including setting up a database and a schema to write to. It will create views with name such as `ANALYTICS_<property_id>` for each BigQuery property synchronized
1. Change the source data location for `events` and `users` entities (in `events/datasets/events.yml` and `users/datasets/users.yml`). Instead of `GOOGLE_ANALYTICS_RAW_DATA_DEST_SCHEMA.ANALYTICS_<property_id>__VIEW` add the database, schema and property id of your google analytics.
