- 📌**When should we use  `switch` ?**
	- Use it when you have *multiple* and *parallel* conditions.
- 📌**What is fall-through?**
	- In short, it combines conditions with same behaviors.
	- ``` c#
	  switch(flag)
	  {
	      case Hearts:
	      case Diamonds:
	          color="Red";
	          break;
	      case Clubs:
	      case:Spades:
	          color="Black";
	          break;
	      default:
	          color=null;
	          break;
	  }
	  ```
- 📌**Rules Using  `switch` **
	- `case`  must be unique.
	- every  `case`  should be ended with  `break`
- [[C#]]
	- ``` c#
	  int day = 5;
	  string dayName = "";
	  switch (day)
	  {
	      case 0:
	          dayName = "Sunday";
	          break;
	      case 1:
	          dayName = "Monday";
	          break;
	      case 2:
	          dayName = "Tuesday";
	          break;
	      case 3:
	          dayName = "Wednesday";
	          break;
	  	//..
	      default:
	          dayName = "Unknown";
	          break;
	  }
	  ```
-