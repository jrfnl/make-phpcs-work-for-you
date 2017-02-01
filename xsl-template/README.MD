# Using the XSL template

This XSL template has been setup to work with the PHPCS checkstyle report.

You will need to instruct PHPCS to write the report to a file to be able to use this template.

You can do this in two ways:

**From the command-line**:
```
phpcs . -standard=PSR2 --report-checkstyle=./xsl-template/phpcs-checkstyle.xml
```

**By adding the following to your custom ruleset**:
```xml
<arg name="report-checkstyle" value="./xsl-template/phpcs-checkstyle.xml"/>
```
   
Of course, you can customize the path and file name of the log file to your liking.
If you do change the path/file name, you'll also need to change this in the `phpcs_results.html` file (line 36).

Once you've run PHPCS over your code and generated your first log file, open the `phpcs_results.html` file in the browser to see the results displayed in an easily navigatable and user-friendly interface.

![screenshot](https://github.com/jrfnl/make-phpcs-work-for-you/blob/master/xsl-template/screenshot.png)

### FAQ

If you see a blank screen, that means you haven't created an initial log file yet.
