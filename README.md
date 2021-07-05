# Auto-self-delgate
withdraw rewards and delegate bot
I share scripts that use `expect` code.

# Install expect command 
```apt install expect```

# Expect scripts
rewards.exp
```
#!/usr/bin/expect
spawn desmos tx distribution withdraw-rewards <your operator address: desmosvaloper...> --from <your key> --commission --chain-id morpheus-apollo-1 --broadcast-mode block -y

expect {
    "Enter keyring passphrase:" {
        send "<your password of key>\n"
        exp_continue
    }
}
```

delegate.exp
```
#!/usr/bin/expect

spawn desmos tx staking delegate <your operator address: desmosvaloper...> <amount of stake token> --from <your key> --chain-id morpheus-apollo-1 --broadcast-mode block -y

expect {
    "Enter keyring passphrase:" {
        send "<your password of key>\n"
        exp_continue
    }
}
```
Make the above two different scripts (reward.exp, delegate.exp) with editing tool.


