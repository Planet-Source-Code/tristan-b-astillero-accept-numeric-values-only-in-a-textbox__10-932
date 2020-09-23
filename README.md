<div align="center">

## Accept numeric values only in a textbox


</div>

### Description

It validates the entries of a textbox while it is being entered, and allows only one instance of the decimal point(period) to be entered. Please vote and leave a comment so that at least i know im doing something right. =)
 
### More Info
 
It has 2 parameters: e.keychar(eventargs) and the textbox control.

If you have any suggestions or encounter an error I would appreciate your comments. Thanks. I it's simple but hopefully this will garner me some votes. =P

Returns a boolean value indicating if the event is handled or not.

None to my knowledge(so far).


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Tristan B\. Astillero](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/tristan-b-astillero.md)
**Level**          |Intermediate
**User Rating**    |4.7 (99 globes from 21 users)
**Compatibility**  |VB\.NET
**Category**       |[Algorithims](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithims__10-29.md)
**World**          |[\.Net \(C\#, VB\.net\)](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/net-c-vb-net.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/tristan-b-astillero-accept-numeric-values-only-in-a-textbox__10-932/archive/master.zip)





### Source Code

```
Private Sub TextBox1_KeyPress(ByVal sender As Object, ByVal e As System.Windows.Forms.KeyPressEventArgs) Handles TextBox1.KeyPress
 e.Handled = NumbersOnly(e.KeyChar, TextBox1)
 End Sub
Private Function NumbersOnly(ByVal pstrChar As Char, ByVal oTextBox As TextBox) As Boolean
 'validate the entry for a textbox limiting it to only numeric values and the decimal point
 If (Convert.ToString(pstrChar) = "." And InStr(oTextBox.Text, ".")) Then Return True 'accept only one instance of the decimal point
 If Convert.ToString(pstrChar) <> "." And pstrChar <> vbBack Then
 Return IIf(IsNumeric(pstrChar), False, True) 'check if numeric is returned
 End If
 Return False 'for backspace
 End Function
```

