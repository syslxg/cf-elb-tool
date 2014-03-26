cf-elb-tool
===========

Install
-------

1. run `bundle install`
1. set up AWS credentials in environment varibles

    ```
    export BOSH_AWS_ACCESS_KEY_ID=KKK
    export BOSH_AWS_SECRET_ACCESS_KEY=SSS
    ```


Backup
------
1. bundle exec ./cf-elb-tool backup [elbs.yml]

Restore
-------

1. bundle exec . /cf-elb-tool restore elbs.yml

