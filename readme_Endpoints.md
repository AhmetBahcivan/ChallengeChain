Endpoint may look like these:


API Endpoints:

**User Management Service:**

- **AUTH**:
  
    **POST /auth/signup:** Create a new user account.

      Request body:
      {
        "email": "example@example.com",
        "password": "password123"
      }
    
      Response:
      {
        "userId": "123456",
        "email": "example@example.com",
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
      }
    
    **POST /auth/login:** Authenticate user credentials and generate an access token.
    
      Request body:
      {
        "email": "example@example.com",
        "password": "password123"
      }
      
      Response:
      {
        "userId": "123456",
        "email": "example@example.com",
        "accessToken": "eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9..."
      }
    
    **POST /auth/logout:** Revoke the user's access token and log them out.
    
    No request body required.
    
      Response:
      {
        "message": "Logout successful."
      }

  
- **PROFILE**:

    **GET /users/{userId}:** Get user profile information.
    
      Response:
      
      {
        "userId": "123456",
        "email": "example@example.com",
        "name": "John Doe",
        "avatar": "https://example.com/avatar.jpg"
      }
    
    **PUT /users/{userId}:** Update user profile information.
    
      Request body:
      
      {
        "name": "John Doe",
        "avatar": "https://example.com/avatar.jpg"
      }
    
      Response:
      
      {
        "userId": "123456",
        "email": "example@example.com",
        "name": "John Doe",
        "avatar": "https://example.com/avatar.jpg"
      }

- **SOCIAL**:

    **POST /friends/request**: Send a friend request to another user.
    
      Request body:
      
      {
        "friendId": "789012"
      }
      
      Response:
      
      {
        "message": "Friend request sent successfully."
      }
    
    **POST /friends/accept**: Accept a friend request from another user.
    
      Request body:
      
      {
        "requestId": "345678"
      }
      
      Response:
      
      {
        "message": "Friend request accepted."
      }
    
    **GET /friends/list**: Get a list of user's friends.
    
      Response:
      
      {
        "friends": [
          {
            "userId": "789012",
            "name": "Jane Smith",
            "avatar": "https://example.com/avatar.jpg"
          },
          {
            "userId": "345678",
            "name": "Alex Johnson",
            "avatar": "https://example.com/avatar.jpg"
          }
        ]
      }

**Challenge Tracker Service:**

- **CREATION**:

    **POST /challenges**: Create a new challenge.
    
      Request body:
      
      {
        "name": "Fitness Challenge",
        "duration": 7,
        "participants": ["789012", "345678"],
        "alarmTime": "09:00 AM"
      }
      
      Response:
      
      {
        "challengeId": "123456",
        "name": "Fitness Challenge",
        "duration": 7,
        "participants": ["789012", "345678"],
        "alarmTime": "09:00 AM"
      }
    
    **PUT /challenges/{challengeId}**: Update challenge details.
    
      Request body:
      
      {
        "name": "New Challenge Name",
        "duration": 10,
        "participants": ["789012", "345678"],
        "alarmTime": "08:30 AM"
      }
      
      Response:
      
      {
        "challengeId": "123456",
        "name": "New Challenge Name",
        "duration": 10,
        "participants": ["789012", "345678"],
        "alarmTime": "08:30 AM"
      }
    
    **DELETE /challenges/{challengeId}**: Delete a challenge.
    
    No request body required.
    
      Response:
      
      {
        "message": "Challenge deleted successfully."
      }

- **PROGRESS**:

  **GET /challenges/{challengeId}/progress**: Get the current progress and status of participants in a challenge, including challenge details.

      Response:
      
      {
        "challengeId": "123456",
        "challengeName": "Fitness Challenge",
        "duration": 7,
        "participants": [
          {
            "participantId": "789012",
            "status": "completed",
            "completedDays": 7,
            "lastAction": "Performed exercise routine"
          },
          {
            "participantId": "345678",
            "status": "in_progress",
            "completedDays": 4,
            "lastAction": "Took a walk"
          },
          {
            "participantId": "901234",
            "status": "not_started",
            "completedDays": 0,
            "lastAction": null
          }
        ]
      }

    **POST /challenges/{challengeId}/participants**: Add a participant to a challenge.
    
      Request body:
      
      {
        "participantId": "901234"
      }
      
      Response:
      
      {
        "message": "Participant added successfully."
      }
    
    **PUT /challenges/{challengeId}/participants/{participantId}/action**: Update the daily action of a participant.
    
      Request body:
      
      {
        "action": "Performed exercise routine"
      }
      
      Response:
      
      {
        "message": "Daily action updated successfully."
      }
    
    **GET /challenges/{challengeId}/participants/{participantId}**: Get the progress of a participant in a challenge.
    
      Response:
      
      {
        "participantId": "789012",
        "challengeId": "123456",
        "completedDays": 5,
        "lastAction": "Performed exercise routine"
      }

- **REMINDER**:

    **POST /reminders**: Schedule a reminder for a challenge.
    
      Request body:
      
      {
        "challengeId": "123456",
        "participantId": "789012",
        "reminderTime": "08:30 AM"
      }
      
      Response:
      
      {
        "message": "Reminder scheduled successfully."
      }

**Notification Service:**

- **Push Notification:**

    **POST /notifications**: Send a push notification to a user.
    
      Request body:
      
      {
        "userId": "789012",
        "title": "Challenge Update",
        "message": "You have a new message from a participant."
      }
      
      Response:
      
      {
        "message": "Notification sent successfully."
      }
    
    **GET /notifications/{notificationId}**: Get details of a specific notification.
    
      Response:
      
      {
        "notificationId": "123456",
        "userId": "789012",
        "title": "Challenge Update",
        "message": "You have a new message from a participant.",
        "timestamp": "2023-07-05T10:00:00Z"
      }
