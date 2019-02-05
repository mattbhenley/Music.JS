!(https://github.com/mattbhenley/Images/blob/master/applemusic.PNG)

### Startup 
This HTML file is a template.
If you open it directly in the browser, you will see an empty page.

To begin the development, run `npm start`
To create a production bundle, use `npm run build`

### Database
There are six required columns: 
- `name`: The name of the song
- `artist`: The artist name
- `album`: The album name
- `track`: The index of the song relative to the album (To order songs in an album)
- `url`: A URL to the audio file
- `artwork`: A URL to the album artwork image
```mysql
mysql> use music;

Database changed
mysql> desc tracks;
+------------+------------------+------+-----+---------+----------------+
| Field      | Type             | Null | Key | Default | Extra          |
+------------+------------------+------+-----+---------+----------------+
| id         | int(10) unsigned | NO   | PRI | NULL    | auto_increment |
| created_at | timestamp        | YES  |     | NULL    |                |
| updated_at | timestamp        | YES  |     | NULL    |                |
| name       | varchar(255)     | NO   |     | NULL    |                |
| artist     | varchar(255)     | NO   |     | NULL    |                |
| album      | varchar(255)     | NO   |     | NULL    |                |
| track      | int(11)          | NO   |     | NULL    |                |
| url        | varchar(255)     | NO   |     | NULL    |                |
| artwork    | varchar(255)     | NO   |     | NULL    |                |
+------------+------------------+------+-----+---------+----------------+
9 rows in set (0.05 sec)
```

### API Endpoints
The backend is built with PHP using the Laravel ORM. I only needed a few API endpoints to get this working:
- `/albums` - Returns a list of all album names with their corresponding artist
- `/album/{album}` - Returns a list of songs from a specified album
- `/artists` - Returns a list of all artists
- `/artist/{artist}` - Returns a list of all albums from a specific artist
