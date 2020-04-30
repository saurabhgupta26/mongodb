1. Create a database named `blog`.
use blog;

2. Create a collection called 'articles'.
db.createCollection('articles');

3. Insert multiple documents(at least 3) into articles. It should have fields
db.articles.insert({name:'Amir', profession: 'Actor', place : 'Mumbai', age: 45});
db.articles.insert({name:'Vicky Kaushal', profession: 'Actor', place : 'Mumbai', age: 33});
db.articles.insert({name:'Nasseruddin Shah', profession: 'Actor', place : 'Mumbai', age: 72});

4. Find all the articles using `db.COLLECTION_NAME.find()`
db.articles.find().pretty();

5. Find a document using _id field.
db.articles.find({_id: ObjectId("5ea72182aa1f07e506495d93")});

6. Find documents using title and author's name field.
db.articles.find({}, {title: 1, author_name: 1});

7. Find document using a specific tag.
db.articles.find({age: 33});

8. Update title of a document using its _id field.
db.articles.update({_id: ObjectId("5ea72ad0a50db3a0a9f2c483")}, {$set: {'name': 'Nassiruddin Shah'}});

9. Update a author's name using article's title.
db.articles.update({name:"Vicky Kaushal"}, {$set: {'place': 'Delhi'}});

10. rename details field to description from articles collection. 

db.articles.update({}, {$rename: {'name' : 'FirstName'}});

11. Add additional tag in a specific document.
db.articles.update({_id: ObjectId("5ea72ac3a50db3a0a9f2c482")}, {$push: {tags: 'Actor, Writer, Dancer'}});

12. Update an article's tags using $set and without $set.
  - Write the differences here ?
  
db.articles.update({_id: ObjectId("5ea72ac3a50db3a0a9f2c482")}, {$set: {tags: 'Actor, Dancer'}});
db.articles.update({_id: ObjectId("5ea72ac3a50db3a0a9f2c482")}, {$rename: {'Actor, Dancer': 'Actor, Dancer, Musician'}});

13. Increment an author's age by 5. 

db.articles.update({_id: ObjectId("5ea72ac3a50db3a0a9f2c482")}, {$inc:{age:5});


14. Delete a document using _id field with `db.COLLECTION_NAME.remove()`.

db.articles.remove({_id:ObjectId("5ea72ab6a50db3a0a9f2c481")});

Use sample.js data for below queries.

1. Find all males who play cricket.

2. Update user with extra golf field in sports array whose name is "Steve Ortega".

3. Find all users who play either 'football' or 'cricket'.

4. Find all users whose name includes 'ri' in their name.
