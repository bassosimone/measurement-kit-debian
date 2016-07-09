# MeasurementKit Debian

Repository for creating MeasurementKit packages for Debian. You may need
to add the `7733D95B` PGP key to your keyring.

## How to create source package

```
# on the host machine
./script/get-source
vagrant up trusty
vagrant ssh trusty

# following commands run inside the vagrant machine
cd /mk/
./script/debuild
exit

# again on the host machine
./script/sign
vagrant ssh trusty

# again on the vagrant machine
gpg --recv-keys 7733D95B
for file in *.changes; do dput ppa:bassosimone/measurement-kit $file; done
```

## How to build source package on Debian

```
vagrant up jessie
vagrant ssh jessie
apt-get build-dep libmeasurement-kit-dev
apt-get source --build libmeasurement-kit-dev
```
