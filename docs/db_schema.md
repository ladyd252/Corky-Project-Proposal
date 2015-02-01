#Schema Information

##Users

| Column Name     | Data Type | details               |
|-----------------|-----------|-----------------------|
| id              | integer   | not null, primary key |
| email           | string    | not null, unique      |
| password_digest | string    | not null              |
| session_token   | string    | not null, unique      |


##Events

| Column Name  | Data Type | details               |
|--------------|-----------|-----------------------|
| id           | integer   | not null, primary key |
| title        | string    | not null              |
| creator_id   | integer   | not null              |
| phone_num_id | string    | not null, unique      |


##Posts

| Column Name | Data Type | details               |
|-------------|-----------|-----------------------|
| id          | integer   | not null, primary key |
| picture_url | string    |                       |
| event_id    | integer   | not null              |
| body        | string    |                       |


##Messages

| Column Name | Data Type | details               |
|-------------|-----------|-----------------------|
| id          | integer   | not null, primary key |
| body        | string    |                       |
| event_id    | integer   | not null              |
