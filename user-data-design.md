# User data

The database uses SQLite interfacing via [Prisma](https://www.prisma.io/), an ORM interface which generates code to interact with databases programatically. This greatly simplifies coding of database operations, and allows a relational model to be defined.

## Usage

The database utilizes SQLite, a lightweight implementation of SQL that is standalone and stored as a single generated file on disk, in `watchers-app/prisma/dev.db`.

## User profile data concept

The user data contains the following components:

- user unique ID
- username
- email
- password hash
- display name

The user posts data are in another collection differentiated using the unique ID

- post type (profile-post)
  - user unique ID
  - post unique ID
  - post text content
  - referenced movie unique ID
  - post likes:
    - user account likes (unique ID list)
  - post comments (only relevant if profile-post):
    - each comment body contains
      - commenting user unique ID
      - comment unique ID
      - comment text content
      - comment likes:
      - user account likes (unique ID list)

## Check all user in website

Check the user list by inputing "@" in webstie.
User can’t choose a username, it defaults to their email alias (whatever is before the '@') like sichunw for sichunw@bu.edu.  