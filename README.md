# MeasurementKit Debian

Repository for creating MeasurementKit packages for Debian.

```
vagrant up
vagrant ssh
# following commands run inside the ssh
cd /mk/measurement-kit
./autogen.sh
debuild -b -uc -us
```
