2). Create a database with suitable example using MongoDB and implement Execute at least 10 queries on any suitable MongoDB database that demonstrates following:

a. Find and find One (specific values)

b. Query criteria (Query conditionals, OR queries, $not, Conditional semantics) Type-specific queries (Null, Regular expression, Querying arrays)
Intermediate Theory Questions
What are query conditionals in MongoDB? Provide an example using $gt and $lte.

Answer: Query conditionals allow you to specify conditions for filtering documents. $gt checks for values greater than a specified number, and $lte checks for values less than or equal to a specified number. For example:
db.students.find({ age: { $gt: 20 } }) finds students older than 20.
db.students.find({ age: { $lte: 20 } }) finds students aged 20 or younger.
Explain the $or operator in MongoDB. How does it differ from using multiple conditions in an AND operation?

Answer: The $or operator returns documents that match at least one of the specified conditions. An AND operation matches documents that satisfy all conditions. For example:
$or: db.students.find({ $or: [{ department: "IT" }, { age: 20 }] }) returns students in the IT department or aged 20.
AND: db.students.find({ department: "IT", age: 20 }) returns students who are in the IT department and aged 20.
How can you filter documents using the $not operator in MongoDB, and when would you use it?

Answer: The $not operator inverts the result of a condition, filtering documents that do not match the given condition. For example:
db.students.find({ age: { $not: { $eq: 20 } } }) retrieves documents where age is not equal to 20.
Use $not when you want to exclude specific matches from your query results.
How do regular expression queries work in MongoDB, and what are their typical use cases?

Answer: Regular expression queries match string patterns within document fields. For example:
db.students.find({ name: { $regex: "^H" } }) finds documents where the name field starts with "H".
They are typically used for searching or filtering text data based on patterns, such as finding names starting with a specific letter.
What are type-specific queries in MongoDB, and why might you use the $type operator?

Answer: Type-specific queries allow you to filter documents based on the BSON type of a field. The $type operator is used to match documents where a field has a specific type. For example:
db.students.find({ graduated: { $type: "bool" } }) finds documents where graduated is a boolean value.
This is useful for ensuring data type consistency in queries.
Advanced Theory Questions
How does MongoDB handle indexing, and why is it important for query performance?

Answer: MongoDB uses indexes to improve query performance by allowing the database to quickly locate documents without scanning the entire collection. Indexes store a small portion of the dataset in a sorted order, which speeds up read operations. For example:
db.students.createIndex({ name: 1 }) creates an index on the name field.
Without indexing, queries can be slow, especially on large datasets.
Explain how logical operators like $and, $or, and $not work together in a complex query. Provide an example.

Answer: Logical operators can be combined in complex queries to filter documents based on multiple conditions. For example:
db.students.find({ $and: [{ age: { $gt: 20 } }, { $or: [{ department: "IT" }, { graduated: true }] }] })
This query finds students older than 20 who are either in the IT department or have graduated.
What are the potential performance issues when using regular expression queries in MongoDB? How can you optimize these queries?

Answer: Regular expression queries can be slow because they may require scanning the entire collection, especially if the pattern is complex or unindexed. Optimization can be achieved by:
Using an index on the field being searched with the regular expression, such as db.students.createIndex({ name: 1 }).
Using anchored expressions like ^pattern to reduce the search space.
How would you query for documents where an array field contains at least one element matching a specific condition (e.g., using $elemMatch)?

Answer: You can use $elemMatch to match documents where an array field contains at least one element that satisfies a condition. For example:
db.students.find({ subjects: { $elemMatch: { $eq: "Math" } } })
This finds documents where the subjects array contains "Math".
What is the difference between querying a nested document and querying an array in MongoDB? Give an example of each.

Answer: Querying a nested document involves accessing fields within an embedded document, while querying an array involves matching elements within an array field.
Nested Document: db.students.find({ "address.city": "Pune" }) queries a field inside an embedded address document.
Array: db.students.find({ subjects: "Math" }) queries documents where the subjects array contains "Math".
