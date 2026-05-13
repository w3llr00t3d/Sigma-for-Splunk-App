# Sigma-for-Splunk-App
App for Splunk that auto-ingests new Sigma rules, converting them to saved searches within Spunk


Download sigma_auto_alert.spl

Install it in Splunk
Via the UI (easiest):

Go to Settings → Apps → Install app from file
Upload sigma_auto_alert.spl
Restart Splunk when prompted

Via CLI:
bash$SPLUNK_HOME/bin/splunk install app sigma_auto_alert.spl -auth admin:password
$SPLUNK_HOME/bin/splunk restart

One required post-install step
All Python deps (pySigma, requests, beautifulsoup4) are bundled in lib/ — no pip install needed. The only thing you must do is create your local config:
bashcp $SPLUNK_HOME/etc/apps/sigma_auto_alert/default/sigma_auto_alert.conf \
   $SPLUNK_HOME/etc/apps/sigma_auto_alert/local/sigma_auto_alert.conf
Then edit local/sigma_auto_alert.conf and set your Splunk host/credentials, SMTP server, and recipient address. The full reference is in install.txt inside the app (also available at install.txt).
