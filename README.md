# AppFog PHP Jumpstart

## Introduction

The AppFog PHP Jumpstart is a sample application that can be used to get started quickly with a new PHP web application on AppFog.

## Getting Started
### Building the app and pushing to AppFog

To get started, copy the contents of this repo to a new source code repository that you have edit privileges to. Clone that repository and [login to AppFog](https://www.centurylinkcloud.com/knowledge-base/appfog/login-using-cf-cli/). To deploy the application, run the following from the top-level project directory:

```
$ cf push
```

Since the manifest.yml file sets the name of the application to `${random-word}`, the name of the application will be generated during the deployment process. Here is example output of the application deployment using `cf push`:

```
cf push
Using manifest file /Users/demo/php/manifest.yml

Creating app ungoverned-underpilaster in org Demo / space dev as Demouser...
OK

Creating route ungoverned-underpilaster.cfapps.io...
OK

Binding ungoverned-underpilaster.cfapps.io to ungoverned-underpilaster...
OK

Uploading ungoverned-underpilaster...
Uploading app files from: /Users/demo/php
Uploading 28.3K, 5 files
Done uploading
OK

Starting app ungoverned-underpilaster in org DEMO / space dev as Demouser...
-----> Downloaded app package (12K)
-------> Buildpack version 3.2.2
Installing HTTPD
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_unixd-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_setenvif-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_proxy-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_dir-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_reqtimeout-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_log_config-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_authz_core-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_mime-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_proxy_fcgi-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_remoteip-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_env-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_mpm_event-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_rewrite-2.4.12.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/httpd/2.4.12/httpd-mod_authz_host-2.4.12.tar.gz] to [/tmp]
Installing PHP
PHP 5.5.25
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-5.5.25.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-fpm-5.5.25.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-mcrypt-5.5.25.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-curl-5.5.25.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-zlib-5.5.25.tar.gz] to [/tmp]
Downloaded [https://pivotal-buildpacks.s3.amazonaws.com/php/binaries/trusty/php/5.5.25/php-bz2-5.5.25.tar.gz] to [/tmp]
Finished: [2015-06-16 20:14:11.897684]

-----> Uploading droplet (16M)

1 of 1 instances running

App started


OK

App ungoverned-underpilaster was started using this command `$HOME/.bp/bin/start`

Showing health and status for app ungoverned-underpilaster in org DEMO / space dev as Demouser...
OK

requested state: started
instances: 1/1
usage: 256M x 1 instances
urls: ungoverned-underpilaster.cfapps.io
last uploaded: Tue Jun 16 20:13:59 UTC 2015
stack: cflinuxfs2

     state     since                    cpu    memory          disk          details
#0   running   2015-06-16 05:14:21 PM   0.4%   28.2M of 256M   37.9M of 1G      

```

Once the application is running, copy the value for `urls:`, in the case above `ascitic-flavopurpurin.useast.appfog.ctl.io`, and go to that URL in a browser. You should see a page that looks like:

<img src="https://raw.githubusercontent.com/CenturyLinkCloud/af-static-jumpstart/master/images/welcome-to-appfog-screenshot.png"/>

## Customizing the app

### Knowing where the code is

* Web page: `public/index.html`.
* Application Controller: `index.php`.

### Deploying PHP apps to AppFog

A very useful read is [here](https://www.centurylinkcloud.com/knowledge-base/appfog/deploy-an-application/). This will give you an overview of the general process used to deploy PHP applications to AppFog.

### Moving forward

As a start point, you can modify the file `index.php` as needed.

There is a lot of information and tutorials on the internet to learn PHP. The place to start is [here](http://php.net/manual/en/tutorial.php).

The complete manual for the language is [here](http://php.net/manual/en/index.php)
