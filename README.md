# DSA_Core_4you
This repository is a personal space dedicated to building a consistent habit of solving Data Structures and Algorithms (DSA) problems.beyond Placements.

| Sno | Problem | Difficulty | Platform | Solution |
|---|--------|------------|----------|----------|
| 1 | Consecutive Subsequences
 | 🟢 E | [LeetCode](https://www.hackerrank.com/challenges/consecutive-subsequences/problem) | [View](#consecutive-subsequences) |
### 🔹 Consecutive Subsequences

<a name="consecutive-subsequences"></a>

<details>
<summary>💡 Click to view solution</summary>

---

### 🧠 Approach

* Use prefix sum and modulo
* If two prefix sums have same remainder → subarray sum divisible by k
* Use hashmap to store frequency

---

### ⏱️ Complexity

* Time: O(n)
* Space: O(k)

---

### 💻 Code

```cpp
#include<bits/stdc++.h>
using namespace std;

int main() {
    int T;
    cin>>T;
    while(T--){
        int n,k;
        cin>>n>>k;
        
        vector<int>arr(n);
        for(int i=0;i<n;i++){
            cin>>arr[i];
        }
        
        long long s=0,c=0;
        unordered_map<int, int>mpp;
        mpp[0]=1;
        
        for(int i=0;i<n;i++){
            s+=arr[i];
            s%=k;
            
            if(s<0) s+=k;
            
            if(mpp.find(s)!=mpp.end()) 
                c+=mpp[s];
            
            mpp[s]++;
        }
        
        cout<<c<<endl;
    }
    return 0;
}
```

</details>
