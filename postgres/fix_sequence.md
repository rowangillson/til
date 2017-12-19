You might have noticed that after bulk inserting records using the COPY statement in PostgreSQL the sequence IDs are not getting updated for any further inserts later on, and it would throw duplicate sequence ID errors.

So you would be wondering what makes this COPY statement different that it does not update the sequences.

Well the copy statement is not entirely the culprit here.

Internal Details/Reason
When you perform a normal INSERT, you often don't specify the value for the SEQUENCE-backed primary key explicitly. But if for some reason you did, you would run in to the same problems as you have with COPY. So as you see, COPY statement is not the real culprit here.

The sequence only increments when a value is evaluated by the database itself during the INSERT statements( it internally uses the nextval function underneath). If you provide values for your ID, the sequence is not used, thus it doesn't get incremented.

Fix
So now you know why it does not increment the sequence, but how do you fix the sequence after a bulk insert?

The answer is simple: you need to call the nextval function to reset the sequence generator.

    select setval('seqname',select max(id) from tablename));
