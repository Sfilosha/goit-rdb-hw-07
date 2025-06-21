use mydb;

// 1st task
select id, date,
YEAR(date) as year,
MONTH(date) as month,
DAY(date) as day
from orders;

// 2nd task
select id, date,
date_add(date, interval 1 day) as new_date
from orders;

// 3rd task (without .00 in timestamp)
select id, date,
floor(unix_timestamp(date)) as timestamp_value
from orders;

// 3rd task (default)
select id, date,
unix_timestamp(date) as timestamp_value
from orders;

// 4th task
select count(\*) as counter
from orders
where date between '1996-07-10 00:00:00' and '1996-10-08 00:00:00';

//5th task
select id, date,
json_object('id', id, 'date', date) as json_object
from orders;
