### 5 Steps to design any system
- Requirements Analysis 
  - 
  - we want to manage employee at our company


- Api Design
  - 
  - CreateDepartment(DepName): DepObject
  - CreateEmployee(array EmpData): EmpObject
  - updateEmployee(array EmpData): EmpObject
  - AddEmployeeToDepartment(EmpId, DepId): Void;
  - getEmployee(EmpId): EmpObject
  - getDepartmentEmployees(DepId) : EmpObject[] 
  

- Define Data Model - db structure
  - 
  - Employee Table
    - EmpId (int) - PK
    - EmpName (varchar)
    - EmpSalary (decimal) 
    - EmpDepartmentId (int)
  - Department Table
    - DepId (int) - PK
    - DepName (varchar)


- High Level Design 
  - 
  - 
- Scale up
  - 
  - since we are want our system to be high available
  - we can not stand a single point of failure 
  - so we'll use
    - 2 load-balancers
    - 2 servers (we can use also a server for reading operation and another server for writing operations)
    - 2 databases (master, replication)  
  - if our system is read-heavy system we can all more servers for reading
  - we can use also caching server
  -  
  - Servers Diagram
  - ![Alt text](02-imgs/servers.jpg?raw=true "Servers")




