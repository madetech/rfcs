# Server naming convention

## Summary

Have servers named in a consistent, descriptive and therefore helpful-at-a-glance way.

## Problem

We have no consistency when it comes to naming servers as we have no agreed convention to follow. This makes it difficult to quickly identify details about a server and resolve issues.

## Proposal

At a glance from the server name we would like to be able to identify:

 1. Customer
 2. Hosting provider
 3. Server location
 4. Environment
 5. Optional: Blue/Green if used
 6. Count/index of server
 7. Application/role

### Proposed format

```
<app><count>-(blue|green)-<env>-<location>-<provider>-<customer>
```

**Note:** We use hyphens rather than periods so that wildcard SSL certificates can be used if needed.

### Breakdown of format

 * `env`: `prod`, `stag`, `test`, `cont`
 * `location`: `ire`, `lon`, `euw1`, `usw1`
 * `provider`: `aws`, `rsp`
 * `customer`: support short codes, so; `khc`, `sparqa`, `dints`, `diners`, `akzo` etc
 * `count`: incremental, or `1` if a solo server for a particular application.
 * `app`: can be as descriptive as possible, with no additional hyphens

### Examples

```
middleware1-blue-prod-ire-aws-khc
middleware1-green-prod-ire-aws-khc
presentation1-blue-prod-ire-aws-khc
middleware1-blue-stag-ire-aws-khc
middleware1-test-ire-aws-khc

postcodeservice1-prod-lon-rsp-akzo
checkoutbeige1-prod-lon-rsp-akzo
ecomapi1-cont-lon-rsp-akzo

portal1-prod-ire-aws-diners
portal1-test-lon-aws-diners
```
