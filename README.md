# AnonAr

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/bandera-nacional-4.jpg" width="300">
</p>

AnonAr is a zero-knowledge protocol that allows DNI's holders to prove their identity in a privacy preserving way.

DNI = Documento Nacional de Identidad (Argentina's ID issued by [ReNaPer](https://www.argentina.gob.ar/interior/renaper) )


## Motivation

As an Argentinian PSE Core Program student and after diving around projects like [zkEmail](https://prove.email/), [OpenPassport](https://openpassport.app/) and mainly [Anon Addhaar](https://anon-aadhaar.pse.dev/), I've found an opportunity to create value and impact in the web3 ecosystem.


## Project description

By using programmable cryptography techniques we can leverage the uses of "DNI Digital" by creating a SDK toolkit where developers can implement it in their apps and enable argentinians to keep their personal data private while proving some aspects of it.

"DNI Digital" is a digital ID considered equally valid as the physical national ID card (except for voting and travelling) delivered by ReNaPer. To possess this document it's required to go into a validation process including biometrics.

The digital DNI is accessed throught the application [Mi Argentina](https://www.argentina.gob.ar/miargentina) that have a QR code containing a JSON Web Token signed using RS256 algorithm (RSA with SHA-256). 

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/dni-digital-2024.webp">
</p>

The digital ID could be verified offline with the application [ValidAR](https://www.argentina.gob.ar/validar). 



## Legal

As declared in the "Art. 4" of the "[Decreto 744/2019](https://www.boletinoficial.gob.ar/detalleAviso/primera/220176/20191030)": 

"ARTÍCULO 4º.- Establécese que la credencial virtual del Documento Nacional de Identidad para dispositivos móviles inteligentes será considerada a todos los efectos Documento Nacional de Identidad, teniendo pleno valor identificatorio en todos los actos públicos y privados en los términos de la Ley Nº 17.671 y sus modificatorias."

Translation:

"Article 4.- Stay that the virtual credential of the National Identity Document for smart mobile devices will be considered for all purposes National Identity Document, having full identifying value in all public and private acts in the terms of Law No. 17.671 and its amendments."

## Potential use cases

- Funding / voting
- Anon checkin
- Ticketing (Devconnect Buenos Aires 2025???)
- Proof of Citizenship / Proof of Age
- Gitcoin Passport