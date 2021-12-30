# gameSet y = CreateObject("Scripting.FileSystemObject")
Set y = Nothing
Do
a = 0
u = 0
Randomize
Number = Int((RND*99)+1)
MsgBox "Я загадал число от 1 до 100, попробуй отгадать",64,"Угадайка"
Do
a = a + 1
c = InputBox("Угадай число" & vbCrLf & vbCrLf & "Попытка: " & a & vbCrLf & vbCrLf & "Чтобы посмотреть результаты введите число !" & vbCrLf & vbCrLf & "Для выхода оставьте поле пустым" & vbCrLf & vbCrLf,"Угадайка")
If c = "!" Then CreateObject("WScript.Shell").Run "notepad C:\Windows\Result.dll",3,True : Exit Do
If c <> "" Then
If IsNumeric(c) = True Then
If CInt(c) < Number Then MsgBox "Нет, это не " & c & ". Я загадал число больше",64,"Угадайка"
If CInt(c) > Number Then MsgBox "Нет, это не " & c & ". Я загадал число меньше",64,"Угадайка"
If CInt(c) = Number Then
Set y = CreateObject("Scripting.FileSystemObject")
MsgBox ("Количество попыток: " & a)
If MsgBox ("Правильно, это было число " & c & ". Начать заново?",36,"Угадайка") = 6 Then Exit Do Else WScript.Quit
End If
Else
MsgBox "Это не число!",16,"Угадайка"
a = a - 1
End If
Else
a = a - 1
l = MsgBox ("Ты ничего не ввел. Выйти из программы?",36,"Угадайка")
If l = 6 Then WScript.Quit
End If
Loop[github.txt](https://github.com/YakupovaKarina/game/files/7793644/github.txt)
