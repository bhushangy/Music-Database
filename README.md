# Music-Database

This application will read an iTunes export file in XML and produce a properly 
normalized database with this structure:

Table name:     Artist
Columns   :  id     name


Table name:     Genre
Columns   :  id     name


Table name:     Album
Columns   :  id     artist_id    title


If you run the program multiple times in testing or with different files, make
sure to empty out the data before each run.

You can use this code as a starting point for your application: 
http://www.pythonlearn.com/code/tracks.zip. The ZIP file contains the Library.xml
file to be used as a sample track. You can export your own tracks from iTunes
and create a database.

Run a query like this on your
database and look for the data you expect to see:

SELECT Track.title, Artist.name, Album.title, Genre.name 
    FROM Track JOIN Genre JOIN Album JOIN Artist 
    ON Track.genre_id = Genre.ID and Track.album_id = Album.id 
    AND Album.artist_id = Artist.id
    ORDER BY Artist.name LIMIT 3
