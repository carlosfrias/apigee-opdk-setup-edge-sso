Apigee OPDK Setup Edge SSO
=========

This role will setup the SSO component of the Apigee Edge platform. This is used to interface with an on premise IDP. 

Requirements
------------

This role requires elevated priviledge to install OpenSSL.  

Role Variables
--------------

| Variable Name | Description |
| --- | --- |
| edge_sso_installation_config_filename | edge-sso-installer-config.conf |
| edge_sso_installation_config_file | "{{ opdk_installer_path }}/{{ edge_sso_installation_config_filename }}" |
| verification_private_key | private_key.pem |
| signing_public_key | public_key.pem |
| saml_private_server_key | server.key |
| saml_private_encryption_type | aes256 |
| saml_private_key_size | 1024 |
| saml_self_key_size | 2048 |
| saml_cert_signing_request | server.csr |
| saml_cert_self_signed | server.crt |
| saml_cert_encryption_type | sha256 |
| saml_cert_expiry_days | 365 |
| saml_cert_subject | "/C=US/O=google/OU=apigee/CN=apigee.com" |

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: apigee-opdk-setup-edge-sso }

License
-------

Apache 2.0

Author Information
------------------

Carlos Frias


<!-- BEGIN Google Required Disclaimer -->

# Not Google Product Clause

This is not an officially supported Google product.
<!-- END Google Required Disclaimer -->
<!-- BEGIN Google How To Contribute -->
# How to Contribute

We'd love to accept your patches and contributions to this project. Please review our [guidelines](CONTRIBUTION.md).
<!-- END Google How To Contribute -->
