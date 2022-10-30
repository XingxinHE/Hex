```c#
using CliWrap;
using CliWrap.Buffered;

const string LOGSEQ_PAGES_DIR = @"C:\Users\Xingxin\github\Hex\pages";

string[] fileEntries = Directory.GetFiles(LOGSEQ_PAGES_DIR).Select(e => Path.GetFileName(e)).ToArray();
Dictionary<string, string> failed = new Dictionary<string, string>();
foreach (string fileName in fileEntries)
{
    try
    {
        Console.WriteLine("Processing \"" + fileName + "\" ...");
        var powershellResults = await Cli.Wrap("cargo")
        .WithWorkingDirectory(@"C:\E-Architecture\ComputationalDesign\migration\logseq2obsdn")
        .WithArguments(new[] { @"run", "--", @$"C:\Users\Xingxin\github\Hex\pages\{fileName}", @"C:\E-Architecture\ComputationalDesign\migration\Obs\pages" })
        .ExecuteBufferedAsync();

        Console.WriteLine(powershellResults.StandardOutput);
        Console.WriteLine(powershellResults.StartTime);
        Console.WriteLine(powershellResults.ExitCode);
        Console.WriteLine(powershellResults.StandardError);
    }
    catch (Exception ex)
    {
        failed[fileName] = ex.Message;
    }
    
}

foreach(var item in failed)
{
    Console.WriteLine(item.Key);
    //Console.WriteLine(item.Value);
}

Console.ReadLine();
```


