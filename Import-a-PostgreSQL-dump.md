### Goal

Populate one Sagan database with the contents of another.

### Prerequisites

1. A PostgreSQL DB with permissions to drop and create objects (referred to as `$DB_URL` below).
1. Access to the file created by the instructions in [[export a PostgreSQL dump]] (referred to as `sagan-db.sql` below)
1. A local PostgreSQL installation (for access to `pg_dump` command).

### Steps

#### Import dump

    psql --file sagan-db.sql $DB_URL

where `$DB_URL` is of the form `postgres://USERNAME:PASSWORD@HOST:PORT/DBNAME`.


### See also

 - [[Export a PostgreSQL dump]]

