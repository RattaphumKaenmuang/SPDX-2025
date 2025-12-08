# Software Development (API + Testing)
## API
Entry for accessing the backend server's service on the their own terms
### REST API
* GET
* POST
* PUT
* DELETE

## Unit Testing
* A software test where each individual unit/component is tested
  * A unit may be an individual function, method, procedure, module, or object
* Best to ask PO (Product Owner) for unclear specifics when decisions need to be made, as developers may have misunderstood the finer details of the business side of the product

### Test Scope
* Boundary
  * Inputs at the edges of the acceptable/allowed range of inputs
  * Example:
    * Accept integers in the range of 10-20; Must test 9,10 and 20,21
    * Accept date from 10-10-1999 to 21-1-2010; Must test 9-10-1999, 10-10-1999, 21-1-2010, 22-1-2010
* Equivalence

### Test Coverage
* Lines of code executed / Total number of lines (Ideally should be at 100%)
* Commands (python)
  * pip install coverage
  * coverage run -m unittest unit_test.py -v
  * coverage report -m

Example of the result using the above commands:
  
| Name          | Stmts | Miss | Cover | Missing    |
|:-------------:|:-----:|:----:|:-----:|:----------:|
| app/app.py    |  19   |  9   |  53%  |8, 17-30, 34|
| unit_test.py  |  11   |  0   |  100% |            |

## Robot Framework
Open-source automation framework
* Call the API instead of calling the lines of code directly
  * Such as http://127.0.0.1/calculate/6/9 or http://127.0.0.1/index
* Able to generate detailed and very readable logs and test report files (XML/HTML)
* Made for people not familiar with programming in standard programming languages
  * Functions are called *Keywords*
  * Very loose with whitespaces in code
  * Incomprehensible
* Should be in a separate repository from the actual project's
* On Python (Windows Machine), needs both the robotframework and robotframework-requests pip packages to function
  * ```pip install robotframework```
  * ```pip install robotframework-requests```