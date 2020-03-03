# Patches to make `pg_dump` compatible with FDW

These patches extend the compatibility of `pg_dump` with foreign data wrappers for PostgreSQL 13 (it can easily be
adapted for Postgres versions 11 and 12).
Now data in FDW backed tabled can be optionally dumped and the `ALTER TABLE` commands on foreign tables are written as
`ALTER FOREIGN TABLE`.

To compile and use the patch follow these instructions:

1. Get the PostgreSQL source code, for example via
    - `git clone https://github.com/postgres/postgres.git --depth=1` or
    - `apt-get source postgresql-11` and `sudo apt-get build-dep postgresql-11`
1. Apply these patches with e.g.: `patch -p1 < somepatch`
1. Compile PostgreSQL

The related threads in the PostgreSQL hackers mail list are:
- https://www.postgresql.org/message-id/flat/CALDaNm1pdQHgp14ppcUkzQ7AQPodEyBCbzbkK6%2BuETxn0TKpQA%40mail.gmail.com#6c7457d32
- https://www.postgresql.org/message-id/flat/20200114230411.GA10233%40alvherre.pgsql#6d0ed361f0c99be940f53dad86db6839
