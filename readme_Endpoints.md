Endpoint may look like these:


Apologies for the oversight. Here are the additional API endpoints and model updates for the sign-up and sign-in processes:

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
  
- **PROGRESS**:

POST /challenges/{challengeId}/participants: Add a participant to a challenge.

Request body:

{
  "participantId": "901234"
}

Response:

{
  "message": "Participant added successfully."
}

PUT /challenges/{challengeId}/participants/{participantId}/action: Update the daily action of a participant.

Request body:

{
  "action": "Performed exercise routine"
}

Response:
json
Copy code
{
  "message": "Daily action updated successfully."
}
GET /challenges/{challengeId}/participants/{participantId}: Get the progress of a participant in a challenge.

Response:

{
  "participantId": "789012",
  "challengeId": "123456",
  "completedDays": 5,
  "lastAction": "Performed exercise routine"
}

Reminder:

POST /reminders: Schedule a reminder for a challenge.

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
