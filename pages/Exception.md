- ## 🧠Intuition
	- The fundamental idea of exception is
	  id:: 6312c61a-2fde-4796-9a0b-16c03f434fdc
		- 1️⃣
			- to separate detection of an [[Error]] (which should be done in a called function, a.k.a. [implementer](((63109965-8627-4373-8bcc-b72865e07938))) ) from
			- the handling of an error (which should be done in the calling function, a.k.a. [client](((63109965-aeca-4aac-8c3a-3043e5cdedb1))))
		- 2️⃣
			- while in the meantime ensuring that a detected error cannot be ignored.
- ## ⌨Sample Code
	- example of throwing exceptions in C++
		- throwing bad argument
			- ``` c++
			  class Bad_area { }; // a type specifically for reporting errors from area()
			  
			  // calculate area of a rectangle;
			  // throw a Bad_area exception in case of a bad argument
			  int area(int length, int width)
			  {
			    if (length<=0 || width<=0) throw Bad_area{};  //👈the 'throw' is to hope that some `catch` will provide an appropriate response
			    return length*width;
			  }
			  
			  int main()
			  {
			    try {
			        int x = –1;
			        int y = 2;
			        int z = 4;
			        // . . .
			        int area1 = area(x,y);
			        int area2 = framed_area(1,z);
			        int area3 = framed_area(y,z);
			        double ratio = area1/area3;
			  }
			    
			  catch (Bad_area) {
			  	cout << "Oops! bad arguments to area()\n";
			  }
			  }
			  
			  ```
			- The separation of duty is extremely important of [understanding exception](((6312c61a-2fde-4796-9a0b-16c03f434fdc))).
				- `main()` knows nothing about which function did a throw `Bad_area{}`
				- `area()` knows nothing about which function (if any) cares to catch the `Bad_area` exceptions it throws.