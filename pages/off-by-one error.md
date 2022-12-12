---
tags:
  - error-prone
---
# 📝Definition
 The index is not in range...
# 🗃Example
📂example of "off-by-one error"
``` c++
vector<int> v; // a vector of ints
for (int i; cin>>i; )
{
	v.push_back(i); // get values
}

for (int i = 0; i<=v.size(); ++i) // 👈here is the off-by-one error
{
	cout << "v[" << i <<"] == " << v[i] << '\n';
}

```