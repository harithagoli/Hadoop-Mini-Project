# Hadoop-Mini-Project
In this project, we will read from a vehicle accident/repair data file and output the counts of accidents group by combination of verhicle make and year.

Implementation
Overview
We will use map-reduce pragramming model to solving this problem. Programming language is python.

map-reduce process
There will be two map-reduce process

Map-reduce 1: to filter out accidents with vehicle make and year populated. It will read source data file and output key pair as (make+year,1)

Map-reduce 2: to output the count number of accident occurrences for vehicle make and year. It will read the output of map-reduce 1 and output result, (make+year, count)

python code
There are 4 python scripts, which will server as mappers, reducers of the two map-reduce process

mapper1.py: reads the input data, extract vin_number and output (key, value) pair as key--vin_number, value --incident type, make, and year.
reducer1.py: reads the mapper output, pick accident records, populate year and make and write them to output destination
mapper2.py: reads the previous reducer output and output (key, value) pair as (combination of make and year, 1)
reducer2.py: reads the mapper output . Within the group of make and year, sum all the 1s to produce the total count as the output.
