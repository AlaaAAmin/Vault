# Getting into HashiCorp Vault, Part 1: Clusters, Seals, & Storage.
## Installing and configuring Vault
1. Vault Architecture: https://developer.hashicorp.com/vault/docs/internals/architecture
2. Installing Vault: https://developer.hashicorp.com/vault/install
3. In order to configure you will need to know the path of vault configurations, for that you can use the command `systemctl status vault` to know where the uni file that starts Vault.
4. Look for `ExecStart` variable as it will point to the binary and configuration file path. usually it is in /etc/vault.d/vault.hcl
5. An example for the configuration is found here https://developer.hashicorp.com/vault/docs/configuration