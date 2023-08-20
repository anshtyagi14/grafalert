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

# Mailtrap configuration

```yml
#################################### SMTP / Emailing ##########################
[smtp]
enabled = true
host = sandbox.smtp.mailtrap.io:587 # You can choose any port from 25, 465, 587, 2525 depending on your requirement
user = XXXXXXXXXX
password = XXXXXXXXXX # If the password contains # or ; you have to wrap it with triple quotes
;cert_file =
;key_file =
;skip_verify = false
from_address = admin@grafana.localhost
from_name = Grafana
ehlo_identity = dashboard.example.com
startTLS_policy = OpportunisticStartTLS # As TLS is optional

[emails]
welcome_email_on_sign_up = false
templates_pattern = emails/*.html, emails/*.txt
content_types = text/html
```
