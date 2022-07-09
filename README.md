# VB-calculator
Public Class Form1
    Dim firstvalue, seconvalue, result As Double
    Dim op As String
    Private Sub TextBox1_TextChanged(sender As Object, e As EventArgs) Handles txtDisplay.TextChanged

    End Sub

    Private Sub Button1_Click(sender As Object, e As EventArgs) Handles btnDel.Click
        If (txtDisplay.Text.Length > 0) Then
            txtDisplay.Text = txtDisplay.Text.Remove(txtDisplay.Text.Length - 1, 1)

        End If
        If (txtDisplay.Text = "") Then
            txtDisplay.Text = "0"
        End If
    End Sub

    Private Sub number_click(sender As Object, e As EventArgs) Handles btnDot.Click, btn9.Click, btn8.Click, btn7.Click, btn6.Click, btn5.Click, btn4.Click, btn3.Click, btn2.Click, btn1.Click, btn0.Click
        Dim b As Button = sender
        If (txtDisplay.Text = "0") Then
            txtDisplay.Text = ""
            txtDisplay.Text = b.Text

        ElseIf (b.Text = ".") Then
            If (Not txtDisplay.Text.Contains(".")) Then
                txtDisplay.Text = txtDisplay.Text + b.Text
            End If
        Else
            txtDisplay.Text = txtDisplay.Text + b.Text
        End If
    End Sub

    Private Sub btnEqual_Click(sender As Object, e As EventArgs) Handles btnEqual.Click
        seconvalue = txtDisplay.Text
        If op = "+" Then
            result = firstvalue + seconvalue
            txtDisplay.Text = result
        ElseIf op = "-" Then
            result = firstvalue - seconvalue
            txtDisplay.Text = result
        ElseIf op = "*" Then
            result = firstvalue * seconvalue
            txtDisplay.Text = result
        ElseIf op = "/" Then
            result = firstvalue / seconvalue
            txtDisplay.Text = result
        End If
    End Sub

    Private Sub btnPM_Click(sender As Object, e As EventArgs) Handles btnPM.Click
        If (txtDisplay.Text.Contains("-")) Then
            txtDisplay.Text = txtDisplay.Text.Remove(0, 1)
        Else
            txtDisplay.Text = "-" + txtDisplay.Text
        End If
    End Sub

    Private Sub btnC_Click(sender As Object, e As EventArgs) Handles btnC.Click
        txtDisplay.Text = ""
        If (txtDisplay.Text = "") Then
            txtDisplay.Text = "0"
        End If
    End Sub

    Private Sub btnCE_Click(sender As Object, e As EventArgs) Handles btnCE.Click

    End Sub

    Private Sub Operator_Click(sender As Object, e As EventArgs) Handles Button16.Click, btnPlus.Click, btnMulti.Click, btnMinus.Click
        Dim b As Button = sender
        firstvalue = txtDisplay.Text
        op = b.Text
        txtDisplay.Text = " "
    End Sub
End Class
