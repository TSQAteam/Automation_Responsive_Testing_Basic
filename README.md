# Automation_Responsive_Testing_Basic
Automation Responsive Testing  (Galen Framework)

**Introduction:**

Galen is a test framework originally designed for testing layout of web applications, When it comes to testing a responsive layout it works in a following way:
*Open a page in browser
*Resize it to specified size
*Test the layout according to user-defined specs

Once it sees that something is wrong – Galen reports the error, makes a screenshot and highlights the misbehaving element on it.

**Installing galen:**

We can install on Install on OS X and Linux.
At the moment there is no installer for Windows. In order to make galen.bat script accessible in your command line you need to manually add it to your Path variable.

**Adding config file:**

Galen allows to configure each project separately. You just need to create a galen.config file in your test project directory or you can run this command and Galen will create a config file.


**Configuring Browsers:**

By default Galen uses Firefox browser (Now it supports Firefox version 46) but you can configure it to use any other browser in case it is not explicitly declared in your test suite. You can do it using this property in your config file.
Supported browsers: firefox, chrome, ie, phantomjs, edge

**Running Galen :**

**Steps which I followed to create simple sample test for single responsive run test:**

Create an empty folder with your test project name(tutorial) and in it create a file(homepage.gspec)

Galen allows to configure each project separately. You just need to create a galen.config file in your test project directory
Added config file for a added project.

Create a file “homepage.gspec” for user defined spec.

In order for galen to be able to communicate with browser we need to get a special driver for it. For Firefox you will need a geckodriver. For Chrome - chromedriver. Download a driver for whatever browser you have and extract it somewhere on your file system. 
Now you need to define path for that driver in your global config.

Downloaded geckodriver added the path in config file which is used for Firefox browser

Now I have worked out for the test site http://testapp.galenframework.com/

Tested for the responsive size of 360x640 and checked the spacing between the logo and header in site with respect to user spec
             

Galen has specific syntax for  to express exactly how you want your website to behave on different devices. There are two main parts in page specs file: object definitions and object specs. For every section we have to define syntax in a page.

Each Galen spec file normally starts with object definition. It is the place where you give names to page objects and also define the so called locators - the way for Galen to find element on test page. The available locators are:
id - searches for object by id in DOM
css - uses CSS selectors to find objects
xpath - uses XPath expressions

**1. Test case - Failed**

Create an object by inspecting element and use CSS selector that allows me to fetch the element from the page.


In homepage.gspec file. Here I have given the header logo  as 3px left of header text . (But the correct value is 22 px). 

To perform a single page test you can use the command "check".
Now run the test in command prompt using
galen check homepage.gspec --url http://testapp.galenframework.com/ --size 360x640 --htmlreport reports

Now when we can view the reports screen in browser

**2. Test case - Passed**

In homepage.gspec file.  Here I have given the header logo  displays between 3 to 25px  left of header text 

Now run the same test in command prompt using
galen check homepage.gspec --url http://testapp.galenframework.com/ --size 360x640 --htmlreport reports

Now when we can view the reports screen in browser


***Note :**

Now I have workout and checked for basic run of single section in a page and run for a single responsive size at a time.
Other workouts with Test Suites in Galen Framework are inprogress.
More galen Specs Language – learning is in progress

**Reference links:**

http://galenframework.com/docs/reference-galen-spec-language-guide/

http://galenframework.com/docs/reference-galen-test-suite-syntax/

http://galenframework.com/docs/tutorial-first-project/
