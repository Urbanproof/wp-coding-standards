# WordPress coding standards by Urbanproof

## Installation
1. Add this repository into composer.json;
    ```json
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/Urbanproof/wp-coding-standards.git"
        }
    ],
    ```
2. Set stability requirements (necessary beacuse of the roave/security-advisories-package):
    ```json
    "minimum-stability": "dev",
    "prefer-stable": true,
    ```
3. Require the package: `composer require --dev urbanproof/wp-coding-standards`

## Minimal configuration
This is a configuration file for the PHPCS. Create `phpcs.xml`- file into your project root directory, and add following lines:
```xml
<?xml version="1.0"?>
<ruleset name="PHPCS Configuration">
    <rule ref="UWPCS"/>
</ruleset>
```

## Recommended configuration
Extending the ruleset is higly recommended, as it is very hard to predict exact loactions, text domains etc, so this ruleset comes without them.
```xml
<?xml version="1.0"?>
<ruleset name="PHPCS Configuration">
    <file>singular-php-file.php</file>
    <file>or-a-directory/</file>
    <rule ref="UWPCS"/>
    <rule ref="WordPress.WP.I18n">
        <properties>
            <property name="text_domain" type="array" value="your-text-domain-here" />
        </properties>
    </rule>
</ruleset>
```

## Usage
- Run automatically before each commit with my [PHPCS-pre-commit git-hook](https://github.com/Urbanproof/phpcs-pre-commit)
- Run from command line; `vendor/bin/phpcs`
- Integrate into your IDE
    - Tested only with VS Code using [this phpcs extension](https://marketplace.visualstudio.com/items?itemName=ikappas.phpcs)
    - Note that you might have to restart your IDE before PHPCS is detected

## Troubleshooting
- IDE complains that it cannot detect PHPCS
    - It happens, try restarting your IDE
- Feel free to submit an issue
