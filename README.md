# bcrypt

Generate a strong password:
```bash
PASSWORD="$(openssl rand -base64 48 | tr -dc 'A-Za-z0-9' | head -c 32)"
```

Get the password value:
```bash
echo "$PASSWORD"
```

Generate bcrypt hash with cost factor 100:
```bash
htpasswd -bnBC 100 "" "$PASSWORD" | tr -d ':\n'; echo
```

