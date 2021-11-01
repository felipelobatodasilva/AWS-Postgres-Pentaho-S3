# Table of Contents  
● [Preparing Database to Make a Full Backup](#Preparing%201%20Database%201%20to%201%20Make%201%20a%201%20Full%201%20Backup)  
● [Setting Up Postgres](#Setting%201%20Up%201%20Postgres)<br/>
&emsp;◌ [Connecting Postgres with Pentaho](#Connecting%201%20Postgres%201%20with%201%20Pentaho)

  

# Preparing Database to Make a Full Backup

In this tutorial, I will show how to create a sample database downloaded on the web known as SportsDB for Postgres.

This sample can be downloaded in the following link:

http://www.sportsdb.org/sd/samples

Once you've downloaded this file and unzip the script to a specific path as choosen by you, don't forget where is it!

Before, you keep doing the footsteps, I recommend you to check whether Postgres 11 version is installed on your local machine.

If you don't have Postgres version 11 installed yet. Just ckick on the link below to download it

https://www.enterprisedb.com/downloads/postgres-postgresql-downloads

Hence, I will open PG Admin 4 and start the process of reading the script we do

1) Use the right click of the mouse on Databases and then Select Create -> Database
<img src="https://user-images.githubusercontent.com/69978184/136665826-5a20504a-2d9a-48e9-89a5-3a155828a494.png" width="500" height="300"/>

2) Give a name to the database and save it
<img src="https://user-images.githubusercontent.com/69978184/136666252-37185925-ff79-4011-b7bd-f0fec304faf7.png" width="500" height="300"/>

3) Load the script into Query Tool by using the right click on SportsDB and select Query Tools

<img src="https://user-images.githubusercontent.com/69978184/136666370-ee9890ec-c570-4b96-bf05-1f985ceb9eca.png" width="500" height="300"/>

4) Once you have already opened the Query Tool just import the script.sql for it. 
That is why, it is important you must remember where you saved it
For that just clck on open file icon
<img src="https://user-images.githubusercontent.com/69978184/136666568-688e4518-ca9b-4b8d-a7c0-ffd49c49e167.png" width="100" height="100"/>

5) Then, just Run the Script and if everything is ok, then a message of "Query returned Successfully" will be shown
<img src="https://user-images.githubusercontent.com/69978184/136666752-0b6e05b5-bc66-443d-b0bf-0b812a923402.png" width="500" height="300"/>

### Making Full Backup from Database

1) Open Prompt Command and type CD + Local Path for Postgres
![image](https://user-images.githubusercontent.com/69978184/136667015-b2772e9d-b2b8-4403-8f73-6fae7bf28452.png)
2) Type pg_dump -h localhost -p 5432 -U postgres SportsDB > D:\SportsDB.sql and put your password to complete the process
![image](https://user-images.githubusercontent.com/69978184/136667180-01100ed5-1258-46b4-ae15-7b2a7c58f307.png)


# Setting Up Postgres

Access the following link in order to install pentaho at your local machine: https://medium.com/@databool/pentaho-data-integration-pdi-guia-de-instala%C3%A7%

After doing that, just unzip the file downloaded in a specified path and get started with pentaho


## Connecting Postgres with Pentaho

Once you have set up your Pentaho Environment to be used, you'll need to create a transformation by following the step shown below:<br/>
<img src="https://user-images.githubusercontent.com/69978184/139607565-b91f13dc-7df8-42ba-901a-ea4ee56678de.png" width="500" height="300"/>

and then Click on the File Tab -> Database Connection<br/>
<br/>
<img src="https://user-images.githubusercontent.com/69978184/139607715-89606284-d841-47ae-98b2-da761ab54a26.png" width="500" height="300"/>

As In our case, we're gonna use postgres as database, so We'll Select this one and fill it with its respective configuration fields that has been set up locally

<img src="https://user-images.githubusercontent.com/69978184/139608134-581d4781-147c-443c-8edc-6195adfacde9.png" width="500" height="400"/>

