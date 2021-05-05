
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


Problem 2
If two interface can contain a variable with same variable. And there maybe variable naming complix but we can solve this problem by using interface names.

![image](https://user-images.githubusercontent.com/67812755/117003277-468b3480-ad02-11eb-995e-1badd4cc7e38.png)

 
### Marker Interface
IF an interface doesn't contain any method and by implementing that interface if our object will get some ability such type of interface are called marker interface.
Example: Serializable, Cloneable,RandomAccess,SignalThreadGroup

Example 1:
By implementing Serializable our object can be saved to any file and can travel across a network. 

Example 2:
By implementing Cloneable interface our object are in position to produce exactly duplicate cloned objects.

Without having any method how the object will get the ability in marker Interface?
Internally JVM is responsible to provide required ability.


Why JVM is providing required ability in Marker Interfaces?
To reduce complexity of programming and to make Java language as simple.


Is it possible to create our own Marker Interface?
Yes, but customization of JVM is required.

### Adapter Classes

Adapter class is a simple java class that implements an interface with only empty implementation
If we implement an interface for each and every method compulosory we should provide implementation wether it is required or not requied.

**Problem** 

The main problem is it increase length of the code and reduces readibilty. We can solve this problem by using Adapter classes. 


![image](https://user-images.githubusercontent.com/67812755/117110057-370ff800-ada3-11eb-9ac8-ebb87848d0cb.png)


**Solution**

Instead of implementing intrerface if we extends Adapter class we have to provide implementation for only required method and we are not responsible to provide implementation for each and every method of the interface. So that length of the code will be reduce.


![image](https://user-images.githubusercontent.com/67812755/117110340-97069e80-ada3-11eb-957c-d6e53f52493b.png)

> TIP: make Adapter class an abstract class so no one object will be created. 

### Interface  V/s abstract class V/s Concrete class

1. If we don't know anything about implementation just we have requirement specification. Then we should go for interface 
Example: Servlet

2. If we are talking about implementation but not completely(partial) then we should go for abstract class
Example: Genric Servlet, HTTP servlet

3. If we area talking about implementation completely and ready to provide service then we should go for concrete class.
Example: MyOwnServlet

![Blank diagram](https://user-images.githubusercontent.com/67812755/117121298-05525d80-adb2-11eb-8aab-ac558565b43e.jpeg)

### Difference Between Interface and Abstract Classes

| Interface      | Abstract Classes |
| ----------- | ----------- |
| If we dont know anything about implementation and just we have requiremnet specification | If we are talking about implementation but not completely(partial implementation)|
| In Interface every method is public and abstract wether we declare or not.Hence Interface is considered as 100% pure abstract class| Every method present in abstract need not be public and abstract and we can take concrete method also|
| As every interface method is always public and abstract and hence we can't declare with the following modifer private,protected,final,static,synchronized,native and stricfp | There are no restriction  abstract class method modifiers | 
|Every variable present inside interface is always public static final wether we are declaring or not.|Every variable present inside abstract class need not be always public static final|
|As every interface varible is always public static final we can't declare with that following modifer: private,protected voliate and transisent|There are no restriction abstact class variable modifers| 
|For interface variale compulsory we should perform intilization at the time of declaration only Otherwise we will get CE error| For abstract class variable we are not required to perform at the time of declaration |
|Inside interface we can't declare static and instance block|Inside abstract class we can declare static and instance block|
|Inside interface we can't declare constructor|Inside abstract class we can declare constructor|

### Conclusion

Any we can't create object for abstract class but abstact class can contain constructor what is the need?
Abstract class constrcutor will be executed whenever we are creating child object to perform intilization of child class object.

**Problem:**

We have to provide implmenation of constructor in every class we extend Person. Well this is definetly not a good programming practise.Our code length will be increase and readibilty will be less.


![image](https://user-images.githubusercontent.com/67812755/117138018-23c35380-adc8-11eb-9677-e0c66335ee07.png)

**Solution:**
Provide the abstract class constructor and implement the common properties and it will invoked when we create child class object.


![image](https://user-images.githubusercontent.com/67812755/117138565-d1cefd80-adc8-11eb-96f2-4961c4980246.png)


**Can we replace interface with abstract class?**
Yes, we can replace interface with abstract class but it is not a good programming practise.This is something like recruiting IAS officer for sweeping acitivy. If everything is abstract then it highly recommeded to go for interface.

**Abstract class:**
1. The problem with abstract class is we have to extend that class and we will lose the concept of inheritance.
2. While creating the object parent class constrcutor and static block will also execute.


![image](https://user-images.githubusercontent.com/67812755/117148818-3c396b00-add4-11eb-8d18-ae115b7dcc7a.png)


**Interface**
1. In Interface we use the implement keyword and inheritance concept is available for future purpose
2. Parent class constructor and static block such thing are not present so execution time will be decreases.

![image](https://user-images.githubusercontent.com/67812755/117149431-d8637200-add4-11eb-9493-7eb62dfd3dd7.png)
