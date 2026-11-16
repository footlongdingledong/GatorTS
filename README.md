Blog Aggregator guided project in TypeScript.
Dropped this project for a couple months and worked on other projects before returning, so this one's a mess.

Uses drizzle-orm with postgresql database. Postgres database must be created, and connection string provided in config file (explained below).

Requires ".gatorconfig.json" in home directory (can be changed in config.ts - getConfigFilePath())
.gatorconfig.json requires "db_url" and "current_user_name" fields. db_url is required, but current_user_name should be ok if left blank (program will update it).

It makes far more sense for this to be in a .env file, but that's not what the project wanted for some reason, so feel free to correct it if you use this for some reason (you shouldn't).

Commands:
Function (required fields) - description

Register (username: string) - Creates User in DB with provided name, also sets current user to newly created user.

Users () - lists users currently in db, shows which user is current logged in

Login (username: string) - switches logged in user to username provided.

Reset () - resets all databases

Addfeed (feedName: string, feedURL: string) - adds feed with given name and URL to feeds database

Follow (feedURL: string) - Adds existing feed to follow list (only necessary for multiple users following same feed)

Following () - Lists feeds you are currently following (feeds are automatically followed when added to db)

Unfollow (feedURL: string) - Removes feed with given URL from following list for current user

Agg (timeBetweenRequests: # ms|s|m|h) - Begins scrapping feeds every given interval (ex: 1m = 1 minute). Adds posts to the posts db.

Browse (limit: number) - Lists posts in database newest first. Limit on number of posts returned can be provided, defaults at 2.
