# 🛡️ GDPR-Compliant DID System using DIDKit

[![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/DevManoj19/mwh_bi2/blob/main/bi_2.ipynb)

This project showcases a decentralized identity system built with `DIDKit`, focusing on **GDPR compliance**, **verifiable credentials**, and **metadata registration** for contributors.

## 📜 Description

We generate Decentralized Identifiers (DIDs), issue Verifiable Credentials (VCs), and associate them with rich metadata. This Python-based system runs in Google Colab and demonstrates secure identity issuance and verification for decentralized apps and digital heritage use cases.

---

## 🚀 Features

- 🔑 Generate Ed25519 key and `did:key` format DIDs
- 🧾 Create and issue Verifiable Credentials (VCs)
- ✅ Verify issued credentials using `DIDKit`
- 🗃️ Register & lookup contributor metadata (e.g. name, location, timestamp)
- 🌐 Sample data integration from the [Dataverse Demo API](https://demo.dataverse.org)

---

## 📂 Project Structure

```text
bi_2.ipynb     - Main notebook (open in Colab to run)
sample_credential.json - Output file for the issued VC
````

---

## 🛠️ Installation (Colab)

Colab auto-installs dependencies. Manual installation:

```bash
pip install didkit pyld requests
apt-get install -y libsodium-dev
```

---

## 🧪 Usage

In Colab, run each cell step-by-step. Highlights include:

```python
# Generate key and DID
key = didkit.generate_ed25519_key()
did = didkit.key_to_did("key", key)

# Issue VC asynchronously
await issue_and_verify_credential(key)
```

Check `sample_credential.json` for the issued VC.

---

## 🔁 Example Metadata Registration

```python
register_metadata("did:example:abcdef123", {
    "name": "Heritage Archive Contributor",
    "locale": "Kolkata",
    "timestamp": "2025-07-05T20:00:00Z"
})
```

---

## 📡 External API Integration

We connect to Dataverse Demo API:

```python
response = requests.get("https://demo.dataverse.org/api/search?q=metadata")
print(response.json())
```

---

## 🧠 Learn More

* [DIDKit Documentation](https://docs.spruceid.com/didkit/)
* [Verifiable Credentials W3C Spec](https://www.w3.org/TR/vc-data-model/)
* [Dataverse Project](https://dataverse.org/)

---

## 👤 Author

**[@DevManoj19](https://github.com/DevManoj19))**
**[@Eshrathsubhani](https://github.com/Eshrathsubhani))**


---

## 📄 License

MIT License. See `LICENSE` for more details.

---

## 🙏 Acknowledgements

* 🧪 [SpruceID - DIDKit](https://github.com/spruceid/didkit)
* 🌐 [Dataverse Demo API](https://demo.dataverse.org)
* ❤️ Built with love in Colab
