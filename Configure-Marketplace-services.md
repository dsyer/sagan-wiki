### Goal

Make your Sagan instance production ready with Marketplace services.

### Prerequisites

1. [[Get started with Cloud Foundry]]

### Steps

> _**Note:** These steps assume use of the public Cloud Foundry instance at http://run.pivotal.io and its marketplace._

#### Add Marketplace services to your Cloud Foundry space

- First, [[Add a PostgreSQL Service]] for data persistence
- Then [[Add a Redis Service]] for distributed caching

#### Bind the Sagan app to those services

    $ cf bind-service $APP_NAME sagan-db
    $ cf bind-service $APP_NAME sagan-cache

#### Configure Sagan app's Spring profiles

When no Spring profiles are specified, the Sagan app assumes it should use its in-memory H2 database by default. Therefore, setting any active profile name will cause the app to assume there is a PostgreSQL database available. We'll use the profile name "staging" here, but it could be literally any value. See the `DatabaseConfiguration` class for details.

    $ cf set-env sagan SPRING_PROFILES_ACTIVE staging
    Updating $APP_NAME... OK

Verify with the following:

    $ cf env sagan
    Getting env for $APP_NAME... OK

    SPRING_PROFILES_ACTIVE: staging

#### Restart the Sagan app

    $ cf restart $APP_NAME

#### Verify that the PostgreSQL DB has been initialized

The Sagan app automatically initializes the DB Schema using Flyway (see `DatabaseConfiguration` for details). This means you should now be able to connect to the Postgres DB and see the correct tables in place:

<pre>
$ psql $DB_URL
psql (9.2.4)
Type "help" for help.

uoztokrw=> \d
                  List of relations
 Schema |         Name         |   Type   |  Owner
--------+----------------------+----------+----------
 public | memberprofile        | table    | uoztokrw
 public | memberprofile_id_seq | sequence | uoztokrw
 public | post                 | table    | uoztokrw
 public | post_id_seq          | sequence | uoztokrw
 public | schema_version       | table    | uoztokrw
(5 rows)
</pre>

where `$DB_URL` is the URL displayed from the "Manage" link available on the "sagan-db" service from within the Cloud Foundry console.


### Next steps

 - [[Import a PostgreSQL dump]]
 - [[Enable search on Cloud Foundry]]