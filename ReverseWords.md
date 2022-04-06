### [Back2Home](https://github.com/RecursiveSharma/StringCodingQuestions) | [Go2Video](https://www.youtube.com/playlist?list=PLhvdldYcnZMnrzXlXBai6_MYYSvEtCa7Y)
```java

//sol1 = Best Time Soln with  String Builder = O(n)
class Solution {
      public String reverseWords(String s) {
          
       if(s.length()==0 || s==null) return "";
        
        StringBuilder sb=new StringBuilder();
         String[] str_arr=s.split(" ");
        int n=str_arr.length-1;
        for(int i=n;i>=0;i--){
            if(!str_arr[i].equals("")){
                sb.append(str_arr[i]).append(" ");
            }
        }
        return sb.length()==0?"":sb.substring(0,sb.length()-1);
      }
}

```

```java

// Solution O(n) time complexity 
class Solution {
      public String reverseWords(String s) {
          
        if(s.length()==0 || s==null) return "";
        
        s = s.replaceAll("\\s++", " ").trim();
        String[] str = s.split(" ");
        
        String result = "";
        int last = str.length - 1;
        for (int i = last; i > 0; i--) {
            result += str[i] + " ";
        }
     
       return result += str[0];
    }
}
```

```java

//sol3 = simple Naive Soln = O(n^2) time complxity 
     
    if(s.length()==0 || s==null) return "";

        int i = 0;
        int n = s.length();
        String res = "";
        while (i < n) {
            while (i < n && s.charAt(i) == ' ') {
                i++;
            }
            if (i >= n) {
                break;
            }
            int j = i + 1;
            while (j < n && s.charAt(j) != ' ') {
                j++;
            }
            String w = s.substring(i,j);
            
            if (res.length() == 0) {
                res = w;
            } else {
                res = w + " " + res;
            }
            i = j+1;
            
        }

    return res;
     
