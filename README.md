## Introduction
In the previous lab, I had already create a web application creating databasse first. Therefore, in this lab, I will learn how to build an ASP.NET MVC 5 application that uses Entity Framework 6 for data access with the Code First workflow. </br>
This lab will show how to build the Contoso University sample application. The sample application is a simple university website. With it, users can view and update student, course, and instructor information.
## Body
In this lab, I used Visual Studio 2019 t create an MVC web app.
!image/appcreate.png
Then, I set up the site style in the _Layout.cshtml_ file with the path is: "Views\Shared\_Layout.cshtml" and make some changes:
!image/setupstyle.png
And I also configure again the homepage index in "Views\Home\Index.cshtml":
!image/setupindex.png
Next, I installed Install Entity Framework 6 with the command: 'Install-Package EntityFramework'
After that, I created the entity classes for the application:
Course class: !image/courseclass.png
Enrollmentclass: !image/enrollmentclass.png
Studentclass: !image/studentclass.png
Next, I created the database context by adding a new folder named DAL (Data Access Layer) and add a new class in there named SchoolContext.cs with the following code:
!image/schoolcontext.png
And then, I initialized database with the test data. Particularly, I created a new class named SchoolInitializer.cs and create the database with some test data:
!image/testdata.png
To tell Entity Framework to use my initializer class, I added an element to the entityFramework element in the application Web.config file:
!image/addcontextelement.png
In addition, I also have to add a connectionStrings element in the Web.config file to initiate and use the database: (In the image below, my connectionStrings is to connect with the database on Azure in order to host the web application on it)
!image/connectionstrings.png
And next, I have to create the conntrollers and views with each entity class using entity framework. (The image below shows the creating of Student controller and view as an example, creating Course controller is similar with this)
!image/createcontrollers.png
!image/addstudentcontroller.png
Now, let's see the result.
!image/result.gif
