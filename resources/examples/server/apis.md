# Exposed APIs Time Pod Command

Short ID: [S0183](readme_server.md)

API Version: 3.0.12.8

API Type: GraphQL

## getProjectList

**Type:** Query

**Expects:** none

**Description:**

Gets all available projects for the requesting user.

**Returns:**

    type Project{
        publicID: String!
        name: String!
        activities: [ActivityDetail]!
        constants: Constants!
        breaks: [ActivityDetail]
    }

## beginActivity

**Type:** Mutation

**Description:**

Starts the activity, by adding an entry to the database.

**Expects:**

    input ProjectInputData{
        eventID: String
        projectID: String
        newProjectID: String
        activityID: String
        newActivityID: String
        status: String
        isBreakType: Boolean
        startTime: Date
        endTime: Date
    }

**Returns:**

    type CombinedActivityData{
        currentEvent: ActivityEvent
        projectID: String
        latestActivityList: [ActivityEvent]
    }

## General Type Definitions

### ActivityDetail

**Description:**

Data Type for details about an activity.

**Structure:**

    type ActivityDetail{
        publicID: String!
        name: String!
        description: String!
        type: String!
    }

#### Constants

**Description:**

The constants used by a project.

**Structure:**

    type Constants{
        activityTypeNames: [String]!
        breakTypeNames: [String]!
        statusCodes: StatusCodes
    }

#### StatusCodes

**Description:**

Status code defined for a project.

**Structure:**

    type StatusCodes{
        Abgemeldet: Int!
        Angemeldet: Int!
        Pause: Int!
    }

#### ActivityEvent

**Description:**

Data type for an activity event. Contains the information about the whats and whens.

**Structure:**

    type ActivityEvent{
        _id: String
        projectID: String
        activityID: String
        activityType: String
        startTime: Date
        endTime: Date
        status: String
        previousEventID: String
    }
