# Flight Backend

The Flight Backend project is a comprehensive system designed to manage flight-related services through a set of microservices. Each microservice is responsible for specific aspects of the flight management process, ensuring scalability, maintainability, and efficient performance.

## Overview

The Flight Backend system consists of four main microservices:

1. [Flight Search Service](#1-flight-search-service)
2. [Flight API Gateway Service](#2-flight-api-gateway-service)
3. [Flight Booking Service](#3-flight-booking-service)
4. [Flight Notification Service](#4-flight-notification-service)

Each service is built using Node.js and various supporting technologies to handle different functionalities such as database management, inter-service communication, and user authentication.

## Microservices Breakdown

### 1. Flight Search Service

This service handles the search functionality for flights, providing users with fast and accurate results based on their search criteria.

- **Sequelize ORM**: Utilized for efficient querying and database management in MySQL.
- **Advanced Search Algorithms**: Implemented to ensure quick and precise flight search results.
- **Model Relationships**: Established one-to-many relationships between models to reflect the real-world data structure.
- **Inter-Service Communication**: Used Axios to fetch additional data from other services.

**Repository**: [Flight Search Service](https://github.com/hritikkkkk/Flights-service)

### 2. Flight API Gateway Service

The API Gateway service acts as a central hub for routing requests to the appropriate microservices. It ensures secure and efficient handling of incoming API requests.

- **API Gateway Design**: Managed request routing to appropriate microservices.
- **JWT Authentication**: Implemented JSON Web Tokens (JWT) for secure authentication and authorization.
- **Rate Limiting and Traffic Management**: Integrated mechanisms to maintain API performance under heavy load.
- **Model Relationships**: Implemented many-to-many relationships in MySQL to handle complex data interactions.

**Repository**: [Flight API Gateway Service](https://github.com/hritikkkkk/flights-api-gateway)

### 3. Flight Booking Service

This service manages the flight booking process, ensuring transactional integrity and preventing overbooking.

- **Database Management**: Used MySQL to manage bookings and ensure transactional integrity and atomicity.
- **Concurrency Handling**: Addressed concurrency issues to prevent overbooking and ensure accurate seat availability.
- **Inter-Service Communication**: Used Axios to verify seat availability and confirm bookings.
- **Event Publishing**: Published booking events to RabbitMQ to notify other services.

**Repository**: [Flight Booking Service](https://github.com/hritikkkkk/flights-booking-service)

### 4. Flight Notification Service

The Notification Service is responsible for sending automated email notifications related to flight bookings.

- **Automated Notifications**: Implemented email notifications for booking confirmations.
- **Event Subscription**: Subscribed to RabbitMQ for receiving booking events and triggering notifications.
- **Error Handling and Retries**: Implemented mechanisms to ensure message delivery success despite potential errors.
- **Inter-Service Communication**: Used Axios to retrieve booking and user details for notifications.

**Repository**: [Flight Notification Service](https://github.com/hritikkkkk/flights-mailNotification-service)

## Conclusion

The Flight Backend project showcases a robust architecture for managing flight-related services through well-defined microservices. Each service is designed to handle specific tasks, ensuring that the system is scalable, maintainable, and capable of handling complex operations efficiently. The use of modern technologies and best practices makes this project a solid example of microservices architecture in action.


