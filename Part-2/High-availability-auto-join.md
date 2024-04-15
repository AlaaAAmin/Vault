# High availability and auto join
## Manually joining servers
- When joining multiple servers you might want to only generate one key to unseal Vault using the command `vault operator init -keyshares=1 -key-threshold=1`.
- When using RAFT HA configuration are automatically set to true, but. this doesn't mean that it is fully configured as you will only have one server if you don't create and join other servers.
- `vault operator members` will show the list of VAULT servers, at first you will find only one, this will be the leader and we need the API address of it for joining new servers.
>> Cluster address is used by RAFT to communicate between the servers.
- On the new servers you will need to put the ca, cert and the key and specify the path to it as usaual till the initialization step. we won't init but join.
- run `vault operator raft join -leader-ca-cert=@/path/to/leader/cert -leader-client-cert=@/path/to/client/cert -leader-client-key=@/path/to/leader/key https://api_address:port`
- unseal vault with the key from the original server. 
## Retry_join stanza