# Non-functional Testing & Defect Tracking
* Not testing main features such as an API to query products, or export something as PDF
* But for requirements such as:
  * *This page must load within 20 ms*
  * *This site must be able to handle at least 1000 clients at once*
  * etc.

## jMeter
* Open source software developed by Apache in Java
* Load and performance testing tool (Simulate user traffics)
* Measures application performance
* Scriptable test scenarios
* Provides real-time results
* Analyses and reports data
* Supports testings for JDBC, FTP, LDAP, SMTP


### Thread Group
An element used to simulate user traffic, by representing a collection of concurrent users

* Loop Count: How many times each user will execute the test
* Ramp-Up Period: How long it will take to start all the users
  * In the case of 100 users with 100-second ramp-up period, the 100 users will be divided evenly along the timeframe; (100 users)/(100 seconds) = A new user is started every 1 second until the 100th user at the 100th second

### jMeter Elements
Example: Use HTTP Request Defaults to set the target server name (e.g., www.google.com) and create specific HTTP Request samplers for desired paths

### Listener
Turn the various metrics of the traffics into graphs in real-time.

* Throughput
* Average response time
* Deviation

## Defect Tracking

### Defect Types
* Requirement: A business requirement is changed abruptly and is yet to be reflected on the software
* Coding: Skill issue
* Graphic Design: Display/Browser issue
* Data Test: Environment/Data mismatches

### Severity Levels
* Critical: The related functions just died
* High: The system outputs incorrect results for a valid input
* Medium: Valid input begets correct outputs, but invalid inputs cause errors
* Low: Incorrect display of the data but otherwise low impact

### Defect Status Flow
![Defect Status Flow Image](https://www.c-sharpcorner.com/article/software-testing-the-essential-guide-to-bug-reports/Images/image003.jpg)