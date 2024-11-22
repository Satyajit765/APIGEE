# :label::bookmark: Apigee-Components :high_brightness:


##  Management Server (MS)

Purpose: Acts as the central control plane for managing the Apigee environment.
Functions:
Provides a user interface and API for managing APIs, policies, and deployments.
Handles configurations, deployments, and analytics.

## Cassandra

Purpose: Distributed database used for storing persistent data.
Functions:
Stores API configurations, analytics data, and operational metrics.
Highly scalable and fault-tolerant for large datasets.

## Zookeeper

Purpose: Manages configuration and coordination between Apigee components.
Functions:
Acts as a registry for managing distributed services.
Ensures high availability by handling cluster state and leader election.

## Router

Purpose: Entry point for all API traffic.
Functions:
Routes client requests to the appropriate Message Processor.
Provides load balancing and traffic management.

## Message Processor (MP)

Purpose: Processes API requests and applies policies.
Functions:
Enforces security, transformations, and mediation policies.
Communicates with the backend service and sends responses back to clients.

## Qpid (Apache Qpid)

Purpose: Messaging service used for internal communication.
Functions:
Facilitates asynchronous communication between Apigee components.
Handles events, logs, and analytics collection.

## Edge UI

Purpose: Web-based graphical user interface.
Functions:
Provides access to manage API proxies, policies, and developer portals.
Monitors API traffic and analytics.

## Analytics

Purpose: Captures and processes usage data from APIs.
Functions:
Provides detailed reports on API usage, performance, and errors.
Stores data in Cassandra for real-time and historical analysis.

## Developer Portal

Purpose: Facilitates interaction between API providers and consumers.
Functions:
Allows developers to discover, test, and consume APIs.
Offers tools for documentation, self-service onboarding, and API key management.

## Postgres

Purpose: Relational database for storing lightweight data.
Functions:
Maintains configuration data for the Developer Portal and user management.

## Management API

Purpose: Provides programmatic access to manage Apigee components.
Functions:
Enables automation for API lifecycle management, including creation, deployment, and monitoring.