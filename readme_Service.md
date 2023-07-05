**User Management Service:**
This service handles user authentication, registration, and user-related operations. It manages user accounts and authentication tokens.
- Authentication: Handles user authentication, registration, login, and token management.
- User Profile: Manages user profiles, including personal information, preferences, and settings.
- User Interaction: Handles interactions between users, such as friend requests, messaging, and social features.

**Challenge Tracker Service:**
This service is responsible for creating, updating, and tracking challenges. It handles the logic related to challenge creation, participants, progress tracking, and completion status.
- Challenge Creation: Manages the creation of challenges, including defining challenge parameters, duration, and participants.
- Challenge Progress: Tracks and updates the progress of challenges for each participant, including marking completion status and logging daily actions.
- Challenge Reminder: Sends reminders to participants for upcoming challenges or daily actions.

**Notification Service (Firebase):**
This service integrates with Firebase Cloud Messaging (FCM) or a similar notification service to handle push notifications. 
It sends notifications to users regarding challenge updates, reminders, or messages from other participants.

- Push Notification Subservice: Handles sending push notifications to users' devices using Firebase Cloud Messaging (FCM) or a similar service.
- Notification Templates Subservice: Manages notification templates and message content for different types of notifications.
- Subscription Management Subservice: Handles user subscription preferences, allowing users to opt-in or opt-out of specific types of notifications.
- Delivery Tracking Subservice: Tracks the delivery status of notifications and provides feedback on successful or failed deliveries.

