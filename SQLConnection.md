# Connect Logic Apps to Azure SQL

In this article let's see how we can store the output from a http response to a SQL database. 

### Step 1: Create a Azure SQL Server
- If you already have a Resouce group naviate to it and Select **Create > Create a Resource**
- Search for **Azure SQL** in Marketplace
- Click on **Create**

<img width="284" alt="image" src="https://user-images.githubusercontent.com/41346103/172854631-e35aa256-7231-489e-85bf-4e3f4c9e219c.png">


- Under Select SQL deployment option page Select **Single databse > Create**

<img width="241" alt="image" src="https://user-images.githubusercontent.com/41346103/172854769-595414ed-e050-4a7d-a031-761a2fac604e.png">

- Give a **Database name**
- Create a new **Server** 
- Give a **ServerName**
- Choose a **Location**
- Choose authentication method as **SQL authentication**
- Create a **Server admin login** and **password**
- Select **OK**
- Other settings are optional you can choose as per your requirement 
- Select **Review + Create**
- Select **Create**

### Step 2: Create a Table
- Go to **Resources**
- On the Side Blade Select **Query Editor (Preview)**

<img width="366" alt="image" src="https://user-images.githubusercontent.com/41346103/172854256-3e18600a-b12b-4a90-98c9-7e635eba204b.png">

- Enter your **Credentials** which you craeted in Step 1
- You might get an error for **Firewall Rule**
- Click on the Error to create the Rule in the Fireall
- Select **OK**
- Write a query to create a Table

> Below query create a Table with Table name CALLID and one column with title callid where the output from the http response will be stored

```
CREATE TABLE CALLID(
callid varchar(255)
);
```

<img width="497" alt="image" src="https://user-images.githubusercontent.com/41346103/172854415-946ae302-739a-4c13-bf23-21167b557eee.png">


- To validate if the table has been created properly write below query

```SELECT TOP (100) * FROM [dbo].[CallID]```

>Below query creates a Table with Table name DETAILEDCALLID with multiple colums to store output from the HTTP response

```
CREATE TABLE DETAILEDCALLRECORDS (
"@odata.context" varchar(255),
id varchar(255),
version varchar(255),
type varchar(255),
modalities varchar(255),
lastModifiedDateTime varchar(255),
startDateTime varchar(255),
endDateTime varchar(255),
joinWebUrl varchar(255),
organizer: varchar(1000),
organizerUserDetails: varchar(255),
participants varchar(1500),
sessions varchar(20000),
caller varchar(8000),
callee varchar(8000),
failureinfo varchar (255),
media (8000)
);
```
