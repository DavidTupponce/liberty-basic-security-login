# liberty-basic-security-login

* Import the attached zip to your Eclipse workspace
* Then open server.xml in liberty profile
* Add the following feature in server.xml and install it if required in the profile
<feature>appSecurity-2.0</feature>
* Add below lines to server.xml

`<basicRegistry id="basic" realm="defaultRealm">
      <user name="bob" password="bobpwd"/>
</basicRegistry>

<webApplication id="TestwebAppWithLibertyBasicLogin" location="TestwebApp.war"
       name="TestwebApp">
       <application-bnd>
           <security-role name="testing">
               <user name="bob"/>
           </security-role>
       </application-bnd>
</webApplication>`

* Then start the server and try the following url  http://localhost:9080/TestwebAppWithLibertyBasicLogin/MyServlet

