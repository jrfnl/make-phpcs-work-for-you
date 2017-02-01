# Logging PHPCS results

PHPCS offers a number of different report formats. These can be echo-ed out to the screen or writing to a file.

Especially with repositories with lots of infractions, a log file might be easier to read & navigate.
For information on the different report formats and writing reports to a file, see the [PHPCS wiki](https://github.com/squizlabs/PHP_CodeSniffer/wiki/Reporting).

### Setting up logging in your ruleset

What the wiki does not tell you is that you can also set the logging up in your ruleset file.

To generate, for example, a summary report on the screen and write a full report to a log file, you could add the following to your ruleset file:
```xml
	<arg name="report" value="summary" />
	<arg name="report-full" value="./logs/phpcs.txt"/>
```

### Working with a standard log file directory

You can add a `logs` directory to your repository to store these log files, but you normally wouldn't want to commit these.
To prevent this, add a `.gitignore` file to the root of your repository and add the following on a line by itself to it:
```
logs/*
```


Also see: [Using the XSL template](https://github.com/jrfnl/make-phpcs-work-for-you/tree/master/xsl-template)
