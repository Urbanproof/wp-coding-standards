# WordPress coding standards by Urbanproof

## Installation
1. Add this repository into composer.json;
    ```json
    "repositories": [
        {
            "type": "vcs",
            "url": "https://github.com/Urbanproof/wp-coding-standards.git"
        },
    ]
    ```
2. Require the package: `composer require --dev urbanproof/wp-coding-standards`

## Recommended - extend the ruleset
I also recommend extending it, specifying couple of things, mainly text domain, and files to scan.
1. Create `phpcs.xml`- file into your project root directory
2. Add following lines:
    ```xml
    <?xml version="1.0"?>
    <ruleset name="Yournamehere">
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
