Instructions to run the SQLite3 version of the DB demo application.
All data will be stored locally in a SQLite database file (.db extension).
This does not use the SQL instance on GCP in any way.

STEP 1: Install SQLite3 on GCP: sudo apt-get install sqlite3
  SQLite3 is a lightweight database that doesn't require any authentication.
  The database file is stored locally and you can interact with it using SQL.

  You may wish to set up sqlite3 on your local computer and run this demo
  application.  SQLite3 supports numerous operating systems,
  see https://www.sqlite.org/download.html


STEP 2: Install the python DB related python modules from the command line:
sudo pip3 install requests flask-wtf flask-sqlalchemy


STEP 3:
  *********
  This step is only needed the first time you run the application in order
  to create the SQLite3 database file (this will be stored in the app folder).
  *********
    Still from the project directory, perform the following:
    - Start python interpreter by typing:     python3
    - At the python prompt type (>>>), run following Python statement in
      sequence:
            from app import app
            from app import db
            from dotenv import load_dotenv
            load_dotenv('flaskenv')
            db.create_all()
            quit()    # this takes you back to the terminal prompt

   The create_all function creates the database schema defined in app/models.py.


   **** To delete the data and recreate the table *****
  Follow the Python statements above and type db.drop_all() before
  db.create_all()

STEP 4: Now run the Flask application from the project top-level directory:

    flask run
