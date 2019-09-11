# Week 14 - Day 3

**Coding Session**

- Copy  this file with the name `firstname_lastname.md`
- Place it in `submissions/<your_folder>/week_14/day_3/` folder in `cohort_1` repo
- Push the file back to the online repo

**The provided database contains the marks obtained by the students in the following subjects Mathematics, Physics, Chemistry, Biology, Hindi & English (only available if they are present for that particular exam)**

Write the queries and the answers in the place provided for the questions

**1. Total count of users**  
Query

```
db.users.count()
```
Answer
```
5664

```

**2. Count of users who scored 50 marks in Mathematics**  
Query
```
db.marks.find({"Mathematics":50}).count()

```
Answer
```
43
```
**3. Count of users who scored less than 30 marks in Physics**  
Query
```
db.marks.find({Physics:{$lt:30}}).count()
```
Answer
```
1636
```
**4. Count of users who scored more than 70 marks in Biology**  
Query
```
db.marks.find({Biology:{$gt:70}}).count()

```
Answer
```
1647
```
**5. List of top 10 performers in Physics sorted alphabetically**  
Query
```
db.marks.aggregate({$sort:{Physics:-1,name:1}},{$limit:10})

```
**6. Count of students who score more than 80 in Physics & Chemistry and less than 30 in Biology**  
Query
```
db.marks.find({$and:[{Physics:{$gt:80}},{Chemistry:{$gt:80}},{Biology:{$lt:30}}]}).count()

```
Count
```
38
```
**7. Count of students who are absent for the Biology examination**  
Query
```
db.marks.find({Biology:0}).count()

```
Count
```
50
```

**8. List of top 20 performers based on their marks obtained in Physics and Chemistry**  
Query
```
db.marks.aggregate({$sort:{Physics:-1,Chemistry:-1}},{$limit:20})


```
Count
20```

```
**9. List of students from rank 25 to 50 based on the marks scored in English**  
Query
```
db.marks.aggregate({$sort:{English:-1}},{$skip:25},{$limit:25})
```
Count
```
25
```
**10. Count of student who are absent for atleast one examination**  
Query
```
db.marks.find({$or:[{English:0},{Physics:0},{Chemistry:0},{Biology:0},{Hindi:0},{Mathematics:0}]}).count()

```
Count
```
323

```
