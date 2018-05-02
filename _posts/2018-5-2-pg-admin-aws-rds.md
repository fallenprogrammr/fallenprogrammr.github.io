---
layout: post
title: pg admin aws rds connectivity issue
---

If you create a postgresql database in Amazon RDS, are getting a timeout connecting via pgAdmin.

If the [troubleshooting](https://docs.aws.amazon.com/AmazonRDS/latest/UserGuide/CHAP_GettingStarted.CreatingConnecting.PostgreSQL.html) steps haven't helped you.

On the aws rds dashboard, click on the security group for the postgres instance: 
{: .center}
![_config.yml]({{ site.baseurl }}/images/security-groups.png)

Note that there will be a single rule created by default

The default source for the inbound connection is set to the ip address of the machine that was used to create the postgres instance (I am assuming that this should apply to other databases as well).

Edit the rule
{: .center}
![_config.yml]({{ site.baseurl }}/images/security-group-inbound-rule.png)

Set the source set to Anywhere.
{: .center}
![_config.yml]({{ site.baseurl }}/images/inbound-rule-set.png)

Save the changes and this should resolve the connectivity issue.