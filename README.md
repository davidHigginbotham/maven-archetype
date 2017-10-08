//Goals of the archetypes 

1 - Provide us with templates for different types of projects Here's a couple patterns we've seen:

A rabbit consumer with database support
A Rest endpoint with rabbit support 
A Rest endpoint with database support

2 - Over time enhancements, better practices, and upgrades will be applied to the archetypes allowing us to isolate/control
our best practices.

How to use it:

1 - Create a new project based on the patriarch archetype.

2 - Place all code you want copied into your project under src/main/resources/archetype-resources/src/main/java

3 - Place any test code you want copied into your project under src/test/resources/archetype-resources/src/main/java

4 - Modify the pom under src/main/resources/archetype-resources for the archetype's needs.
 
5 - up the release of the archetype so we can track changes just like any other project.

6 - When your ready to build the archetype do a mvn install.

7 - A local catalog file is required in order for Maven to be aware of your archetype.
 
    To generate the archetype catalog file: mvn archetype:crawl -Dcatalog=archetype-catalog.xml.
    The file should be created in your local .m2 folder.
    
8 - Now you can try to create a project with your archetype.

    There might be a better way but what I did was create a folder under my IdeaProjects folder, then run this command
    
 

mvn archetype:generate 
    -DarchetypeGroupId={group id found in the pom file of the archetype}
    -DarchetypeArtifactId={Artifactid found in the pom file of the archetype} 
    -DarchetypeVersion={version found in the pom file of the archetype} 
    -DgroupId={group id you want to use in your new project}
    -DartifactId={artifact id you want to use in your new project}
    
Example:
 
mvn archetype:generate 
    -DarchetypeGroupId=com.domain.archetype 
    -DarchetypeArtifactId=rest-crud 
    -DarchetypeVersion=1.0.0.SNAPSHOT 
    -DgroupId=com.domain 
    -DartifactId=test-archetype
