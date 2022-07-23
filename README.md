# Medisage-Assignment-2
Medisage has a team of telecallers that connects with doctors across the country and notifies about the new product launches in the medical market.

Points to remember:

Setup SQL in your machine.
Import the data in your database. ( Can use either SQL or CSV to dump the data ).
Provide 2-3 lines of your explanation on the approach of your solution.
Provide your queries along with the results in a new repository in github ( View the below format ).
Problem Statement
Explanation (2-3 lines)
Solution
Result Screenshot
Data: click here

Table: call_logs

Column Name	Type
id	int
doctor_id	int
city	varchar
state	varchar
telecaller_id	int
call_time_in_sec	int
product_call_status	varchar
created_at	datetime
updated_at	datetime
id represents primary key of the table.

doctor_id represents the id of doctor.

city and state are where a doctor is located.

telecaller_id is the foreign key id of telecaller.

call_time_in_sec is the call duration between the telecaller and doctor.

created_at is when the record has been created.

updated_at is when the record has been updated.

Table: telecallers

Column Name	Type
id	int
name	varchar
id represents primary key of the table.

name is the telecaller's name.

Column Name	Type
id	int
call_status	varchar
rank	int
id represents primary key of the table.

rank is the order of the call_status.

Problem1
You would like to fetch the doctors who got CALL_SUCCESSFUL and CALL_DONE_WITH_MORE_INFO_NEEDED in the first attempt.

Explanation: Let's say doctor id 4433 has been called thrice. In the first attempt, the telecaller got NO_RESPONSE status. In the second attempt, the telecaller got CALL_BACK_LATER status and in the third attempt, the telecaller got CALL_SUCCESSFUL status.

Another doctor with 2322 has been only once and the telecaller got CALL_SUCCESSFUL status.

We fetch the id 2322 and ignore the 4433.

The statement result format is in the following example.

doctor_id
1232
2131
123144
12314
Problem2
Write an SQL query that gives the top city with the more number of doctors with best call status CALL_SUCCESSFUL and CALL_DONE_WITH_MORE_INFO_NEEDED.

Example 1: What is best call status?

Let's say doctor id 4433 from city Mumbai has been called thrice. In the first attempt, the telecaller got NO_RESPONSE status. In the second attempt, the telecaller got CALL_BACK_LATER status and in the third attempt, the telecaller got CALL_SUCCESSFUL status.

So, the best call status for this doctor is CALL_SUCCESSFUL as the rank of this status is 1.

Example 2: Let's say a doctor id 1222 from Chennai has been called twice. In the first attempt, he got NO_RESPONSE status and in the second attempt, the got CALL_DONE_WITH_MORE_INFO_NEEDED status.

So, the best call status for this doctor is CALL_DONE_WITH_MORE_INFO_NEEDED as the rank of this status is 2.

The statement result format is in the following example.

city	call_status	num_of_doctors
Mumbai	CALL_SUCCESSFUL	1
Chennai	CALL_DONE_WITH_MORE_INFO_NEEDED	1
Problem3
Write an SQL query that reports you the doctors that have been called more than twice on the same day, yet got the status other than CALL_SUCCESSFUL, CALL_DONE_WITH_MORE_INFO_NEEDED, CALL_BACK_LATER.

The statement result format is in the following example.

doctor_id
12312
12314
231
243125
