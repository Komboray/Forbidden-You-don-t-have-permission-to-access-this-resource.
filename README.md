# Forbidden-You-don-t-have-permission-to-access-this-resource.
This is a solution for the forbidden error in php my admin server after you try to login a user and save their password with username into the database

//This is the error that you get
![Screenshot (48)](https://github.com/Komboray/Forbidden-You-don-t-have-permission-to-access-this-resource./assets/121002402/b74ccaf4-0999-48ca-9d05-57deaf18bb66)



//How to solve the problem
 1. On the xampp panel, stop all the processes that are running
 2. Click on the Apache config and choose the Apache(httpd-xampp.conf)
 
 //you are looking for the below part after you opended it on a text editor of your choice
 
 3. Alias /phpmyadmin "C:/xampp/phpMyAdmin/"
    <Directory "C:/xampp/phpMyAdmin">
        AllowOverride AuthConfig Limit
        Require Local
        ErrorDocument 403 /error/XAMPP_FORBIDDEN.html.var
    </Directory>
    
    //make sure that you find and change the require local to the way it looks in the 4th process below
  4.Alias /phpmyadmin "C:/xampp/phpMyAdmin/"
    <Directory "C:/xampp/phpMyAdmin">
        AllowOverride AuthConfig Limit
        Require all granted
        order allow, deny
        Allow from all
        ErrorDocument 403 /error/XAMPP_FORBIDDEN.html.var
    </Directory>
    
    
    //That's all you need, please save all the changes and you are now ready to use the features, for images go to the code section
