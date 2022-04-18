### [Back2Home](https://github.com/RecursiveSharma/StringCodingQuestions) | [Go2Video](https://youtu.be/Cl-FZVo69gk)
```java

//sol1 = Best Time Soln with  map = O(n)
class Solution {
     public int romanToInt(String s) {
        if(s==null || s.length()==0) return 0;
        
        Map<Character,Integer> map= new HashMap();
        map.put('I',1);
        map.put('V',5);
        map.put('X',10);
        map.put('L',50);
        map.put('C',100);
        map.put('D',500);
        map.put('M',1000);
        
        int result=0;
        result=map.get(s.charAt(s.length()-1));
        
        for(int i=s.length()-2;i>=0;i--){
            if(map.get(s.charAt(i))<map.get(s.charAt(i+1))){
                result-=map.get(s.charAt(i));
            }else{
                 result+=map.get(s.charAt(i));
            }
        }
        return result;
     }
}
```

```java

// Solution O(n) time complexity 
class Solution {
     public int romanToInt(String s) {
            char[] array = s.toCharArray();

                int result = 0;
                for (int i = array.length - 1; i >= 0; i--) {
                    if (result == 0) {
                        result += this.convert(array[i]);
                        continue;
                    }

                    if (this.convert(array[i]) == this.convert(array[i + 1])) {
                        result += this.convert(array[i]);
                        continue;
                    }


                    if (result > this.convert(array[i])) {
                        result -= this.convert(array[i]);
                        continue;
                    }

                    if (result <= this.convert(array[i])) {
                        result += this.convert(array[i]);
                        continue;
                    }
                }
            
                return result;    
        }

        

            private int convert(char c) {
                switch (c) {
                    case 'I':
                        return 1;
                    case 'V':
                        return 5;
                    case 'X':
                        return 10;
                    case 'L':
                        return 50;
                    case 'C':
                        return 100;
                    case 'D':
                        return 500;
                    case 'M':
                        return 1000;

                }
                return 0;
        }
    }
                
```

```java

//sol3 = simple Naive Soln = O(n) time complxity 
    
    
    char[] sArr=s.toCharArray();
    int length=s.length();
    int decimalNum;

    for(int i=length-1;i>-1;i--){
        
        if( i-1 >-1 && sArr[i]=='V' && sArr[i-1]=='I' )
        {
            decimalNum+=4;
            i--;
            continue;
        }
        else if( i-1 >-1 && sArr[i]=='X' && sArr[i-1]=='I' )
        {
            decimalNum+=9;
            i--;continue;
        }
        else if( i-1 >-1 && sArr[i]=='L' && sArr[i-1]=='X' )
        {
            decimalNum+=40;
            i--;continue;
        }
        else if( i-1 >-1 && sArr[i]=='C' && sArr[i-1]=='X' )
        {
            decimalNum+=90;
            i--;continue;
        }
        else if( i-1 >-1 && sArr[i]=='D' && sArr[i-1]=='C' )
        {
            decimalNum+=400;
            i--;continue;
        }
        else if( i-1 >-1 && sArr[i]=='M' && sArr[i-1]=='C' )
        {
            decimalNum+=900;
            i--;continue;
        }
        
        
       if(i>-1){
           
           if(sArr[i]=='I'){
               decimalNum+=1;
           }else if(sArr[i]=='V'){
               decimalNum+=5;
           }else if(sArr[i]=='X'){
               decimalNum+=10;
           }else if(sArr[i]=='L'){
               decimalNum+=50;
           }else if(sArr[i]=='C'){
               decimalNum+=100;
           }else if(sArr[i]=='D'){
               decimalNum+=500;
           }
           else{
               decimalNum+=1000;
           }
        
          
        }
       
        
     }
return decimalNum;