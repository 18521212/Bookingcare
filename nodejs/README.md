xampp/phpMyAdmin
config.inc

/* Authentication type and info */
$cfg['Servers'][$i]['auth_type'] = 'config';
$cfg['Servers'][$i]['user'] = 'root';
$cfg['Servers'][$i]['password'] = '${your password mysql}';//
$cfg['Servers'][$i]['extension'] = 'mysqli';
$cfg['Servers'][$i]['AllowNoPassword'] = true;
$cfg['Lang'] = '';

nodejs/src/config/config.json

"development": {
    "username": "root",
    "password": "${your password mysql}",
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

const sequelize = new Sequelize('fullstack', 'root', '${your password mysql}', {
    host: 'localhost',
    dialect: 'mysql',
    logging: false
});