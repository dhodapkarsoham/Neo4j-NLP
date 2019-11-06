# Neo4j-NLP

Natural Language Processing is a hard problem to solve because of ambiguity in natural languages. Adding context gets us one step closer towards solving that problem by giving meaning to the relationships between words.
Graphs are a good structure for representing relationships between text which can help add meaning to how text is interpreted in a particular context.

[Neo4j](https://neo4j.com) is a graph database platform which lets users leverage the power of property-graph model to map relationships between entities involved in the graph in a easy, dynamic and scalable way. Performing NLP functions inside a graph database has been made easy by [GraphAware](https://graphaware.com), which allows usage of NLP functions with a plugin for Neo4j. Refer their documentation for getting started with NLP in Neo4j.
Depending on the data, performing NLP inside a graph enables us to easily find connections in the data and then build a knowledge graph based on those connections.

In addition to going from raw text to knowledge graphs, one can also build NLU-NLG systems on top of a Neo4j database towards a true natural language conversational AI.
The system demonstrated in this application tries to move towards this by building a near-natural language querying for the graph database underneath.
We can also build such an interface on top of an existing database by leveraging the relationships which are already there.
We'll take a look at both of these approaches by using BBC Business Articles for the first approach, and the [Neo4j Panama Papers Database by ICIJ](https://offshoreleaks.icij.org/pages/database) for the second one.

Some instructions/things to remember: <br>
* Neo4j version used -> Neo4j-Enterprise-3.5.6 <br>
* The BBC dataset is in archived format. Unzip it to get a folder containing business news articles having `.txt` extension. The path where you unzip this archive will go into `BBC_Ingestion.ipynb`, the program for reading these articles into a Neo4j database. To play with the BBC Dataset, load the data into a Neo4j database, run the NLP pipelines and see what insights you can get out of the data.
* Make sure that following lines are added to `neo4j.conf` file in `NEO4J_HOME/conf/`. For more help, please refer [Github for graphAware documentation](https://github.com/graphaware/neo4j-framework) <br>
`dbms.unmanaged_extension_classes=com.graphaware.server=/graphaware
com.graphaware.runtime.enabled=true
dbms.security.procedures.whitelist=ga.nlp.*
dbms.security.procedures.unrestricted=ga.nlp.*`<br>
* Before you start with the Panama Papers exploration , make sure that the folder `graph.db` used in Panama Papers Database is copied in your Neo4j folder in `NEO4J_HOME/data/databases/`.<br>
* Make sure you allocate sufficient heap size and page cache for Neo4j by making changes in `neo4j.conf` file in `NEO4J_HOME/conf/`. More help aobut this can be found on [Neo4j documentation page](https://neo4j.com/docs/operations-manual/current/performance/memory-configuration/).<br>
* To read more about this code works, head over to the [Neo4j Blog](https://neo4j.com/blog/accelerating-towards-natural-language-search-graphs/) post about this topic.
