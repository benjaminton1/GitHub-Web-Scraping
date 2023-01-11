import requests
from bs4 import BeautifulSoup as bs
#Pulls specific information from github user and displays based on user request
anything = True 
while anything: #While user is still looking for information
    #Gets github username 
    github_username = input('Input Github Username: ') 
    #Requets type of information to be pulled
    question = input('What would you like to find out? Profile Image, Hometown, Personal Website?')
    link = 'https://github.com/' + github_username
    r = requests.get(link) 
    soup = bs(r.content, 'html.parser') 
    #Function searches for specific information
    profile_imagelink = soup.find('img', {'alt': 'Avatar'})['src']
    hometown = soup.find('li', {'itemprop': 'homeLocation'})['aria-label']
    website = soup.find('a', {'class': 'Link--primary'})['href']
    #Information displayed depending on user request using conditional statements
    if question == 'Profile Image': 
        selectedInfo = profile_imagelink
    elif question == 'Hometown': 
        selectedInfo = hometown 
    elif question == 'Personal Website': 
        selectedInfo = website
    print(selectedInfo) 
    #If user has more requests, if not, stops program
    anythingelse = input('Anything else? Y or N') 
    if anythingelse == 'N' or anythingelse == 'n': 
        anything = False 