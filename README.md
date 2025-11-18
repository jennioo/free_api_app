tiltle ="""
Ceate an an app that uses an api.this is the free api(no key)

"""

import requests

print("Welcome disney fan!! You are right where 'DREAM WORKS'😉")
result = requests.get("https://api.disneyapi.dev/character")

if result.status_code != 200:
    print("Failed to fetch data")
    exit()

print("You're good to go\n")

disney_data= result.json()
characters = disney_data["data"]
#print(disney_data)
#fav = input("What is your favourite disney movie:")

def get_data(category):
    all_data =[]
    for char in characters:
        if char.get(category):
           for item in char[category]:
            all_data.append(item)
    return list(set(all_data))
   

options={
   "1": "films",
   "2": "tvShows",
   "3": "videoGames",
   "4": "parkAttractions",
   "5": "allies",
   "6": "enemies"
}

while True:
    print("I see you want to explore on some disney data")
    print("Select a category:\n")
    for key,value in options.items():
        print(f"{key}.{value}")

    choice =input("\nEnter your choice number:")

    if choice in options:
        category = options[choice]
        results = get_data(category)
        if results:
           print(f"the {category} in the dataset.")
           for item in results:
            print(item)
        else:
            print(f"No {category } items found in the dataset.\n")
    else:
        print("Invalid choice. Enter a valid number\n") 
        print(choice)     


    answer= input("Will you like to explore more? (Y)es or (N)o:").strip().lower()
    if answer == "y":
       get_data(category)   
    elif answer == "n":
        print("Byee see you next time!🥲")
        break
    else:
        print("Invalid input, please enter Y or N")




tiltle ="""
Ceate an an app that uses an api.this is the free api(no key)

"""

import requests

print("Welcome disney fan!! You are right where 'DREAM WORKS'😉")
result = requests.get("https://api.disneyapi.dev/character")

if result.status_code != 200:
    print("Failed to fetch data")
    exit()

print("You're good to go\n")

disney_data= result.json()
characters = disney_data["data"]
#print(disney_data)
#fav = input("What is your favourite disney movie:")

def get_data(category):
    all_data =[]
    for char in characters:
        if char.get(category):
           for item in char[category]:
            all_data.append(item)
    return list(set(all_data))
   

options={
   "1": "films",
   "2": "tvShows",
   "3": "videoGames",
   "4": "parkAttractions",
   "5": "allies",
   "6": "enemies"
}

while True:
    print("I see you want to explore on some disney data")
    print("Select a category:\n")
    for key,value in options.items():
        print(f"{key}.{value}")

    choice =input("\nEnter your choice number:")

    if choice in options:
        category = options[choice]
        results = get_data(category)
        if results:
           print(f"the {category} in the dataset.")
           for item in results:
            print(item)
        else:
            print(f"No {category } items found in the dataset.\n")
    else:
        print("Invalid choice. Enter a valid number\n") 
        print(choice)     


    answer= input("Will you like to explore more? (Y)es or (N)o:").strip().lower()
    if answer == "y":
       get_data(category)   
    elif answer == "n":
        print("Byee see you next time!🥲")
        break
    else:
        print("Invalid input, please enter Y or N")




