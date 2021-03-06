# About

This plugin makes [Slick](http://slick.typesafe.com/) a first-class citizen of Play 2.x.

The play-slick plugins consists of 3 features: 
 - A wrapper DB object that uses the datasources defined in the Play config files, and pulls them from a connection pool. It is there so it is possible to use Slick sessions in the same fashion as you would Anorm JDBC connections. There are some smart caching and load balancing that makes your connections to your DB more performant.
 - A DDL plugin, that reads Slick tables and automatically creates schema updates on reload. This is useful in particular for demos and to get started.
 - In addition it contains a wrapper to use play enumeratees together with Slick (thanks to Marc)

[![Build Status](https://travis-ci.org/playframework/play-slick.png?branch=master)](https://travis-ci.org/playframework/play-slick)

# Setup

In the `project/Build.scala` file add::

In your application, add `"com.typesafe.play" %% "play-slick" % "0.6.0.1"` to the appDependencies in your `project/Build.scala` file:

to your `play.Project`.

Example :

```scala
 val appDependencies = Seq(
   //other deps
  "com.typesafe.play" %% "play-slick" % "0.6.0.1" 
 )
```

```
db.default.driver=org.h2.Driver
db.default.url="jdbc:h2:mem:play"
db.default.user=sa
db.default.password=""
```
to **application.conf** and create a model. Creating models are described in the Slick documentation: http://slick.typesafe.com/doc/1.0.1/lifted-embedding.html#tables. 

# Usage
Please read more about usage on the [wiki](https://github.com/playframework/play-slick/wiki/Usage)

# Versioning

The Play Slick plugin supports several different versions of Play and Slick.

| Plugin version  | Play version       | Slick version      | Scala version |
|-----------------|--------------------|--------------------|---------------|
| 0.4.x           | 2.1.x              | 1.0.x              | 2.10.x        |
| 0.5.x           | 2.2.x              | 1.0.x              | 2.10.x        |
| 0.6.x           | 2.2.x              | 2.0.x              | 2.10.x        |
| 0.7.x (planned) | 2.3.x (unreleased) | 2.0.x              | 2.10.x        |
| 0.8.x (planned) | 2.3.x (unreleased) | 2.1.x (unreleased) | 2.10.x/2.11.x |

The plugin has its own release cycle and therefore is not integrated into either core Play or Slick.

Copyright
---------

Copyright: Typesafe 2013-2014
License: Apache License 2.0, http://www.apache.org/licenses/LICENSE-2.0.html
