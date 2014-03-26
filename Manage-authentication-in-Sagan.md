### Goal

Customize the authentication configuration in your Sagan app, to access the admin UI and Spring Boot's actuator endpoints. 

### Background

Sagan has an admin web interface (to manage team members, projects, blog posts...) and exposes [Spring Boot Actuator Endpoints](https://github.com/spring-projects/spring-boot/blob/master/spring-boot-docs/src/main/asciidoc/production-ready-features.adoc#endpoints).

Both features can require customization when running Sagan for your own team!

### Prerequisites

1. You must be able to [[run the site locally]] or [[run the site on Cloud Foundry]].
2. You must be a member of an existing team in a [GitHub organization](https://help.github.com/categories/2/articles), or [create an organization](https://help.github.com/articles/creating-a-new-organization-account--2) and [add team members](https://help.github.com/articles/adding-organization-members-to-a-team).


### Steps

> _**Note:** We've taken great care of not having sensitive information in checked-in configuration files. So don't write sensitive information in your fork of the project!_

#### Change the admin password for Actuator Endpoints

As mentioned in [Spring Boot's documentation](https://github.com/spring-projects/spring-boot/blob/master/spring-boot-docs/src/main/asciidoc/production-ready-features.adoc#exposing-sensitive-endpoints), sensitive endpoints are protected by authentication; and unless configured specifically, a default password is generated at startup.

Since we're deploying to several Cloud Foundry instances, Sagan is defining an application-wide password in `application.yml`:

    security:
      user:
        password: ${ADMIN_PASSWORD:} 

You can change that password when running Sagan locally (along with other overrides):

    $ ADMIN_PASSWORD=carlsagan ./gradlew :sagan-site:bootRun

Or udpate your Cloud Foundry environment variables:

    $ cf set-env sagan ADMIN_PASSWORD carlsagan
    $ cf restart sagan

Once done, [Endpoints](https://github.com/spring-projects/spring-boot/blob/master/spring-boot-docs/src/main/asciidoc/production-ready-features.adoc#endpoints) such as <http://yourname-sagan.cfapps.io/env> will be made available with the configured credentials: e.g. login `user` and password `carlsagan`.

#### Configure the GitHub organization in Sagan

First, you need to register a new application with your organization: <https://github.com/organizations/yourorg/settings/applications/new>

For a Sagan app hosted on `http://yourname-sagan.cfapps.io`, you should have:

    Application name: Sagan admin
    Homepage URL: http://yourname-sagan.cfapps.io
    Authorization callback URL: https://yourname-sagan.cfapps.io

Once configured, you should find at the top right of the page:

    Client ID: cafed00d
    Client Secret: deadbeef8badf00d

For now, you also need to know the ID of the GitHub you want to configure - see issue [#325](https://github.com/spring-io/sagan/issues/325) for more details on how to get this ID.

Now, you can use all those informations to [[run the site locally]]:

    $ GITHUB_CLIENT_ID=cafed00d GITHUB_CLIENT_SECRET=deadbeef8badf00d GITHUB_TEAM_ID=1234 ./gradlew sagan-site:bootRun

Or [[run the site on Cloud Foundry]]:

    $ cf set-env sagan GITHUB_CLIENT_ID cafed00d 
    $ cf set-env sagan GITHUB_CLIENT_SECRET=deadbeef8badf00d
    $ cf set-env sagan GITHUB_TEAM_ID=1234
    $ cf restart $APP_NAME
