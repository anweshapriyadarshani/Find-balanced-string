# Find-balanced-string
Given a string of parentheses, find the balanced string that can be produced from it using the minimum number of insertions and deletions. If there are multiple solutions, return any of them.  For example, given "(()", you could return "(())". Given "))()(", you could return "()()()()".

#include <bits/stdc++.h> 
using namespace std; 
  
// Function to return required minimum number 
int minParentheses(string p) 
{ 
  
    // maintain balance of string 
    int bal = 0; 
    int ans = 0; 
  
    for (int i = 0; i < p.length(); ++i) { 
  
        bal += p[i] == '(' ? 1 : -1; 
  
        // It is guaranteed bal >= -1 
        if (bal == -1) { 
            ans += 1; 
            bal += 1; 
        } 
    } 
  
    return bal + ans; 
} 
  
// Driver code 
int main() 
{ 
  
    string p = "())"; 
  
    // Function to print required answer 
    cout << minParentheses(p); 
  
    return 0; 
} 
