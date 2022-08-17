Database Schema :  https://drawsql.app/


* How to get month from cratead_at as name jan

 SELECT monthname(created_at) FROM posts GROUP BY created_at;