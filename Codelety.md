```Java
class Solution { public int solution(String S) { int patches = 0; int i = 0; while (i < S.length()) { if (S.charAt(i) == 'X') {  
patches++; i += 3; } else { i++; } } return patches; } }
```

Map to find inpair
``` Java
import java.util.*;
import java.util.Map.Entry;

class Solution {

    public int solution(int[] A) {

        int index=0;
        Map<Integer, Integer> mapValues = new HashMap<Integer, Integer>();

        for(int i=0; i<A.length; i++ ){
            int count = mapValues.containsKey(A[i]) ? mapValues.get(A[i]) : 0;

            mapValues.put(A[i], count+1);
        }
        for(Entry<Integer, Integer> entry : mapValues.entrySet()){
            Integer value = entry.getValue();
            if(value%2 == 1){
                index = entry.getKey();
            }
        }
        return index;
    }
}
```
