# 🔐 Elliptic Curve Cryptography (ECC)

<div align="center">

![Course](https://img.shields.io/badge/Course-MATH%20203-blue?style=flat-square)
![Topic](https://img.shields.io/badge/Topic-Cryptography-brightgreen?style=flat-square)
![Type](https://img.shields.io/badge/Type-Research%20Report-orange?style=flat-square)
![Status](https://img.shields.io/badge/Status-Complete-success?style=flat-square)

**A report on Elliptic Curve Cryptography — from the algebraic structure of elliptic curve groups to the Elliptic Curve Diffie-Hellman (ECDH) key exchange and its real-world use in Bitcoin.**

</div>

---

## TL;DR

ECC builds a public-key cryptosystem on the algebraic group formed by points on an elliptic curve `y² = x³ + ax + b` over a finite field. Point addition and scalar multiplication on the curve are easy to compute in one direction but computationally infeasible to reverse — the **discrete logarithm problem** — which is exactly the one-way function cryptography needs. This report walks through that group structure, derives the **Elliptic Curve Diffie-Hellman (ECDH)** protocol for securely agreeing on a shared secret over a public channel, and covers real-world usage, including how Bitcoin uses the `secp256k1` curve to derive public keys and sign transactions.

**Why it matters:** ECC delivers the same security level as RSA with much smaller key sizes and less computational overhead, making it well suited to mobile devices and embedded systems.

---

## Contents Covered

- **Elliptic curve fundamentals** — the defining equation, the field restriction (mod p), and the geometric/algebraic properties (line-curve intersection, symmetry about the x-axis) that make the group operations well-defined.
- **Group operations** — point addition and scalar multiplication, and why the resulting point is always the curve's reflection of the geometric intersection point.
- **The discrete logarithm problem** — why knowing points P and Q with P = kQ does not reveal k, the hardness assumption ECC security rests on.
- **Diffie-Hellman over elliptic curves (ECDH)** — domain parameters {p, a, b, G, n, h}, key pair generation, and how two parties derive a shared secret point without ever transmitting their private keys.
- **Cryptosystem design considerations** — weak vs. verifiably random curves, and how curve parameters are generated safely using hash functions.
- **ElGamal over elliptic curves** — point compression/decompression for efficient storage once keys are exchanged.
- **Bitcoin case study** — how `secp256k1` (a = 0, b = 7) is used to derive public keys `K = k·G` from private keys, and why this direction is easy while the reverse is not.

---

## Key Takeaway

The security of ECC-based systems rests entirely on the **discrete logarithm problem remaining unsolved**: scalar multiplication on the curve is cheap to compute but has no known efficient inverse. Combined with small key sizes relative to RSA for equivalent security, this is what makes ECC the practical choice for constrained environments — from HTTPS key exchange to Bitcoin transaction signing.

---

## 📁 Project Structure

```
Elliptic-Curve-Cryptography/
│
├── README.md
└── Discrete_Report_ECC.md          # Full report with derivations and references
```

## Skills & Topics

Public-key cryptography · elliptic curve group theory · discrete logarithm problem · Diffie-Hellman key exchange · ECDH · ElGamal encryption · applied number theory.

## References

R. Pierce, *Elliptic Curve Diffie Hellman* · N. Koblitz, A. Menezes, S. Vanstone, *Designs, Codes and Cryptography*, vol. 19 · K. Magons, *Applications and Benefits of Elliptic Curve Cryptography* · MATH 203 Course Materials (see full report for complete citation list)

---

## 👥 Team

Collaborative undergraduate team project — **MATH 203, Dr. Ahmed Etman**.

- Mazen Salem (202400447)
- Youssef Mohamed (202400956)
- Moustafa Hesham Sallam (202400624)
- Hassan Emad (202401299)
- Mahmoud Abdelwahab (202402046)

## 📄 License

No license — educational use only.
