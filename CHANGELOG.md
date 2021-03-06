# 3.5.0 / 2017-07-13

## Enhancements

* Systemd support for authoritative

## Maintenance

* Improving documentation for backends for an edge case that break chef.

# 3.4.1 / 2017-06-29

## Bug Fixes

* Stopping the default recursor on `pdns_recursor_service` for sysvinit.
  Fixes: https://github.com/dnsimple/chef-pdns/issues/77

## Maintenance

* Removing DB schema from files/ directory

# 3.4.0 / 2017-06-27

## Maintenance

* Split the rake file into differents pieces
* Add concurrency for kitchen tests.

# 3.3.2 / 2017-06-20

## Bug Fixes

* Recursor init script should create pid directory on start if it does not exist.

# 3.3.1 / 2017-06-20

## Bug Fixes

* Fixing MySQL package name for debian

# 3.3.0 / 2017-06-14

## Enhancements

* Recursor latest version 4.0.5
* Updated README

## Bug Fixes

* Correcting naming conventions on init scripts that were not following PowerDNS considerations for virtual hosting.
* Fixing tests

# 3.2.0 / 2017-06-02

## Enhancements

* Added systemd support for recursors

## Bug Fixes

* Stop and Disable the service 'pdns-recursor' as soon as new instance
is created

# 3.1.0 / 2017-06-01

## Enhancements

* Expanding ChefSpec matchers

# 3.0.0 / 2017-05-29

## Enhancements

* Complete rewrite of the cookbook 
* Using official PowerDNS apt repositories
* Using Chef 12.5+ resources to create PowerDNS installs and settings for recursors and authoritatives.
* ChefSpec and Inspec Tests
* Centos 6, 7 Support
* Ubuntu 14.04, 16.04 Support
* Debian 8 support

# 2.5.0 / 2017-02-08

## Maintenance

* Updating to latest pdns 3.4.11
* Updating to latest recursor 3.7.4

## Bug fixes

* Adding libssl-dev as dependency for source installs

# 2.4.1 / 2016-14-09

## Bug Fixes
* Update download link to correct one for 3.4.10

# 2.4.0 / 2016-13-09

## Enhancements

* Add partial support for CentOS/REHL (recursor) PR #36

# 2.3.0 / 2016-09-09

## Warning
* In PowerDNS 3.4.10 the default for any-to-tcp has been changed to 'yes'
  * https://doc.powerdns.com/3/authoritative/upgrading/#3xx-to-3410

## Bug fixes

* Update authoritative to 3.4.10 to fix PowerDNS Security Advisory 2016-01
  * https://doc.powerdns.com/md/security/powerdns-advisory-2016-01/
  * Crafted queries can cause unexpected backend load
* update source_url and issues_url

## Enhancements

* Add a new Rakefile for testing
* Clean up docs a little

# 2.2.1 / 2016-03-03

## Bug Fixes

* Resolved an issue where pdns install would run over and over again due
  to a bad path.

# 2.2.0 / 2016-03-03

## Enhancements

* We have eliminated the node attributes from the attributes folder to make
  this cookbook more wrapper pattern friendly. Remember kids, don't put node
  attributes in your attributes folder, everyone will have a bad time. :(

## Cleanup

* Added some basic rubocop rules that we're starting to use with DNSimple
  cookbook. Nothing intense, but should help get things looking spiffy :+1:
* Made sure to comply with foodcritic, the ultimate yelp reviewer of the
  Chef Supermarket.

# 2.1.1 / 2016-03-03

## Bug Fixes

* Renamed some ambiguous variables that might be causing a bug in certain
  circumstances.

## Cleanup

* Updated some copyrights and trimmed a bunch of whitespace

# 2.1.0 / 2016-11-01

### Enhancements

* Added bind as backend option and made it default

### Cleanup

* Some spelling mistakes in the README were corrected

# 2.0.0 / 2015-12-23

### Enhancements

* Adds the capability of installing a recursor from source
* Adds the capability of installing a recursor with pipe backend (source and package install).
* Updating documentation.

### Cleanup

* Major code refactor

### Breaking changes

* Resolver no longer uses a separated template for configuration and it uses the same
  attribute (flavor) to decide the functionality, so it is not possible to install a
  resolver and an authoritative on the same machine anymore.
* Only authoritative servers install or compile backends now.

# 1.1.1 / 2015-12-23

### Enhancements

* Creating schema, grants and users for postgres backend.

### Bug Fixes

* Handling the URL for downloading the source gracefully using lazy evaluation
 since this provoked a malformed URL string when concatenated with the version
 on source recipe.

# 1.1.0 / 2015-12-10

### Enhancements

* Recursor is now the default behavior
* Using bind as a default backend per recommendation on irc channel
* Adding a new slave PowerDNS server configuration
* Refactor of authoritative part
* Refactor of build related code
* Expanded documentation

# 1.0.5 / 2015-11-10

## Security

* Updating to 3.4.7 addressing PowerDNS Security Advisory 2015-03.
More information about this CVE can be found here:
http://www.openwall.com/lists/oss-security/2015/11/09/3

# 1.0.4 / 2015-09-02

## Security

* Updating to 3.4.6 addressing PowerDNS Security Advisory 2015-02.
More information about this CVE can be found here:
http://www.openwall.com/lists/oss-security/2015/09/02/5

# 1.0.3 / 2015-05-04

### Bug Fixes

* Executing bootstrap command on every pdns compilation run

# 1.0.2 / 2015-05-04

### Security

* Updating to version 3.4.4 of authoritative powerdns server in order to address
  PowerDNS Security Advisory 2015-01: Label decompression bug can cause crashes
  or CPU spikes.

### Bug Fixes

* Allowing pdns_server to automatically upgrade in source installs

# 1.0.1 / 2014-12-17

### Bug Fixes

* Adding missing configuration bits for authoritative_package recipe

# 1.0.0 / 2014-12-15

### Breaking Changes

* There have been major changes to the recipes and attributes of this
  cookbook in the first of many efforts to stabilize and modernize everything.
  Please review the updated README and take special note of the install type
  and backend attributes to suit your configuration.

* We plan to eventually migrate the recipes over to LWRP's to make this
  cookbook easier to wrap and extend.

# 0.3.4 / 2014-07-15

### Testing

* Testing Updates

### Bug Fixes

* Fixed missing build-essential include

# 0.3.3 / 2014-07-15

### Bug Fixes

* Not actually sure what happened here

# 0.3.2 / 2014-07-14

### Bug Fixes

* Remove incorrect search domains

# 0.3.0 / 2014-02-21

### Bug Fixes

* DNS should install the sqlite gem (needs build-essentials) and use the correct pdns template filename [COOK-978]

# 0.2.0 / 2013-08-28

### Improvements

* Add source recipe [COOK-3106]

# 0.1.2 / 2013-05-07

### Bug Fixes

* pdns cookbook has foodcritic failures [COOK-2986]

### Improvements

* Configure a PowerDNS server [COOK-2604]

# 0.1.0

### Initial Release

- Fixes for centos/rhel boxen and pdns::recursor cookbook [COOK-1080]
