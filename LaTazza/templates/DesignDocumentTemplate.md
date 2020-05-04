# Design Document Template

Authors: 
- Cetera Clemente s257234
- Borgone Roberto s267571
- Cefalo Domenico s267569
- Miro Filomeno Davide s256870

Date:
- 4/06/2019

Version:
- 3.0.0


# Contents

- [Package diagram](#package-diagram)
- [Class diagram](#class-diagram)
- [Verification traceability matrix](#verification-traceability-matrix)
- [Verification sequence diagrams](#verification-sequence-diagrams)

# Instructions

The design document has to comply with:
1. [Official Requirement Document](../Official\ Requirements\ Document.md)
2. [DataInterface.java](../src/main/java/it/polito/latazza/data/DataInterface.java)

UML diagrams **MUST** be written using plantuml notation.

# Package diagram

\<define UML package diagram >

```plantuml

package "it.polito.latazza" {

}

package "it.polito.latazza.data" {

}

package "it.polito.latazza.exception" {

}

package "it.polito.latazza.gui" {

}

it.polito.latazza ..down..> it.polito.latazza.data
it.polito.latazza ..down..> it.polito.latazza.gui
it.polito.latazza.data ..down..> it.polito.latazza.exception
it.polito.latazza.gui ..down..> it.polito.latazza.data

```

\<explain rationales for choices>

We have agreed that there is no need for additional packages since the existent ones are sufficent.

\<mention architectural patterns used, if any>

### Architectural patterns used: Layered (3 tiers: Data, Application Logic, Presentation), MVC

# Class diagram

\<for each package define class diagram with classes defined in the package>

```plantuml

title Class diagram of Package it.polito.latazza


class LaTazza {
  +void main()
}

```
***

```plantuml

title Class diagram of Package it.polito.latazza.exceptions


class BeverageException {
  +long serialVersionUID
}

class DateException {
  +long serialVersionUID
}

class EmployeeException {
  +long serialVersionUID
}

class NotEnoughCapsules {
  +long serialVersionUID
}

class NotEnoughBalance {
  +long serialVersionUID
}

```
***

```plantuml

title Class diagram of Package it.polito.latazza.data




class DataInterface {

  +Integer sellCapsules(Integer employeeId, Integer beverageId, Integer numberOfCapsules, Boolean fromAccount)
  +void sellCapsulesToVisitor(Integer beverageId, Integer numberOfCapsules)
  +Integer rechargeAccount(Integer id, Integer amountInCents)
  +void buyBoxes(Integer beverageId, Integer boxQuantity) 
  +List<String> getEmployeeReport(Integer employeeId, Date startDate, Date endDate)
  +List<String> getReport(Date startDate, Date endDate) 
  +Integer createBeverage(String name, Integer capsulesPerBox, Integer boxPrice) 
  +void updateBeverage(Integer id, String name, Integer capsulesPerBox, Integer boxPrice)
  +String getBeverageName(Integer id) 
  +Integer getBeverageCapsulesPerBox(Integer id) 
  +Integer getBeverageBoxPrice(Integer id)
  +List<Integer> getBeveragesId();
  +Map<Integer, String> getBeverages();
  +Integer getBeverageCapsules(Integer id) 
  +Integer createEmployee(String name, String surname) 
  +void updateEmployee(Integer id, String name, String surname)
  +String getEmployeeName(Integer id) 
  +String getEmployeeSurname(Integer id) 
  +Integer getEmployeeBalance(Integer id) 
  +List<Integer> getEmployeesId();
  +Map<Integer, String> getEmployees();
  +Integer getBalance();
  +void reset();
}

class Colleague{
+String name
+String surname
+Integer id
+Integer balance
+String getName()
+String getSurname()
+Integer getId()
+Integer getBalance()
+void setName(String new)
+void setSurname(String new)
+Integer decreaseBalance(Integer value)
+Integer increaseBalance(Integer value)
}
class CapsuleType{
+Integer ID
+String name
+Integer price
+Integer newPrice
+Integer capsulesPerBox
+Integer quantityAvailable
+Integer newQuantityAvailable
+Integer boxPrice
+Integer getId()
+String getName()
+Integer getPrice()
+Integer getCapsulePerBox()
+Integer getQuantityAvailable()
+Integer getNewQuantityAvailable()
+Integer getNewPrice()
+Integer getBoxPrice()
+void setName(String new)
+void setPrice(Integer new)
+void setCapsulePerBox(Integer new)
+void setBoxPrice(Integer new)
+void setNewQuantityAvailable()
+void setNewPrice()
+Integer decreaseQuantity(Integer qta)
+Integer increaseCapsules(Integer qta)
}

class DataImpl{
    +Map<Integer,CapsuleType> capsules
    +Integer cashAccount
    +Map<Integer,Colleague> employees
    +String databaseName
    +String databaseName2

}

DataInterface <|..down.. DataImpl: Implementation
DataImpl "1" -- "*" CapsuleType
DataImpl "1" -- "*" Colleague



note right of DataImpl
csv file for data persistency
end note


```

\<mention design patterns used, if any>
### Design patterns used: Façade


# Verification traceability matrix

\<for each functional requirement from the requirement document, list which classes concur to implement it>


||Class: DataImpl|Class: Colleague|Class: CapsuleType|
|----|:----:|:----:|:----:|
|FR1||X|X|
|FR2|||X|
|FR3||X||
|FR4|||X|
|FR5|X|||
|FR6|X|||
|FR7|||X|
|FR8|X|X||

# Verification sequence diagrams 
\<select key scenarios from the requirement document. For each of them define a sequence diagram showing that the scenario can be implemented by the classes and methods in the design>

## Scenario 1

```plantuml
": DataImpl" -> ": CapsuleType": ":getPrice()"
": DataImpl" -> ": Colleague": ":getBalance()"
": DataImpl" -> ": CapsuleType": ":getQuantityAvailable()"
": DataImpl" -> ": CapsuleType": ":decreaseQuantity()"
": DataImpl" -> ": Colleague": ":decreaseBalcance()"
```

## Scenario 2

```plantuml
": DataImpl" -> ": CapsuleType": ":getPrice()"
": DataImpl" -> ": Colleague": ":getBalance()"
```