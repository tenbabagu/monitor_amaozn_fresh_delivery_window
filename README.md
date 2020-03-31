# monitor_amaozn_fresh_delivery_window
scripts to monitor amaozn fresh delivery window

## preps
### 1. download header json file from chrome
(1) go to the amazon fresh shipping&payment page by using Chrome, and right click -> click "inspect". In the dev tool, please click the "Network" tab.  
And now the page is shown as the following img.
![Screenshot from 2020-03-29 02-25-29](https://user-images.githubusercontent.com/19834770/77845931-59c6ea80-7167-11ea-964d-97f4ec069feb.png)

(2) Refresh the page. This is step is required.

(3) Download the headers file at Place 2, and save it at this proj path: data/www.amazon.com.json

### 2. find the session id and brand id in the url 
(1) for amazon fresh  
Go to the page named "before you checkout", which is the latst page before the checkout page just like its name. You'll find its url format is:   
```
https://www.amazon.com/alm/byg?sessionID=XXXXX&useDefaultCart=1&brandId=YYYYY (....)
```
Thus session_id = XXXXX, amazon_fresh_brandid = YYYYY

(2) for amazon wholefoods    
Also go to the page named "before you checkout", you'll find its url format is: 
```
https://www.amazon.com/alm/byg?brandId=ZZZZZ
```
Thus amazon_wholefoods_brandid = ZZZZZ


### 3. install libs to play mp3
```
sudo apt-get update
sudo apt-get install vlc
```

Now, you have found all the preps, just run the jupyter script to start to monitor the delivery window.


## FAQ
1. Problem with amazon fresh and whole food.  
[03/29] I find that at client side, amazon fresh and whole food share the same json file, and at amazon server side, it will detect whether the user is at wholefood or amazon fresh page. Thus, it currenlty seems unlikely to monitor the delivery window for both amazon fresh and wholefood now. Wait to be solved.    
[03/30] This problem has been solved, 

