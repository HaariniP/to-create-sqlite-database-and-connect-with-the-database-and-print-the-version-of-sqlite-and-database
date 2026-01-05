# to-create-sqlite-database-and-connect-with-the-database-and-print-the-version-of-sqlite-and-database
import sqlite3
try:
    sqlite_connection=sqlite3.connect('temp.db')
    conn=sqlite_connection.cursor()
    print("\nDatabase created and connected to SQLite.")
    sqlite_select_Query="select sqlite_version();"
    conn.execute(sqlite_select_query)
    record=conn.fetchall()
    print("\nSQLite Database Version is:".record)
    conn.close()
except sqlite3.Error as error:
    print("\nError while connecting to sqlite".error)
    finally:
        if(sqlite_connection):
            sqlite_connection.close()
            print("\nThe SQLite connection is closed.")
