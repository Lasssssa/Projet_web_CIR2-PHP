# University management web application project - Project CIR2 - PHP Course
 
# Goal of the project 

The aim of this project was to create a web-based audio streaming application.
The overall idea is to recreate an application such as Spotify or Deezer.
The following main functionalities are available:
- Create an account / Login
- Listen to music
- Create a playlist / Add music to the playlist
- Liker music
- View history
- Search for music (with filters based on year, singer, etc.)
- Search for playlists, artists or albums
- Have a profile page
- Add friends and chat with them

# Installation with Docker
Unfortunately, this project has not been programmed with docker, so you need to set up your Linux machine.

However, it's possible that a version with docker will be released one day.

# Setup the linux machine

### Update
- `sudo apt-get update`
- `sudo apt-get upgrade`

### Install apache2 Version : 2.4.56
- `sudo apt-get install apache2`

### Install postgresql Version : 13.11
- `sudo apt-get install postgresql`
- `sudo nano /etc/postgresql/13/main/pg_hba.conf`

Change `peer` to `trust` on the lines `local all postgres` and `local all all`

### Install PHP 7.4.33 and module pgsql
- `sudo apt-get update`
- `sudo apt-get install php`
- `sudo apt-get install php-pgsql`

- `sudo service apache2 restart`
- `sudo service postgresql restart`

# Clone the repository Github in apache
### Install git
- `apt-get install git git-core`
### Clone the repository
- `cd /var/www/html`
- `sudo git clone https://github.com/Lasssssa/SCHOOL_MANAGEMENT_APP` 
### Update
- `cd /var/www/html/SCHOOL_MANAGEMENT_APP`
- `sudo git pull https://github.com/Lasssssa/SCHOOL_MANAGEMENT_APP`

# Create the database

### Connect as super user
- `psql postgres postgres`

### Create the database with related role
- `CREATE ROLE adminprojet LOGIN ENCRYPTED PASSWORD 'yourPassword';`
- `CREATE DATABASE dbisen WITH OWNER adminprojet;`
- Leave the database using `\q`

### Create the table and fill it
- To create the table, use the file `model.sql` which is in the dir `sql`.
- To fill the database, use the file `data.sql` which is in the dir `sql` 

First move to that dir
- `cd /var/www/html/SCHOOL_MANAGEMENT_APP/sql`

Then execute the file using : 
- `psql -d dbisen -U adminprojet -f model.sql`
- To fill the database : 
- `psql -d dbisen -U adminprojet -f data.sql`

Now your server is all setup and you can start the application

# Use of the site

### Admin Part : 
- To test the admin part : `admintest@gmail.com` with password : `mdp`

### Student Part : 
- To test the student part : `elevetest@gmail.com` with password : `mdp`

### Professor Part : 
- To test the professor part : `proftest@gmail.com` with password : `mdp`

## Repository Github : 
https://github.com/Lasssssa/SCHOOL_MANAGEMENT_APP
