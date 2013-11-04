### Goal

Download HTTP access logs for the Sagan site application.

### Prerequisites

1. [[Run the site on Cloud Foundry]]

### Steps

    $ cf file sagan app/logs/access_log.YYYY-MM-DD.log > sagan-access.log

where `YYYY-MM-DD` is a date between now and the time the application was started.

Note you may also browse for available files with

    $ cf files sagan app/logs

