Apigee OPDK Setup Edge SSO
=========

This role will setup the SSO component of the Apigee Edge platform. This is used to interface with an on premise IDP. 

Requirements
------------

This role requires elevated privilege to install OpenSSL.  

Role Variables
--------------

| Variable Name | Description |
| --- | --- |
| edge_sso_installation_config_filename | edge-sso-installer-config.conf |
| edge_sso_installation_config_file | "{{ opdk_installer_path }}/{{ edge_sso_installation_config_filename }}" |
| jwt_key_folder | "{{ apigee_home }}/customer/application/apigee-sso/jwt-keys" |
| jwt_private_key | private_key.pem |
| sso_jwt_signinig_key_filepath | "{{ jwt_key_folder }}/{{ jwt_private_key }}" |
| jwt_public_key | public_key.pem |
| sso_jwt_verification_key_filepath | "{{ jwt_key_folder }}/{{ jwt_public_key }}" |
| jwt_key_size | 2048 |
| saml_folder | "{{ apigee_home }}/customer/application/apigee-sso/saml" |
| sso_saml_service_provider_key_filename | server.key |
| sso_saml_service_provider_key | "{{ saml_folder }}/{{ sso_saml_service_provider_key_filename}}" |
| saml_private_encryption_type | aes256 |
| saml_private_key_size | 1024 |
| saml_cert_signing_request | server.csr |
| sso_saml_service_provider_certificate_filename | server.crt |
| sso_saml_service_provider_certificate | "{{ saml_folder }}/{{ sso_saml_service_provider_certificate_filename }}" |
| saml_cert_encryption_type | sha256 |
| saml_cert_expiry_days | 365 |
| saml_cert_subject | "/C=US/O=google/OU=apigee/CN=apigee.com" |
| sso_saml_idp_metadata_url | "{{ saml_folder }}/target_idp_metadata_url.xml" |


Dependencies
------------

* apigee-opdk-setup-default-settings

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
