### Getting notifications

spring.io and certain key legacy web properties such as www.springframework.org/schema are monitored by Pingdom and will send alerts after 3 consecutive minutes of downtime.

Alerts are sent:

 - via email and iOS for configured users
 - to the Sagan HipChat room


### When an outage occurs

 - Post a message in the Sagan HipChat room that lets folks know you're aware of the problem and looking into it. Specifically @-mention any other admins you know may be on duty (especially those that may be getting woken up).
 - Notice whether other spring.io properties, e.g. redirect.spring.io are down as well
if multiple properties are down, this may indicate a problem with run.pivotal.io itself. See "Contacting the CF team" below.
 - Verify that the site is actually down:
```
curl -I http://spring.io    # 404? 200?
```
 - If the outage was significant in length, post a message from the [@SpringOps](http://twitter.com/SpringOps) account letting folks know we're back up after a bit of downtime.


### Contacting the CF team

If you have reason to believe that there is an underlying issue with run.pivotal.io, you can contact the CF team:

 - via HipChat in the "Cloud Foundry backend" room
 - via the Cloud Foundry Project Management mailing list (ask Trevor for address).