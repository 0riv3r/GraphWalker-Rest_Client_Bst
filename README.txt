
Rest API:
https://github.com/GraphWalker/graphwalker-project/wiki/Rest-API-overview

----------------------------------------------------------------------------

# generate the rest-client project using maven:
$ mvn -B archetype:generate -DarchetypeGroupId=org.apache.maven.archetypes  -DgroupId=com.cyberark -DartifactId=rest_client


**************************************************************
****     run GraphWalker online test as REST service      ****
**************************************************************

# in another terminal/PuTTy , lunch the GraphWalker REST service and load the model:

    Execute
    # If required, make sure to use the correct java:
    $ export JAVA_HOME=`/usr/libexec/java_home -v 1.8`
    $ cd workspace/GraphWalker-rest_client/
    $ java -jar ../lib/graphwalker-cli-4.2.0.jar -d all online -s RESTFUL -m src/main/resources/com/cyberark/BstModel.json "random(edge_coverage(100))"
    OR:
    $ java -jar ../lib/graphwalker-cli-4.2.0.jar -d all online -s RESTFUL -m src/main/resources/com/cyberark/BstModel.json "random(edge_coverage(100) && vertex_coverage(100))"
    OR:
    $ java -jar ../lib/graphwalker-cli-4.2.0.jar -d all online -s RESTFUL -m src/main/resources/com/cyberark/BstModel.json "random(time_duration(10))"


REST APIs:
https://github.com/GraphWalker/graphwalker-project/wiki/Rest-API-overview

Postman
=======
The Postman data is at lib/GraphWalker.postman_collection.json
you can copy its content and paste in your Postman import.


CLI HTTP client
===============
https://httpie.org/

CentOS:
$ yum install httpie

Mac:
$ brew install httpie

$ http GET  localhost:8887/graphwalker/hasNext

$ http GET  localhost:8887/graphwalker/getNext

$ http GET  localhost:8887/graphwalker/getData

$ http PUT  localhost:8887/graphwalker/restart



# in VS-Code run:
-----------------
Execute
# If required, make sure to use the correct java:
$ export JAVA_HOME=`/usr/libexec/java_home -v 1.8`
$ mvn clean compile exec:java -Dexec.mainClass="com.cyberark.BstTest"

or:
$ mvn clean
$ mvn compile
$ mvn exec:java -Dexec.mainClass="com.cyberark.BstTest"


