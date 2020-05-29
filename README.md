# Hadoop-Mutual-Friends

Hadoop is a framework that can be used to store and process large collection of data in a parallel and distributed manner.
The framework is thus used here to solve the problem of finding mutual friends. This is useful as the process of finding mutual friends need not be repeated every time a profile is opened on many social networking sites , thus it may be pre-calculated and stored.

## Project Description 

The project consists of mapper and reducer code along with a sample input file to test the working.

### input.txt

Input file consists details of person and friends. Each line of the input file consists of name of a person and comma separated list of friends.
The name and list of friends is delimited by tab delimiter.    

### mapper.py

The mapper takes input from the input file and finds a ordered pair for each line in input file and returns the key -> value pair as ordered pair of common key -> friends list to the reducer.

### reducer.py

The reducer takes the common key (ordered pair) and finds the intersection of friends in the list of friends having same ordered pair as the key and finally returns the ordered pair of friends and list of their common friends.

## Running the code

1) Make project directory in the HDFS.
```bash
hadoop fs -mkdir "directory path"
```
2) Include the input file in project directory.
```bash
hadoop fs -put "input file path" "target directory path"
```
3) Run the given command to execute the codes.

```bash
hadoop jar "jar path" -input "input file path" -output "output path" -mapper "mapper path" -reducer "reducer path"
```  
4) Output can be seen by executing following command.
```bash
hadoop fs -cat "output directory path"
```  
