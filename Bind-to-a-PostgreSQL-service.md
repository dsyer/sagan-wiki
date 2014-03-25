### Goal

Use a PostgreSQL database on Cloud Foundry instead of the default in-memory H2 database.

### Prerequisites

1. [[Run the site on Cloud Foundry]]
1. [[Add a PostgreSQL service]]

### Steps

#### Bind the Sagan app to the ElephantSQL service

    $ cf bind-service sagan sagan-db

#### Configure Sagan app's Spring profiles

When no Spring profiles are specified, the Sagan app assumes it should use its in-memory H2 database by default. Therefore, setting any active profile name will cause the app to assume there is a PostgreSQL database available. We'll use the profile name "staging" here, but it could be literally any value. See the `DatabaseConfiguration` class for details.

    $ cf set-env sagan SPRING_PROFILES_ACTIVE staging
    Updating sagan... OK

Verify with the following:

    $ cf env sagan
    Getting env for sagan... OK

    SPRING_PROFILES_ACTIVE: staging

#### Restart the Sagan app

    $ cf restart sagan

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
