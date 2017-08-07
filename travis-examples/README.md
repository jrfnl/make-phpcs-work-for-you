# Example Travis setups

It is good practice to run PHPCS against commits and PRs for your repository as part of an effort to keep your code compliant.

In this folder you will find two example travis scripts showing you how to do this.

### Running PHPCS only once per build

Standards build for PHPCS are generally created to give the same results independently of the PHP version used, though some checks may be skipped on low PHP versions (PHP < 5.6) for some standards.
The standards are also tested against various PHP versions.

It is therefore good practice to only run PHPCS once per build against a relatively high PHP version as the results across versions would be the same anyway.

Both examples have this mechanism build in.

### Don't ignore warnings

I often see people by default ignoring warnings thrown by PHPCS by setting the `-n` flag on the command line or in a custom ruleset, just to prevent their QA builds failing on these.

This is not a good idea. Adding the flag to a custom ruleset is an especially bad idea, as that way developers won't see warnings in their own runs/IDE either.

Much better is to use `--runtime-set ignore_warnings_on_exit 1` in the PHPCS command and only for the Travis script.
This setting will allow warnings to be reported, but it won't fail the build on it.


### Linting your code

It is also good practice to run your code through PHP lint for every PHP version you support, so that little snippet is included in both scripts.

