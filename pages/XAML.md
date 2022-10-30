# 📝Definition
- XAML, which stands for eXtensible Application Markup Language, is Microsoft's variant of XML for describing a [[GUI]].

# 🧠Intuition
- Much like with [[HTML]], you are able to easily write and edit your GUI.

# 🚀Benefit / Pros
- 📌XAML is benefit from syntactical sugar and pretty short
    - The following are equivalent.
    - ``` c#
      Button btn = new Button();
      btn.FontWeight = FontWeights.Bold;
      ```
    - ``` xaml
      <Button FontWeight="Bold" />
      ```
  -
  
# ⛈Characteristics / Properties
- 📌Case-sensitive
    - XAML is case-sensitive because the control name **has to correspond to a type in the .NET framework**.
    
# 🏷(Sub)Categories
- Event
    - There are many types of events. On most controls you will find events like `KeyDown`, `KeyUp`, `MouseDown`, `MouseEnter`, `MouseLeave`, `MouseUp` and several others.
    
# 💫Support Operation
## 🌟Events in XAML
- Intuition
    - Each elements in GUI(controls) have different events on them. For example, a button may have certain events.
        - `MouseDown`
        - `MouseUp`
        - ...etc
        
    - In terms of different event, you want to implement different behaviors. For example,
        - `MouseDown` - corresponding to behavior A. e.g. open a dialog
        - `MouseUp` - corresponding to behavior B. e.g. close a dialog
        
- Participants
    - There are 2 participants in this "event".
        - `Event` - The guy who triggers the event.
        - `EventHandler` - Who is interested in handling this event.
        
- Implementation
    - `EventHandler`
        - For `EventHandler`, you put it in the C# code, always in `.cs` files.
        
    - `Event`
        - You can declare the interested event of that element in either way
            - in `XAML`
            - in code behind file. `.cs`
            
- Code Sample
    - 📌Method 1
        - ``` xaml
          <Window x:Class="WpfTutorialSamples.XAML.EventsSample"
                  xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
                  xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
                  Title="EventsSample" Height="300" Width="300">
          	<Grid Name="pnlMainGrid" MouseUp="pnlMainGrid_MouseUp" Background="LightBlue">        
          		
              </Grid>
          </Window>
          ```
        - ``` c#
          private void pnlMainGrid_MouseUp(object sender, MouseButtonEventArgs e)
          {
          	MessageBox.Show("You clicked me at " + e.GetPosition(this).ToString());
          }
          ```
        
    - 📌Method 2
        - ``` c#
          namespace WpfTutorialSamples.XAML
          {
          	public partial class EventsSample : Window
          	{
          		public EventsSample()
          		{
          			InitializeComponent();
          			pnlMainGrid.MouseUp += new MouseButtonEventHandler(pnlMainGrid_MouseUp);
          		}
          
          		private void pnlMainGrid_MouseUp(object sender, MouseButtonEventArgs e)
          		{
          			MessageBox.Show("You clicked me at " + e.GetPosition(this).ToString());
          		}
          
          	}
          }
          ```
        
# ✒Notation / Syntax
- 📌different syntax on creating controls
    - ``` xaml
      <!--1.-->
      <Button />
      
      <!--2.-->
      <Button></Button>
      ```
    
- 📌different syntax on setting properties of a control
    - ``` xaml
      <!--1.Normal Notation-->
      <Button FontWeight="Bold" Content="This is a button" />
      
      <!--2.Control-Dot-Property notation-->
      <Button>
          <Button.FontWeight>Bold</Button.FontWeight>
          <Button.Content>This is a button</Button.Content>
      </Button>
      ```
    
-
