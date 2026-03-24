# Social-Network

A Django-based social network proof of concept that integrates user timelines with skill-based reputation profiles.

The project builds on two existing applications: a social network app with data models, an internal API, HTML views, timelines, search, posts, follows, authentication, and test data generation; and a separate fame app that manages user reputation profiles. The combined project exposes reputation directly inside the social experience and adds logic for ranking users by expertise area.

## Overview

This repository demonstrates how a social platform can combine content sharing with structured reputation data.

The core idea is simple: user activity can be associated with expertise areas, and those profiles can influence how content is published, displayed, and ranked. That makes the project a good example of application design, data modeling, API development, and Django integration.

## Key Features

* Django-based social network and reputation system
* Timelines and search
* User authentication
* Follow and unfollow workflows
* Internal API for core platform logic
* Expertise ranking views
* Positive and negative reputation aggregation
* Test data generation through the ORM
* Unit and end-to-end test coverage

## Project Structure

```text
.
├── famesocialnetwork/     # Django project configuration
├── socialnetwork/         # Social network app
├── fame/                  # Reputation profile app
├── templates/             # HTML templates
├── tests/                 # Automated tests
└── README.md
```

The implementation is organized so that platform logic stays centralized in the API layer, while HTML views remain thin wrappers around that logic. The assignment brief explicitly calls out this separation, along with the existing models, API layer, views, and tests in both apps.

## Technical Design

### API-Centric Core

The project uses an internal API as the primary place for business logic. That keeps the same behavior available to both HTML views and any future REST-style integration.

### Reputation Profiles

Each user has a fame profile made up of expertise areas and levels. The system supports both positive and negative reputation, which allows the platform to distinguish between trusted and untrusted expertise in a structured way.

### Ranking Logic

Users can be ranked by expertise area based on reputation level and recency. This creates deterministic expert and negative-expert views that are useful both for presentation and for downstream platform logic.

### Social Interaction

The timeline is connected to follow and unfollow actions, so the visible feed reflects the user’s social graph rather than being a static list.

## Core Capabilities

### Reputation-aware publishing

The platform can prevent publication of content that conflicts with an established negative reputation profile.

### Reputation updates from content

When content is considered unreliable, the user’s reputation profile can be updated accordingly.

### Expert and negative-expert views

The system can aggregate users by expertise area and present ranked lists of trusted and untrusted contributors.

### Follow / unfollow flows

Users can subscribe to or unsubscribe from other users, and the timeline updates accordingly.

## Testing

The project is designed to be verified through automated tests, including focused student tests for the main implementation tasks. That makes the repository suitable for iterative development and regression-safe changes over time. The assignment also emphasizes avoiding overfitting to a fixed dataset, which is important for durable implementation quality.

## Why This Project Matters

This project shows how to build a non-trivial web application that combines:

* Django application structure
* API-first domain logic
* reputation and ranking rules
* social-graph behavior
* test-driven implementation discipline
* maintainable separation of concerns

That makes it a strong portfolio project for hiring, promotion, and long-term reference.

## Future Improvements

Possible extensions include:

* more robust reputation rules
* richer moderation workflows
* improved ranking explanations
* stronger abuse prevention
* analytics for social and reputation trends

## License

This project is licensed under the **GNU General Public License v3.0 (GPL-3.0)**.

See the LICENSE file for details.
