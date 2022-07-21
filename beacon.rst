:
# Daily cleanup, run at midnight with cron
cd ~/beacon
date > cronRan
/usr/bin/pkill -u $USER freebeacon
# will be restarted with beacon.cron
sleep 5
# CODEC is string from my USB Behringer UCA202
CARD=`grep CODEC /proc/asound/cards | cut -z -b 2`
rm -f log*a yy*
mv log*b Logs/.
/usr/bin/arecord -D hw:${CARD},0 -d 10 -f S16_LE  > yyy$$
