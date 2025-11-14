<h2>CRUD Operations in MongoDB</h2>  

CRUD stands for:
1.Create
2.Read
3.Update
4.Delete

These are the four basic operations you perform on a database.

 <h3>1. CREATE (Insert Data)</h3>  
Insert One Document
db.users.insertOne({
  name: "John",
  age: 25,
  city: "Mumbai"
});

Insert Many Documents
db.users.insertMany([
  { name: "Aisha", age: 22, city: "Delhi" },
  { name: "Rahul", age: 30, city: "Pune" }
]);
<img width="1771" height="1014" alt="Screenshot 2025-11-14 204421" src="https://github.com/user-attachments/assets/dc15121a-e765-4095-a6d0-24354ae25941" />


<h3>2. READ (Find Data)</h3>  
Find All Documents
db.users.find();

Find One Document
db.users.findOne({ name: "John" });

Filter Data
db.users.find({ age: { $gt: 25 } });

Select Specific Fields
db.users.find(
  { city: "Mumbai" },
  { name: 1, age: 1 }
);
<img width="1802" height="1007" alt="Screenshot 2025-11-14 204615" src="https://github.com/user-attachments/assets/61fe834e-0779-417e-812f-53aa8b8b8ff0" />


<h3> 3. UPDATE (Modify Data)</h3>  
Update One
db.users.updateOne(
  { name: "John" },
  { $set: { age: 26 } }
);

Update Many
db.users.updateMany(
  { city: "Delhi" },
  { $set: { active: true } }
);
<img width="1778" height="1011" alt="Screenshot 2025-11-14 204719" src="https://github.com/user-attachments/assets/fcc422f4-8a6f-40c8-9337-ac789fe5db0e" />


Increment a Field
db.users.updateOne(
  { name: "dev" },
  { $inc: { age: 1 } }
);
<img width="1779" height="1014" alt="Screenshot 2025-11-14 204831" src="https://github.com/user-attachments/assets/a90cda43-4ed9-47e7-b117-0b8874534207" />


<h3>4. DELETE (Remove Data)</h3>  
Delete One Document
db.users.deleteOne({ name: "John" });

Delete Many Documents
db.users.deleteMany({ age: { $lt: 18 } });
