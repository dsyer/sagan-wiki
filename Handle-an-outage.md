### Getting notifications

spring.io and certain key legacy web properties such as www.springframework.org/schema are monitored by Pingdom and will send alerts after 3 consecutive minutes of downtime.

Alerts are sent:

 - via email, iOS or Twitter for configured users
 - to the Sagan Slack room


### When an outage occurs

 - Post a message in the Sagan Slack room that lets folks know you're aware of the problem and looking into it. Specifically @-mention any other admins you know may be on duty (especially those that may be getting woken up).
 - Notice whether other spring.io properties, e.g. redirect.spring.io are down as well
if multiple properties are down, this may indicate a problem with run.pivotal.io itself. See "Contacting the CF team" below.
 - Verify that the site is actually down:
```
curl -I http://spring.io    # 404? 200?
```
 - Verify [CloudFlare's status](https://www.cloudflarestatus.com/) since some outages can be caused by our CDN
 - If the outage was significant in length, post a message from the [@SpringOps](http://twitter.com/SpringOps) account letting folks know we're back up after a bit of downtime.

