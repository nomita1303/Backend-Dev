Q1. Explain the key differences between SQL and NoSQL databases with examples.

Answer:
SQL and NoSQL databases differ in structure, schema, scalability, and usage.
SQL databases use a table-based structure with rows and columns, while NoSQL databases use flexible formats such as documents, key-value pairs, or graphs. SQL databases have a fixed schema, meaning the structure must be defined before inserting data, whereas NoSQL databases have a dynamic schema that allows changes easily.
SQL uses a structured query language (SQL) for operations, while NoSQL databases use different query methods depending on the system, such as MongoDB’s JSON-like queries. SQL databases scale vertically by increasing hardware capacity, whereas NoSQL databases scale horizontally by adding more servers.
SQL databases support strong relationships using JOIN operations, while NoSQL databases typically use embedding or referencing.

Examples: SQL databases include MySQL and PostgreSQL. NoSQL databases include MongoDB and Cassandra.

Example queries:
SQL: SELECT * FROM students WHERE gpa > 3.5;
MongoDB: db.students.find({ gpa: { $gt: 3.5 } })

Q2. What does the CAP theorem state, and why can’t a distributed system guarantee all three properties?

Answer:
The CAP theorem states that a distributed system can guarantee only two out of the following three properties: Consistency, Availability, and Partition Tolerance.
Consistency means all nodes in the system see the same data at the same time. Availability means every request receives a response, even if it may not be the latest data. Partition tolerance means the system continues to function even when there is a network failure between nodes.
In real-world distributed systems, network partitions are unavoidable. When a partition occurs, the system must choose between consistency and availability. If it chooses consistency, some requests may be rejected, reducing availability. If it chooses availability, it may return outdated or inconsistent data. Therefore, it is not possible to guarantee all three properties simultaneously.

Q3. Describe three scenarios where MongoDB would be preferred over a relational database.

Answer:
MongoDB is preferred in the following scenarios:
When dealing with unstructured or semi-structured data where the schema may change frequently, such as user profiles or logs.
When high scalability is required, especially for applications that need to handle large volumes of data across multiple servers, such as social media platforms.
When rapid development and prototyping are needed, as MongoDB does not require a predefined schema, making it easier to build and modify applications quickly.

Q4. Why does MongoDB use BSON internally instead of storing documents as JSON?

Answer:
MongoDB uses BSON (Binary JSON) instead of JSON because it is more efficient for storage and processing. BSON is a binary format, which makes it faster for machines to parse compared to text-based JSON.
It also supports additional data types such as Date, ObjectId, and binary data, which are not directly supported in JSON. BSON improves performance in indexing and querying, making database operations faster and more efficient.

Q5. Write MongoDB queries to find all students with GPA above 3.5 and enrolled in “CS101”.

Answer:
Basic query:
db.students.find({ gpa: { $gt: 3.5 }, course: "CS101" })

Optimized query with projection:
db.students.find(
{ gpa: { $gt: 3.5 }, course: "CS101" },
{ name: 1, gpa: 1, _id: 0 }
)

For better performance, an index can be created:
db.students.createIndex({ gpa: 1, course: 1 })