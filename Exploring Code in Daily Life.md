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

link:

which lines from which files:

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

link:

which lines from which files:

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
