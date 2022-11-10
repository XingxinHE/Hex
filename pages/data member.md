---
aliases: [instance variable, field(csharp)]
---
# 📝Definition
Across #cpp , #csharp , and #Python , they have different terminology on same or similar things.

| Language | Terminology                    |
| -------- | ------------------------------ |
| C++      | data member, instance variable |
| C#       | field                          |
| Python   | data member                    |

# 🧠Intuition
[[variable]] in [[class]] scope.

# ⌨Sample Code
## #cpp 
OK but not recommend👎 .
```cpp
class Point
{
    public:
    	int x;
    	int y;
    private:
    	double a;
    	double b;
}
```
recommend👍. No `public` data member.
```cpp
class Point
{
    public:
    // ..methods here
    
    private:
    	int x;
    	int y;
};
```

## #csharp 
```csharp
public class CalendarEntry
{

    // 👇private field
    private DateTime _date;

    // 👍public property exposes _date field safely.
    public DateTime Date
    {
        get => _date;
        set
        {
            // 👍check validity
            if (value.Year > 1900 && value.Year <= DateTime.Today.Year)
            {
                _date = value;
            }
            else
            {
                throw new ArgumentOutOfRangeException("Date");
            }
        }
    }

    // 👎public field (Generally not recommended).
    public string? Day;

    // 👇public method to set. it also exposes _date field safely.
    public void SetDate(string dateString)
    {
        DateTime dt = Convert.ToDateTime(dateString);
		// check validity
        if (dt.Year > 1900 && dt.Year <= DateTime.Today.Year)
        {
            _date = dt;
        }
        else
        {
            throw new ArgumentOutOfRangeException("dateString");
        }
    }
	// 👇public method to get
    public TimeSpan GetTimeSpan(string dateString)
    {
        DateTime dt = Convert.ToDateTime(dateString);

        if (dt.Ticks < _date.Ticks)
        {
            return _date - dt;
        }
        else
        {
            throw new ArgumentOutOfRangeException("dateString");
        }
    }
}
```

