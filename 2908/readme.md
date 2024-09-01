Tasks Completed Find the data where student has age = 22 and marks = 90

Find the student whose marks is >= 80 and age >= 18

Find whose grades are A++

Last login: Sun Sep  1 20:13:39 on ttys000
/Users/apple/.zshrc:2: command not found: Export
apple@Prachis-MacBook-Air ~ % brew services start mongodb-community@7.0
Service `mongodb-community` already started, use `brew services restart mongodb-community` to restart.
apple@Prachis-MacBook-Air ~ % mongosh
Current Mongosh Log ID:	66d480cf13c4797cd2478fac
Connecting to:		mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.3.0
Using MongoDB:		7.0.14
Using Mongosh:		2.3.0

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-09-01T08:03:24.026+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
------

test> db.faculty.findOne({_id:ObjectId('66d4801a22a137132ddc02a0')})
null
test> use Chitkara
switched to db Chitkara
Chitkara> db.faculty.findOne({_id:ObjectId('66d4801a22a137132ddc02a0')})
{
  _id: ObjectId('66d4801a22a137132ddc02a0'),
  name: 'Nav',
  age: 21,
  marks: 92,
  subject: 'Chemistry'
}
Chitkara> db.faculty.find({marks:{$gte:80},age:{$gte:18}})
[
  {
    _id: ObjectId('66d4801a22a137132ddc029e'),
    name: 'Jack',
    age: 20,
    marks: 85,
    subject: 'Mathematics'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a0'),
    name: 'Nav',
    age: 21,
    marks: 92,
    subject: 'Chemistry'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a1'),
    name: 'Illu',
    age: 23,
    marks: 88,
    subject: 'Biology'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a2'),
    name: 'Eva',
    age: 19,
    marks: 95,
    subject: 'Computer Science'
  }
]
Chitkara> db.faculty.updateMany( {},{ $set:{subject:"DataScience", address:"Chitkara University"} } )
{
  acknowledged: true,
  insertedId: null,
  matchedCount: 6,
  modifiedCount: 6,
  upsertedCount: 0
}
Chitkara> db.faculty.bulkWrite([{ updateOne:{filter:{name:"Alice"},update:{$set:{grade:"A+"}}}},{updateOne:{filter:{name:"Bob"},update:{$set:{grade:"A"}}}}])
{
  acknowledged: true,
  insertedCount: 0,
  insertedIds: {},
  matchedCount: 1,
  modifiedCount: 1,
  deletedCount: 0,
  upsertedCount: 0,
  upsertedIds: {}
}
Chitkara> db.faculty.find({address:{$exists:true}})
[
  {
    _id: ObjectId('66d47f5722a137132ddc029d'),
    name: 'heena',
    age: 20,
    address: 'Chitkara University',
    subject: 'DataScience'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc029e'),
    name: 'Jack',
    age: 20,
    marks: 85,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc029f'),
    name: 'Bob',
    age: 22,
    marks: 78,
    subject: 'DataScience',
    address: 'Chitkara University',
    grade: 'A'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a0'),
    name: 'Nav',
    age: 21,
    marks: 92,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a1'),
    name: 'Illu',
    age: 23,
    marks: 88,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a2'),
    name: 'Eva',
    age: 19,
    marks: 95,
    subject: 'DataScience',
    address: 'Chitkara University'
  }
]
Chitkara> db.faculty.find({age:{$type:"number"}})
[
  {
    _id: ObjectId('66d47f5722a137132ddc029d'),
    name: 'heena',
    age: 20,
    address: 'Chitkara University',
    subject: 'DataScience'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc029e'),
    name: 'Jack',
    age: 20,
    marks: 85,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc029f'),
    name: 'Bob',
    age: 22,
    marks: 78,
    subject: 'DataScience',
    address: 'Chitkara University',
    grade: 'A'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a0'),
    name: 'Nav',
    age: 21,
    marks: 92,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a1'),
    name: 'Illu',
    age: 23,
    marks: 88,
    subject: 'DataScience',
    address: 'Chitkara University'
  },
  {
    _id: ObjectId('66d4801a22a137132ddc02a2'),
    name: 'Eva',
    age: 19,
    marks: 95,
    subject: 'DataScience',
    address: 'Chitkara University'
  }
]
Chitkara> 
