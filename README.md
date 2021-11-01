# Table of Contents  
● [Preparing Database to Make a Full Backup](#Preparing%201%20Database%201%20to%201%20Make%201%20a%201%20Full%201%20Backup)  
● [Setting Up Postgres](#Setting%201%20Up%201%20Postgres)<br/>
&emsp;◌ [Connecting Postgres with Pentaho](#Connecting%201%20Postgres%201%20with%201%20Pentaho)<br/>
● [Pentaho Data Integration](#Pentaho%201%20Data%201%20Integration)<br/>
&emsp;◌ [Creating two samples of Transformations in Pentaho Data Integration](#Creating%201%20two%201%20samples%201%20of%201%20Transformations%201%20in%201%20Pentaho%201%20Data%201%20Integration)<br/>

  

# Preparing Database to Make a Full Backup

In this tutorial, I will show how to create a sample database downloaded on the web known as SportsDB for Postgres.

This sample can be downloaded in the following link:

http://www.sportsdb.org/sd/samples

Once you've downloaded this file and unzip the script to a specific path as choosen by you, don't forget where is it!

Before, you keep doing the step-by-step guide, I recommend you to check whether Postgres 11 version is installed on your local machine.

If you don't have Postgres version 11 installed yet. Just ckick on the link below to download it

https://www.enterprisedb.com/downloads/postgres-postgresql-downloads

Hence, I will open PG Admin 4 and start the process of reading the script we do

1) Use the right click of the mouse on Databases and then Select Create -> Database
<img src="https://user-images.githubusercontent.com/69978184/136665826-5a20504a-2d9a-48e9-89a5-3a155828a494.png" width="500" height="400"/>

2) Give a name to the database and save it
<img src="https://user-images.githubusercontent.com/69978184/136666252-37185925-ff79-4011-b7bd-f0fec304faf7.png" width="500" height="400"/>

3) Load the script into Query Tool by using the right click on SportsDB and select Query Tools

<img src="https://user-images.githubusercontent.com/69978184/136666370-ee9890ec-c570-4b96-bf05-1f985ceb9eca.png" width="500" height="400"/>

4) Once you have already opened the Query Tool just import the script.sql for it. 
That is why, it is important you must remember where you saved it
For that just clck on open file icon
<img src="https://user-images.githubusercontent.com/69978184/136666568-688e4518-ca9b-4b8d-a7c0-ffd49c49e167.png" width="200" height="200"/>

5) Then, just Run the Script and if everything is ok, then a message of "Query returned Successfully" will be shown
<img src="https://user-images.githubusercontent.com/69978184/136666752-0b6e05b5-bc66-443d-b0bf-0b812a923402.png" width="500" height="300"/>

### Making Full Backup from Database

1) Open Prompt Command and type CD + Local Path for Postgres<br/>
<img src="https://user-images.githubusercontent.com/69978184/136667015-b2772e9d-b2b8-4403-8f73-6fae7bf28452.png" width="500" height="200"/>
2) Type pg_dump -h localhost -p 5432 -U postgres SportsDB > D:\SportsDB.sql and put your password to complete the process<br/>
<img src="https://user-images.githubusercontent.com/69978184/136667180-01100ed5-1258-46b4-ae15-7b2a7c58f307.png" width="500" height="200"/>


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

if you wanna check whether the connection is working properly or not, just click on Test button

<img src="https://user-images.githubusercontent.com/69978184/139608292-60dc26d0-c9a3-44e8-9d6a-12d1fb1d0d51.png" width="400" height="200"/>

# Pentaho Data Integration

## Setting Up AWS credentials to be used with Pentaho

We're gonna use S3 with Pentaho further, then before that We'll need to set up the credentials to make it possible.

For that is requested to have an AWS Access Key ID and Secret Access Key and can get to learn how to get it [here](https://medium.com/@Rajendrasinh/aws-access-key-id-and-secret-access-key-for-iam-user-8e3625ea850)

After that you can access the provided [link](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-files.html) by AWS where you can follow the step-by-step guide

It will be shown above, but it does not mean that this way will be the same on your local machine. Below, we have the following steps:<br/>

➤  Create .aws folder<br/>
➤  Create Config and Credential files using Notepad ++<br/>
➤  Save these created files in .aws folder<br/>

<img src="https://user-images.githubusercontent.com/69978184/139674620-bbf7128f-aa51-4326-aa8f-5e41fbf061ea.png" width="500" height="200"/>

<img src="https://user-images.githubusercontent.com/69978184/139676177-baee0ef3-6225-402f-9995-35b4a8d2716c.png" width="500" height="200"/>

<img src="https://user-images.githubusercontent.com/69978184/139676513-cd3c4775-ae22-4e39-901b-79db9a122450.png" width="400" height="200"/>

## Creating two samples of Transformation in Pentaho Data Integration

The first Transformation has to do with Getting a specific table, create a filter just selecting the columns desired and generate an excel file saved on local machine.

Before starting this transformation, it will be needed to select four items to complete this first task and here they are:<br/>
➤ Table Input<br/>
➤ Select Values<br/>
➤ Text File<br/>
➤ Microsoft Excel Output<br/>

Now, We will see the step-by-step process to complete this task:

<img src="https://user-images.githubusercontent.com/69978184/139609940-d4a36760-6a28-4bbd-8a3e-4c6a58c7e1f9.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139610076-75f92ad4-4c16-4fa4-9bb4-f5334d1cefd1.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139610225-9c4296c3-db31-453f-8da1-1ae31cc48e90.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139610486-cb970481-baff-440d-af41-326f8a05a83d.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139610653-3f64dd47-9637-4ad6-9088-4d7dbcfd2cd9.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139610725-988d1d3d-faa8-44f3-968b-a9a4060a36ea.png" width="500" height="300"/>

By following the step-by-step for this process, just click on the run icon to check whether the process is running properly. You don't need to finish up the process to try it out, it means that as you are creating the transformation as shown above, you can run to test it before going to the next step and so on. At the end, you will get something like this, mostly after running it:

<img src="https://user-images.githubusercontent.com/69978184/139611265-f52c77b8-ddc1-4333-8682-d65596c9d747.png" width="500" height="300"/>

The second Transformation gets the data from CSV input and put it into a S3 bucket.

Before starting this transformation, it will be needed to select four items to complete this first task and here they are:<br/>

➤ Table Input<br/>
➤ Select Values<br/>

<img src="https://user-images.githubusercontent.com/69978184/139678146-c46545c4-d0a0-47a4-bbab-457da88999e7.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139678519-f9c225cc-0127-41ec-b49d-2b11aea2c0fc.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139678733-110b69b3-c0f5-4af4-946c-ee9c5f3d5ff9.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139680243-3dbcfb18-29b4-427e-8378-ad4d8be747e3.png" width="500" height="300"/>

<img src="https://user-images.githubusercontent.com/69978184/139680609-744639db-c8a2-44bf-aab0-71696c669bc6.png" width="500" height="300"/>

