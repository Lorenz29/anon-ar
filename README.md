# AnonAr

<p align="center">
  <img src="https://github.com/Lorenz29/anon-ar/blob/main/files/bandera.webp" width="300" theme="transparent">
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

The digital ID could be verified offline with the application [ValidAR](https://www.argentina.gob.ar/validar). 

## How it works

The prover upload the QR code generated in the app Mi Argentina: Mis Documentos->DNI->Ver DNI Digital->Pin->Verifica código QR.

From this QR, which is a JWT, it parse the signed data and verify it with the [pubkey](/circuits/assets/renaper-public.pem). See this test [example](https://jwt.io/#debugger-io?token=eyJhbGciOiJSUzI1NiIsInR5cCI6IkpXVCJ9.eyJkbmkiOiIxMjM0NTY3OCIsInNleG8iOiJNIiwiYXBlbGxpZG8iOiJSSVFVRUxNRSIsIm5vbWJyZSI6Ikp1YW4gUm9tYW4iLCJpc3MiOiJSRU5BUEVSIiwiYXVkIjoiaWQuYXJnZW50aW5hLmdvYi5hciIsImlhdCI6MTcyNTM2NTc1NSwibmJmIjoxNzI1MzY1NzU1LCJleHAiOjE3MjU0MTg3OTl9.Vcu4Lce14vM3b1TIvqnoVgvMblcI2M5USze75IELiLA6zyusQAHFkqe3GtdqcA1rwCB17G3VyY5qL25QOJfHvgaVCgiK1Hkjc0q9SM34Cp4lsMVFC-QbBBrKpbCvRco4T6MvFOLpCp2qnf4KTJw8ZOCHKKCF4jL2JeiEl0U0Myfx2WaGkaHx7Vqm5AnHDZSgnrClb8BzeD41-qYHheVEjxoJRIgPV2Xq71OZveBdJItaWTVeEPoDy40n2jcAePBZZwWj8qPmfZNjcqSrvAnHH0SfYOtMo9qT4iMWU-qziLAFoYaEmYedwtYqZWzXc8xZOFQyjUf2cVkt2zDvt9oMCA&publicKey=-----BEGIN%20PUBLIC%20KEY-----%0AMIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAu1SU1LfVLPHCozMxH2Mo%0A4lgOEePzNm0tRgeLezV6ffAt0gunVTLw7onLRnrq0%2FIzW7yWR7QkrmBL7jTKEn5u%0A%2BqKhbwKfBstIs%2BbMY2Zkp18gnTxKLxoS2tFczGkPLPgizskuemMghRniWaoLcyeh%0Akd3qqGElvW%2FVDL5AaWTg0nLVkjRo9z%2B40RQzuVaE8AkAFmxZzow3x%2BVJYKdjykkJ%0A0iT9wCS0DRTXu269V264Vf%2F3jvredZiKRkgwlL9xNAwxXFg0x%2FXFw005UWVRIkdg%0AcKWTjpBP2dPwVZ4WWC%2B9aGVd%2BGyn1o0CLelf4rEjGoXbAAEgAqeGUxrcIlbjXfbc%0AmwIDAQAB%0A-----END%20PUBLIC%20KEY-----)

The circuit will generate the proof that can be use in an App or a Smart Contract to convince the verifier that the prover has a valid argentinian ID. It's important to mention that all the information included in the JWT never leaves the prover's browser.


## Specification

- Extract data from QR code and verify it's signed by ReNaPer using the public key
- 
- Use payload data to generate the proofs (E.G: Proof of Personhood)
- 

## Legal

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