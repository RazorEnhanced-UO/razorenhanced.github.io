<code>
import clr
clr.AddReference ('System.Windows.Forms')
clr.AddReference('System.Drawing')

from System.Drawing import Point
from System.Windows.Forms import TextBox, Keys, KeyPressEventHandler

from System.Windows import Forms

class MyMainForm(Forms.Form):
    def __init__(self):
        self.Width = 300
        self.Height = 200
        self.Text = 'Main Form'
        my_button = Forms.Button(Text='Go!')
        my_button.Click += self.MyOnClick
        my_button.Location = Point(25, 95)
        self.Controls.Add(my_button)
        
        self.textbox = TextBox()
        self.textbox.Text = "0"
        self.textbox.Location = Point(25, 75)
        self.textbox.Width = 150
        #self.textbox.KeyDown += self.OnEnter
        self.textbox.KeyPress += KeyPressEventHandler(self.OnEnter)
        self.Controls.Add(self.textbox)
        
    def MyOnClick(self, *args):
        self.Finished()
    
    def OnEnter(self, e, args):
        key = args.KeyChar
        if key == Keys.Enter:
            self.Finished()
            
    def Finished(self):
        Misc.SendMessage("Answer was: {}".format(self.textbox.Text))
        self.Close()

app = MyMainForm()
Forms.Application.Run(app)
</code>
