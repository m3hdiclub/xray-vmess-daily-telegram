# Xray Vmess Daily Telegram
Xray Vmess with send configuration in the telegram channel every day.This project send Xray Vmess configuration to your channel base on schedule.<br />

# Supported Version
Ubuntu 22.04


# easy way install

Persian Document [README_FA.md](https://github.com/majidrezarahnavard/xray-vmess-daily-telegram/blob/main/README_FA.md)



for more detail please read other parts.

* <b> please run these command one by one. </b> </br>
* <b> I am extremely recommend to change port 22 into another port.</b> 

```
echo "Port 9001" >> /etc/ssh/sshd_config
systemctl restart sshd
service ssh restart
```


```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration
```


* <b>please run these command one by one. </b>

```
wget https://raw.githubusercontent.com/m3hdiclub/xray-vmess-daily-telegram/main/install.sh
sudo chmod +x /root/xray-configuration/install.sh
bash /root/xray-configuration/install.sh
```

if you need modify the setting.json file


```
touch /root/xray-configuration/setting.json
echo "{
    \"port\": 443,
    \"bot_token\" : \"627434621931:bga9g_13IQBuAcDb3DSemBceracA-KDDA3b\",
    \"chat_id\" : \"-1002343276432\",
    \"dynamic_subscription\" : false,
    \"channel_name\" : \"Sarina_Esmailzadeh\",
    \"send_vnstat\" : false,
    \"aggregate_subscriptions\" : [],
    \"send_configuration\" : \"first\",
    \"send_subscriptions\" : true,
    \"random_header\" : false
}">  /root/xray-configuration/setting.json
```



after change the cronjob time, you need to save it. [easy set the time](https://crontab.guru/)

```
crontab -e
```

Run the command.

```
cd /root/xray-configuration
./xray-telegram
```


# Fill bot token and chanel id files with your own information.


We have two configuration options. Get bot token and chat id from your telegram account and telegram bot father. <br />

get bot token from [BotFather](https://t.me/BotFather)<br />
get chat id from [Find Channel id](https://gist.github.com/mraaroncruz/e76d19f7d61d59419002db54030ebe35)<br />


Fill the configuration inside the setting.json.

examples of configuration
bot_token is "2XXXXXXXX1:AXXXX_9XXXXXXXXXXXXXXXN-RXXXXXs"
chat_id is "-10000000000000" 


# Fill setting file with your values

Setting file is located in /root/xray-configuration/settings.json and you can easily modify settings. After changing settings, it necessary to run again `./xray-configuration` after changing.  <br />

Edit this setting file base on your needs.<br />

```port``` are the port that you want to use in your server. <br />
```bot_token``` is the bot token that you get from the bot father. <br />
```chat_id``` is the chat id that you get from the channel. <br />
```dynamic_subscription``` is the boolean value that you want to have dynamic subscribe link like ```subscribe.txt``` or dynamic ones like ```subscribe.122.txt``` <br />
```channel_name``` is the channel name that you want to send your configuration. You can choose what ever your want. System didn't check it. <br />
```send_vnstat``` is the boolean value that you want to send ( Bandwidth usage ) vnstat information to the channel. <br />
```list_of_subscriptions``` is list of other services that you want to aggregate . if you don't need it leave it without data  ```aggregate_subscriptions : []```

```send_configuration``` is send configuration to the channel. you can choose  ```first``` or ```none``` <br />
```send_subscriptions``` is send subscription to the channel. you can choose ```true``` or ```false```  <br />
```random_header``` set random header and response
<br />

```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration
touch /root/xray-configuration/setting.json
echo "{
    \"port\": 443,
    \"bot_token\" : \"627434621931:bga9g_13IQBuAcDb3DSemBceracA-KDDA3b\",
    \"chat_id\" : \"-1002343276432\",
    \"dynamic_subscription\" : true,
    \"channel_name\" : \"Sarina_Esmailzadeh\",
    \"send_vnstat\" : true,
    \"aggregate_subscriptions\" : [],
    \"send_configuration\" : \"first\",
    \"send_subscriptions\" : true,
    \"random_header\" : false
}">  /root/xray-configuration/setting.json
```


Another Method for modify setting.json


```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration
wget https://raw.githubusercontent.com/majidrezarahnavard/xray-vmess-daily-telegram/main/setting.json
nano /root/xray-configuration/setting.json
```
[ آموزش کار کردن با نانو](https://www.youtube.com/watch?v=Aj2pmC0u2ow)<br />



```
wget https://raw.githubusercontent.com/majidrezarahnavard/xray-vmess-daily-telegram/main/setting.json
```

Instead of creating the setting.json file, you can also use the following command to create the file and fill it with the default values. <br />

Using Online Tool : Open a JSON Formatter tool from the link below <br />


```
https://jsonformatter.org
or
https://codebeautify.org/jsonviewer
or
https://json-gui.esstudio.site/
```
Copy and Paste the JSON Data, which is mentioned in Option 1 in the Input tool of the online tool . after making json format, write it with nano in ```setting.json```

nano /root/xray-configuration/setting.json




# Check the setting.json 

For check your json file you can use below command line. <br />

```cat /root/xray-configuration/setting.json```


You have to see below result. <br />
```
{
   "ports": 443,
   "bot_token" : "627444321931:bga9g_13IQBuAcDb3DSemBceracA-KDDA3b",
   "chat_id" : "-1003342276432",
   "dynamic_subscription" : false,
   "channel_name" : "Sarina_Esmailzadeh",
   "send_vnstat" : true,
   "aggregate_subscriptions" : [],
   "send_configuration" : "first",
   "send_subscriptions" : true,
   "random_header" : false
}

```


If you don't see setting.json file, you can create it with below command line. <br />
You can also edit your file with nano editor. <br />
[ How To Make and Edit Files With Nano ](https://www.youtube.com/watch?v=fJTPjWuyrIY) <br />
[ Nano for Text Editing in Ubuntu](https://www.youtube.com/watch?v=NV9PyPJKqH4) <br />
[ Learn JSON in 10 Minutes ](https://www.youtube.com/watch?v=iiADhChRriM) <br />

```
rm -rf /root/xray-configuration/setting*
wget https://raw.githubusercontent.com/majidrezarahnavard/xray-vmess-daily-telegram/main/setting.json
nano setting.json
```
And then modify your json file. <br />


If these method didn't work for use FileZilla to upload file directly to the server.
[ How to upload files to your web server using FileZilla ](https://www.youtube.com/watch?v=9wlNS1iO_AM )




# Make setting without telegram and change SSH configuration

In this case you need to connect server with subscription only. <br />

```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration
touch /root/xray-configuration/setting.json
echo "{
    \"port\": 8585,
    \"bot_token\" : \"\",
    \"chat_id\" : \"\",
    \"dynamic_subscription\" : false,
    \"channel_name\" : \"sarina\",
    \"send_vnstat\" : false,
    \"aggregate_subscriptions\" : [],
    \"send_configuration\" : \"none\",
    \"send_subscriptions\" : false,
    \"random_header\" : false
}">  /root/xray-configuration/setting.json
```


# For sending the new configuration to telegram channel. 

Check send the new configuration to telegram channel.

```
./xray-configuration
```

after command execution the configuration send to your telegram channel.






# Aggregate list of subscription

Imagine you have three servers in different zones. And you want to aggregated all of these link and make one single link.<br />

for example: <br />
http://1.22.33.444/subscribe.txt <br />
http://2.22.33.444/subscribe.txt<br />
http://3.22.33.444/subscribe.txt<br />

now we make one single endpoint for you by this future: <br />

We will put this server subscription in front of these links as default values: <br />


Final result will be in below address <br />

http://ip-this-server/aggregate.txt

 ```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration
touch /root/xray-configuration/setting.json
echo "{
    \"port\": 443,
    \"bot_token\" : \"627444321231:bga9g_13IQBuAcDb3DSemBceracA-KDDA3b\",
    \"chat_id\" : \"-1003342276432\",
    \"dynamic_subscription\" : false,
    \"channel_name\" : \"Sarina\",
    \"send_vnstat\" : true,
    \"aggregate_subscriptions\" : [ \"http://1.22.33.444/subscribe.txt\" , \"http://2.22.33.444/subscribe.txt\" , \"http://3.22.33.444/subscribe.txt\"],
    \"send_configuration\" : \"first\",
    \"send_subscriptions\" : true,
    \"random_header\" : false
}">  /root/xray-configuration/setting.json
```





# Diagnosis and check problems


Show errors of cron jobs
```
cat /root/xray-configuration/cronjob.log
```

Reinstall the first time install the Xray

```
cd /root
mkdir /root/xray-configuration
cd /root/xray-configuration

rm -rf /root/xray-configuration/install.sh*
wget https://raw.githubusercontent.com/majidrezarahnavard/xray-vmess-daily-telegram/main/install.json

sudo chmod +x /root/xray-configuration/install.sh

bash /root/xray-configuration/install.sh
```


Check Xray version
```
xray version
```


Check status of xray 
```systemctl status xray```

Restart Xray service 
```systemctl restart xray```


Check logs of Xray
```
journalctl -u xray.service
systemctl status xray
```

Check volume of disk usage in server

```
df -h

ls -laht /var/log

echo "" > /var/log/kern.log
echo "" > /var/log/syslog
echo "" > /var/log/syslog.1
service syslog restart
journalctl --vacuum-size=50M

```

check the website 
```
http://ip

```

If you had firewall on your server, you need to open the port that you want to use. 
```
sudo ufw status
```
[Linux Security - UFW Complete Guide](https://www.youtube.com/watch?v=-CzvPjZ9hp8)



If vnstat didn't work properly, you need to reset the database.
```
vnstat -D
```

Or Another solution was to remove the folder it uses to store its data (/var/lib/vnstat) and create a new empty directory instead. You may need to run vnstatd manually once to create the database after that:

```
vnstatd -n -s
```
Apart from that, I also needed to apply 
```
sudo chown -R vnstat:vnstat /var/lib/vnstat
```

# Uninstall xray


you need to run these commands manually:

```
# Stop and disable xray service
systemctl stop xray
systemctl disable xray

# Remove files
rm /etc/systemd/system/xray.service
rm /root/xray-configuration/vmess.json
rm /root/xray-configuration/xray
rm /root/xray-configuration/subscribe.*
rm -rf /var/www/hml/subscribe.*
rm /root/xray-configuration/key_pair.txt
rm /root/xray-configuration/xray-telegram
rm /root/xray-configuration/install.sh
rm /root/xray-configuration/reinstall.sh
rm /root/xray-configuration/make_subscribe.sh
```

And if you want delete setting.json

```
rm /root/xray-configuration/setting.json
```


## remove logs

```
df -h

ls -laht /var/log

echo "" > /var/log/kern.log
echo "" > /var/log/syslog
echo "" > /var/log/syslog.1
service syslog restart
journalctl --vacuum-size=50M
```




##  << Other options ( professional edit project) >>


# Modify the cronjob ( change time that want to send to the channel)
Cron job is the time scheduler for run the script automatically. after two days new configuration will send to your channel.


see the cronjob list
```crontab -l```

result:

```
30 11 * * * cd /root/xray-configuration && /root/xray-configuration/xray-telegram > /root/xray-configuration/cronjob.log 2>&1
```



for edit cronjob use these command
```crontab -e```

[more information for cron job](https://www.youtube.com/watch?v=v952m13p-b4) 


show log of cronjob ``` cat cronjob.log ```

you can change the cronjob time in the cronjob.sh file. [easy set the time](https://crontab.guru/)


for example use ```30 9 * * 6``` for the “At 09:30 on Saturday.” 



# Fake HTML and subscribe to xray 
This part for fake html and give url link to members of the Telegram channel.


you can share ```http://ip/subscribe.txt``` to members of the Telegram channel.
Dynamic subscribe has different format like this ```http://ip/subscribe.122.txt``` 
And Also you can use ```http://ip ``` for fake html.



# Install bach maker for different SNI with Golang 

for build go file use below command line:
```
GOOS=linux GOARCH=amd64 CGO_ENABLED=0 go build -o xray-telegram
```

<br />
if you got below error it means that the architecture of your server is not amd64. 

```
cannot execute binary file exec format error 
```

It was said: Usually that error message means Linux doesn't recognize the file as a shell script or as an executable file. Typically the cause is running an executable on the wrong architecture - if you try to run x86 executables on an ARM CPU, this message comes up.


# Base64 String
```
vmess://eyJhZGQiOiI0NS4xNTYuMjQuMjI0IiwiYWlkIjoiMCIsImhvc3QiOiJtYXNoaGFkMS5pcmFuY2VsbC5pciIsImlkIjoiNTEwN2RhNzAtYjgyNy00NGQzLTlhYWEtNjM5MGJhYmIyYjA2IiwibmV0IjoidGNwIiwicGF0aCI6Ii8iLCJwb3J0IjoiODA4MCIsInBzIjoic2FyaW5hIiwic2N5IjoiYXV0byIsInNuaSI6IiIsInRscyI6IiIsInR5cGUiOiJodHRwIiwidiI6IjIifQ==
```

base64 decode :
```

{"add":"45.156.24.224","aid":"0","host":"mashhad1.irancell.ir","id":"5107da70-b827-44d3-9aaa-6390babb2b06","net":"tcp","path":"/","port":"443","ps":"sarina","scy":"auto","sni":"","tls":"","type":"http","v":"2"}

```

# cron tab file example


```
30 8 * * * cd /root/xray-configuration && /root/xray-configuration/xray-telegram > /root/xray-configuration/cronjob.log 2>&1
0 5 * * * cd /root/xray-configuration && /root/xray-configuration/xray-telegram > /root/xray-configuration/cronjob.log 2>&1
30 16 * * * cd /root/xray-configuration && /root/xray-configuration/xray-telegram > /root/xray-configuration/cronjob.log 2>&1
30 20 * * * cd /root/xray-configuration && /root/xray-configuration/xray-telegram > /root/xray-configuration/cronjob.log 2>&1
```
