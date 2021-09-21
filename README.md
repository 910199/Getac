# Getac
Build a container with PostGresql DB in it, anda run an API service connected with it 


The database is build with the Code-First Style, with the help of entity framework core migration.

\
\
Api service:
\
\
Following we follow the restful style to build a REST API service:


\
**Students perspective:**(Student Table, with [id] as primary key)

**-POST    url/stds**     (to create a student profile)

**-GET     url/stds/id**  (to query a student profile according to the identity of a student)

**-PUT     url/stds/id**  (to modify content of a student profile according to the identity of a student)

**-Delete  url/stds/id**  (to delete a student profile according to the identity of a student)






\
**Grade perspective** (GradeRow Table, with [id,subject] as primary key)

**-POST      url/grade**             (to create a new grade record)

**-GET       url/grade**             (to query all grade records)

**-GET       url/grade/id/subject**  (to query the grade of a certain subject of a certain student)

**-PATCH     url/grade/id/subject**          (to modify the grade of a certain subject of a certain student)

**-Delete    url/grade/id**          (to delete the grade of a certain subject of a certain student)

\
**From the Overview of Students' grade**

**-GET       url/relation**    (to return the following information sorted by the descending order)

A. Class

B. Identity

C. Name

D. Total grade

E. Rank




**The process to make API webservice into a docker image, and run as a container**


Try to wrap the api service into a container , and connect with the other container which has a PostgreSQL DB in it.

Success to build a docker image of our api service, two containers(DB and our web service) can be linked by command "--link", while running the image as a container.

