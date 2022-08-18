Database Schema :  https://drawsql.app/


* How to get month from cratead_at as name jan
     SELECT monthname(created_at) FROM posts GROUP BY created_at;


 * Get shortname as created at Eg jan feb march
      SELECT DATE_FORMAT(created_at, '%b') FROM posts GROUP BY created_at;

* sql mode enable in sql 
      set global sql_mode='';

* sql in WHERE IN condition (Note: multiple categories where condition (1,43,4))

SELECT * from users WHERE 9 IN (category_id) 