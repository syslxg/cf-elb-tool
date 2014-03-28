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
1. Run `bundle exec ./cf-elb-tool backup [elbs.yml]`
2. Edit the yml file, add dns_record, domain and ttl

    ```
    ---
    elbs:
      cfrouter:
        subnets:
    ...
        listeners:
        - load_balancer_port: 80
          protocol: http
          instance_port: 80
          instance_protocol: http
        - load_balancer_port: 443
          protocol: https
          instance_port: 80
          instance_protocol: http
          ssl_certificate_id: arn:aws:iam::713204667821:server-certificate/cfrouter_cert
        dns_record: '*'
        domain: garyliu.cf-app.com
        ttl: 3600
    ```

Restore
-------

1. bundle exec . /cf-elb-tool restore elbs.yml

