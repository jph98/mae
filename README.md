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

How do I use this?
------------------

Git clone the repository:

        git@github.com:jph98/MavenArchetypeExample.git
        
Install it into your local Maven repository:

        mvn install
        
If all goes well you can generate a new project using this archetype with:

        mvn archetype:generate -DarchetypeCatalog=local -DarchetypeGroupId=com.froyo -DarchetypeArtifactId=exampleproject-archetype -DarchetypeVersion=0.0.1-SNAPSHOT -DinteractiveMode=false -DgroupId=com.froyo -DartifactId=myfirstproject -Dpackage=com.froyo
        
An explanation of the parameters here:

* archetypeCatalog - specifies to use the local Maven catalog to locate the archetype
* archetypeGroupId - the group id I used for the archetype
* archetypeArtifactId - the artifact id I used for the archetype
* archetypeVersion - the version I used for the archetype
* interactiveMode - don't prompt for the above, do it in batch mode
* groupId - the group id YOU want to use (customise as you like)
* artifactId - the artifact id YOU want to use (customise as you like)
* pacakge - the package you want to use (customise as you like)



