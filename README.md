# Grafana alert configuration

# MailHog setup

### Download MailHog

```console
wget https://github.com/mailhog/MailHog/releases/download/v1.0.1/MailHog_linux_amd64
```

### Make It Executable

You'll need to make the downloaded file executable:

```console
chmod +x MailHog_linux_amd64
```

### Run MailHog

Simply run the binary

```console
./MailHog_linux_amd64
```

By default, MailHog starts an SMTP server on port 1025 and a web interface on port 8025.

### Access the Web Interface

Open your web browser and navigate to http://localhost:8025 to view the caught emails.

### Configure Your Application

Finally, configure your application (e.g., Grafana) to send emails to localhost:1025, and they will be caught by MailHog.
