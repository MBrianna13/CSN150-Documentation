# B.M 2024 Cybersecurity 150 Lab

## Name of Project
Send SMS with the ESP32 (Twilio)

## Purpose
The purpose of my project is to send a SMS with the ESP32 using Twilio. 

## Equipment
* [ESP32Cam](https://www.amazon.com/Aideepen-ESP32-CAM-Bluetooth-ESP32-CAM-MB-Arduino/dp/B08P2578LV/ref=sr_1_3?crid=4FY0ECFW0ZX7&keywords=ESP32+Cam&qid=1678902050&sprefix=esp32+cam%2Caps%2C240&sr=8-3)

* [USB Micro Data Cable](https://www.amazon.com/AmazonBasics-Male-Micro-Cable-Black/dp/B0711PVX6Z/ref=sr_1_1_sspa?keywords=micro+usb+data+cable&qid=1678902214&sprefix=Micro+USB+data+%2Caps%2C89&sr=8-1-spons&psc=1&spLa=ZW5jcnlwdGVkUXVhbGlmaWVyPUFaU0NaUVZHU1RFUlAmZW5jcnlwdGVkSWQ9QTA3NTA4MDVFVERCS01HVlgxM1YmZW5jcnlwdGVkQWRJZD1BMDE4NTE1NTIwWUdONkdWSzU1M1Amd2lkZ2V0TmFtZT1zcF9hdGYmYWN0aW9uPWNsaWNrUmVkaXJlY3QmZG9Ob3RMb2dDbGljaz10cnVl)


## Link to Documentation Followed
- [GitHub - martin-ger/esp32_nat_router](https://randomnerdtutorials.com/send-sms-esp32-twilio/)

##### Youtube Video 1: - [Send an SMS from ESP32 (ft. Twilio)](https://www.youtube.com/watch?v=SP4pvYCQAfc)

##### Youtube Video 2:  

##### Other Links: 


## Steps I followed
1. Write the steps you followed here.  This way you can keep track of where you might have messed up if the project does not work. 
I started off by creating an Twilio account which was a free trial account.
You would then have to add in your number in order to create the account and then you have to verify your number.
You then have to verify your phone number on the Twilio by going on Phone Numbers > Manage > Verified Called IDs
You must keep in mind that every number that you want to send a SMS must be verified.
1. In order to send SMS through Twilio you need to buy a number. The free trial account comes with $15.50 credit(know that with the free account you can only purchase one phone number)
2. Either you automatically get a number or you go and purchase a number of your chossinh.
3. To purchase anb number you would go on the dashboard and click Phone Numbers > Manage > Buy a Number.
4. You first want to select the country you are in. I am in the United States so I pick US.
5. You then look for a number that is to your liking and once you find the number you like, you click on *BUY*.
6. It will direct you to a "review phone number" tab and you click on "Buy +xxxxxxxxxx" to buy the number.
7. Now that you have purchased the nunber you want to try and send a SMS.
8. On the dashboard, click on Messaging > Try it Out > Send an SMS.
9. First you want to Create a message friendly service name that says *ESP32 Alerts*
10. You then select the Twilio number that you purchased previously and click on "Add this number"
11. You skip the next page as it is not that relevant.
12. Then you click on create messaging service and you are done and ready to send a SMS.
13. You click on "Try SMS" to get started.
14. One you are on "Send a SMS" page you start with step one.
15. for recepient "to" you click on "Use my personl number".
16. On the "To phone number" you will choose that number that is verified to receive SMS.
17. you then go to the *sender* section.
18. for sender "from" you select "Messeging Service" and on *Select a messaging service* you select "ESP32 SMS"
19. On step 2 on *message* you add your message. My message was *This is a test message from Twilio - Data rates may apply*
20. Once you put in your message you click on the blue icon that says *Send Test Message*
21. You should receive a message to your phone. Also on that page underneath the *message* box you will see a green box stating *Test message sent*.
22. Now we get to the fun part where send SMS using ESP32.
23. First you want to start off by going to Arduino, click on Sketch > Include Library > Manage Libraries search up twlio-esp32 client and install it.
24. once the twilio-esp32-client is install, you go to Arduino then click on Files > Examples > twilio-esp32-client > send_sms (this will give you the entire template without having to in all the codes. Youl'll only need to plug in where it says "REPLACE_WITH...ect"
25. I plugged in the ssid and the password which was my wifi and my wifi password then I plugged in the account_sid, auth_token, the from_number(the twilio number), the to_number(which is my number), and the message which I put *Hello from my ESP32 (via twilio)*
26. once the code is done, I click on *upload* icon on Arduino so that the ESP32 can connect to the Twilio's api
27. You will then go to Serial Monitor to see if the connection was complete.
28. And then you are done.
    


## Problems
Note your problems or errors here.  Google any error you may come across, and not what you tried (even if it does not work), and what was the final answer.

Example
1. Arduino code will not load on ESP32 Cam.
   Answer: Camera drivers were incorrect I needed to install the driver: [https://www.wch-ic.com/downloads/CH341SER_ZIP.html](https://github.com/martin-ger/esp32_nat_router).  I used file, "CH341SER.ZIP" and it worked.

Some of the problems I came across was first the number I bought from Twilio would not send an SMS to my number and also it wouldn't allow me to select my phone number as the receiver of the test message. 
On Arduino, when I clicked on *Serial Monitor* it kept showing *connecting, conecting conecting* this meant that I basically had to put my Wfif and password for it to work. 
Because I was still having issues with sending sms from the Twilio number to my phone I ended up closing that account (if it even closed 🤡) and created a whole new account. I did the entire process all over again and that is when I was able to see a test text message sent from Twilio to my number(well google voice 👹). 
The biggest problem of my project was that the ESP32 was not able to connect to Twlio's api, it kept showing connection failed. I made sure that I put in all the correct information and still I would get a *connection failed*. However the ESP32 did connect to my Wifi.
