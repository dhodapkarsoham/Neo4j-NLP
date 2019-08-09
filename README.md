# Neo4j-NLP

Natural Language Processing is a hard problem to solve because of ambiguity in natural languages. Adding context gets us one step closer towards solving that problem by giving meaning to the relationships between words.
Graphs are a good structure for representing relationships between text which can help add meaning to how text is interpreted in a particular context.

[Neo4j](https://neo4j.com) is a graph database platform which lets users leverage the power of property-graph model to map relationships between entities involved in the graph in a easy, dynamic and scalable way. Performing NLP functions inside a graph database has been made easy by [GraphAware](https://graphaware.com), which allows usage of NLP functions with a plugin for Neo4j.
Depending on the data, performing NLP inside a graph enables us to easily find connections in the data and then build a knowledge graph based on those connections.

In addition to going from raw text to knowledge graphs, one can also build NLU-NLG systems on top of a Neo4j database towards a true natural language conversational AI.
The system demonstrated in this application tries to move towards this by building a near-natural language querying for the graph database underneath.
We can also build such an interface on top of an existing database by leveraging the relationships which are already there.
We'll take a look at both of these approaches by using BBC Business Articles for the first approach, and the [Neo4j Panama Papers Database by ICIJ](https://offshoreleaks.icij.org/pages/database) for the second one.
