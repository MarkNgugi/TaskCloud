# Features:

### Add tags or categories to tasks.
### Set priority levels (e.g., low, medium, high).
### Filter tasks by status or due date.

---------------------------------------------------------------------------------------------------------------------------------------


# Database Tables

## Users (if user authentication is required)
- **id**: Integer (Primary Key)
- **username**: String
- **email**: String (Unique)
- **encrypted_password**: String (for authentication)
- **created_at**: Timestamp
- **updated_at**: Timestamp

## Tasks
- **id**: Integer (Primary Key)
- **user_id**: Integer (Foreign Key, references Users)
- **title**: String
- **description**: Text
- **due_date**: DateTime
- **status**: String (e.g., 'completed', 'pending')
- **priority**: String (e.g., 'low', 'medium', 'high')
- **created_at**: Timestamp
- **updated_at**: Timestamp

## Tags
- **id**: Integer (Primary Key)
- **name**: String (Unique)
- **created_at**: Timestamp
- **updated_at**: Timestamp

## TaskTags (join table for many-to-many relationship between Tasks and Tags)
- **id**: Integer (Primary Key)
- **task_id**: Integer (Foreign Key, references Tasks)
- **tag_id**: Integer (Foreign Key, references Tags)
- **created_at**: Timestamp
- **updated_at**: Timestamp
