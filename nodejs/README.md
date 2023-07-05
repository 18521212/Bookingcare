xampp/phpMyAdmin
config.inc

/* Authentication type and info */
$cfg['Servers'][$i]['auth_type'] = 'config';
$cfg['Servers'][$i]['user'] = 'root';
$cfg['Servers'][$i]['password'] = '${your password mysql}'; // notice password undefine source
$cfg['Servers'][$i]['extension'] = 'mysqli';
$cfg['Servers'][$i]['AllowNoPassword'] = true;
$cfg['Lang'] = '';

nodejs/src/config/config.json

"development": {
    "username": "root",
    "password": "${your password mysql}", // notice password undefine source
    "database": "${your table phpMyAdmin}",
    "host": "127.0.0.1",
    "dialect": "mysql",
    "logging": false,
    "query": {
      "raw": true
    },
    "timezone": "+07:00"
  },

nodejs/src/config/connectDB.js

const sequelize = new Sequelize('fullstack', 'root', '${your password mysql}', { // not mysql password
    host: 'localhost',
    dialect: 'mysql',
    logging: false
});

xampp config image max size

Note that: A BLOB can be 65535 bytes maximum (0.065535 MB) If you need more consider using a MEDIUMBLOB for 16777215 bytes (16.777215 MB) or a LONGBLOB for 4294967295 bytes (~ 4GB)

C:/xampp/mysql/bin/my.ini

# The MySQL server
default-character-set=utf8mb4
[mysqld]
port=3306
socket="C:/xampp/mysql/mysql.sock"
basedir="C:/xampp/mysql"
tmpdir="C:/xampp/tmp"
datadir="C:/xampp/mysql/data"
pid_file="mysql.pid"
# enable-named-pipe
key_buffer=16M
max_allowed_packet=16M
sort_buffer_size=512K
net_buffer_length=8K
read_buffer_size=256K
read_rnd_buffer_size=512K
myisam_sort_buffer_size=8M
log_error="mysql_error.log"

server.js

// app.use(bodyParser.json());
// app.use(bodyParser.urlencoded({ extended: true }))
app.use(bodyParser.json({ limit: '50mb' }));
app.use(bodyParser.urlencoded({ limit: '50mb', extended: true }))