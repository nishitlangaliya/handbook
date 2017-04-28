# wp scaffold theme-tests

<small>Quick links: <a href="https://github.com/issues?q=is%3Aopen+label%3Acommand%3Ascaffold-theme-tests+sort%3Aupdated-desc+org%3Awp-cli">Github issues</a></small>

Generate files needed for running PHPUnit tests in a theme.

The following files are generated by default:

* `phpunit.xml.dist` is the configuration file for PHPUnit.
* `.travis.yml` is the configuration file for Travis CI. Use `--ci=&lt;provider&gt;` to select a different service.
* `bin/install-wp-tests.sh` configures the WordPress test suite and a test database.
* `tests/bootstrap.php` is the file that makes the current theme active when running the test suite.
* `tests/test-sample.php` is a sample file containing the actual tests.
* `phpcs.ruleset.xml` is a collenction of PHP_CodeSniffer rules.

Learn more from the [plugin unit tests documentation](http://wp-cli.org/docs/plugin-unit-tests/).

### ENVIRONMENT

The `tests/bootstrap.php` file looks for the WP_TESTS_DIR environment
variable.

### OPTIONS

[&lt;theme&gt;]
: The name of the theme to generate test files for.

[\--dir=&lt;dirname&gt;]
: Generate test files for a non-standard theme path. If no theme slug is specified, the directory name is used.

[\--ci=&lt;provider&gt;]
: Choose a configuration file for a continuous integration provider.
\---
default: travis
options:
  - travis
  - circle
  - gitlab
\---

[\--force]
: Overwrite files that already exist.

### EXAMPLES

    # Generate unit test files for theme 'twentysixteenchild'.
    $ wp scaffold theme-tests twentysixteenchild
    Success: Created test files.


