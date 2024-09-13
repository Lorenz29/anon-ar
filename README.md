# AnonAr

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/bandera.jpeg" width="300" theme="transparent">
</p>

AnonAr is a zero-knowledge protocol that allows DNI's holders to prove their identity in a privacy preserving way.

DNI = Documento Nacional de Identidad (Argentina's ID issued by [ReNaPer](https://www.argentina.gob.ar/interior/renaper) )


## Motivation

As an Argentinian PSE Core Program student and after diving around projects like [zkEmail](https://prove.email/), [OpenPassport](https://openpassport.app/) and mainly [Anon Aadhaar](https://anon-aadhaar.pse.dev/), I've found an opportunity to create value and impact in the web3 ecosystem.


## Project description

By using programmable cryptography techniques we can leverage the uses of "DNI Digital" by creating a SDK toolkit where developers can implement it in their apps and enable users to generate a zero-knowledge proof of their identities. 

"DNI Digital" is a digital ID considered equally valid as the physical national ID card (except for voting and travelling) delivered by ReNaPer. To possess this document it's required to go into a validation process including biometrics. Instructions [here](files/instructivo_de_descarga_dni_en_tu_celular_-_renaper.pdf).

The digital DNI is accessed throught the application [Mi Argentina](https://www.argentina.gob.ar/miargentina) that have a QR code containing a [JSON Web Token](https://en.wikipedia.org/wiki/JSON_Web_Token) signed using RS256 algorithm (RSA with SHA-256). 

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/dni-digital-2024.webp">
</p>

The digital ID could be validated offline with the application [ValidAR](https://www.argentina.gob.ar/validar).

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/validar_pantallas.png">
</p>

## How it works

The prover upload the QR code generated in the app Mi Argentina: Mis Documentos->DNI->Ver DNI Digital->Pin->Verifica código QR.

From this QR, which is a JWT, it parse the signed data and verifies it with the [pubkey](/circuits/assets/renaper-public.pem). See this test [example](https://tinyurl.com/stmrmeav)

The circuit will generate the proof that can be use in an App or a Smart Contract to convince the verifier that the prover has a valid argentinian ID. It's important to mention that all the information included in the JWT never leaves the prover's browser.


## Specification

- Extract data from QR code and parse it
- Verify the RSA signature of the hashed data
- Verify it's signed by ReNaPer using the public key
- Extract fields from signed data
- Generate the proofs (e.g. Proof of Personhood)


### Inputs

- Signature (private)
- Signed Data (private)
- Public Key (public)
- signalHash (public)

### Outputs

- userNullifier
- identityNullifier
- timestamp
- pubKeyHash
- signalHash


## Law

As declared in the "Art. 4" of the "[Decreto 744/2019](https://www.boletinoficial.gob.ar/detalleAviso/primera/220176/20191030)": 

"ARTÍCULO 4º.- Establécese que la credencial virtual del Documento Nacional de Identidad para dispositivos móviles inteligentes será considerada a todos los efectos Documento Nacional de Identidad, teniendo pleno valor identificatorio en todos los actos públicos y privados en los términos de la Ley Nº 17.671 y sus modificatorias."

Translation:

"Article 4.- Stay that the virtual credential of the National Identity Document for smart mobile devices will be considered for all purposes National Identity Document, having full identifying value in all public and private acts in the terms of Law No. 17.671 and its amendments."

## Potential use cases

- Funding / voting
- Anon checkin
- Ticketing (Devconnect Buenos Aires 2025???)
- Proof of Personhood / Proof of Age
- Gitcoin Passport
- Wallet recovery?

## Possible challenges

I've found [ReNaPer's publicKey](circuits/assets/renaper-public.pem) by doing reverse engineering of the [ValidAR App](https://www.argentina.gob.ar/validar) but couldn't find a public site where the it's published by the goverment. This could be an issue since the verifier will need to validate the origin of this key.

## Goal of the project

To build a MVP allowing users to generate a valid proof.

## Mentors

- @Meyanis95 [Github](https://github.com/Meyanis95) | [X](https://x.com/yanis_mezn)
- @brech1 [Github](https://github.com/brech1) | [Linktree](https://linktr.ee/brechy)

## Resources

- [Anon Aadhaar repo](https://github.com/anon-aadhaar/anon-aadhaar/tree/main)
- [zkEmail repo](https://github.com/zkemail)
