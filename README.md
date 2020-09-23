<div align="center">

## Debug\.Print\.\.\.from an Exe


</div>

### Description

Everyone knows how useful Debug.Print can be when debugging a program in the run time environment...but why not make these debug comments available from an executable.

Simply replace Debug.Print with the following, and then when your application is running as an executable you can use a debugger (such as DBMON.EXE, downloadable form MSDN) to see the debug comments as they occur:
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Duncan Jones](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/duncan-jones.md)
**Level**          |Intermediate
**User Rating**    |4.3 (13 globes from 3 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Windows API Call/ Explanation](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-api-call-explanation__1-39.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/duncan-jones-debug-print-from-an-exe__1-22003/archive/master.zip)

### API Declarations

```
Private Declare Sub OutputDebugString Lib "kernel32" Alias "OutputDebugStringA" (ByVal lpOutputString As String)
Private Declare Function IsDebuggerPresent Lib "kernel32" () As Long
```


### Source Code

```
Private Sub DebugNote(ByVal DebugString As String)
If IsDebuggerPresent Then
 Call OutputDebugString(DebugString)
End If
End Sub
```

