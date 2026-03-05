# Verify attestation

The signing keys are backed by FIDO security keys and can be verified using [ssh-sk-verify](https://github.com/supply-chain-tools/ssh-sk-verify).

Download the FIDO Alliance Metadata Service blob ([MDS Legal Terms](https://fidoalliance.org/metadata-legal-terms/))
```
curl -L https://mds3.fidoalliance.org/ --output mds.jwt
```

Verify developer keys
```
ssh-sk-verify --public-key stiankri_1.pub --attestation stiankri_1_attestation.bin --challenge stiankri_1_challenge.bin --mds mds.jwt
ssh-sk-verify --public-key stiankri_2.pub --attestation stiankri_2_attestation.bin --challenge stiankri_2_challenge.bin --mds mds.jwt
```

Verify 3FA keys
```
ssh-sk-verify --public-key stiankri-3fa_1.pub --attestation stiankri-3fa_1_attestation.bin --challenge stiankri-3fa_1_challenge.bin --mds mds.jwt
ssh-sk-verify --public-key stiankri-3fa_2.pub --attestation stiankri-3fa_2_attestation.bin --challenge stiankri-3fa_2_challenge.bin --mds mds.jwt
```
