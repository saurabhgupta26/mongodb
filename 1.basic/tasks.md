#### write commands for following mongodb opertaions

1. create a database named `sports`
// Answer here ..
use sports;

2. list all databases present in local mongod server.
// Answer here..
show dbs;

3. create 3 collections named `cricket`, `football`, `TT` in sports database.
//Answer here...
db.createCollection('cricket');
db.createCollection('football');
db.createCollection('tt');


4. add 3 players in each of above collections which should have fields like `name`, `age`, `email`, state and auction_price.
db.cricket.insert({name: 'Sachin', age: 33, email: 'sachinindia@gmail.com', state: 'Mumbai', auction_price: '40000000'});
db.cricket.insert({name: 'Saurav', age: 45, email: 'sauravganguly@gmail.com',state : 'Kolkata', auction_price:'20000000'});
db.cricket.insert({name: 'Kohli', age: 33, email: 'kohliindia@gmail.com', state: 'Delhi', auction_price: '40000000'});

db.football.insert({name: 'C.Ronaldo', age: 43, email: 'ronaldo@gmail.com', state: 'Mumbai', auction_price: 40000000});
db.football.insert({name: 'Messi', age: 45, email: 'messi@gmail.com',state : 'Kolkata', auction_price:20000000});
db.football.insert({name: 'Neymar', age: 33, email: 'neymar@gmail.com', state: 'Delhi', auction_price: 40000000});

db.tt.insert({name: 'Sachin', age: 33, email: 'sachinindia@gmail.com', state: 'Mumbai', auction_price: 40000000});
db.tt.insert({name: 'Saurav', age: 45, email: 'sauravganguly@gmail.com',state : 'Kolkata', auction_price:20000000});
db.tt.insert({name: 'Kohli', age: 33, email: 'kohliindia@gmail.com', state: 'Delhi', auction_price: 40000000});


5. list all collections in sports database.
db.cricket.find();
db.football.find();
db.tt.find();


6. rename `TT` collection to `tennis`.
db.tt.renameCollection('tennis');

7. create a capped collection called `khokho` which should have max 3 documents.
  Try inserting more than 3 and output the result here ?

db.createCollection('Khokho', {capped: true,size: 64*1024, max:3});
//It overwrites the previous gives documents, i.e., FIFO.

8. check whether a collection is capped or not?
db.khokho.isCapped();
//true
db.tennis.isCapped();
//false

9. remove all documents from `football` collection.
db.football.remove({});

10. delete cricket collection completely.
db.cricket.drop();

11. rename database sports to games

db.copyDatabase('sports', 'games');
use sports;
db.dropDatabase();

12. delete sports database. 
use sports;
db.dropDatabase();
