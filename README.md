# Expire CloudFront

This module is an [Cache Expiration](https://www.drupal.org/project/expire) plugin for AWS CloudWatch.
  
## Installation

This module requires you to have the AWS SDK loaded in your classpath.

The recommended approach is to have a composer file in your project root, and run:

```
composer require aws/aws-sdk-php:~3.0
```

In order to have composers autoloader available to Drupal, add the following line to settings.php

```
require_once DRUPAL_ROOT . '/../vendor/autoload.php';
```

The above assumes Drupal is installed into a sub-directory of your project root, and  `/vendor`
lives in the project root.

## Configuration

You need to provide a CloudFront Distribution ID. The simplest way is to add the following to settings.php:

```
$conf['expire_cloudfront_distribution_id'] = 'MY_DISTRIBUTION_ID';
```

## AWS Authentication

This module does not require setting AWS access keys, and assumes you are following best practices and 
following the SDK Guide on [Credentials](http://docs.aws.amazon.com/aws-sdk-php/v3/guide/guide/credentials.html)

This means, either using:

- IAM Roles
- Exporting credentials using environment variables
- Using a profile in a ~/.aws/credentials file
