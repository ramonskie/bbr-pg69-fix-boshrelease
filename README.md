# BOSH release for fakepackage

This BOSH release and deployment manifest deploy a cluster of fakepackage.

## Usage

This repository includes base manifests and operator files. They can be used for initial deployments and subsequently used for updating your deployments:

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=fakepackage
git clone https://github.com/cloudfoundry-community/fakepackage-boshrelease.git
bosh deploy fakepackage-boshrelease/manifests/fakepackage.yml
```

If your BOSH does not have Credhub/Config Server, then remember `--vars-store` to allow generation of passwords and certificates.

### Update

When new versions of `fakepackage-boshrelease` are released the `manifests/fakepackage.yml` file will be updated. This means you can easily `git pull` and `bosh deploy` to upgrade.

```
export BOSH_ENVIRONMENT=<bosh-alias>
export BOSH_DEPLOYMENT=fakepackage
cd fakepackage-boshrelease
git pull
cd -
bosh deploy fakepackage-boshrelease/manifests/fakepackage.yml
```
