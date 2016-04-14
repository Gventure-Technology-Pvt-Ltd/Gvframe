# Gvframe
Framework Developement
Documentation GVFrame
17 march 2016
Management.php
Location: /lib/plugin/Management.php
This file contains the main logic behind binding data coming from database with view which is display on the browser. You must extends this management class into your include directory to work with your application. Management class is the one of the major class to put your application to work. This class contains all prime function which are soon am going to explain. Before we start you must include this class into your include file.
List of function in Management.php: 
•	__construct
•	__set
•	__get
•	Option
•	AddNew
•	Execute
•	Response
•	RawSave
•	RawUpdate
•	RollBack
•	Save
•	UnBlock
•	Block
•	RawDeleted
•	Delete
•	Remove
•	Edit
•	RawEdit
•	Update
•	Detail
•	ListView
•	RawListView
•	Custom
•	CustomView
__cunstruct(string [dbtype], static object [logger]):
__set(sting [key], mixed[value]):
__get(srint [key]):
Option(string [tablename], string [column name], array [filter option with associative kay value pair], string [key]):
This function is used to display html dropdown into web browser. 
Example:
$this->Option(‘table_name’,’columnName’, array(‘column’=>’value’,’column’));
 
AddNew(string [template name]):
Use to render the add template to the browser.
Execute():
This function is used to execute the function after binding controller login with view logic. This is not necessary to use into include files. 
Response():
This is used for the return the response of execute function. Some time we use it into include files where we need to manually response from the function.
RawSave(string [tablename], array [contains data which are going to be insert], string [primary key name of the table]):
This function is used when we manually want to insert records. For example we have to insert into multiple table at a time and want a last insert id from previous table then we use this function. For getting last insert is we use $this->last; to get a last insert id.
RawUpdate(string [tablename], array [contains data which are going to be update], string [keyes], string [column name]):
As per RawSave we use RawUpdate for the same reason. You can use this function when you want to update multiple table.
RollBack():
This function is worked like transaction in database. When we bulk insert into table and if there is any error occur during insertion then it rollback its operation. You no need to put it into your code it is call automatically.
Save(array [contains data which are going to be insert]):
This function is used when we need to insert records into single table. Just put all data into an associative array format.
UnBlock():

Block():

RawDeleted(string [tablename], string [column value], string [column name]):
You can manually give information to delete records through this function.
Deleted():
This function is used to delete records from table.
Remove():
This function is used to update the status from table like 0 or 1 
Edit(string [template name], optional array [columns name], optional array [filters]):
This function is used to edit the records.
RawEdit(string [template name] , array [values which are going to be display for update]):
This function is used when you want to edit multiple table into a single form.
Update(array [records to update], array [fiters]):
This is used when you update single table.
Detail(string [template name], optional array [fields], optional array [filters]):
This function is used to show the detail of the table like profile or something.
ListView(string [template name], optional array [fields], optional array [filters]):
This function is used to display records into tabular format into browser.
RawListView(string [template]):
This function is used to display records into tabular format into browser. I believe this function is used very frequently by developers. 
Custom():
This function is used to execute your custom query. This is very important function to use your most of the database query through this.
CustomView(string [template], array [contains records to be display on the template]):
This is used when you need custom display on your template. It takes two parameter first one is the template name and seconds parameter is the data which are going to display into browser.

Controller.php
Location: /lib/plugin/Controller.php
As a framework development, it is very important to manage all request URLs, POST data, sessions, module, action and verifying those data for security majors. Here are the controller class manage all of this. This class contains functions which are as below: 
•	__construct()
•	__set()
•	__get()
•	Roles()
•	Module()
•	ModuleSetting()
•	verifySession()
•	SenitizeRequest()
•	PreLoad()
•	LoadModule()
•	Prepare()
•	Printsetting()
•	Execute()
You don’t need to change these settings until and unless you need to change or modify it. 
Userinterface.php
Location: /lib/plugin/view/Userinterface.php
Userinterface class is the tool where you can set your custom variable that can be access from smarty template side (view or presentation layer). For example you want a custom constant. You can define anywhere in your include file or config. Go to the userinterface class and bind it to the desired variable into assign function and then use it anywhere in your template.
Common.lib.php 
Location /lib/common.lib.php
This is the file where you put your own custom function to use it throughout the application. You can directly call your function. In this library few are most important function already included which are as below:
•	encode
•	decode
•	roles_HREFURL
•	login
•	MakeTime
•	MakeDate
•	DateFormat
In above function we have only need to understand Login function because we need this function in /module/index.php file
Login(string [login table name], array [put column name here while login], array [filter option for login authentication], array [put module and action if authentication success ], array [put module and action if authentication fails], object [logger object]):
It takes only six parameters. I am going to brief you. 
1.	Takes login table name which may be user or login.
2.	Takes column name while authenticating you can select columns like id, name etc.
3.	Takes filter option for authenticating login.
4.	Takes module and action name if authentication success. We use default module name as a user and action is detail. 
5.	Takes module and action name if authentication fail. We have default set to login and login for both module and action. 
6.	Last one is we pass logger object. You don’t have to alter or modify it. We use this for debugging purpose. 


