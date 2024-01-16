Generieren der Schlüssel und Zertifikate

```bash
openssl req -newkey rsa:2048 -nodes -keyout rp-key.key -x509 -days 365 -out rp-certificate.crt
```

Zur Nutzung des keys zum Signieren:

```java

```
