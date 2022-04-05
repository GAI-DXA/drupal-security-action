# Drupal Security Github Action


## Usage

With composer.json and composer.lock in the current working directory:

```
jobs:
  check-security:
    ...
    - uses: GAI-DXA/drupal-security-action@1.0.0
```

With composer.json and composer.lock elsewhere, specify the path to the directory which contains those files:

```
jobs:
  check-security:
    ...
    - uses: GAI-DXA/drupal-security-action@1.0.0
      working-directory: /path/to/composer/files
```

If you need to whitelist a security package due to false positives (or you just want to ignore this *youshouldneverignoresecuritywarnings*), add a comma-separated list of package names and version pairings:

```
jobs:
  check-security:
    ...
    - uses: GAI-DXA/drupal-security-action@1.0.0
      with:
        allowed: 'drupal/group:1.0.0-rc5,drupal/false_positive:5.2.0'
```