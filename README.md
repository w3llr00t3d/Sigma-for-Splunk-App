# Sigma for Splunk App

**Auto-ingest new Sigma rules and convert them to Saved Searches in Splunk.**

---

## Download

[Download sigma_auto_alert.spl](sigma_auto_alert.spl)

---

## Installation

### Via Splunk Web UI (Recommended)

1. Go to **Settings → Apps → Install app from file**
2. Upload `sigma_auto_alert.spl`
3. Restart Splunk when prompted

### Via CLI

`
$SPLUNK_HOME/bin/splunk install app sigma_auto_alert.spl -auth admin:password
$SPLUNK_HOME/bin/splunk restart`

## Post-Installation Steps

All required Python dependencies (`pySigma`, `requests`, `beautifulsoup4`) are bundled in the `lib/` directory, so **no `pip install` is needed**.

### 1. Create your local configuration file

`
cp $SPLUNK_HOME/etc/apps/sigma_auto_alert/default/sigma_auto_alert.conf \
   $SPLUNK_HOME/etc/apps/sigma_auto_alert/local/sigma_auto_alert.conf`


Then edit local/sigma_auto_alert.conf and set your Splunk host/credentials, SMTP server, and recipient address. The full reference is in install.txt inside the app (also available at install.txt).

