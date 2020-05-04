# Acceptance Testing Documentation template

Authors: Domenico Cefalo (s267569)

Date: 23/05/2019

Version: 1.0.0

# Contents

- [Scenarios](#scenarios)

- [Coverage of scenarios](#scenario-coverage)
- [Coverage of non-functional requirements](#nfr-coverage)



# Scenarios

```
<Define here additional scenarios for the application. The two original scenarios in the Requirements Document are reported here.>
```

| Scenario ID: SC1 | Corresponds to UC1                             |
| ---------------- | ---------------------------------------------- |
| Description      | Colleague uses one capsule of type 1           |
| Precondition     | account of C has enough money to buy capsule T |
| Postcondition    | account of C updated, count of T updated       |
| Step#            | Step description                               |
| 1                | Administrator selects capsule type T           |
| 2                | Administrator selects colleague C              |
| 3                | Deduce one for quantity of capsule T           |
| 4                | Deduce price of T from account of C            |

| Scenario ID: SC2 | Corresponds to UC2                                     |
| ---------------- | ------------------------------------------------------ |
| Description      | Colleague uses one capsule of type T, account negative |
| Precondition     | account of C has not enough money to buy capsule T     |
| Postcondition    | account of C updated, count of T updated               |
| Step#            | Step description                                       |
| 1                | Administrator selects capsule type T                   |
| 2                | Administrator selects colleague C                      |
| 3                | Deduce one for quantity of capsule T                   |
| 4                | Deduce price of T from account of C                    |
| 5                | Account of C is negative, issue warning                |

| Scenario ID: SC3 | Corresponds to UC3 |
| ---------------- | ------------------ |
| Description      | Colleague wants to recharge his account   |
| Precondition     | Account A exist  |
| Postcondition    | Account A of colleague C updated (post amount > pre amount) |
| Step#            | Step description |
| 1 | Administrator selects account A of colleague C|
| 2 | Administrator	increase account A of a certain quantity|
| 3 | Increase the LaTazza balance | 


| Scenario ID: SC4 | Corresponds to UC4 |
| ---------------- | ------------------ |
| Description      | Administrator wants to buy a certain type of capsules CT |
| Precondition     | LaTazza balance has enough money to buy capsules |
| Postcondition    | Number of capsules CT > previuos number of capsules CT and LaTazza balance < previuos LaTazza balance |
| Step#            | Step description          |
| 1 | Administrator selects the capsules type CT|
| 2 | Deduce the LaTazza balance |
| 3 | Increase the quantity of CT |
| 4 | Decrease the LaTazza balance |

| Scenario ID: SC5 | Corresponds to UC5 |
| ---------------- | ------------------ |
| Description      | Administrator wants to create a report on one colleague C |
| Precondition     | Colleague C exist and start timestamp < end timestamp |
| Postcondition    |  |
| Step#            | Step description  |
| 1 | Administrator selects the colleague C|
| 2 | Administrator selects the start timestamp and end timestamp |
| 3 | Application collects all transactions for C (recharges and capsules taken) |
| 4 | Application produces the report |

| Scenario ID: SC6 | Corresponds to UC6 |
| ---------------- | ------------------ |
| Description      | Administrator wants to create a report on all consumptions |
| Precondition     | Start timestamp < end timestamp |
| Postcondition    |  |
| Step#            | Step description  |
| 1 | Application collects all transactions (recharges, purchases, and capsules taken)|
| 2 | Administrator defines time range |
| 3 | Application produces the report |

| Scenario ID: SC7 | Corresponds to UC2 |
| ---------------- | ------------------ |
| Description      | Visitor V uses one capsule of type 1           |
| Precondition     | Capsult type 1 exist and Visitor V has no account  |
| Postcondition    | count of capsule type 1 updated and post LaTazza balance > pre LaTazza balance |
| Step#            | Step description                               |
| 1                | Administrator selects capsule type T           |
| 2                | Decrease one for quantity of capsule type 1|
| 3                | Deduce price of T |
| 4				   | Increase the LaTazza balance |



# Coverage of Scenarios

```
<Report in the following table the coverage of the scenarios listed above. Report at least an API test (defined on the functions of DataImpl only) and a GUI test (created with EyeAutomate) for each of the scenarios. For each scenario, report the functional requirements it covers.
In the API Tests column, report the name of the method of the API Test JUnit class you created. In the GUI Test column, report the name of the .txt file with the test case you created.>
```

### 

| Scenario ID | Functional Requirements covered | API Test(s) | GUI Test(s) |
| ----------- | ------------------------------- | ----------- | ----------- |
| 1 | FR1 |  it.polito.latazza.data.AcceptanceTest.scenario1Test()   |    test1.txt    |
| 2 | FR1 |      it.polito.latazza.data.AcceptanceTest.scenario2Test()       |      test2.txt      |
| 3 | FR3 |      it.polito.latazza.data.AcceptanceTest.scenario3Test()       |         test3.txt    |
| 4 | FR4 |      it.polito.latazza.data.AcceptanceTest.scenario4Test()       |      test4.txt       |
| 5 | FR5 |      it.polito.latazza.data.AcceptanceTest.scenario5Test()       |       test5.txt      |
| 6 | FR6 |      it.polito.latazza.data.AcceptanceTest.scenario6Test()       |       test6.txt      |
| 7 | FR2 |	it.polito.latazza.data.AcceptanceTest.scenario7Test()	|	test7.txt	|	



# Coverage of Non Functional Requirements

```
<Report in the following table the coverage of the Non Functional Requirements of the application - only those that can be tested with automated testing frameworks.>
```

### 

| Non Functional Requirement | Test name |
| -------------------------- | --------- |
| NFR2                           | it.polito.latazza.data.AcceotanceTest.testNFR2          |

