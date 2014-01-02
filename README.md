MavenArchetypeExample
=====================

This is an example Custom Maven Archetype that provides the following:

* JUnit 4.4
* Guava 13.0.1

How was this created?
---------------------

This was created by generating a standard Maven project (from Eclipse or Intellij) with the above dependencies.  Running the following command generates the archetype:

    mvn archetype:create-from-project

in the target directory.  This project is the result of the archetype created.

How do I use this instead of the maven-quickstart archetype?
------------------------------------------------------------

