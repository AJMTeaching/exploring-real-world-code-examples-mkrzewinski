- Code that specifies when an alarm clock should start making audible sounds.

link: [https://github.com/ROSHAN-KHANDAGALE/Alarm-Clock](https://github.com/tilak30/alarm-clock/tree/master)

which lines from which files: lines 3-36 from alarm-clock / alarm-clock.py

def sound(p):
    for i in range(10):
        winsound.MessageBeep(-1)
        time.sleep(1)


def when_sound(p):
    time.sleep(p)
    sound(p)


def input_no(n):
    if (n == 1):
        x = int(input('Enter hours : '))
        when_sound(60*60*x)
    elif (n==2):
        x = int(input('Enter minutes : '))
        when_sound(60*x)
    elif (n == 3):
        x = int(input('Enter seconds : '))
        when_sound(x)
    elif (n == 4) :
        hours = int(input('Enter Hours : '))
        min = int(input('Enter minutes : '))
        sec = int(input('Enter seconds : '))
        when_sound((hours*60*60)+(min*60)+(sec))




def main():
    print("enter time after which alarm should ring: press 1)for hours 2)for minutes 3)for seconds 4)for combination")
    n = int(input(":"))
    input_no(n)

why? def input_no (n) allows us to schedule the alarm for the alarm for a specific time (hour, minute, second) and the def main () allows for the action to be executed at that specific time

- Code for a rocket targeting system.

link: https://github.com/123nadeem/Smart-Rocket-System/tree/main

which lines from which files: lines 281-319 from Smart-Rocket-System / main.py

def Mainloop():
    LIFE = 0
    popl = Population()
    pygame.init()
    win = pygame.display.set_mode((WIDTH, HEIGHT))
    pygame.display.set_caption("Smart Rockets Game")
    clock = pygame.time.Clock()

    count = 0
    Fps = 200

    run = True
    while run:
        clock.tick(Fps)
        keys = pygame.key.get_pressed()

        for event in pygame.event.get():
            if event.type == keys[pygame.QUIT] or keys[pygame.K_ESCAPE]:
                run = False
                sys.exit()

        # popl.run(win, LIFE)
        LIFE += 1
        if LIFE == LIFESPAN:
            LIFE = 0

        count += 1
        if count == LIFESPAN:
            popl.evaluate()
            popl.natural_selection()
            count = 0

        # time.sleep(0.01)
        redrawwindow(win, popl, LIFE)
    pygame.QUIT
    quit()


Mainloop()

why? line 298 allows for the missile to stop firing at the target

- File compression utility algorithm.

link: https://github.com/ElvisKoech/Python-code-to-zip-and-compress-files/tree/main

which lines from which files: lines 18-35 from Python-code-to-zip-and-compress-files / main.py

# Open the original zip file in read mode
with zipfile.ZipFile('Zone_3_Road.zip', 'r') as original_zip:

    # Create a new zip file in write mode
    with zipfile.ZipFile('new.zip', 'w', compression=zipfile.ZIP_DEFLATED) as new_zip:

        # Iterate over the files in the original zip file
        for file in original_zip.filelist:

            # Read the contents of the file
            data = original_zip.read(file.filename)

            # Write the contents of the file to the new zip file
            new_zip.writestr(file.filename, data)

# Replace the original zip file with the new zip file
import os
os.replace('new.zip', 'Zone_3_Road.zip')

why? lines 21 and 22 allow us to create a zip file and lines 33-35 allow for the replacement of the original file to become a zip file

- Weather forecasting algorithm.

link: https://github.com/Naman-Bhalla/Weather_Forecasting_Sliding_Window_Algorithm/tree/master

which lines from which files: lines 10-44 from Weather_Forecasting_Sliding_Window_Algorithm / main.py

def enter_data(year):
    if year == "present":
        slots = 7
    elif year == "last":
        slots = 14

    data_list = []

    for num in range(slots):

        value = []

        for slot in range(4):

            if slot == 0:
                quantity = "max_temp"
            elif slot == 1:
                quantity = "min_temp"
            elif slot == 2:
                quantity = "humidity"
            elif slot == 3:
                quantity = "rainfall"

            print("Please enter the", quantity, "for day",str(num + 1), "for", year, "year:- ")

            #-------------- TEST ONLY
            ##print(data)
            #-------------- TEST ONLY

            data = int(input())
            value.append(data)

        data_list.append(value)

    return data_list

why? lines 24-33 allow us to view the minimum and maximum temperatures for a specific day as well as view any rain that may comeabout as well as other features such as humidity.
  
- E-commerce checkout system process.

link: https://github.com/JeremyTallant/online_store/tree/main

which lines from which files: lines 16-43 from online_store / main.py

def run(self):
        while True:
            print("\nWelcome to the Online Store!")
            print("1. Browse products")
            print("2. View cart")
            print("3. Checkout")
            print("4. Load money")
            print("5. Exit")

            choice = input("Enter your choice (1-5): ")

            if choice == "1":
                self.store.browse()
                product_id = input("Enter the ID of the product you'd like to add to your cart (or 'q' to go back): ")
                if product_id.lower() != 'q':
                    self.store.add_to_cart(product_id, self.user.shopping_cart)
            elif choice == "2":
                self.user.shopping_cart.view_cart()
            elif choice == "3":
                self.store.checkout(self.user)
            elif choice == '4':
                amount = float(input("Enter the amount of fake money you'd like to load: "))
                self.user.load_fake_money(amount)
            elif choice == "5":
                print("Thank you for shopping with us. Goodbye!")
                break
            else:
                print("Invalid input. Please try again.")


why? lines 34-40 allow us to checkout any items that we wish to purchase on the respected website and then the transaction is finalized on line 40 with the message displaying "Thank you for shopping with us. Goodbye!" What follows is an error message that requires the user to either exit the tab or return to the homescreen.
  
- Social media post scheduler.

link: https://github.com/Ayotundepaul/Automated-Social-Media-Poster-python/tree/main

which lines from which files: lines 7-19 from Automated-Social-Media-Poster-python / social.py

# Function to post to Twitter
def post_to_twitter(api_key, api_secret_key, access_token, access_token_secret, message):
    auth = tweepy.OAuthHandler(api_key, api_secret_key)
    auth.set_access_token(access_token, access_token_secret)
    api = tweepy.API(auth)
    api.update_status(message)

# Function to schedule a tweet
def schedule_tweet(s, delay, api_keys, message):
    s.enter(delay, 1, post_to_twitter, argument=(api_keys['api_key'], api_keys['api_secret_key'], 
                                                 api_keys['access_token'], api_keys['access_token_secret'], 
                                                 message))
    s.run()

why? lines 7-12 grant us access to post to a specific social media platform, in this case, Twitter. On Twitter, we have the option to schedule a tweet, which is accomplished by lines 14-19.
  
- Fitness app calorie counter.

link: https://github.com/Abdulmalik420/Calorie-Counter

which lines from which files: lines 48-105 from Calorie-Counter / main.py

def calorieAdder(user, date, nowDate):
    counter = 0
    os.chdir(mainPath)
    os.chdir(user)
    if(os.path.exists(nowMonth) == True):
        os.chdir(nowMonth)
    else:
        os.mkdir(nowMonth)
        os.chdir(nowMonth)
    print("Please add your calories in this format (Item-Quantity)\nIf you are a new user please add calories in this format (Item-Quantity-Calorie)")
    count = input("Please input the amount items you want to input: ")
    count = int(count)
    itemArray = []
    quantityArray = []
    caloriesArray = []
    perArray = []
    totalArray = []
    while (counter != count):
        item = input("Item: ")
        itemArray.append(item)
        quantity = input("Quantity: ")
        quantity = int(quantity)
        quantityArray.append(quantity)
        calories = input("Calories: ")
        calories = int(calories)
        caloriesArray.append(calories)
        perAmount = input("Per amount: ")
        perAmount = int(perAmount)
        perArray.append(perAmount)
        total = (quantity/perAmount)*calories
        totalArray.append(total)
        counter += 1
        if(counter == count):
            titledColumn = ({"Item": itemArray, "Quantity": quantityArray, "Calories": caloriesArray, "Per Amount": perArray, "Total": totalArray})
            data = pd.DataFrame(titledColumn)
            if(os.path.exists(date)):
                data.to_csv(date, mode='a', header=False, index=False)
                print("Added to database")
                totalCalculator(user, date, nowDate)
                menu(user, nowDate)
            else:
                data.to_csv(date, index=False)
                totalCalculator(user, date, nowDate)
                menu(user, nowDate)

def grapher(user):
    print(f"This will graph for {user}")

def weightAdder(user, date):
    print(f"This will add weight for {user} for the date of {date}") 

def totalMonthTable(user):
    os.chdir(mainPath)
    os.chdir(user)
    os.chdir(nowMonth)
    print(f"This is the total Calories for {nowMonth}")
    df = pd.read_csv('Total.csv')
    print(df.to_markdown())

why? lines 48-91 allow us to insert a specific amount of food for a given month and from there, the calculations are prepared to be executed by lines 99-105. This will calculate the total number of caloric intake in a given month based on the inputs that were provided in lines 48-91.

- Online voting system mechanics.

link: https://github.com/Bharati2301/Online-Voting-System-using-Python-and-MySQL/tree/main

which lines from which files: lines 390-437 from Online-Voting-System-using-Python-and-MySQL / final.py

  def show_result(self):
        query="SELECT Result.PartyID, party_table.PartyName,SUM(Vote_Count) AS 'Total_Count' FROM Result,party_table WHERE Party_table.Partyid = Result.partyID GROUP BY result.PartyID ORDER BY Total_Count DESC"
        cur=self.db.cursor()
        cur.execute(query)
        print("\n\tVOTES FOR EACH PARTY\n")
        print("Party ID   Party Name   Count")
        for i in cur:
            print("  ", i[0],"\t\t ",i[1],"\t  ",i[2],'\n')
            
    def party_candidate(self,Aadhaar):
        query="select PartyId,PartyName from party_table where LeaderAadhaar='{}'".format(Aadhaar)
        cur=self.db.cursor()
        cur.execute(query)
        for r in cur:
            PartyId=r[0]
            PartyName=r[1]
        print("\nShowing candidate details for '{}' party\n".format(PartyName))
        query_2="select voter_table.FirstName,voter_table.LastName,address.Locality,address.City,address.State from address,candidate_table,voter_table where candidate_table.DistrictId=address.DistrictId and candidate_table.Aadhaar=voter_table.Aadhaar and candidate_table.PartyId={}".format(PartyId)
        cur2=self.db.cursor()
        cur2.execute(query_2)
        #print("  Name\t\t \t\tLocality\t\t \t\tCity\t\t \t\tState")
        print("\t{:<15} {:<15} {:<10} {:10}".format("Name","Locality","City","State"))
        for r in cur2:
            name=r[0]+" "+r[1]
            print("{:<15} \t{:<15} {:<10} {:<10}".format(name,r[2],r[3],r[4]))

vs=voting_system()
while True:
    print("What do you want to do?\n")
    print("SIGN UP\t LOGIN\t PARTY REGISTRATION\tVIEW RESULT\t LEAVE") 
    task=input("What do you want to do? ")
    if task.upper()=="SIGN UP":
        print("\n\n\nSIGN UP:\n")
        vs.sign_up()
    elif task.upper()=="PARTY REGISTRATION":
        print("\n\n\nPARTY REGISTRATION:\n")
        vs.party_registration()
    elif task.upper()=="LOGIN":
        print("\n\n\nLOGIN:\n")
        vs.login()
    elif task.upper()=="VIEW RESULT":
        vs.show_result()
    elif task.upper()=="LEAVE":
        print("\n\n\nBYE!!!")
        quit()
    else:
        print("Invalid Input!")

why? lines 399-414 allow us to select a candidate for which we need to supply our first and last name and address. Once completed, lines 416-436 then ask the user what they wish to do after voting. If the voter is satisfied with their vote, they may wish to exit the sight as demonstrated in lines 432-436. 

- Automated email response system.

link: https://github.com/thekamik/email-automation-with-gpt-ai-and-python/tree/main

which lines from which files: lines 74-98 from email-automation-with-gpt-ai-and-python / email_bot.py

def send_email(self, subject, body, receiver_email):
        
        # Create a multipart message and set headers
        message = MIMEMultipart()
        message["From"] = self.sender_email
        message["To"] = receiver_email
        message["Subject"] = subject

        # Add body to email
        message.attach(MIMEText(str(body), "plain"))

        # Add attachment to message and convert message to string
        text = message.as_string()

        # Log in to server using secure context and send email
        context = ssl.create_default_context()
        with smtplib.SMTP_SSL(self.mail_host, self.SMTP_SSL, context=context) as server:
            server.login(self.sender_email, self.password)
            server.sendmail(self.sender_email, receiver_email, text)

        # Add email to send folder, and mark email as seen
        imap = imaplib.IMAP4_SSL(self.mail_host, self.IMAP_SSL)
        imap.login(self.sender_email, self.password)
        imap.append(self.sent_folder, '\\Seen', imaplib.Time2Internaldate(time.time()), text.encode('utf8'))
        imap.logout()

why? Lines 74-80 help to specify from whom the email was received and to who it should be sent to. Lines 82-98 allow the user with the self-automated email to insert a description of the email as an attachment so that the person who sent the email to the person with an automated email response will automatically receive an automated email.

Personal blurbs

1. Code for a do not disturb notification

link: https://github.com/josephcslater/Do-Not-Disturb/tree/master

which lines from which files: lines 93-138 from Do-Not-Disturb / dnd.py

if numin > 4.01 or colloc != 0:
    a5 = subprocess.Popen(['killall sleep -s;sleep ' + str(numin * 60) + ';defaults -currentHost write \
                     ~/Library/Preferences/ByHost/com.apple.notificationcenterui doNotDisturb -boolean false; \
                     defaults -currentHost delete ~/Library/Preferences/ByHost/com.apple.notificationcenterui \
                     doNotDisturbDate; killall NotificationCenter'], shell=True)
    print('Sleeping for ' + str(numin) + ' min.')
    logging.debug('Minute Mode')
else:
    a5 = subprocess.Popen(['sleep ' + str(numin * 3600) + ';defaults -currentHost write \
                     ~/Library/Preferences/ByHost/com.apple.notificationcenterui doNotDisturb -boolean false; \
                     defaults -currentHost delete ~/Library/Preferences/ByHost/com.apple.notificationcenterui \
                     doNotDisturbDate; killall NotificationCenter'], shell=True)
    numin = numin
    logging.debug('Sleeping for ' + str(numin) + ' min.')
    logging.warning(
        'Hour Mode- to never be entered again! Please report this error.')

wakehour = curhour
logging.debug('wakehour temp')
logging.debug(wakehour)

wakemin = numin + curmin

logging.debug('wakemin temp')
logging.debug(wakemin)

while wakemin > 59:
    logging.debug('swapping min for hour')
    wakemin = wakemin - 60
    logging.debug(wakemin)
    wakehour = wakehour + 1
    logging.debug(wakehour)

strwakemin = str(wakemin)

if wakehour > 12:
    wakehour = wakehour - 12

logging.debug(strwakemin)
logging.debug(str.find(strwakemin, '.'))
if str.find(strwakemin, '.') == 1:
    strwakemin = '0' + strwakemin
    logging.debug(strwakemin)

print('Do not disturb set until ' + str(wakehour) + ':' + strwakemin[:2]
      + '. (' + str(numin)[:-2] + ' minutes.)')

why? Since Do Not Disturb is a feature that involves silencing notifications for a definite/indefinite amount of time. Lines 93-108 allow for the notifications to be silenced, while lines 137-138 allow for this function to be executed until a certain time that the user has decided for the notifications to be silenced until. 

2. Code for checking battery percentage

link: https://github.com/HxnDev/Battery-Percentage-Notifier/tree/main

which lines from which files: lines 6-23 from Battery-Percentage-Notifier / main.py

def conversion(sec):    # Will convert seconds into Hrs and minutes
    second = sec % (24*3600)
    hour = second // 3600
    second %= 3600
    minute = second // 60
    second %= 60
    return hour, minute

while True:
    battery = psutil.sensors_battery()  # Gets battery information
    h, m = conversion(battery.secsleft)     # Converting them into hours and minutes
    notification.notify(    # Notifying
        title="Battery Percentage",
        message=f'{h}Hr {m}Min {battery.percent}% remaining',
        timeout=10
    )
    time.sleep(60*60)   # Notifies every hour

why? Lines 6-14 are responsible for converting hours and minutes into seconds, which allow for the battery percentage to be read to any given second, which makes the battery life that is displayed to be a more accurate reading. Lines 15-23 allow for the function of the battery percentage to be retrieved to the user as displayed by lines 15 & 16. This retrieves the battery information to the user and allows for the user to access their battery percentage in that given second.

3. Code for face recognition on electronic devices

link: https://github.com/fis-11/faceDET/tree/main

which lines from which files: lines 15-43 from faceDET / detector.py

def getProfile(id):
    conn=sqlite3.connect('faceBase.db')
    cmd="SELECT * FROM people WHERE ID="+str(id)
    cursor=conn.execute(cmd)
    profile=None
    for row in cursor:
        profile=row
    conn.close()
    return profile
    
#id=0
cam=cv2.VideoCapture(0)
#font=cv2.cv.InitFont(cv2.cv.CV_FONT_HERSHEY_COMPLEX_SMALL,5,1,0,4)
font=cv2.FONT_HERSHEY_SIMPLEX
fontscale=1
fontcolor=(255,255,0)
while True:
    ret,img=cam.read();
    gray=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
    #faces=faceCascade.detectMultiScale(gray,1.3,5);
    faces=faceCascade.detectMultiScale(gray, scaleFactor=1.2, minNeighbors=5); #,minSize=(100, 100), flags=cv2.CascadeClassifier
    for(x,y,w,h) in faces:
        id,conf=recognizer.predict(gray[y:y+h,x:x+w])
        cv2.rectangle(img,(x,y),(x+w,y+h),(0,0,255),2)
        profile=getProfile(id)
        if (profile!=None):
            cv2.putText(img,str(profile[1]),(x,y+h+30),font,fontscale,fontcolor)                    
        cv2.imshow("face",img)
        cv2.waitKey(10)

why? lines 15-23 allow for the electronic device to process the face and recognize it. Lines 25-36 give the command for what the electronic device to do if the face shown is in fact the face of interest. Lines 40-43 give the command for a face that is not familiar and therefore, this ends up in the wait section, and the electronic device cannot do further commands until the proper face is identified.
