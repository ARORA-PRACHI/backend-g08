<!-- task1: db.col_name.updateOne() db.col_name.updateMany() db.col_name.findOneAndUpdate() db.col_name.replaceOne()

task2: db.col_name.deleteOne() db.col_name.deleteMany() db.col_name.findOneAndDelete()

//$type:-

// chitkara> db.student.find({ age: { $type: "number" } })
// [
//   {
//     _id: ObjectId('66cec02ff94e82ba792710c1'),
//     name: 'Alice',
//     age: 20,
//     marks: 85,
//     subject: 'DataScience',
//     address: 'Chitkara University',
//     grade: 'A+'
//   },
//   {
//     _id: ObjectId('66cec02ff94e82ba792710c2'),
//     name: 'Bob',
//     age: 22,
//     marks: 90,
//     subject: 'DataScience',
//     address: 'Chitkara University',
//     grade: 'A'
//   },
//   {
//     _id: ObjectId('66cec02ff94e82ba792710c3'),
//     name: 'Charlie',
//     age: 21,
//     marks: 92,
//     subject: 'DataScience',
//     address: 'Chitkara University',
//     grade: 'B+'
//   },
//   {
//     _id: ObjectId('66cec02ff94e82ba792710c4'),
//     name: 'David',
//     age: 23,
//     marks: 88,
//     subject: 'DataScience',
//     address: 'Chitkara University',
//     grade: 'A'
//   },
//   {
//     _id: ObjectId('66cec02ff94e82ba792710c5'),
//     name: 'Eve',
//     age: 19,
//     marks: 95,
//     subject: 'DataScience',
//     address: 'Chitkara University',
//     grade: 'C'
//   }
// ]
Last login: Sun Sep  1 20:59:08 on ttys000
/Users/apple/.zshrc:2: command not found: Export
apple@Prachis-MacBook-Air ~ % mongosh
Current Mongosh Log ID:	66d4aa754f2113b7cab7651f
Connecting to:		mongodb://127.0.0.1:27017/?directConnection=true&serverSelectionTimeoutMS=2000&appName=mongosh+2.3.0
Using MongoDB:		7.0.14
Using Mongosh:		2.3.0

For mongosh info see: https://www.mongodb.com/docs/mongodb-shell/

------
   The server generated these startup warnings when booting
   2024-09-01T08:03:24.026+05:30: Access control is not enabled for the database. Read and write access to data and configuration is unrestricted
------

test> show dbs
Chitkara  152.00 KiB
admin      40.00 KiB
config     72.00 KiB
local      72.00 KiB
test> use Chitkara
switched to db Chitkara
Chitkara> db.student.find({ $and: [ { age: 22 }, { marks: 50 }] })

Chitkara> db.Student.find({ $and: [ { age: 22 }, { marks: 50 }] })
[
  {
    _id: ObjectId('66d0325f09a820681c903b97'),
    name: 'John',
    age: 22,
    marks: 50,
    subject: 'Math'
  }
]
Chitkara> db.Student.find({ $or: [ { age: 22 }, { marks: 50 }] })
[
  {
    _id: ObjectId('66d0325f09a820681c903b97'),
    name: 'John',
    age: 22,
    marks: 50,
    subject: 'Math'
  }
]
Chitkara> db.Student.find({ $nor: [ { age: 22 }, { marks: 50 }] })
[
  {
    _id: ObjectId('66d0325f09a820681c903b96'),
    name: 'Emily',
    age: 21,
    marks: 48,
    subject: 'Science'
  },
  {
    _id: ObjectId('66d0325f09a820681c903b98'),
    name: 'Michael',
    age: 20,
    marks: 42,
    subject: 'History'
  }
]
Chitkara> db.Student.find({age:{$not:{$eq:22}}})
[
  {
    _id: ObjectId('66d0325f09a820681c903b96'),
    name: 'Emily',
    age: 21,
    marks: 48,
    subject: 'Science'
  },
  {
    _id: ObjectId('66d0325f09a820681c903b98'),
    name: 'Michael',
    age: 20,
    marks: 42,
    subject: 'History'
  }
]
Chitkara>  -->
