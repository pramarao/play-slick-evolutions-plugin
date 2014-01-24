play-slick-evolutions-plugin
============================

A Play Framework SBT Plugin for Auto-Generating Slick Code. Still a prototype.

How to include
--------------

To use it in your Play project, download the code and add the following two lines to your `project/plugins.sbt` (replace the path to play-slick-evolutions-plugin as needed)

```
lazy val root = project.in(file(".")).dependsOn(playSlickPlugin)
lazy val playSlickPlugin = file(new File("./play-slick-evolutions-plugin").getAbsolutePath)
```

How to use
----------

1. Have some database evolutions (X.sql) in your /conf/evolutions/{databaseName} dir.
2. Configure the code generator in your application.conf:
  * `db.default.generator.profile` Required: The Slick profile you want to use in your app (e.g. `scala.slick.driver.MySQLDriver`)
  * `db.default.generator.mode` Optional: the compatibility mode that H2 should use for reading your evolutions (e.g. `MySQL`)

