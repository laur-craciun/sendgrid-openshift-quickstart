Sendgrid on OpenShift
======================

This git repository helps you to send emails quickly and easily through SendGrid on OpenShift using PHP.


Running on OpenShift
----------------------------

Create an SendGrid account at http://sendgrid.com/user/signup

Create an account at http://openshift.redhat.com/ and set up you local machine with the client tools.

Create a php-5.3 application (you can call your application whatever you want) and change into the application directory.
<pre>
    rhc app create sendgrid php --from-code https://github.com/openshift/sendgrid-openshift-quickstart
    cd sendgrid
</pre>

###Configuration###
Configure <strong>php/send_email.php</strong> file with your information:

Update the username and password with your SendGrid credentials.
```php
    $sendgrid = new SendGrid('<sendgrid_username>', '<sendgrid_password>');
```

Update your email address, subject, text content and html content:
```php
    $mail->
          addTo('foo@bar.com')->
          setFrom('me@bar.com')->
          setSubject('Subject goes here')->
          setText('Hello World!')->
          setHtml('Hello World!');
```
Then push the repo
<pre>
    git add .
    git commit -m "my first commmit"
    git push
</pre>
That's it, you can now checkout your application at:
<pre>
    http://sendgrid-$yournamespace.rhcloud.com
</pre>

For more details about SendGrid libray please read http://sendgrid.com/docs/Code_Examples/php.html

You can create your Sendgrid Quickstart with other programming languages using the following examples: http://sendgrid.com/docs/Code_Examples/index.html

