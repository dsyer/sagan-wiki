### Goal

Export the contents (schema and data) of one Sagan DB, typically for the purpose of [[importing|Import a PostgreSQL dump]] it into another.

### Prerequisites

1. Access to the PostgreSQL DB to be dumped (referred to as `$DB_URL` below)
1. A local PostgreSQL installation (for access to `pg_dump` and `psql` commands).

### Steps
<pre>
$ pg_dump $DB_URL \
          --clean \
          --file sagan-db.sql \
          --table memberprofile* --table post* --table schema_version
</pre>
> **TIP**: The `sagan-db.sql` output file will be tens of MB in size, but can be reduced to several MB using gzip.

### See also

 - [[Import a PostgreSQL dump]]
