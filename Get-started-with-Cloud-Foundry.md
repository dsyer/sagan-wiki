### Goal

Get a Cloud Foundry account and set up CLI tools.

### Prerequisites

 - *None*

### Create a Cloud Foundry account

Go to https://run.pivotal.io/ and click on "sign up for free" for a new account if you don't already have one. 

This will add you to the waiting list for new accounts. You can bypass this list with an invitation code.

### Install CLI tools

Go to https://console.run.pivotal.io/tools and install the CLI tools for your platform.

The getting started steps will help you to set up those tools with your account.

```
$ cf help
$ cf login -a https://api.run.pivotal.io
  API endpoint: https://api.run.pivotal.io
  Username> your_username
  Password> your_password
  Org> your_org
  Space> your_space
```

Additional information is available [in the cf documentation](http://docs.run.pivotal.io/devguide/installcf/whats-new-v6.html)

### Next steps

Return to [[run the site on Cloud Foundry]].
