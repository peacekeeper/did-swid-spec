## The SWID Registry

The SWID Registry contains a list of SWIDs. For each SWID, the SWID Registry contains a
cryptographic event log following the [Cryptographic Event Log](https://digitalbazaar.github.io/cel-spec/#the-did-document-cel-specification)
specification. Every entry in the event log is cryptographically signed by the entity
that controls a SWID.

For example, the SWID Registry could contain the following cryptographic event log for a
SWID that has been created, and then updated once:

```json
{
  "log": [{
    "event": {
      "operation": {
        "type": "create",
        "data": {
          "@context": [
            "https://www.w3.org/ns/did/v1.1",
            "https://spatialwebfoundation.org/contexts/did/1.0"
          ],
          "id": "did:swid:",
          "verificationMethod": [{
            "id": "#keys-1",
            "type": "Multikey",
            "controller": "did:swid:",
            "publicKeyMultibase": "z6MkmM42vxfqZQsv4ehtTjFFxQ4sQKS2w6WR7emozFAn5cxu"
          }],
          "authentication": [
            "#keys-1"
          ],
          "assertionMethod": [
            "#keys-1"
          ],
          "service": [{
            "id": "#hstp",
            "type": "HSTPEndpoint",
            "serviceEndpoint": "https://hstp.example.com/hstpendpoint"
          }],
          "proof": {
            "type": "DataIntegrityProof",
            "cryptosuite": "ecdsa-jcs-2019",
            "created": "2024-11-29T13:56:28Z",
            "verificationMethod": "#keys-1",
            "proofPurpose": "assertionMethod",
            "proofValue": "z5obCSsrQxuFJdq6PrUMCtqY93gBHqGDBtQLPFxpZxzwVWgHYrXxoV"
          }
        }
      }
    }
  }, {
    "event": {
      "previousEvent": "uEkoYyQ6YVtUmER8pN24wLZcLK9EBguM5WZlbAgfXBDuQiA",
      "operation": {
        "type": "update",
        "data": {
          "@context": [
            "https://www.w3.org/ns/did/v1.1",
            "https://spatialwebfoundation.org/contexts/did/1.0"
          ],
          "id": "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv",
          "verificationMethod": [{
            "id": "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv#keys-1",
            "type": "Multikey",
            "controller": "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv",
            "publicKeyMultibase": "z6MkmM42vxfqZQsv4ehtTjFFxQ4sQKS2w6WR7emozFAn5cxu"
          }],
          "authentication": [
            "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv#keys-1"
          ],
          "assertionMethod": [
            "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv#keys-1"
          ],
          "service": [{
            "id": "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv#hstp",
            "type": "HSTPEndpoint",
            "serviceEndpoint": "https://hstp.example.com/new_hstpendpoint"
          }],
          "proof": {
            "type": "DataIntegrityProof",
            "cryptosuite": "ecdsa-jcs-2019",
            "created": "2024-11-29T13:56:28Z",
            "verificationMethod": "did:swid:zQmQoeG7u6XBtdXoek5p3aPoTjaSRemHAKrMcY2Hcjpe3jv#keys-1",
            "proofPurpose": "assertionMethod",
            "proofValue": "z5obCSsrQxuFJdq6PrUMCtqY93gBHqGDBtQLPFxpZxzwVWgHYrXxoV"
          }
        }
      }
    }
  }]
}
```