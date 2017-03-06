# Crontab

```
$ crontab -e

0 * * * * date >> test.log
59 23 * * * ~/moveLog.sh
```

# moveLog.sh:

```
#!/bin/bash

TIME=`date +%Y-%m-%d_%H:%M:%S`
FILENAME=remotelog-$TIME.log

mv ~/test.log ~/$FILENAME
echo "A new day:" >> ~/test.log
```


