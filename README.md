# OverTheWire-Natas
A walkthough of the OverTheWire:Natas CTF

Welcome to the OverTheWire-Natas wiki!

Let's Begin with the CTF. Visit the https://overthewire.org/wargames/natas/ there you will see the details regarding the Natas. Now, Head on to the CTF you can see the below details when you visit the site. 
### Natas 0: 
url: http://natas0.natas.labs.overthewire.org/
username: natas0 (given)
password: natas0 (given)

Just visit the url and provide the credentials. You will be presented with a page. 
Steps: 
1. Right click on the white box of the page and go to inspect.
2. Check below the text you will see a commented line.
3. That's it, You will find the password in the commented line.

Solution: gtVrDuiDfck831PqWsLEZy5gyDz1clto

Now edit your url to http://natas0.natas.labs.overthewire.org/ to http://natas1.natas.labs.overthewire.org/
### Natas 1:
url: http://natas1.natas.labs.overthewire.org/
username: natas1
password: gtVrDuiDfck831PqWsLEZy5gyDz1clto

Here right click is disabled! So use keyboard shortcut to Ctrl+Shift+I (Chrome) open the web inspector. 
Steps:
1. Go to inspect by pressing CTRL+SHIFT+I
2. Check below the visible text i.e. "You can find the password for the next level on this page, but rightclicking has been blocked!". 
3. You can see a commented line which hold the password for the natas2.

Solution: ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi

### Natas 2:
url: http://natas2.natas.labs.overthewire.org/
username: natas2
password: ZluruAthQk7Q2MqmDeTiUij2ZvWy2mBi

Here you can see a page with text "There is nothing on the page".
Steps:
1. Right Click and Go to inspect
2. Below the visible text you can find an img tag which points to an image file. i.e. "<img src="files/pixel.png">"
3. Now you need to check the directory listing for the folder "files" i.e. http://natas2.natas.labs.overthewire.org/files/. You can see two files "pixel.png" and "users.txt". 
4. Open the users.txt 
Voila !! You can find the password for the natas3.
Solution: sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14 

### Natas 3:
url: http://natas3.natas.labs.overthewire.org/
username: natas3
password: sJIJNW6ucpu6HPZ1ZAchaDtwd7oGrD14

Here also you can see a page with text "There is nothing on the page". Upon inspect there is a comment "No more information leaks!! Not even Google will find it this time...". 
So I thought for a second and looked for unusual things in the codes. I didn't find anything, then I check for any robots.txt. There it is a link to hidden folder.
Steps:
1. Open url http://natas3.natas.labs.overthewire.org/robots.txt
2. You will find a folder in disallowed. 
3. To access the hidden folder visit the url http://natas3.natas.labs.overthewire.org/s3cr3t
4. You can find the directory listing having a single file named "users.txt".
5. Open the file you will get the password for the next stage.

Solution: Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ

### Natas 4:
url: http://natas4.natas.labs.overthewire.org/
username: natas4
password: Z9tkRkWmpt9Qr7XrR5jWRkgOU901swEZ

Message on screen
Access disallowed. You are visiting from "" while authorized users should come only from "http://natas5.natas.labs.overthewire.org/"
In this one you need to be come from proper channel to access the page. So for this you will need to capture and modify the packets.
You need to start burp suite for this one.
Steps:
1. Configure burp suite to capture the packets.
2. Once the page is loaded you can see a text along with a refresh button. 
3. Turn "ON" intercept in burp suite. Open the page and click the "Refresh page" link.
4. In burp suite you can find the captured packet. Modify the referrer to "http://natas5.natas.labs.overthewire.org"
5. You will get a Access Granted Message along with the password for the next stage.

Solution: iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq

### Natas 5:
url: http://natas5.natas.labs.overthewire.org/
username: natas5
password: iX6IOfmpN7AYOQGPwtn3fXpbaJVJcHfq

Upon login you will be presented with "Access disallowed. You are not logged in"
Steps:
1. Right Click and open the inspector.
2. Goto Application Menu -> Cookies
3. Edit the value of loggedin to 1
4. Reload and there u have it....the password for the next stage.
Using burp suite
1. Configure burp suite to capture the packets.
2. Reload the page and capture the request. Send that to repeater.
3. If you notice carefully the cookie holds a value loggedin, whose value is 0.
4. Modify loggedin to 1 and SEND.
5. Access granted along with password for the next stage will be provided.

Solution: aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1

### Natas 6:
url: http://natas6.natas.labs.overthewire.org/
username: natas6
password: aGoY4q2Dc6MgDq4oL4YtoKtyAg9PeHa1

Here you need to input secret code to view the password for the next stage. There is also a "View sourcecode" link available. 
Steps:
1. Click the View sourcecode button.
2. Carefully go through the function. You will find a file has been included "includes/secret.inc";
3. Open the secret.inc by accessing http://natas6.natas.labs.overthewire.org/includes/secret.inc you will find a secret variable initialized with value "FOEIUWGHFEEUHOFUOIU". 
4. Pass this code in the input box provided and click on submit button.
5. You will get a message "Access Granted" along with the password for the next stage.

Solution: 7z3hEENjQtflzgnT29q7wAvMNfZdh0i9

### Natas 7:
url: http://natas7.natas.labs.overthewire.org/
username: natas7
password: 7z3hEENjQtflzgnT29q7wAvMNfZdh0i9

In this stage you have given links to 2 pages "Home" and "About".
Steps:
1. Right click and inspect the page. You will find a comment <!-- hint: password for webuser natas8 is in /etc/natas_webpass/natas8 -->
2. Click on any one of the menu link. 
3. Change the parameter value of page to /etc/natas_webpass/natas8 i.e http://natas7.natas.labs.overthewire.org/index.php?page=/etc/natas_webpass/natas8
4. You will get the password for the natas8.

Soluton: DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe

### Natas 8:
url: http://natas8.natas.labs.overthewire.org/
username: natas8
password: DBfUBfqQG69KvJvJ1iAbMoIpwSNQ9bWe

This stage also looks similar to previous stage. upon clicking "View sourcecode" link. We can see the complete code.
Steps:
1. Convert the encodedSecret = "3d3d516343746d4d6d6c315669563362" code. Use cyberchef of any online converts to conver hex to ASCII values.
2. Reverse the output and decode the base64. You will get the output as "oubWYf2kBq".
3. Submit this in the provied box and you will get the password for the next stage.

Solution: W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

### Natas 9:
url: http://natas9.natas.labs.overthewire.org/
username: natas9
password: W0mMhUcRRnG8dcghE4qvk3JA9lGt8nDl

Here command injection need to be done.
Steps:
1. Provide "n /etc/natas_webpass/natas10" in the input field and search.
2. You will be provided with the password for the next stage.

Solution: nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu

### Natas 10:
url: http://natas10.natas.labs.overthewire.org/
username: natas10
password: nOpp1igQAkUzaI1GUUjzn1bFVj7xCNzu

Steps: 
1. Provide input as "1 /etc/natas_webpass/natas11".
2. You will get the password for the natas 11.

Solution: U82q5TCMMQ9xuFoI3dYX61s7OZD9JKoK
