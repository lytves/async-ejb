## Java EE 7 Tutorial:  Asynchronous Method Invocation in Session Beans

[Java Platform, Enterprise Edition: The Java EE Tutorial. Oracle](https://docs.oracle.com/javaee/7/tutorial/) - web version

[The Java EE Tutorial. Oracle](https://docs.oracle.com/javaee/7/JEETT.pdf) - pdf
___
#### - **async-ejb**

This two aplications is demonstration of implementation asynchronous business methods in Enterprise Session Beans and call it from a web client

1. __*async-war*__ module - is a web aplication that contains a stateless session bean and a JavaServer Faces interface. The *MailerBean* stateless session bean defines an asynchronus method, *sendMessage*, which uses the JavaMail API to send an email an specified email address

2. __*async-smtpd*__ module - is a Java SE program auxiliary, thet simulate an SMTP server. This program listen on TCP port 3025 for SMTP request and prints the email messages to the *standard output console*

#### - running this example

+ running a module __*async-smtpd*__ project, Run as --> Java Aplication in your IDE. In the output console tab show the results and future messages

+ In order to compile the __*async-smtpd*__ example you have to update the resource name of JavaMail in class *MailerBean*

  *in case of servidor WildFly as specified in the  Management Console (Configuration > Subsystems > Mail > default > Attributes).

+ deploy module __*async-war*__ on your aplication server, open URL http://localhost:8080/async-war/ and enter a email in a form and press "Send email"