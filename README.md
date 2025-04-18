# a-statement-journey
Backing materials for a blog post about the use of PDF 

# Example Embedded Font
```html
  <style>
    @font-face {
      font-family: 'BankFont';
      src: url(data:font/woff2;base64,d09GMgABAAAAAAP8AA0AAAAAB7gAAAOnAAEAAAAAAAAAAAAAAAAAAAAAAAAAAAAAP0ZGVE0cGhgGYACCYhEICoN0gzULEgABNgIkAyAEIAWEAQcyG38GAC4O7MYfG2IkKVAxYJw8C7xKBJTd8/XM7pcRAnIKMAR0cOjw6v3/c787VH0b8r6ovQ3RJto4JLJJpoo1iJY94YlDKga6MxhcD8vkq84y0SX/b8SpmqkLbH4GeUQjMpcFE0wKNilCNV+6rFgr9qIlqtWxQlj1xkkhNf89T5yEfCYI8Ln3wT/hVfnPK+CXaoffC8iN/EBEiogkVgo7ZJHGOxG2jDcP3zT0RwSwgmpABJixcGgYOmTA8T1TJI9CPgQI38fnKI9AggSlEWAIbwGl+WgB5JRdFJXXxQBnIhOu75P5+T8EQIqsIBshKwEQIiJwFEjYT3FZ/JqsZAMvGzJFkB3kB3LgKD4AUhABiSgIaVooR77auYuWDk7yxFGh3rlz9feVBt/l2vzOird93nFdzkFBXtr+Q1j5fg6bH3y4fbmeqnrs/rXxudZf59xU/ZEVd3p7L7TSL5K+OaWHzab36ova73+w//r+04cHbP5Qrv9hnxt3rDjpppbJuUdIg5FYIglq7xcTF6RvHplsuua5nG4cKR77hsi8pTJCJtnM/3WfvlW/O/4d2qBkpbbE5ZXa+EezOYcz2r42Wq5MVvoxail3yjU8IqnJ1pKEhuzpc3GW2+SOqh7VEda/WqVmWud19ub5YaAPkTE/vy9RXJ+6Vqp8S075iKo/AlkF6hi4KN6Zu1m8i01dVdXeRBdV9nQ0V6ie7v6/dskc3/Q2eY9hwUWLEoOxqXEP8nWgfOis4+Vuyu+Y07z/rdnFLTd+7N7ub96e6/kHxKx3bQu89iTcti/VUZf58VeFbF3JMJqMo4vpcmJgc5yhSuLskytF8Nu1LQAEBNZM3vPj8Hwt/2Xv5I/wvS1fRrw4sosgEHhxtBBkft4hgFlmD/9qCAhdAUJtEN8rkYWUZhPhcRwkIJBdc94gIghoAQD5XQmAUhrICLIZQ0Z2CRIF7CKVzWNkkcV3yCqbf2/IrnBU5S2kOdAUkBHk1YeM7BQkKppDKq9byCKn18gqr1+enl11/3rrg2TgYVlgGSgMbEQGxMHEAhtmkaEADwUpBL07ot8V3Cfn4GWlL+BRyOD+VgxsMIMhZtBqpA0bhswAvVjYjHK3Ar6OOwegHR4uMaRTlyY8slJIcvxRSAwy215GnV1NPDFFylPXnuhp0UCZCuygwVTAROv9vVkYGQwb4TgBUcQgWzm4t1ksBvQemzDxRzosOENkwFaH28GyDEAEMlc1RGX2K+eSKnpwCQAA) format('woff2');
    }
...
  </style>
```

# Example Embedded Transaction Data
```html
  <script type="application/ld+json" id="jsonld">
  {
    "@context": [
      "https://www.w3.org/2018/credentials/v1",
      "https://schema.org",
      "https://w3id.org/security/suites/ed25519-2020/v1"
    ],
    "id": "urn:uuid:de09cbf0-d94c-4c89-89a5-e0b6205cce91",
    "type": ["VerifiableCredential", "BankStatement"],
    "issuer": "https://bank.example.com/issuers/123",
    "issuanceDate": "2025-04-18T10:00:00Z",
    "credentialSubject": {
      "id": "did:example:consumer123",
      "name": "Alice Consumer",
      "accountNumber": "1234567890",
      "currency": "EUR",
      "statementPeriod": {
        "startDate": "2025-04-01",
        "endDate": "2025-04-17"
      },
      "transactions": [
        {
          "@type": "FinancialTransaction",
          "id": "urn:txn:001",
          "date": "2025-04-01",
          "description": "Grocery Store",
          "amount": {
            "@type": "MonetaryAmount",
            "value": "-50.00",
            "currency": "EUR"
          },
          "merchant": {
            "name": "SuperMart",
            "identifier": "SM123"
          },
          "category": "groceries"
        },
        {
          "@type": "FinancialTransaction",
          "id": "urn:txn:002",
          "date": "2025-04-05",
          "description": "Employer Payment",
          "amount": {
            "@type": "MonetaryAmount",
            "value": "3000.00",
            "currency": "EUR"
          },
          "category": "income"
        },
        {
          "@type": "FinancialTransaction",
          "id": "urn:txn:003",
          "date": "2025-04-10",
          "description": "Electricity Bill",
          "amount": {
            "@type": "MonetaryAmount",
            "value": "-120.00",
            "currency": "EUR"
          },
          "category": "utilities"
        }
      ]
    },
    "proof": {
      "type": "Ed25519Signature2020",
      "created": "2025-04-18T10:00:00Z",
      "proofPurpose": "assertionMethod",
      "verificationMethod": "https://bank.example.com/keys/ed25519-pubkey-2025",
      "proofValue": "z5LdN3zRwZc...8F2kM"
    }
  }
  </script>
```
