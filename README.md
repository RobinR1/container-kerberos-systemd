# Systemd service file to run RobinR's kerberos container via systemd and podman

* `/etc/sysconfig/container-kerberos` contains generic settings
* `/etc/kerberos-secrets/` contains files for setting the:
  * `MASTER_PASS` - master password for the kerberos realm
  * `ADMIN_PASS` - password for the cn=krbadm kadmin user
  * `KDC_PASS` - password for the cn=krbkdc kdc user
  * `DM_PASS` - password of the cn=Directory Manager
  They should not be readable by anyone but root user and it is highly recommended to remove these files after initialization of the container. This location can be altered via `SECRETS_DIR`
  in the `/etc/sysconfig/container-kerberos` file.