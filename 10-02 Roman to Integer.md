``` java
// DO NOT SOLVE QUIZE LIKE THIS
class Solution {
    public int romanToInt(String s) {
       HashMap<String, Integer> map = new HashMap<String, Integer>(7);
        //map 세팅
        map.put("I", 1);
        map.put("V", 5);
        map.put("X", 10);
        map.put("L", 50);
        map.put("C", 100);
        map.put("D", 500);
        map.put("M", 1000);

        String[] arr;
        arr = s.split("");
        int i =0; // index
        int res = 0;//result
        int len = s.length();
        int num1,num2; //비교용
        if(len==1){
            return map.get(s);
        }
        while (true){
            num1=map.get(arr[i]);
            num2=map.get(arr[i+1]);
            if (num1<num2){
                int sum=num1+num2;
                if(sum%6==0){
                    res+=(sum/6)*4;
                }else{
                    res+=(sum/11)*9;
                }
                i+=1;
                if(i+1==len-1){
                    return res+map.get(arr[i+1]);
                }
                else if(i+2>len-1){
                    return res;
                }
                i++;
            }else {
                res+=num1;
                i+=1;
                if(i+1>len-1){
                    return res+num2;
                }
            }
        }
    }
}
```

