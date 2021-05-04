
# Interface-in-java

### What is an Interface?
Any Service Requirement Specification(SRS) is considered as an Interface.


Example: JDBC API acts as requirement specification to develop database driver.Database vendor is responsible to implement these JDBC API.

![Blank diagram (8)](https://user-images.githubusercontent.com/67812755/116966088-02317180-accd-11eb-8473-10ee8ae880c1.png)

Example:Servlet API acts as requirement specification to develop WebServer.Webserver vendor is responsible to implement Servlet API.

![image](https://user-images.githubusercontent.com/67812755/116966362-98659780-accd-11eb-8e3b-f09556e445b5.png)

**2nd Defination :** Inside Interface every method is always abstact whether we are declaring or not. Hence Interface is considered as 100% pure abstract class.

**Summary Defination :** Any Service Requiremnt Specification or any Contract between client and service provide OR 100% pure abstract class is an Interface.

### Interface Declaration And Implementation

1. Whenever we are implementing for each and every method of that interface we have to provide implementation. Otherwise we have to declare class as abstract then next level child class is responsible to provide implementation.
2. Every Interface method is always public and abstact.Whether we are declaring or not.Hence whenever we are implemting interface method we have to declare public otherwise we will get compile time error.


![image](https://user-images.githubusercontent.com/67812755/116974213-60fde780-acdb-11eb-96db-6522cebea5df.png)


### Extends V/S implements 

1. A class can extends only one class at a time.
2. A interface can extends any number of interface simultaneously.
3. A class can implments any other of interface simultaneously.
4. A class can extends another class and can implement any number of interface simultaneously 

### Interface Variable 
![Blank diagram (9)](https://user-images.githubusercontent.com/67812755/116993448-2143f980-acf5-11eb-8b24-af37c683d444.png)

For interface variable there should always be intilization.

### Interface Tips
If two interface contains method with same signature and same return type.Then in the implmentation class we have to provide implementation for only one method.


![image](https://user-images.githubusercontent.com/67812755/116998588-1476d400-acfc-11eb-834b-6ab6d6c8dab9.png)


If two interface contains method with same signature and different return type.Then in the implmentation class we have to provide implementation for only one method.


![image](https://user-images.githubusercontent.com/67812755/116999446-4177b680-acfd-11eb-94d6-a6ac1c4bd195.png)

Problem 1


![image](https://user-images.githubusercontent.com/67812755/117001767-5efa4f80-ad00-11eb-91db-61d957cc63ea.png)

Still Problem not solved

![image](https://user-images.githubusercontent.com/67812755/117002577-5b1afd00-ad01-11eb-9eeb-684f46906234.png)

Conclusion: If two  interface contains same signature but different return then it is impossible to implement both interface simulatenously. If return type are not co-varirant
