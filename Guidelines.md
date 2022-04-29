1. Different responsibilities should be divided among different objects.

2. Encapsulation: One class should be responsible for knowing and maintaining a set of data, even if that data is used by many other classes
```
Example 1: (correct)
public class Auto{
  private String make;
  private String color;
  public String getColor() {
    return color;
  }
  public String getMake() {
    return make;
  }
  public void setColor(String newColor) {
    color = newColor;
  }
  public void setMake(String newMake) {
     make = newMake;
  }
}
public class AutoDealer{
  public static void main() {
    Auto a1 = new Auto();
    a1.setColor ("green");
  }
}

Example 2:
public class Auto{
  public String make;
  public String color;
  public String getColor() {
    return color;
  }
  public String getMake() {
    return make;
  }
}
public class AutoDealer{
  public static void main(){
    Auto a1 = new Auto();
    a1.color = "green";
  }
}
```
```
Example 1(correct):
public class Student {
private String name;
private String idNum;
private int age;
public int getAge() { return age; }
public String getName() { return name; }
public String getIdNum() { return idNum; }
public void setAge( int newAge) { age = newAge; }
public void setName(String newName) { name = newName; }
public void setIdNum( String newId) { idNum = newId; }
}
public static void main(String [] args){
Student S1 = new Student();
S1.setAge(21);
System.out.println("Age of the student is " + S1.getAge());
}
Example 2:
public class Student {
public String name;
public String idNum;
public int age;
}
Public Static void main(String [] args){
Student S1 = new Student();
S1.age =21;
System.out.println("Age of the student is " + S1.age);
}
```
3. Expert pattern: The object that contains the necessary data to perform a task should be the object that manipulates the data
 ```
 Example 1:
public class Banker {
public updateUserEmail(User current_user, String message){
current_user.email = message;
}
}
public class User{
String email;
}
Example 2(correct):
public class Banker {
public updateUserEmail(User current_user, String message){
current_user.updateEmail(message);
}
}
public class User{
String email;
public updateEmail( String message){
this.email = message;
}
 ```
4. The DRY principle: Code should not be duplicated
```
Example 1:
public class Auto{
private String make;
private String color;
public String getColor(){
return color;
}
public String getMake(){
return make;
}
public void setColor(String newColor){
color = newColor;
}
public void setMake(String newMake){
make = newMake;
}
}
public class AutoDealer{
public static void main(){
Auto a1 = new Auto();
Auto a2 = new Auto();
System.out.println("Make of the car a1 is : " + a1.getMake());
System.out.println("Color of the car a1 is : " + a1.getColor());
System.out.println("Make of the car a2 is : " + a2.getMake());
System.out.println("Color of the car a2 is : " + a2.getColor());
}
}

Example 2(correct):
public class Auto{
private String make;
private String color;
public String getColor(){
return color;
}
public String getMake(){
return make;
}
public void setColor( String newColor){
color = newColor;
}
public void setMake(String newMake){
make = newMake;
}
public void printDetails(){
System.out.println("Make of the car a1 is : " + this.getMake());
System.out.println("Color of the car a1 is : " + this.getColor());
}
}
public class AutoDealer{
public static void main(){
Auto a1 = new Auto();
Auto a2 = new Auto();
a1.printDetails();
a2.printDetails();
}
}
```

```
Example 1:
void analyzeMidtermPerformance() {
float sum=0;
for (int score : scores)
sum = sum + score;
float average = sum / size;
// ... more code to do the analysis
}
void analyzeProjectPerformance() {
float sum=0;
for (int score : scores)
sum = sum + score;
float average = sum / size;
// ... more code to do the analysis
}
Example 2(correct):
float getAverage() {
float sum=0;
for (int score : scores)
sum = sum + score;
float average = sum / size;
return average;
}
void analyzeMidtermPerformance() {
float average= getAverage();
// ... more code to do the analysis
}
void analyzeProjectPerformance() {
float average=getAverage();
// ... more code to do the analysis
}
```
5. Design your classes so that they can handle change

6. Code to interfaces, not classes

7. Encapsulate the concepts that vary

8. Give classes a complete interface

9. A wellformed class has a consistent interface

```
Example 1:
find_employee_by_name(..)
get_employee_by_id(..)
retrieve_employee_by_department(..)
fetch_employee_by_address(..)
Example 2(correct):
find_employee_by_name(..)
find_employee_by_id(..)
find_employee_by_department(..)
find_employee_by_address(..)
```
