## debian-12-letsencrypt

[![CI](https://github.com/nlware/ansible-debian-12-letsencrypt/workflows/CI/badge.svg)](https://github.com/nlware/ansible-debian-12-letsencrypt/actions?query=workflow%3ACI)

Set up Let's Encrypt on Debian 12.

#### Variables

* `debian_12_letsencrypt_admin_email`: [optional]: Email used for registration and recovery contact.

* `debian_12_letsencrypt_certificates_present`: [default: `[]`]: List of the certificates to create
* `debian_12_letsencrypt_certificates_present.{n}.name`: [optional, default: `domains.0`]: The name of the certificate, defaults to the first domain given in `domains`
* `debian_12_letsencrypt_certificates_present.{n}.domains`: [required]: List of the domains

* `debian_12_letsencrypt_certificates_absent`: [default: `[]`]: List of the certificates to remove
* `debian_12_letsencrypt_certificates_absent.{n}.name`: [optional, default: `domains.0`]: The name of the certificate, required when `domains` is empty, defaults to the first domain given in `domains`
* `debian_12_letsencrypt_certificates_absent.{n}.domains`: [optional]: List of the domains

* `debian_12_letsencrypt_authenticator`: [default: `standalone`]: Authenticator to use
* `debian_12_letsencrypt_http_01_port`: [optional]: Port used in the http-01 challenge.
* `debian_12_letsencrypt_http_01_address`: [optional]: The address the server listens to during http-01 challenge.

* `debian_12_letsencrypt_acme_challenge_forward_host`: [optional]: Host to forward acme challenges to, when not found on the current host

* `debian_12_letsencrypt_webroot_path`: [default: `/var/lib/certbot/http_challenges`]: The path to the public_html / webroot folder being served by your web server.
* `debian_12_letsencrypt_webroot_webserver`: [optional] : Webserver to create configuration for, supported values `apache` and `nginx`

* `debian_12_letsencrypt_deploy_hook`: [optional]: Command to be run in a shell once for each successfully issued certificate.
