```java
class Solution {
    int isPalindrome(String S) {
        // using reverse method
      StringBuilder stb = new StringBuilder(S);
       String st = stb.reverse().toString();
       if(st.equals(S)){
           return 1;
       }
       return 0;
    }
}
```

```java
class Solution {
    int isPalindrome(String S) {
      //using 2 pointer approach
     int i=0,j=S.length()-1;
	    while(i<=j){
	        if(S.charAt(i++)==S.charAt(j--)){
	            continue;
	        }else{
	            return 0;
	        }
	    }
	    return 1;
    }
};
```
