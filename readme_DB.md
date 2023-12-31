**How DB may look like:**

**Table: Users**
user_id (Primary Key)
username
password
email
created_at

**Table: Challenges**
challenge_id (Primary Key)
challenge_name
alarm_time
duration (in days)
creator_id (Foreign Key referencing Users.user_id)
is_started (Boolean)

**Table: ChallengeParticipants**
challenge_participant_id (Primary Key)
challenge_id (Foreign Key referencing Challenges.challenge_id)
participant_id (Foreign Key referencing Users.user_id)

**Table: ChallengeInvitations**
invitation_id (Primary Key)
challenge_id (Foreign Key referencing Challenges.challenge_id)
invitee_id (Foreign Key referencing Users.user_id)
is_accepted (Boolean)

**Table: ChallengeDailyStatus**
status_id (Primary Key)
challenge_participant_id (Foreign Key referencing ChallengeParticipants.challenge_participant_id)
status_date
is_completed

**Table: ChallengeMessages**
message_id (Primary Key)
challenge_participant_id (Foreign Key referencing ChallengeParticipants.challenge_participant_id)
sender_id (Foreign Key referencing Users.user_id)
recipient_id (Foreign Key referencing Users.user_id)
message_content
message_time

**Table: Rewards**
reward_id (Primary Key)
challenge_participant_id (Foreign Key referencing ChallengeParticipants.challenge_participant_id)
points
rewarded_date
