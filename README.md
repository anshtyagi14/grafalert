# Grafana alert configuration

# MailHog setup

### Download MailHog

```console
$ wget https://github.com/mailhog/MailHog/releases/download/v1.0.1/MailHog_linux_amd64
```

### Make It Executable

You'll need to make the downloaded file executable:

```console
$ chmod +x MailHog_linux_amd64
```

### Configure Your Application

Configure Grafana.ini to send emails to localhost:1025, and they will be caught by MailHog.

```console
$ sudo vim /etc/grafana/grafana.ini
/smtp
```

```yml
[smtp]
enabled = true
host = localhost:1025
from_address = admin@grafana.localhost
from_name = Grafana
startTLS_policy = NoStartTLS
```

### Run MailHog

Simply run the binary

```console
$ ./MailHog_linux_amd64
```

By default, MailHog starts an SMTP server on port 1025 and a web interface on port 8025.

### Access the Web Interface

Open your web browser and navigate to http://localhost:8025 to view the caught emails.


