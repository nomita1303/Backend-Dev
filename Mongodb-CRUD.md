Q1. What are the advantages of using Mongoose over the native MongoDB driver?

Answer:
Mongoose provides a higher-level abstraction over the native MongoDB driver, making development easier and more structured. It allows developers to define schemas and models, which enforce a consistent structure on the data. It also provides built-in validation to ensure data integrity.
Mongoose simplifies database operations with easy-to-use methods instead of writing complex queries. It supports middleware (hooks) to run logic before or after operations such as saving or updating documents. It also provides features like population to handle relationships between collections. Overall, it improves code readability, maintainability, and developer productivity.

Q2. Explain the difference between findOneAndUpdate() and updateOne().

Answer:
findOneAndUpdate() finds a single document and updates it, and it can return the updated document if specified. It is useful when you need the modified document immediately after the update.
updateOne() updates a single document that matches the condition but does not return the updated document. It only returns a result object indicating whether the update was successful.
In summary, findOneAndUpdate() is used when you need the updated document, while updateOne() is used for simple updates where the returned document is not required.

Q3. What is the purpose of middleware in Mongoose?

Answer:
Middleware in Mongoose is used to execute functions before or after certain operations such as saving, updating, or deleting documents. These functions are also called hooks.
The purpose of middleware is to automate tasks like validation, logging, data transformation, or security-related operations such as password hashing. It helps in keeping the code clean and reusable by separating business logic from database operations.

Q4. How do you implement pagination in Mongoose?

Answer:
Pagination in Mongoose is implemented using the skip() and limit() methods. skip() is used to skip a certain number of documents, and limit() is used to restrict the number of documents returned.
Example:
db.students.find().skip(10).limit(5)
In Mongoose:
Student.find().skip(10).limit(5)
Here, skip(10) skips the first 10 documents, and limit(5) returns the next 5 documents. Pagination is useful for handling large datasets efficiently.

Q5. When should you use embedding vs referencing in MongoDB schema design?

Answer:
Embedding is used when related data is frequently accessed together and does not grow too large. It stores related data within the same document, which improves read performance. It is suitable for one-to-one or one-to-few relationships.
Referencing is used when related data is large, frequently updated, or shared across multiple documents. It stores references (IDs) of related documents in separate collections. It is suitable for one-to-many or many-to-many relationships.
In summary, embedding is preferred for simplicity and performance when data is closely related, while referencing is used for flexibility and scalability when data relationships are complex.