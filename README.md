# Coturn AWS cloudformation

Simple AWS Cloudformation template that deployes a coturn server and adds basic configuration.

The EC2 instance that is being deploy is being assigned with a Elastic Static IP (EIP) that helps with the configuration. You should already have a hosted zone configured.

## Coturn configuration
This is the coturn configuration that is being created:

**/etc/default/coturn**
TURNSERVER_ENABLED=1

**/etc/turnserver.conf**
external-ip={aws_public_ip}
fingerprint
user={turn_user}:{turn_password}
lt-cred-mech
realm=realm
simple-log