- 📝Definition
  In programming, there 2 ways of for loop in general.
    - traditional for loop
    - range for loop
    
- 🧠Intuition
    - ⭐traditional `for`  loop in abstract
        - ```
          for(initialization; Boolean expression; update sentinel variable)
          {
          	statement
          }
          ```
        - This is of tremendous importance since no matter what kinds of implementation and this is the key.
        
    - ⭐range for loop in abstract
        - ``` 
          for item in item_list:
          	do something
          ```
        
- ⛈Characteristics / Properties
    - Variable in `for` loop is local variable
        - ```c#
          for (int i = 0; i < 3; i++)
          {
              Console.WriteLine($"Say {i}.");
          }
          for (int i = 20; i > 17; i--)
          {
              Console.WriteLine($"Yell {i}!");
          }
          ```
        - Output:
          ```
          Say 0.
          Say 1.
          Say 2.
          Yell 20!
          Yell 19!
          Yell 18!
          ```
        
# ⌨Sample Code
- traditional for loop
    - [[C#]]
        - Iterate on variable
          ``` c#
          for(int i = 0; i < 10; i++)
          {
              Console.WriteLine(i);
          }
          
          // Multiple variable for-loop
          for (int i = 0, j=10; i < j; i++, j--)
          {
              Console.WriteLine($"i val:{i}, j val:{j}");
          }
          ```
        - Iterate on "not a variable"
          ```c#
          for(string line = reader.ReadLine(); line!=null; line=reader.ReadLine())
          {
              source.Text += line + "\n";
          }
          ```
        
  #cpp
  - iterating using index
      - ``` c++
        // 1.Counting from 1 to 100
        for (int i = 1; i <= 100; i++);
        
        // 2.Counting by sevens starting at 0 until the number has more than two digits
        for (int i = 0; i < 100; i += 7);
          
        // 3.Counting backward by twos from 100 to 0
        for (int i = 100; i >= 0; i -= 2);
        ```
      
- range for loop
  #cpp
  - the `foreach.h` is deprecated. Use the `for ( for-range-declaration : expression )` syntax.
  - ``` c++
    vector<int> v = {5, 7, 9, 4, 6, 8};
    for (int x : v) // for each x in v
    {
      cout << x << '\n';
    }
    ```
  
    - [[C#]]
        - ``` c#
          var fibNumbers = new List<int> { 0, 1, 1, 2, 3, 5, 8, 13 };
          foreach (int element in fibNumbers)
          {
              Console.Write($"{element} ");
          }
          ```
        
  #JavaScript
  - ``` javascript
      let result = '';
      for (const i in obj) {
        result += `${objName}.${i} = ${obj[i]}<br>`;
      }
    ```
  