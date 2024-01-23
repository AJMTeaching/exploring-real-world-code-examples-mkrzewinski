- Code that specifies when an alarm clock should start making audible sounds.

link: https://github.com/ROSHAN-KHANDAGALE/Alarm-Clock

which lines from which files

import datetime
import time

def set_alarm(alarm_time):
    while True:
        current_time = datetime.datetime.now().strftime("%H:%M:%S")
        
        if current_time == alarm_time:
            print("Wake up! It's time for your alarm.")
            # You can add code here to play a sound or perform any other action
            break
        
        time.sleep(1)  # Check the time every second

# Set the alarm time in HH:MM:SS format
alarm_time = "07:00:00"
set_alarm(alarm_time)

why? lines 14 & 15 indicate that the operating system will sound the alarm when the current time is equal to the alarm time and display the message "Wake up! It's time for your alarm." 

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

why?

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

why?

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

why?
  
- E-commerce checkout system process.

link:

which lines from which files:

why?
  
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

why?
  
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

why?

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

why?

- Automated email response system.

link:

which lines from which files:

why?

Personal blurbs

1. Code for a do not disturb notification

link:

which lines from which files:

why?

2. Code for a read message notification

link:

which lines from which files:

why?

3. Code for opening a new tab on Chrome

link:

which lines from which files:

why?
