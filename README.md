<div align="center">

## Disable/Enable CTRL\+ALT\+DEL


</div>

### Description

' This code disables/enabled CTRL+ALT+DEL pressing

' To disable CTRL+ALT+DEL, call the function Disable_CTRL_ALT_DEL

' To enabled CTRL+ALT+DEL, call the function Enable_CTRL_ALT_DEL
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[King Patrik the Zerg](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/king-patrik-the-zerg.md)
**Level**          |Unknown
**User Rating**    |3.5 (7 globes from 2 users)
**Compatibility**  |VB 4\.0 \(32\-bit\), VB 5\.0, VB 6\.0
**Category**       |[Windows System Services](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/windows-system-services__1-35.md)
**World**          |[Visual Basic](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/visual-basic.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/king-patrik-the-zerg-disable-enable-ctrl-alt-del__1-1494/archive/master.zip)

### API Declarations

```
'***************************************************************
'Windows API/Global Declarations for :Dissable / Enable CTRL + AL
'   T + DEL
'***************************************************************
Declare Function SystemParametersInfo Lib "user32" Alias "SystemParametersInfoA" (ByVal uAction As Long, ByVal uParam As Long, lpvParam As Any, ByVal fuWinIni As Long) As Long
  Public Const SPI_SCREENSAVERRUNNING = 97
Public Sub Disable_Ctrl_Alt_Del()
  'Disables the Crtl+Alt+Del
  Dim AyW As Integer
  Dim TurFls As Boolean
  AwY = SystemParametersInfo(SPI_SCREENSAVERRUNNING, True, TurFls, 0)
End Sub
Public Sub Enable_Ctrl_Alt_Del()
  'Enables the Crtl+Alt+Del
  Dim AwY As Integer
  Dim TurFls As Boolean
  AwY = SystemParametersInfo(SPI_SCREENSAVERRUNNING, False, TurFls, 0)
End Sub
```


### Source Code

```
' Put this into Sub Main in a module
' Disable/Enable CTRL+ALT+DEL
'***************************************************************
' Name: Dissable / Enable CTRL + ALT + DEL
' Description:Dissable / Enable CTRL + ALT + DEL , This does just
'   what it says, it disables a used from pressing CTRL+ALT+DEL. Well
'   not dissables them from doing it, it just wont do anything if the
'   y do. :o)This is useful in setup programs when it is important th
'   ea a user not end task your program.
' By: Cy Toad
'
'
' Inputs:'Example of use:
' Call Disable_Ctrl_Alt_Del()
'Then at another time:
' Call Enable_Ctrl_Alt_Del()
'
' Returns:Dissables / Enables CTRL + ALT + DEL You wont be able t
'   o use CTRL + ALT + DEL until you Enable it again, or restart your
'   system.
'
'Assumes:None
'
'Side Effects:You wont be able to use CTRL + ALT + DEL until you
'   Enable it again, or restart your system.
'
'Code provided by Planet Source Code(tm) (http://www.PlanetSource
'   Code.com) 'as is', without warranties as to performance, fitness,
'   merchantability,and any other warranty (whether expressed or impl
'   ied).
'***************************************************************
    Dim X
  X = MsgBox("Do you wish to disable CTRL+ALT+DEL?", 36, "Disable/Enable CTRL+ALT+DEL")
    If X = vbYes Then
      Disable_Ctrl_Alt_Del
      MsgBox "CTRL+ALT+DEL is disabled, try pressing CTRL+ALT+DEL now.", , "Disable/Enable CTRL+ALT+DEL"
Again:
      X = MsgBox("Enbale CTRL+ALT+DEL now?", 36, "Disable/Enable CTRL+ALT+DEL")
        If X = vbYes Then
          Enable_Ctrl_Alt_Del
        ElseIf X = vbNo Then
          MsgBox "The program will not end before CTRL+ALT+DEL is enabled.", , "Disable/Enable CTRL+ALT+DEL"
          GoTo Again
        End If
    End If
```

