3). Create a database with suitable example using MongoDB and implement

 a. Inserting and saving document (batch insert, insert validation):
 
 b. $where queries
 
 d. Cursors(Limit, skip, sort, advanced query options) 

 6. What is a $where query, and when should you use it?
Answer: A $where query in MongoDB allows you to use JavaScript expressions for querying documents. It should be used sparingly as it can be slower and less efficient than standard queries, especially on large datasets.

8. How can you retrieve only a subset of documents from a collection?
Answer: You can use the limit() and skip() methods. limit(n) retrieves the first n documents, while skip(n) skips the first n documents.

10. What does the sort() function do in MongoDB?
Answer: The sort() function orders the documents in a specified manner based on a given field. For example, { year: -1 } sorts the documents by the year field in descending order.

12. What are the differences between $and and $or operators?
Answer: The $and operator filters documents that satisfy all specified conditions, while the $or operator filters documents that satisfy at least one of the specified conditions.

14. What is a cursor in MongoDB, and how is it used?
Answer: A cursor in MongoDB is an object that allows you to iterate over query results one document at a time. Methods like limit(), skip(), and sort() can be chained with cursors for refined data retrieval.

16. What is the purpose of using use libraryDB in MongoDB?
Answer: The command use libraryDB switches the current database context to libraryDB. If the database does not exist, it will be created when a collection is added.

17. How does MongoDB handle schema validation?
Answer: MongoDB has a flexible schema by default, but schema validation rules can be added to collections using JSON Schema to enforce data types and structure.

18. Explain how you can filter books published before the year 1950 using a normal query without $where.
Answer: You can use a standard query like { "year": { $lt: 1950 } } to find books published before 1950. This is more efficient than using $where.

19. Why should $where queries be used cautiously in MongoDB?
Answer: $where queries evaluate JavaScript expressions, which can be slow and may pose security risks, such as JavaScript injection attacks. Standard MongoDB operators are generally faster and safer.

20. What is the difference between db.createCollection() and inserting documents directly into a new collection?
Answer: db.createCollection() explicitly creates a collection with optional settings (e.g., validation rules). However, inserting a document into a non-existent collection automatically creates the collection without additional settings.

21. How can you update documents in a MongoDB collection?
Answer: You can use updateOne(), updateMany(), or replaceOne() methods to modify existing documents based on specified criteria.

22. What are some advantages of using MongoDB for large datasets?
    
Answer: MongoDB offers high scalability, flexible schemas, and efficient handling of unstructured data, making it ideal for large and rapidly changing datasets.

23. How would you delete all documents from the 'books' collection without dropping the collection itself?
Answer: You can use db.books.deleteMany({}) to remove all documents without dropping the collection.
24. What is the use of find() in MongoDB, and how can it be enhanced?
Answer: find() retrieves documents matching a query. It can be enhanced using methods like sort(), limit(), and projection to customize the output.

25. What is the significance of using sort() in combination with limit()?
Answer: Using sort() with limit() is useful for retrieving a specific subset of ordered documents, like finding the latest entries or top results based on certain criteria.
