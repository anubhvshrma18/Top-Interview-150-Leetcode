# Zigzag Conversion

Leetcode Problem Link - [here](https://leetcode.com/problems/zigzag-conversion/description/?envType=study-plan-v2&envId=top-interview-150)!

### [Solution](/Array%20and%20Strings/):

```cpp
    string convert(string s, int numRows) {
        if(numRows==1 || numRows >= s.length()){
            return s;
        }
        string ans="";
        
        for(int i=0;i<numRows;i++){
            string n="";
            bool down=true;
            for(int j=i;j<s.length();){
                n+=s[j];
                if(i==0 || i==numRows-1){
                    int left=numRows-1;
                    j+=(left*2);
                }
                else{
                    int dleft=numRows-1-i;
                    int uleft=i*2;
                    if(down){
                        j+=(dleft*2);
                    } else{
                        j+=uleft;
                    }
                    down=!down;
                }
            }
            ans+=n;
            cout << n << endl;
        }
        return ans;
    }
```