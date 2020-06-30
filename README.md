# Saneblog
A minimalistic blogging platform because I am sick and tired of finding a blogging platform that is not bloated with unnecessary features.  Bottle(a microframework for Python) is required for this project

## Below is the technical diagram.
![alt text](https://github.com/o92/Saneblog/blob/master/Overview.PNG)

## Schema is as follows
CREATE TABLE `Comments` (
  `guid` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `dateCreated` datetime DEFAULT CURRENT_TIMESTAMP,
  `commenttext` mediumtext NOT NULL,
  `userguid` varchar(200) NOT NULL,
  `postguid` varchar(200) NOT NULL,
  `email` varchar(100) NOT NULL,
  PRIMARY KEY (`guid`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

CREATE TABLE `Posts` (
  `guid` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `title` varchar(100) CHARACTER SET latin1 NOT NULL,
  `articleText` longtext NOT NULL,
  `dateCreated` datetime DEFAULT CURRENT_TIMESTAMP,
  `dateUpdated` datetime DEFAULT NULL ON UPDATE CURRENT_TIMESTAMP,
  `createdBy` varchar(200) NOT NULL,
  PRIMARY KEY (`guid`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;

CREATE TABLE `Likes` (
  `guid` int(10) unsigned NOT NULL AUTO_INCREMENT,
  `userguid` varchar(200) NOT NULL,
  `postguid` int(10) unsigned NOT NULL,
  `dateCreated` datetime DEFAULT CURRENT_TIMESTAMP,
  PRIMARY KEY (`guid`)
) ENGINE=InnoDB DEFAULT CHARSET=utf8mb4;