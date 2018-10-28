# apex-hello-world

Create your first hello world project in Apex/Salesforce code.

```java
global class HelloWorld {
  public String hello() {
    return 'Hello World!';
  }
}
```

```java
@isTest
private class HelloWorldTest {
  @isTest static void hello() {
    HelloWorld hello_world = new HelloWorld();
    String result = hello_world.hello();

    system.assertEquals(result, 'Hello World!');
  }
}
```

## Tutorial

### Setup Salesforce.com

[Create a salesforce.com developer account](https://developer.salesforce.com/signup).

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-0.png)

You'll receive an email from Salesforce with a link to confirm. Click it.

On the next screen, set your password. Yeah, it's an odd flow, but it's salesforce so what do you expect.

You now have a developer account.

Generate your security token. We will need this later. While logged into your developer account, click "Your Name > My Settings" at the top right portion of your developer account dashboard.

Then on the left side of the screen click "Personal > Reset My Security Token". Click the "Reset Security Token" button. Salesforce emails you a security token. You will need this later.

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-4.png)

### Setup local environment

[Install Sublime Text 3](http://www.sublimetext.com/3).

[Install Mavens Mate](http://mavensmate.com/).

Open up Sublime Text 3, and then open up Mavens Mate on your machine. There should be a Mavens Mate icon, at the top bar of your screen. Click it and then click "Plugins".

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-1.png)

On the next window, click "Install Plugin". This installs the Mavens Mate plugin into Sublime Text 3.

Close and reopen Sublime Text 3.

Click Mavens Mate > Settings > User at the top Sublime Text 3 Toolbar.

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-2.png)

This will open a file called `mavensmate.sublime-settings`. Paste the following in that file. Adjust to the path and directory you want to store your salesforce code in.

```json
{
  "mm_workspace": "/Users/scottmotte/code/salesforce"
}
```

Save and close that file.

### Create a project

With Sublime Text 3 still open, click Mavens Mate > Project > New Project.

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-3.png)

On the next screen enter the following:

* For project name: name it something you'd like
* For username: enter your email address
* For password: enter your password APPENDED with your salesforce security token. (see above for how to generate the security token) 
* Click the Advanced tab and unselect everything except ApexClass and CustomObject.

When you're ready click the 'Create Project' button.

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-5.png)
![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-6.png)

This will create the project up on Salesforce.com and locally on your machine. That's what we want. It's the way salesforce development works. Now when we develop locally it will sync things up remotely. Yeah, it's strange. I feel bad for Salesforce developers. 

### Create a class

With Sublime Text 3 still open, click "Mavens Mate > Metadata > New Apex Class". Then from the popup click "Default". Finally, name your class "HelloWorld".

Edit that file to look like the following.

```java
global class HelloWorld {
  public String hello() {
    return 'Hello World!';
  }
}
```

### Create a test class

Next, click "Mavens Mate > Metadata > New Apex Class". Then from the popup click "Unit Test". Finally, name this class "HelloWorldTest".

Edit that file to look like the following.

```java
@isTest
private class HelloWorldTest {
  @isTest static void hello() {
    HelloWorld hello_world = new HelloWorld();
    String result = hello_world.hello();

    system.assertEquals(result, 'Hello World!');
  }
}
```

Let's run this test.

Click "Mavens Mate > Unit Testing > Open Apex Test Runner UI".

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-7.png)

On the next screen, make sure the HelloWorldTest is selected and click the Run Tests button.

![](https://raw.githubusercontent.com/scottmotte/apex-hello-world/master/apex-hello-world-8.png)

### You're done

Congrats, you wrote your first Apex hello world code! 

![](http://media.giphy.com/media/haOPSTE9rVqlW/giphy.gif)

It was much more difficult than most languages, but we got through it. If you can avoid it, don't become a salesforce developer. Learn [Go](http://golang.org/), [Ruby](https://www.ruby-lang.org) or [NodeJS](http://nodejs.org/). You will be even [happier](http://media.giphy.com/media/iFmxR5QdkEQKI/giphy.gif).

