Bayes: A probabilistic personal wiki system and journal
=======================================================

Node:
-----

The 'node' is the basic data structure in Bayes, consisting of the following:

Node(label, probability, value)

Where each of these are:

Label (Varchar(512)) - A label for the node, also the unique key for a node.

Probability (Float) - A probability value that gives the chance of the value in the node
being true/correct/etc.

Value (text) - The data associated with the node. Sometimes a node is just a label and 
the labels probability value, otherwise it can be a photo, an article, an HTML
hyperlink, etc.

Relationships:
--------------

Nodes are laid out in a networked structure which is managed by different kinds 
of relationships between nodes. Each relationship in the database is between one 
pair of nodes only. A relationship consists of:

Relationship(node1, node2, type, probability, quantity)

Where each of these are:

Node1 (Varchar(512)) - Label of the first node in the relationship, which node this is depends on the 
type of relationship.

Node2 (Varchar(512)) - Label of the second node in the relationship, which node this is depends on the 
type of relationship.

Type (Varchar(30)) - The type of relationship between the two nodes.

Probability (Float) - The probability that this relationship holds, this attribute is
often used when nodes and their relationships are generated through a probabilistic
algorithm.

Quantity (Integer) - How many instances of this relationship exist. A relationship has a 
unique key of the two nodes and the relations type, this value is determined
by the key. If either of the two nodes or the type are changed it becomes a
different relationship, meaning that this is a sane way to store the number
of instances of this relationship. 