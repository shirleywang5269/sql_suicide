# Queries for patients:

1. Query to get all the patients:
```sql
select * from patients
```

2. Query to get all the patients:
```sql
select * from patients
```

3. Query for getting age &time:
```sql
select admissions.subject_id, group_concat(admissions.hadm_id) , group_concat(dischtime), group_concat(admittime),group_concat(cast((julianday(admissions.dischtime)-julianday(admissions.admittime))as integer)), min(admissions.admittime), group_concat(cast((julianday(admissions.admittime) - nadmissions.mintime)as integer)) from admissions left outer join (select subject_id, min(julianday(admissions.admittime)) as mintime from admissions group by subject_id) nadmissions on
admissions.subject_id = nadmissions.subject_id where admissions.subject_id is not null group by admissions.subject_id;
```
