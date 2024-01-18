### Cron Things

*Send all cron-generated output to a specific e-mail*<br>
MAILTO=notifications@unluckysysop.com<br>
<br>
*Run every day at 2AM*<br>
0 2 * * * /root/at2am.sh<br>
<br>
*Run every day at 2:15AM*<br>
15 2 * * * /root/at215am.sh<br>
<br>
*run a backup script at reboot*<br>
@reboot /root/backup.sh<br>
<br>
*Run a test 4 times per minute, every minute*<br>
\* \* \* \* \* sleep 15; date >> /tmp/cron_test<br>
\* \* \* \* \* sleep 30; date >> /tmp/cron_test<br>
\* \* \* \* \* sleep 45; date >> /tmp/cron_test<br>
\* \* \* \* \* sleep 60; date >> /tmp/cron_test<br>
<br>
