Question 2:
SELECT COUNT(DISTINCT PULocationID) FROM (EXTERNAL OR NATIVE TABLE);

Question3:
SELECT COUNT(*) FROM green_taxi WHERE fare_amount = 0;

Question 4"
CREATE TABLE green_taxi_opt
PARTITION BY pickup_date
CLUSTER BY PUlocationID
AS
SELECT
  *  
FROM
  green_taxi;

Question 5:
SELECT DISTINCT PULocationID
FROM (green_taxi partitioned and clustered and normal)
WHERE pickup_date >= date('2022-06-01')
  AND pickup_date < date('2022-07-01');

