# How to update Globaleaks

- change App
- grunt build
- upload to running server

```
scp -r ./js admin@xx.xx.xxx.xxx:/usr/share/globaleakz
scp -r ./css admin@xx.xx.xxx.xxx:/usr/share/globaleakz
```

And then

```
#!/usr/bin/env bash


mkdir /usr/share/globaleakz/backup/js/"$(date +"%d-%m-%Y")"
mkdir /usr/share/globaleakz/backup/css/"$(date +"%d-%m-%Y")"


echo "Backup JS"
cp -v /usr/share/globaleaks/client/js/* /usr/share/globaleakz/backup/js/"$(date +"%d-%m-%Y")"/
echo "Backup CSS"
cp -v /usr/share/globaleaks/client/css/* /usr/share/globaleakz/backup/css/"$(date +"%d-%m-%Y")"/

echo "Updating JS"
mv -v /usr/share/globaleakz/js/* /usr/share/globaleaks/client/js/

echo "Updating CSS"
mv -v /usr/share/globaleakz/css/* /usr/share/globaleaks/client/css/

echo "finished"
```

See notion for detailed docs
