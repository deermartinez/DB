# DB
Students database
Every year, students apply and compete through extra curricular and gpa for their top chosen classes
We get to look at some of the basic information of these students and those classes
## Model
![Beg. Model](/images/model.png)
Although more is included, we are only lookin at the relationship between the Students table and the Classes. 
## Tables
![Starting table](/images/Insert.png)
## Queries and questions
### How do we read out data?
select * from Class ;
select * from Students;
### Which students have an averageand above GPA?
select * from Students where student_gpa>25;;
### I want to look at Students in rank of GPA from highest to lowest
select * from Students order by student_gpa asc;
### I want to find this specific student
select * from Students where student_first like '&C' or student_last like 'B&';
### How many students do we have data collected on?
select count(*) as student_first from Students;
### What is the highest GPA?
select max(student_gpa) from Students;
### What is the name of the student with the highest GPA?
select student_first,student_last from Students where student_gpa=(select max(student_gpa));
### Change the room number of Course 101 section 2002
update Class set room=378326 where class_course_id="101/2002";
### Monday and Wednesday classes are being moved-take them out.
delete from Class where course_days="M/W";
## What Students have a matchind GPA to the requirements of any class listed?
select * from Class inner join Students on Class.req_id=Students.student_gpa;
## Which classes are students applying for?
select * from Students left join Class on Students.class_id=Class.class_course_id;
### What does our database look like now?
select * from Students;
select * from Class;

## Total operation output
![Total](/images/output.png)


