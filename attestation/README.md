# Verify attestation

The signing keys are backed by FIDO security keys and can be verified using [ssh-sk-verify](https://github.com/supply-chain-tools/ssh-sk-verify).

Download the FIDO Alliance Metadata Service blob ([MDS Legal Terms](https://fidoalliance.org/metadata-legal-terms/))
```
curl -L https://mds3.fidoalliance.org/ --output mds.jwt
```

Verify
```
ssh-sk-verify --public-key git_sign.pub --attestation git_sign_attestation.bin --challenge git_sign_challenge.bin --mds mds.jwt
ssh-sk-verify --public-key git_sign_backup.pub --attestation git_sign_backup_attestation.bin --challenge git_sign_backup_challenge.bin --mds mds.jwt
```
