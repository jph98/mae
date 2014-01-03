MavenArchetypeExample
=====================

This is an example Custom Maven Archetype that provides the following:

* JUnit 4.4
* Guava 13.0.1

How was this created?
---------------------

This was created by generating a standard Maven project (from Eclipse or Intellij) with the above dependencies.  Running the following command generates the archetype:

    mvn archetype:create-from-project

in the target directory.  

This project is the result of the archetype created in the target/generated-sources/archetype folder

How do I use this?
------------------

Git clone the repository:

        git clone git@github.com:jph98/mae.git
        
Install it into your local Maven repository:

        mvn install
        
If all goes well you can generate a new project using this archetype with:

        mvn archetype:generate -DarchetypeCatalog=local -DarchetypeGroupId=com.froyo -DarchetypeArtifactId=exampleproject-archetype -DarchetypeVersion=1.0 -DinteractiveMode=false -DgroupId=com.froyo -DartifactId=myfirstproject -Dpackage=com.froyo
        
An explanation of the parameters here:

* archetypeCatalog - specifies to use the local Maven catalog to locate the archetype
* archetypeGroupId - the group id I used for the archetype
* archetypeArtifactId - the artifact id I used for the archetype
* archetypeVersion - the version I used for the archetype
* interactiveMode - don't prompt for the above, do it in batch mode
* groupId - the group id YOU want to use (customise as you like)
* artifactId - the artifact id YOU want to use (customise as you like)
* pacakge - the package you want to use (customise as you like)

How do customise this further?
------------------------------

Download this project and look at the general structure of the project.

A good starting point is the Main.java class in the archetype-resources folder.  It contains a number of Velocity tags that are used replaced by Maven during the project creation process.

        #set( $symbol_pound = '#' )
        #set( $symbol_dollar = '$' )
        #set( $symbol_escape = '\' )
        package ${package};
        
Package in this case comes from the parameter passed in when you create a new project.

You might want to try the following from here:
* Adding more dependencies to the pom.xml to specify a more complete starter project (Mockito, log4j etc...)
* Adding a standard properties/yaml file in src/main/resources
* Customise the package structure where the source files are found
* Add the standard Maven plugins you need for your project
* Add custom repositories you require

The archetype-metadata.xml provides a list of filtering that occurs during project generation also.  The following extract creates the src/test/java directory.

        <fileSet filtered="true" encoding="UTF-8">
          <directory>src/test/java</directory>
          <includes>
            <include>**/*.java</include>
          </includes>
        </fileSet>
    
