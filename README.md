# bcrypt

Generate a strong `32` characters password:
```bash
PASSWORD="$(openssl rand -base64 48 | tr -dc 'A-Za-z0-9' | head -c 32)"
```

Get the password value:
```bash
echo "$PASSWORD"
```

bcrypt cost factor range `4 - 31`

Generate bcrypt hash with cost factor of `12`:
```bash
htpasswd -bnBC 12 "" "$PASSWORD" | tr -d ':\n'; echo
```
