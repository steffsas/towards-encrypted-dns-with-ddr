# Towards Encrypted DNS with DDR: Standards, Adoption and Security Implications

This repository contains the materials and insights from my Master's thesis, titled **"Towards Encrypted DNS with DDR: Standards, Adoption and Security Implications"**, submitted in December 2024 at the University of Potsdam.

## 📚 Abstract

The Domain Name System (DNS) has long been a cornerstone of the Internet, yet it traditionally transmits queries in plaintext, exposing users to privacy and security risks. While encrypted DNS protocols (DoT, DoH, DoQ) exist, adoption remains limited due to configuration complexity and lack of awareness.

To address this, the IETF introduced the **Discovery of Designated Resolvers (DDR)** protocol, which enables clients to automatically discover and upgrade to encrypted DNS resolvers. This thesis presents the first large-scale empirical study of DDR deployment, analyzing over 4 million IPv4 and 287K IPv6 DNS servers over four months.

## 🧪 Methodology

We developed a custom measurement platform called **DoE-Hunter** (written in Go, containerized, and open-source) to conduct semi-weekly scans targeting:

- DDR adoption trends
- Configuration patterns and errors
- Protocol support (DoH, DoT, DoQ, ODoH)
- DNS centralization indicators

## 🔍 Key Findings

- **DDR Adoption**: 7.59% of IPv4 and 2.65% of IPv6 resolvers advertise DDR configurations, with DoH/2 being the dominant protocol.
- **Low DoQ Support**: Despite its advantages, <7% of DDR-enabled resolvers support DoQ.
- **Verification Failures**: 99% of DDR-compliant clients fail verified discovery due to widespread misconfigurations.
- **Resolver Centralization**: Over 97% of DDR-enabled resolvers delegate to major cloud DNS providers (e.g., Google, Cloudflare), raising privacy and governance concerns.
- **Traffic Shadowing**: Detected replay behaviors of DNS queries across recursive resolvers.
- **TLS Analysis**: TLS 1.3 dominates among DoE resolvers; mutual TLS is not required, as per spec.

## 🧩 Contributions

- First in-depth analysis of DDR in the wild.
- Largest known dataset of DoQ resolvers by Authentication Domain Name (ADN).
- Contributions to Go’s DNS library for SVCB and ODoH support.
- First measurements of recursive-to-authoritative encrypted DNS (RFC 9539).

## 📁 Repository Contents

- `DoE-Hunter/`: Source code for the measurement platform
- `data/`: Aggregated datasets and analysis artifacts (where applicable)
- `docs/`: Thesis PDF and supplementary material

## 📄 Citation

If you use this work, please cite the thesis as:

> Steffen Sassalla. *Towards Encrypted DNS with DDR: Standards, Adoption and Security Implications.* Master’s Thesis, Hasso Plattner Institute, 2024.

## 📬 Contact

For questions or collaboration, feel free to reach out: [steffen.sassalla@outlook.de]

---

**Keywords**: Encrypted DNS, DDR, DoH, DoT, DoQ, DNS centralization, Internet privacy, Go, DNS measurement