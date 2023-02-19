### Task 1 (6kyu)
Create Phone Number   
Write a function that accepts an array of 10 integers (between 0 and 9), that returns a string of those numbers in the form of a phone number.
### Solution
```java
public class Kata {
public static String createPhoneNumber(int[] numbers) {
StringBuilder sb = new StringBuilder();
sb.append('(');
for(int i=0;i<3;i++){
sb.append(String.valueOf(numbers[i]));
}
sb.append(')');
sb.append(' ');
for(int i=3;i<6;i++){
sb.append(String.valueOf(numbers[i]));
}
sb.append('-');
for(int i=6;i<10;i++){
sb.append(String.valueOf(numbers[i]));
}
return sb.toString();
}
}
```
### Favourite
```java
public class Kata {
  public static String createPhoneNumber(int[] numbers) {
    String number = new String();
    for (int i = 0; i < 10; i++){
      if(i == 0){ number = "("; }
      if(i == 3){ number = number + ") "; }
      if(i == 6){ number = number + "-"; }
      number = number + numbers[i];
    }
    return number;
  }
}
```
[Task link](https://www.codewars.com/kata/525f50e3b73515a6db000b83/java)
### Task 2 (6kuy)
Remove the parentheses  
Your task is to remove everything inside the parentheses as well as the parentheses themselves.
### Solution
```java
public class Kata {
    public static String removeParentheses(final String str) {
        String res = "";
        int count = 0;
        for (int l = 0; l < str.length(); l++) {
            char c = str.charAt(l);
            if (c == '(') count += 1;
            if (count == 0) res += str.charAt(l);
            if (c == ')') count -= 1;
        }
        return res;
    }
}
```
### Favourite
```java
public class Kata {
    public static String removeParentheses(final String str) {
        String result = "";
        boolean delete = false;
        int bracketCount = 0;
      
        for (int i = 0; i < str.length(); i++) {

            if (str.charAt(i) == '(') {
                delete = true;
                bracketCount++;
            }
          
            if(!delete)
            result += str.charAt(i);

            if (str.charAt(i) == ')'){
                bracketCount--;
                if (bracketCount == 0)
                delete = false;
            }
        }
        return result;
    }
}
```
[Task link](https://www.codewars.com/kata/5f7c38eb54307c002a2b8cc8/java)