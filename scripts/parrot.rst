:
cd ~/parrot
/usr/bin/pkill -u alanb parrot
sleep 5
##CRD=`grep CODEC /proc/asound/cards | cut -b 2`
##CARD=$CRD
##HWCARD=`printf 'hw:%s,0' "$CARD"`
rm -f log*a yy*
/usr/bin/arecord -D hw:1,0 -d 10 -f S16_LE  > yyy$$
