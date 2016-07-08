# MeasurementKit Debian

Repository for creating MeasurementKit packages for Debian. You may need
to add the `7733D95B` PGP key to your keyring.

```
# on the host machine
./script/get-source
vagrant up
vagrant ssh
# following commands run inside the ssh
cd /mk/measurement-kit
./script/debuild
exit
# again on the host machine
./script/sign
```
