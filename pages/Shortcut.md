# Emacs
> [!NOTE] Note
> `C-<chr>` means holding `Ctrl` key and press `<chr>`.
> `M-<chr>` means holding `Alt` key and press `<chr>`.
> e.g. `C-v` means holding `Ctrl` key and press `v` key.




# Visual Assist🍅
| Feature                                | Shortcut        | Description                                                  |
| -------------------------------------- | --------------- | ------------------------------------------------------------ |
| Create From Usage                      | Shift+Alt+C     | Create a target from usage of an unknown symbol.             |
| Find References                        | Shift+Alt+F     | Open a list of references to the current symbol.             |
| Find Selected                          | Alt+K           | Highlight instances of the word under the caret as if you ran Find (Ctrl+F). |
| Find Symbol In Solution                | **Shift+Alt+S** | Open a list of all symbols in your solution.                 |
| GoTo Implementation                    | **Alt+G**       | Jump to the declaration or implementation of the current symbol. If more than one destination exists, a menu opens. |
| GoTo Related                           | Shift+Alt+G     | Jump to locations related to the current symbol.             |
| List Methods                           | **Alt+M**       | See a list of all classes and methods in the current file.   |
| Navigate Back                          | Alt+Left-Arrow  | Navigate in code to the previous visited place.              |
| Navigate Forward                       | Alt+Right-Arrow | Navigate in code to the next visited place.                  |
| Open Corresponding File                | **Alt+O**       | Switch quickly between pairs or n-tuples of related files. If more than one related file exists, a menu opens. |
| Open File in Solution                  | **Shift+Alt+O** | Use a dialog to quickly find and open any file in your solution. |
| Open Quick Action and Refactoring menu | Shift+Alt+Q     | Open a menu of quick fixes, code generation commands, find references commands, and refactorings for the current location or symbol. |
| Paste                                  | Ctrl+Shift+V    | View multiple clipboards in a traditional paste menu.        |
| Rename                                 | **Shift+Alt+R** | Rename the definition and declaration of a symbol, all references to it, and optionally, occurrences in comments and strings. |
| Reset Editor Zoom                      | Ctrl+0          | Reset the zoom level of the text editor to 100%.             |
| Move to Next Scope                     | Alt+Down-Arrow  | Move to the next outermost scope. When at global scope, move to the adjacent scope. |
| Move to Previous Scope                 | Alt+Up-Arrow    | Move to the previous outermost scope. When at global scope, move to the adjacent scope. |
| Smart Select Extend                    | Shift+Alt+]     | Make an initial selection of a small block or grow the selection by a small increment. |
| Smart Select Extend Block              | Alt+]           | Make an initial selection of a large block or grow the selection by a large increment. |
| Smart Select Shrink                    | Shift+Alt+[     | Make an initial selection of a small block or reduce the selection by a small increment. |
| Smart Select Shrink Block              | Alt+[           | Make an initial selection of a large block or reduce the selection by a large increment. |
| VA Hashtags                            | Shift+Alt+H     | Open a tool window with all VA Hashtags in the solution.     |

# Visual Studio
## Build
|Commands|Keyboard shortcuts |Command ID|
|-|-|-|
|Build solution|**Ctrl+Shift+B** | Build.BuildSolution |
|Cancel|**Ctrl+Break** | Build.Cancel |
|Compile|**Ctrl+F7** | Build.Compile |
|Run code analysis on solution|**Alt+F11**| Build.RunCodeAnalysisonSolution |

## Debug
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Break at function|**Ctrl+B**| Debug.BreakatFunction |
|Break all|**Ctrl+Alt+Break**| Debug.BreakAll |
|Delete all breakpoints|**Ctrl+Shift+F9**| Debug.DeleteAllBreakpoints |
|Exceptions|**Ctrl+Alt+E**| Debug.Exceptions |
|Quick watch|**Ctrl+Alt+Q**<br /><br />or **Shift+F9**| Debug.QuickWatch |
|Restart|**Ctrl+Shift+F5**| Debug.Restart |
|Run to cursor|**Ctrl+F10**| Debug.RunToCursor |
|Set next statement|**Ctrl+Shift+F10**| Debug.SetNextStatement |
|Start|**F5**| Debug.Start |
|Start without debugging|**Ctrl+F5**| Debug.StartWithoutDebugging |
|Step into|**F11**| Debug.StepInto |
|Step out|**Shift+F11**| Debug.StepOut |
|Step over|**F10**| Debug.StepOver |
|Stop debugging|**Shift+F5**| Debug.StopDebugging |
|Toggle breakpoint|**F9**| Debug.ToggleBreakpoint |

## Edit
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Break line|**Enter** [Text Editor, Report Designer, Windows Forms Designer]<br /><br />or **Shift+Enter** [Text Editor]| Edit.BreakLine |
|Collapse to definitions|**Ctrl+M**, **Ctrl+O** [Text Editor]| Edit.CollapseToDefinitions |
|Comment selection|**Ctrl+K**, **Ctrl+C** [Text Editor]| Edit.CommentSelection |
|Complete word|**Alt+Right Arrow** [Text Editor, Workflow Designer]<br /><br />or **Ctrl+Spacebar** [Text Editor, Workflow Designer]<br /><br />or **Ctrl+K**, **W** [Workflow Designer]<br /><br />or **Ctrl+K, Ctrl+W** [Workflow Designer]| Edit.CompleteWord |
|Copy|**Ctrl+C**<br /><br />or **Ctrl+Insert**| Edit.Copy |
|Cut|**Ctrl+X**<br /><br />or **Shift+Delete**| Edit.Cut |
|Delete|**Delete** [Team Explorer]<br /><br />or **Shift+Delete** [Sequence Diagram, UML Activity Diagram, Layer Diagram]<br /><br />or **Ctrl+Delete** [Class Diagram]| Edit.Delete |
|Find|**Ctrl+F**| Edit.Find |
|Find all references|**Shift+F12**| Edit.FindAllReferences |
|Find in files|**Ctrl+Shift+F**| Edit.FindinFiles |
|Find next|**F3**| Edit.FindNext |
|Find next selected|**Ctrl+F3**| Edit.FindNextSelected |
|Format document|**Ctrl+K, Ctrl+D** [Text Editor]| Edit.FormatDocument |
|Format selection|**Ctrl+K, Ctrl+F** [Text Editor]| Edit.FormatSelection |
|Go to|**Ctrl+G**| Edit.GoTo |
|Go to declaration|**Ctrl+F12**| Edit.GoToDeclaration |
|Go to definition|**F12**| Edit.GoToDefinition |
|Go to find combo|**Ctrl+D**| Edit.GoToFindCombo |
|Go to next location|**F8**| Edit.GoToNextLocation |
|Insert snippet|**Ctrl+K**, **Ctrl+X**| Edit.InsertSnippet |
|Insert tab|**Tab** [Report Designer, Windows Forms Designer, Text Editor]| Edit.InsertTab |
|Line cut|**Ctrl+L** [Text Editor]| Edit.LineCut |
|Line down extend column|**Shift+Alt+Down Arrow** [Text Editor]| Edit.LineDownExtendColumn |
|Line open above|**Ctrl+Enter** [Text Editor]| Edit.LineOpenAbove |
|List members|**Ctrl+J** [Text Editor, Workflow Designer]<br /><br />or **Ctrl+K, Ctrl+L** [Workflow Designer]<br /><br />or **Ctrl+K, L** [Workflow Designer]| Edit.ListMembers |
|Navigate to|**Ctrl+,**| Edit.NavigateTo |
|Open file|**Ctrl+Shift+G**| Edit.OpenFile |
|Overtype mode|**Insert** [Text Editor]| Edit.OvertypeMode |
|Parameter info|**Ctrl+Shift+Spacebar** [Text Editor, Workflow Designer]<br /><br />or **Ctrl+K, Ctrl+P** [Workflow Designer]<br /><br />or **Ctrl+K, P** [Workflow Designer]| Edit.ParameterInfo |
|Paste|**Ctrl+V**<br /><br />or **Shift+Insert**| Edit.Paste |
|Peek definition|**Alt+F12** [Text Editor]| Edit.PeekDefinition |
|Redo|**Ctrl+Y**<br /><br />or **Shift+Alt+Backspace**<br /><br />or **Ctrl+Shift+Z**| Edit.Redo |
|Replace|**Ctrl+H**| Edit.Replace |
|Select all|**Ctrl+A**| Edit.SelectAll |
|Select current word|**Ctrl+W** [Text Editor]| Edit.SelectCurrentWord |
|Selection cancel|**Esc** [Text Editor, Report Designer, Settings Designer, Windows Forms Designer, Managed Resources Editor]| Edit.SelectionCancel |
|Surround with|**Ctrl+K, Ctrl+S** <br>(available only in Visual Studio 2019 and earlier)| Edit.SurroundWith |
|Tab left|**Shift+Tab** [Text Editor, Report Designer, Windows Forms Editor]| Edit.TabLeft |
|Toggle all outlining|**Ctrl+M, Ctrl+L** [Text Editor]| Edit.ToggleAllOutlining |
|Toggle bookmark|**Ctrl+K, Ctrl+K** [Text Editor]| Edit.ToggleBookmark |
|Toggle completion mode|**Ctrl+Alt+Space** [Text Editor]| Edit.ToggleCompletionMode |
|Toggle outlining expansion|**Ctrl+M, Ctrl+M** [Text Editor]| Edit.ToggleOutliningExpansion |
|Uncomment selection|**Ctrl+K, Ctrl+U** [Text Editor]| Edit.UncommentSelection |
|Undo|**Ctrl+Z**<br /><br />or **Alt+Backspace**| Edit.Undo |
|Word delete to end|**Ctrl+Delete** [Text Editor]| Edit.WordDeleteToEnd |
|Word delete to start|**Ctrl+Backspace** [Text Editor]| Edit.WordDeleteToStart |



## File
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Exit|**Alt+F4**| File.Exit |
|New file|**Ctrl+N**| File.NewFile |
|New project|**Ctrl+Shift+N**| File.NewProject |
|New web site|**Shift+Alt+N**| File.NewWebSite |
|Open file|**Ctrl+O**| File.OpenFile |
|Open project|**Ctrl+Shift+O**| File.OpenProject |
|Open web site|**Shift+Alt+O**| File.OpenWebSite |
|Rename|**F2** [Team Explorer]| File.Rename |
|Save all|**Ctrl+Shift+S**| File.SaveAll |
|Save selected items|**Ctrl+S**| File.SaveSelectedItems |
|View in browser|**Ctrl+Shift+W**| File.ViewinBrowser |

## Project
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Add existing item|**Shift+Alt+A**| Project.AddExistingItem |
|Add new item|**Ctrl+Shift+A**| Project.AddNewItem |

## Refactor
|Command|Keyboard shortcut [Special contexts]|Command ID|
|-|-|-|
|Extract method|**Ctrl+R, Ctrl+M**| Refactor.ExtractMethod |

## Tools
|Command|Keyboard shortcut [Special contexts]|Command ID|
|-|-|-|
|Attach to process|**Ctrl+Alt+P**| Tools.AttachtoProcess |

## View
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Class view|**Ctrl+Shift+C**| View.ClassView |
|Edit label|**F2**| View.EditLabel |
|Error list|**Ctrl+\\, Ctrl+E**<br /><br />or **Ctrl+\\, E**| View.ErrorList |
|Navigate backward|**Ctrl+-**| View.NavigateBackward |
|Navigate forward|**Ctrl+Shift+-**| View.NavigateForward |
|Object browser|**Ctrl+Alt+J**| View.ObjectBrowser |
|Output|**Ctrl+Alt+O**| View.Output |
|Properties window|**F4**| View.PropertiesWindow |
|Refresh|**F5** [Team Explorer]| View.Refresh |
|Server explorer|**Ctrl+Alt+S**| View.ServerExplorer |
|Show smart tag|**Ctrl+.**<br /><br />or **Shift+Alt+F10** [HTML Editor Design View]| View.ShowSmartTag |
|Solution explorer|**Ctrl+Alt+L**| View.SolutionExplorer |
|TFS Team Explorer|**Ctrl+\\, Ctrl+M**| View.TfsTeamExplorer |
|Toolbox|**Ctrl+Alt+X**| View.Toolbox |
|View code|**Enter** [Class Diagram]<br /><br />or **F7** [Settings Designer]| View.ViewCode |
|View designer|**Shift+F7** [HTML Editor Source View]| View.ViewDesigner |

## Window
|Commands|Keyboard shortcuts [Special contexts]|Command ID|
|-|-|-|
|Activate document window|**Esc**| Window.ActivateDocumentWindow |
|Close document window|**Ctrl+F4**| Window.CloseDocumentWindow |
|Next document window|**Ctrl+F6**| Window.NextDocumentWindow |
|Next document window nav|**Ctrl+Tab**| Window.NextDocumentWindowNav |
|Next split pane|**F6**| Window.NextSplitPane |

