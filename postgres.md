Installation

           sudo apt-get update
           sudo apt-get install postgresql postgresql-contrib

To Avoid Peer Authentication Error

            lacal postgres postgres peer
            sudo -u postgres postgresql

Create a database in postgresql

            $ createdb mydb

Delete a database in postgresql

            $ dropdb mydb

To Know psql

            $ psql --help # shows all commands available

Login to database

            $ psql --username postgres  # Enter password when prompted. Logins to the default database for the given user

List of databases after login

            defaultdb=# \l

List of schema names

            defaultdb=# \dn

To write sql in vim editor instead of command line

            defaultdb=# \e

Create A New Table

            CREATE TABLE weather (
                   city            varchar(80),
                   temp_lo         int,           -- low temperature
                   temp_hi         int,           -- high temperature
                   prcp            real,          -- precipitation
                   date            date
                    );
            CREATE TABLE cities (
                    name            varchar(80),
                    location        point
                    );

Populating a Table With Rows  

            INSERT INTO weather (city, temp_lo, temp_hi, prcp, date)
            VALUES ('San Francisco', 43, 57, 0.0, '1994-11-29');

Querying a Table

            SELECT * FROM weather;
            SELECT * FROM weather ORDER BY city;
            SELECT DISTINCT city FROM weather;

Drop A Table

             =# DROP TABLE tablename

Execute commands from a sql file from inside psql prompt

             =# \i ./myfile.sql

Create Joins Between The Tables

             SELECT * FROM weather INNER JOIN cities ON (weather.city = cities.name);
             SELECT * FROM weather LEFT OUTER JOIN cities ON (weather.city = cities.name);

Updating A Table

           UPDATE weather SET temp_hi = temp_hi - 2,  temp_lo = temp_lo - 2 WHERE date > '1994-11-28';    

Deleting Rows From Table

              DELETE FROM weather WHERE city = 'Hayward';  

Using Aggregate Functions

               SELECT max(temp_lo) FROM weather;
               SELECT city FROM weather WHERE temp_lo = (SELECT max(temp_lo) FROM weather);
               SELECT city, max(temp_lo) FROM weather GROUP BY city;

Creating A View For The Table

               CREATE VIEW myview AS SELECT city, temp_lo, temp_hi, prcp, date, location FROM weather, cities WHERE city = name;
               SELECT * FROM myview;

Building A Transaction

                BEGIN;
                UPDATE accounts SET balance = balance - 100.00 WHERE name = 'Alice';
                SAVEPOINT my_savepoint;
                UPDATE accounts SET balance = balance + 100.00 WHERE name = 'Bob'; -- oops ... forget that and use Wally's account
                ROLLBACK TO my_savepoint;
                UPDATE accounts SET balance = balance + 100.00 WHERE name = 'Wally';
                COMMIT;
              Savepoints allow you to selectively discard parts of the transaction, while committing the rest. After defining a savepoint with SAVEPOINT, you can if needed roll back to the savepoint with ROLLBACK TO. All the transaction's database changes between defining the savepoint and rolling back to it are discarded, but changes earlier than the savepoint are kept.

Table Inheritance

                CREATE TABLE cities (
                             name       text,
                             population real,
                             altitude   int     -- (in ft)
                               );

                CREATE TABLE capitals (
                            state      char(2)
                                  ) INHERITS (cities);
              In this case, a row of capitals inherits all columns (name, population, and altitude) from its parent, cities. The type of the column name is text, a native PostgreSQL type for variable length character strings. State capitals have an extra column, state, that shows their state. In PostgreSQL, a table can inherit from zero or more other tables.

Eixt PostgreSQL

              \q

Restart PostgreSQL

               sudo service postgresql restart
               If you make any changes in the database don't forget to restart
               
