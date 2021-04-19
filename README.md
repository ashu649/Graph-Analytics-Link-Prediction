# Link-Prediction-Graph-Analytics
Use graph analytics to predict relationships between entities

<b>Project Background :</b>

This repo implements the link prediction concepts described in Chapter - 8 of "Graph Algorithm" book by Mark Needham & Amy E. Holder. One can download a free copy of this excellent book at https://neo4j.com/graph-algorithms-book/. In this book, authors have implemented link prediction algorithm using PySpark ML algorithms.

In this repo I have shared the implementation of link prediction algorithm using popular Sklearn and Pandas python libraries (instead of PySpark) and also demontrated how we can use Neo4J (Graph Database) connectors to transmit data/commands across python and Neo4J servers.

We’ll use paper citation dataset containing information about research papers, authors, author relationship and citation relationship. We'll create a coauthors graph based on authors who have collaborated on papers and then predict future collaborations between pairs of authors. We’re only interested in collaborations between authors who haven’t collaborated before—we’re not concerned with multiple collaborations between pairs of authors. (see Dataset section below for more details)

<b>Technologies used in the repo:</b>

Python (Sklearn, Pandas and Neo4j libraries) <br/>
Neo4J Desktop Edition <br/>
Cypher Query Language

<b>Prerequisites:</b>

Graph Theory Concepts (presented very well in the book) <br/>
Familiarity with Neo4J Graph Database <br/>
Basic knowledge of Cypher query language <br/>
Knowledge of Sklearn and Pandas libraries

<b> Dataset (info taken from page 200 of "Graph Algorithms" book) </b> <br/>
<a href = "https://www.aminer.org/citation"> Citation Network Dataset </a>, a research dataset extracted from DBLP, ACM, and MAG. The dataset is described in the paper <a href="http://keg.cs.tsinghua.edu.cn/jietang/publications/KDD08-Tang-et-al-ArnetMiner.pdf">  “ArnetMiner: Extraction and Mining of Academic Social Networks”, by J. Tang et al.</a> The dataset version used in the book (DBLP-Citation-network V10) contains 3,079,007 papers, 1,766,547 authors, 9,437,718 author relationships, and 25,166,994 citation relationships. We’ll be working with a subset focused on articles that appeared in the following publications: <br/>
• Lecture Notes in Computer Science <br/>
• Communications of the ACM <br/>
• International Conference on Software Engineering <br/>
• Advances in Computing and Communications <br/> </br>
Our resulting dataset contains 51,956 papers, 80,299 authors, 140,575 author relationships, and 28,706 citation relationships. We’ll create a coauthors graph based on
authors who have collaborated on papers and then predict future collaborations between pairs of authors. We’re only interested in collaborations between authors
who haven’t collaborated before—we’re not concerned with multiple collaborations between pairs of authors.

<b> Process Overview (see Python Code for details)</b> <br/>
Load data into Neo4J <br/>
Create balance data and split samples into Pandas DataFrames for training and testing <br/>
Implement ML methods for link prediction  <br/>
Train and evaluate various versions of ML prediction models, starting with basic graphy features and adding more graph algorithm features extracted using Neo4j <br/>
