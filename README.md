# AnonAr

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/bandera-nacional-4.jpg" width="300">
</p>

AnonAr is a zero-knowledge protocol that allows DNI's holders to prove their identity in a privacy preserving way.

DNI = Documento Nacional de Identidad (Argentina's ID issued by [ReNaPer](https://www.argentina.gob.ar/interior/renaper) )


## Motivation

As Argentinian citizen and PSE Core Program student and after dive around projects like [zkEmail](https://prove.email/), [OpenPassport](https://openpassport.app/) and mainly [Anon Addhaar](https://anon-aadhaar.pse.dev/), I'd like to build 


## Project description

By using programmable cryptography techniques we can leverage the uses of "DNI Digital" by creating a SDK toolkit where developers can implement it in their apps and enables argentians to keep their personal data private while proving some aspects of it.

"DNI Digital" is a digital ID considered valid in all aspects (except voting and travelling) according to the law as the national ID delivered by ReNaPer which is the official issuing ID entity. To access this document it's required to go into a validation process including biometrics.

The digital DNI is accessed throught the application [Mi Argentina](https://www.argentina.gob.ar/miargentina) with a QR code containing a JSON Web Token signed using RS256 algorithm (RSA with SHA-256). 

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/dni-digital-2024.webp">
</p>

The digital ID could be verified offline with the application [ValidAR](https://www.argentina.gob.ar/validar)



## Goverment statement

As declared in the "Art. 4" of the "[Decreto 744/2019](https://www.boletinoficial.gob.ar/detalleAviso/primera/220176/20191030)": 

"ARTÍCULO 4º.- Establécese que la credencial virtual del Documento Nacional de Identidad para dispositivos móviles inteligentes será considerada a todos los efectos Documento Nacional de Identidad, teniendo pleno valor identificatorio en todos los actos públicos y privados en los términos de la Ley Nº 17.671 y sus modificatorias."

## Potential use cases

- Funding / voting
- Anon checkin
- Ticketing (Devconnect Buenos Aires 2025???)
- Proof of Age