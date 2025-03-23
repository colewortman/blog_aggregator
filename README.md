You'll need to install Postgres and Go in order to run the program.

Install gator CLI with: go install https://github.com/colewortman/blog_aggregator
This will allow you to run gator commands

You'll also need a config file .gatorconfig.json which should be made in your home directory
Use the following format:
```json
{
  "database": {
    "host": "localhost",
    "port": 5432,
    "user": "your_username",
    "password": "your_password",
    "dbname": "your_database_name"
  }
}
```

This is a CLI tool and the program runs on commands with the usage of:
gator <command> <arguments>

Not all commands require arguments, such as the users command:
gator users
  -returns all registered users

Example of command with arguments, such as the register command:
gator register <username>
  -registers a given user

To run blog aggregation use the following commands:
gator register <username>
gator addfeed <feedname> <URL>
  -this uses an RSS URL to add a feed to the database
gator agg <time(m, s)>
  -this scrapes the feed on a recurring interval given the time (with minutes or seconds)
gator browse <(optional) limit>
  - this shows posts aggregated from the agg command with an optional limit to how many posts are shown
