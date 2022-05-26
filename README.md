# project-code

_________LOGIN SCREEN___________

self.login_screan = Frame(win)

self.login_screan.configure(bg="plum")

self.login screan.pack()

self.first = PhotoImage(file='image/mainimage.png')

self.firstlabell = Label(self.login_screan, image=self.first).grid(row-2, column=0, columnspan=15, rowspan=9)

Label(self.login_screan, text="EVENT MANAGEMENT", bg="\#2d64f5" , font="Times 50", fg="gold").grid(row-2, column=-9, columnspan=13, rowspan=4)

self.name_label= Label(self.login_screan, text="USER-ID", fg='white', font="Times

26", bg="#2d64f5").grid( row=2, column=3) self.user_entry = Entry(self.login_screan, width=25, font-" times 20", bg="silver") self.user_entry.grid(row-2, column=4, columnspan=2)

self.password_label= Label(self.login_screan, text="PASSWORD", font=" mathfrak res 26^ prime prime ,

bg="\#2d64f5^ prime prime ,fg="v white").grid( row-3, column m=3) self.password_entry Entry(self.login_screan, width=25, font="times 20", sh Ow =^ prime S ,

bg="silver")

self.password_entry.grid(row-3, column=4, columnspan=2)

self.login_button - Button(self.login_screan, text="LOGIN", font-13, width=20, bg='blue', fg=^ prime white^ prime , command-self.login_verify).grid(row=5, column=4)

self.newuser_label= Label(self.login_screan, text="New user? Click on register", font="time 20", bg="white").grid(row=6, column=7, columnspan=6)

self.rege = PhotoImage(file='image/reg.png')

self.register_button = Button(self.login_screan, image=self.rege, bg=^ prime gray^ prime ,fg=^ prime gold^ prime width=250, command-self.register).grid(row=7, column=7, columnspan=6)




_____________OTP SCREEN___________

#otp frame

self.otp_screan = Frame(win)

self.otp_screan.pack()

self.otp_screan.pack_forget() self.otpimage = PhotoImage(file='image/mail (2).png')

self.otplabel = Label(self.otp_screan, image=self.otpimage). grid(row=0, column=0,

columnspan=12)

self.otplabel = Label(self.otp_screan, text="Check your mail for OTP", font="times

20"),grid(row=1, column=2)

self.otp_entry = Entry(self.otp_screan, width-20, font="times 25")

self.otp_entry.grid(row=3, column=2) self.otp_submit = Button(self.otp_screan, text="Confirm OTP", font="times 15",

fg='brown', width=25, height=2,

command-self.otpconfirm). grid(row-4, column=2)

def otpconfirm(self):


if (self.otp_entry.get()== self.OTP):

cursor= db.cursor()

db = pymysql.connect(host="localhost", user="root", password="", database="event")

sql = "INSERT INTO register(name,mno,email,user,password) VALUES (""+self.al +""+self.a2+"",""+self.a3 +"""""+self.a4+""""+self.a5+"")"

try:

cursor.execute(sql)

self.userlogin_screan.pack() self.otp_screan.pack_forget() self.register_screan.pack_forget()

db.commit()

except:

# Rollback in case there is any error

db.rollback()

messagebox.showinfo("ALERT", "error in register")

else:

messagebox.showinfo("OTP Miss match", "OTP did not match") self.otp_screan.pack_forget()

self.register_screan.pack()



















LOGIN SCREEN

self.login_screan = Frame(win)

self.login_screan.configure(bg="plum")

self.login_screan.pack()

self.first = PhotoImage(file='image/mainimage.png')

self.firstlabell = Label(self.login_screan, image=self.first).grid(row-2, column=0, columnspan-15, rowspan=9)

Label(self.login_screan, text="EVENT MANAGEMENT", bg="#2d64f5", font="Times 50", fg="gold").grid(row=2, column=9, columnspan=13, rowspan=4)

self.name_label= Label(self.login_screan, text="USER-ID", fg='white', font="Times 26", bg="#2d64f5").grid( row=2, column=3)

self.user_entry = Entry(self.login_screan, width=25, font=" times 20", bg="silver")

self.user_entry.grid(row-2, column-4, columnspan=2)

self.password_label= Label(self.login_screan, text="PASSWORD", font="Times 26",

bg="#2d64f5", fg="white").grid( row=3, column=3)

self.password_entry = Entry(self.login_screan, width=25, font="times 20", show='S',

bg="silver")

self.password_entry.grid(row=3, column-4, columnspan=2)

self.login_button = Button(self.login_screan, text="LOGIN", font=13, width-20, bg='blue', fg='white',command-self.login_verify).grid(row=5, column=4)

self.newuser_label= Label(self.login_screan, text-"New user? Click on register",

font="time 20", bg="white"). grid(row-6, column=7, columnspan=6)

self.rege = Photolmage(file='image/reg.png')

self.register_button = Button(self.login_screan, image=self.rege, bg='gray', fg='gold', width=250, command=self.register).grid(row=7, column=7, columnspan=6)











LOGIN VERIFICATION

def login_verify(self):

self.a4 = self.user_entry.get()

self.pwd1 = self.password_entry.get()

con = pymysql.connect(host="localhost", user="root", password="", database="event")

cursor= con.cursor()

cursor.execute("select * from register where user=""+self.a4 + """")

rows = cursor.fetchall()

for row in rows:

self.unm = row[3]

self.pwd = row[4]

print("login success")

if self.a4 == or self.pwd1 == "";

messagebox.showinfo("ALERT", "User id and password cant be empty") 
elif self.a4 = ="admin" and self.pwd1=="admin":

self.login_screan.pack_forget()

self.admin_screan.pack()

elif self.a4 != self.unm:

messagebox.showinfo("ALERT", "Invalid User-id ") elif self.pwd1 != self.pwd:

messagebox.showinfo("ALERT", "Invalid Password")

elif self.a4 self.unm and self.pwd1 self.login_screan.pack_forget() self.userlogin_screan.pack() = self.pwd: ==

#messagebox.showinfo("ALERT", "Invalid Password") 
con.close()







