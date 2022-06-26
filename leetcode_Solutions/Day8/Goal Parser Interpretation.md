# Goal Parser Interpretation
- ## Question:
>You own a **Goal Parser** that can interpret a string command. The command consists of an alphabet of "G", "()" and/or "(al)" in some order. The Goal Parser will interpret "G" as the string "G", "()" as the string "o", and "(al)" as the string "al". The interpreted strings are then concatenated in the original order.
>
>Given the string `command`, return the Goal Parser's interpretation of `command`.

- Example :

      Input: command = "G()(al)"
      Output: "Goal"
      Explanation: The Goal Parser interprets the command as follows:
      G -> G
      () -> o
      (al) -> al
      The final concatenated result is "Goal".
      
- ## Solution:
```cpp
class Solution {
public:
	string interpret(string c) 
	 {
		string s;
		for(auto i=0;i<c.length();)
		    {
			    if(c[i]=='G')
				    s.push_back('G');
				else if(c[i]=='(' and c[i+1]==')')
					{
						s.push_back('o');i++;
					}
				else
					{
						s+="al";i+=3;
					}
				i++;
			}
		return s;
	}
};
```

## Tags
`String`
