---
title: Microsoft 365-Verschlüsselungs Ketten – DoD und gcc High
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 10/16/2020
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
- Strat_O365_IP
description: Zeigen Sie eine vollständige Liste der hohen DoD-und gcc-Stammzertifikate und Zertifizierungsstellen (CAS) in Microsoft 365 an.
ms.openlocfilehash: a933acc14f0984e4935ff6e56ccccd3aed1f16cf
ms.sourcegitcommit: 705915f8bf9b7c082d12a009523d8aa0670a74a1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/16/2020
ms.locfileid: "48493652"
---
# <a name="microsoft-365-encryption-chains---dod-and-gcc-high"></a>Microsoft 365-Verschlüsselungs Ketten – DoD und gcc High

Microsoft 365 nutzt eine Reihe unterschiedlicher Zertifikatanbieter. Im folgenden wird die vollständige Liste der bekannten Microsoft 365-Stammzertifikate beschrieben, denen **DoD-und gcc-hoch Kunden** beim Zugriff auf Microsoft 365 möglicherweise begegnen. Informationen zu den Zertifikaten, die Sie möglicherweise in ihrer eigenen Infrastruktur installieren müssen, finden Sie unter [Planen von Drittanbieter-SSL-Zertifikaten für Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates).

Die folgenden Zertifikatinformationen gelten für **alle DoD-und gcc-High-Kunden**.

Letzte Änderung: **10/16/2020**

>[!NOTE]
>Informationen zu Zertifikaten, die für **Kunden weltweit**gelten, finden Sie unter [Microsoft 365 Encryption Chains](encryption-office-365-certificate-chains.md).

| **Zertifikattyp** | **P7B herunterladen** | **CRL-Endpunkte** | **OCSP-Endpunkte** |
| --- | --- | --- | --- | --- |
| Öffentlich vertrauenswürdige Stamm-und Zwischenzertifikate | [Microsoft 365 ITAR Certificate Bundle (P7B)](https://download.microsoft.com/download/b/3/a/b3ae08a2-516c-46a9-8723-6256e4fd6383/m365_chain_certs_itar20201012.p7b) | crl.entrust.net<br>crl3.digicert.com<br>crl4.digicert.com | ocsp.digicert.com<br>ocsp.entrust.net |

Erweitern Sie die unten aufgeführten Stamm-und zwischen Abschnitte, um weitere Details zu den Zertifikatanbietern anzuzeigen.

## <a name="microsoft-365-certificate-details"></a>**Microsoft 365-Zertifikat Details**

### <a name="baltimore-cybertrust-root"></a>**Baltimore CyberTrust Root**

| **Betreff** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| --- | --- |
| **Seriennummer** | 02:00:00: B9 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Mai 12 18:46:00 2000 UTC |
| **Gültigkeit nicht nach** | Mai 12 23:59:00 2025 UTC |
| **ID des Antragstellerschlüssels** | E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | D4DE20D05E66FC53FE1A50882C78DB2852CAE474 |
| **Fingerabdruck (SHA-256)** | 16AF57A9F676B0AB126095AA5EBADEF22AB31119D644AC95CD4B93DBF3F26AEB |
| **PIN (SHA-256)** | Y9mvm0exBk1JoQ57f9Vm28jKo5lFm/woKcVxrYxu80o = |

### <a name="digicert-cloud-services-ca-1"></a>**Digicert Cloud Services-Zertifizierungsstellen-1**

| **Betreff** | CN = Digicert Cloud Services ca-1<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| **Seriennummer** | 01:9e: C1: C6: BD: 3f: 59:7B: B2:0C: 33:38: E5:51: D8:77 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Aug 04 12:00:00 2015 UTC |
| **Gültigkeit nicht nach** | Aug 04 12:00:00 2030 UTC |
| **ID des Antragstellerschlüssels** | DD: 51: D0: a2:31:73: A9:73: AE: 8F: B4:01:7E: 5D: 8c: 57: CB: 9F: F0: F7 |
| **Autoritäts Schlüssel-ID** | keyid: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | 81B68D6CD2F221F8F534E677523BB236BBA1DC56 |
| **Fingerabdruck (SHA-256)** | 2F6889961A7CA7067E8BA103C2CF9B9A924F8CA293F11178E23A1978D2F133D3 |
| **PIN (SHA-256)** | UgpUVparimk8QCjtWQaUQ7EGrtrykc/L8N66EhFY3VE = |
| **CRL-URLs** | http://crl4.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl3.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="digicert-cloud-services-ca-1"></a>**Digicert Cloud Services-Zertifizierungsstellen-1**

| **Betreff** | CN = Digicert Cloud Services ca-1<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | unsichere: 17:1a: 48: C6: F2:23:80:92:18: CD: 2e: D6: DD: C0: E8 |
| **Länge des öffentlichen Schlüssels** | RSA 2048-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Donnerstag, 24. September 2020 5:00 Uhr |
| **Gültigkeit nicht bis** | Dienstag, 24. September 2030 4:59 Uhr |
| **ID des Antragstellerschlüssels** | DD51D0A23173A973AE8FB4017E5D8C57CB9FF0F7 |
| **Autoritäts Schlüssel-ID** | KeyID: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | B3F6B64A07BB9611F47174407841F564FB991F29 |
| **Fingerabdruck (SHA-256)** | 5F88694615E4C61686E106B84C3338C6720C535F60D36F61282ED15E1977DD44 |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="digicert-global-root-ca"></a>**Globale Stammzertifizierungsstelle Digicert**

| **Betreff** | CN = Digicert globale Stammzertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Seriennummer** | 08:3B: E0:56:90:42:46: B1: a1:75:6a: C9:59:91: C7:4a |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 10 00:00:00 2006 UTC |
| **Gültigkeit nicht nach** | Nov 10 00:00:00 2031 UTC |
| **ID des Antragstellerschlüssels** | 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Autoritäts Schlüssel-ID** | keyid: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | A8985D3A65E5E5C4B2D7D66D40C6DD2FB19C5436 |
| **Fingerabdruck (SHA-256)** | 4348A0E9444C78CB265E058D5E8944B4D84F9662BD26DB257F8934A443C70161 |
| **PIN (SHA-256)** | r/mIkG3eEpVdm + u/ko/cwxzOMo1bk4TyHIlByibiA5E = |

### <a name="digicert-global-root-g2"></a>**Digicert, globales Stammverzeichnis G2**

| **Betreff** | CN = Digicert globales Stammverzeichnis G2<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globales Stammverzeichnis G2, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 03:3A: F1: E6: A7:11: A9: a0: BB: 28:64: B1:1D: 09: Fa: E5 |
| **Länge des öffentlichen Schlüssels** | RSA 2048-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Donnerstag, 1. August 2013 5:00 Uhr |
| **Gültigkeit nicht bis** | Mittwoch, Januar 2038 4:00 Uhr |
| **ID des Antragstellerschlüssels** | 4E2254201895E6E36EE60FFAFAB912ED06178F39 |
| **Autoritäts Schlüssel-ID** | KeyID: 4E: 22:54:20:18:95: E6: E3:6E: E6:: Fa: Fa: B9:12: Ed: 06:17:8F: 39 |
| **Fingerabdruck (SHA-1)** | DF3C24F9BFD666761B268073FE06D1CC8D4F82A4 |
| **Fingerabdruck (SHA-256)** | CB3CCBB76031E5E0138F8DD39A23F9DE47FFC35E43C1144CEA27D46A5AB1CB5F |

### <a name="digicert-high-assurance-ev-root-ca"></a>**Digicert High Assurance EV-Stammzertifizierungsstelle**

| **Betreff** | CN = Digicert High Assurance EV-Stammzertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Seriennummer** | 02: AC: 5C: 26:6a: 0B: 40:9 v: 8F: 0B: 79: F2: AE: 46:25:77 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 10 00:00:00 2006 UTC |
| **Gültigkeit nicht nach** | Nov 10 00:00:00 2031 UTC |
| **ID des Antragstellerschlüssels** | B1:3E: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Autoritäts Schlüssel-ID** | keyid: B1:3E: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Fingerabdruck (SHA-1)** | 5FB7EE0633E259DBAD0C4C9AE6D38F1A61C7DC25 |
| **Fingerabdruck (SHA-256)** | 7431E5F4C3C1CE4690774F0B61E05440883BA9A01ED00BA6ABD7806ED3B118CF |
| **PIN (SHA-256)** | WoiWRyIOVNa9ihaBciRSC7XHjliYS9VwUGOIud4PB18 = |

### <a name="digicert-sha2-extended-validation-server-ca"></a>**Digicert SHA2 Extended Validation Server-Zertifizierungsstelle**

| **Betreff** | CN = Digicert SHA2 Extended Validation Server-Zertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Seriennummer** | 0C: 79: A9:44: B0:8c: 11:95:20:92:61:5f: E2:6b: 1D: 83 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Oct 22 00:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Oct 22 00:00:00 2028 UTC |
| **ID des Antragstellerschlüssels** | 3D: D3:50: A5: D6: a0: AD: EE: F3:4a: 60:0A: 65: D3:21: D4: F8: F8: D6: ungleich |
| **Autoritäts Schlüssel-ID** | keyID: B1:3E: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Fingerabdruck (SHA-1)** | 7E2F3A4F8FE8FA8A5730AECA029696637E986F3F |
| **Fingerabdruck (SHA-256)** | 403E062A2653059113285BAF80A0D4AE422C848C9F78FAD01FC94BC5B87FEF1A |

### <a name="digicert-sha2-secure-server-ca"></a>**Digicert SHA2 Secure Server-Zertifizierungsstelle**

| **Betreff** | CN = Digicert SHA2 Secure Server-Zertifizierungsstelle<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 01: FD: a3: EB: 6E: ca: 75: C8:88:43:8B: 72:4B: CF: BC: 91 |
| **Länge des öffentlichen Schlüssels** | RSA 2048-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Freitag, 8. März 2013 4:00 Uhr |
| **Gültigkeit nicht bis** | Mittwoch, März 8, 2023 4:00 Uhr |
| **ID des Antragstellerschlüssels** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Autoritäts Schlüssel-ID** | KeyID: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Fingerabdruck (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**Digicert SHA2 Secure Server-Zertifizierungsstelle**

| **Betreff** | CN = Digicert SHA2 Secure Server-Zertifizierungsstelle<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 02:74:2e: AA: 17: ca: 8E: 21: C7:17: BB: 1f: FC: FD: 0C: a0 |
| **Länge des öffentlichen Schlüssels** | RSA 2048-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dienstag, September 22, 2020 5:00 Uhr |
| **Gültigkeit nicht bis** | Sonntag, September 22, 2030 4:59 Uhr |
| **ID des Antragstellerschlüssels** | 0F80611C823161D52F28E78D4638B42CE1C6D9E2 |
| **Autoritäts Schlüssel-ID** | KeyID: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | 626D44E704D1CEABE3BF0D53397464AC8080142C |
| **Fingerabdruck (SHA-256)** | C1AD7778796D20BCA65C889A2655021156528BB62FF5FA43E1B8E5A83E3D2EAA |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="digicert-tls-rsa-sha256-2020-ca1"></a>**Digicert TLS RSA SHA256 2020 CA1**

| **Betreff** | CN = Digicert TLS RSA SHA256 2020 CA1<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 0a: 35:08: D5:5C: 29:2B: 01:7D: F8: AD: 65: C0: undicht: F7: E4 |
| **Länge des öffentlichen Schlüssels** | RSA 2048-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mittwoch, September 23, 2020 5:00 Uhr |
| **Gültigkeit nicht bis** | Montag, September 23, 2030 4:59 Uhr |
| **ID des Antragstellerschlüssels** | B76BA2EAA8AA848C79EAB4DA0F98B2C59576B9F4 |
| **Autoritäts Schlüssel-ID** | KeyID: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | 6938FD4D98BAB03FAADB97B34396831E3780AEA1 |
| **Fingerabdruck (SHA-256)** | 25768713D3B459F9382D2A594F85F34709FD2A8930731542A4146FFB246BEC69 |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="entrust-root-certification-authority"></a>**Entrust-Stammzertifizierungsstelle**

| **Betreff** | CN = Entrust-Stammzertifizierungsstelle<br>OU = "(c) 2006 Entrust, Inc."<br>OU = www. Entrust. net/CPS wird durch Verweis übernommen<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Seriennummer** | 45:6b: 50:54 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 27 12:23:42 2006 UTC |
| **Gültigkeit nicht nach** | Nov 27 12:53:42 2026 UTC |
| **ID des Antragstellerschlüssels** | 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 4T |
| **Autoritäts Schlüssel-ID** | keyID: 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 4T |
| **Fingerabdruck (SHA-1)** | B31EB1B740E36C8402DADC37D44DF5D4674952F9 |
| **Fingerabdruck (SHA-256)** | 73C176434F1BC6D5ADF45B0E76E727287C8DE57616C1E6E6141A2B2CBC7D8E4C |

### <a name="entrust-root-certification-authority---g2"></a>**Entrust-Stammzertifizierungsstelle – G2**

| **Betreff** | CN = Entrust-Stammzertifizierungsstelle-G2<br>OU = &quot; (c) 2009 Entrust, Inc. – nur für autorisierte Verwendung&quot;<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Seriennummer** | 4a: 53:8c: 28 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Jul 07 17:25:54 2009 UTC |
| **Gültigkeit nicht nach** | Dec 07 17:55:54 2030 UTC |
| **ID des Antragstellerschlüssels** | 6a: 72:26:7a: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 8 d: 9F: 90:12:66: ab |
| **Fingerabdruck (SHA-1)** | 8CF427FD790C3AD166068DE81E57EFBB932272D4 |
| **Fingerabdruck (SHA-256)** | 43DF5774B03E7FEF5FE40D931A7BEDF1BB2E6B42738C4E6D3841103D3AA7F339 |
| **PIN (SHA-256)** | du6FkDdMcVQ3u8prumAo6t3i3G27uMP2EOhR8R0at/U = |

### <a name="entrustnet-certification-authority-2048"></a>**Entrust.net Certification Authority (2048)**

| **Betreff** | CN = Entrust. NET-Zertifizierungsstelle (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. durch Ref. (Limit s liab.)<br>O = Entrust. net |
| --- | --- |
| **Seriennummer** | 38:63: de: F8 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Dec 24 17:50:51 1999 UTC |
| **Gültigkeit nicht nach** | Jul 24 14:15:12 2029 UTC |
| **ID des Antragstellerschlüssels** | 55: E4:81: D1:11:80: be: D8:89: B9:08: a3:31: F9: a1:24:09:16: B9:70 |
| **Fingerabdruck (SHA-1)** | 503006091D97D4F5AE39F7CBE7927D7D652D3431 |
| **Fingerabdruck (SHA-256)** | 6DC47172E01CBCB0BF62580D895FE2B8AC9AD4F873801E0C10B9C837D21EB177 |
| **PIN (SHA-256)** | HqPF5D7WbC2imDpCpKebHpBnhs6fG1hiFBmgBGOofTg = |

### <a name="entrust-certification-authority---l1c"></a>**Entrust-Zertifizierungsstelle – L1C**

| **Betreff** | CN = Entrust-Zertifizierungsstelle – L1C<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA wird durch Verweis übernommen<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Entrust. NET-Zertifizierungsstelle (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. durch Ref. (Limits liab.)<br>O = Entrust. net |
| **Seriennummer** | 4C: 0E: 8c: 39 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 11 15:40:40 2011 UTC |
| **Gültigkeit nicht nach** | Nov 11 02:51:17 2021 UTC |
| **ID des Antragstellerschlüssels** | 1E: F1: ab: 89:06: F8:49: undicht: 01:33:77: EE: 14:7a: EE: 19:7C: 93:28:4D |
| **Autoritäts Schlüssel-ID** | keyid: 55: E4:81: D1:11:80: be: D8:89: B9:08: a3:31: F9: a1:24:09:16: B9:70 |
| **Fingerabdruck (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Fingerabdruck (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **PIN (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **CRL-URLs** | http://crl.entrust.net/2048ca.crl |
| **OCSP-URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1e"></a>**Entrust-Zertifizierungsstelle – L1E**

| **Betreff** | CN = Entrust-Zertifizierungsstelle – L1E<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA wird durch Verweis übernommen<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Entrust. NET-Zertifizierungsstelle (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. durch Ref. (Limits liab.)<br>O = Entrust. net |
| **Seriennummer** | 4C: 0E: C9:18 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 11 15:40:40 2011 UTC |
| **Gültigkeit nicht nach** | Nov 11 02:51:17 2021 UTC |
| **ID des Antragstellerschlüssels** | 5B: 41:8a: B2: C4:43: C1: BD: BF: C8:54:41:55:9d: E0:96: AD: FF: B9: a1 |
| **Autoritäts Schlüssel-ID** | keyid: 68:90: E4:67: A4: A6:53:80: C7:86:66: A4: F1: F7:4B: 43: FB: 84: BD: 4T |
| **Fingerabdruck (SHA-1)** | 8A000CC056F7D17349F045BEB0319A3B91C9F979 |
| **Fingerabdruck (SHA-256)** | 3C7A634E5778A0F731972B702DAE24B2CF2060219F607E69878B164C61A06C41 |
| **CRL-URLs** | http://crl.entrust.net/rootca1.crl |
| **OCSP-URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1k"></a>**Entrust-Zertifizierungsstelle – L1K**

| **Betreff** | CN = Entrust-Zertifizierungsstelle – L1K<br>OU = &quot; (c) 2012 Entrust, Inc. – nur für autorisierte Verwendung&quot;<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Entrust-Stammzertifizierungsstelle-G2<br>OU = &quot; (c) 2009 Entrust, Inc. – nur für autorisierte Verwendung&quot;<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| **Seriennummer** | 0E: e9:4C: C3:00:00:00:00:51: D3:77:85 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Oct 05 19:13:56 2015 UTC |
| **Gültigkeit nicht nach** | Dec 05 19:43:56 2030 UTC |
| **ID des Antragstellerschlüssels** | 82: a2:70:74: DD: BC: 53:3f: CF: 7B: D4: F7: CD: 7F: A7:60: C6:0A: 4C: BF |
| **Autoritäts Schlüssel-ID** | keyid: 6a: 72:26:7a: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 4D: 9F: 90:12:66: ab |
| **Fingerabdruck (SHA-1)** | F21C12F46CDB6B2E16F09F9419CDFF328437B2D7 |
| **Fingerabdruck (SHA-256)** | 13EFB39A2F6654E8C67BD04F4C6D4C90CD6CAB5091BCEDC73787F6B77D3D3FE7 |
| **PIN (SHA-256)** | 980Ionqp3wkYtN9SZVgMzuWQzJta1nfxNPwTem1X0uc = |
| **CRL-URLs** | http://crl.entrust.net/g2ca.crl |
| **OCSP-URLs** | http://ocsp.entrust.net |

### <a name="entrust-certification-authority---l1m"></a>**Entrust-Zertifizierungsstelle – L1M**

| **Betreff** | CN = Entrust-Zertifizierungsstelle-L1M, OU = &quot; (c) 2014 Entrust, Inc. – nur für autorisierte Verwendung&quot;<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Entrust-Stammzertifizierungsstelle-G2<br>OU = &quot; (c) 2009 Entrust, Inc. – nur für autorisierte Verwendung&quot;<br>OU = siehe www.Entrust.net/legal-terms<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| **Seriennummer** | 61: a1: E7: D2:00:00:00:00:51: D3:66: A6 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dec 15 07:25:03 2014 UTC |
| **Gültigkeit nicht nach** | Oct 15 08:55:03 2030 UTC |
| **ID des Antragstellerschlüssels** | C3: F7: D0: B5:2a: 30: AD: AF: 0d: 91:21:70:39:54: DD: BC: 89:70: C7:3A |
| **Autoritäts Schlüssel-ID** | keyid: 6a: 72:26:7a: D0:1E: EF: 7D: E7:3B: 69:51: D4:6C: 4D: 9F: 90:12:66: ab |
| **Fingerabdruck (SHA-1)** | CC136695639065FAB47074D28C55314C66077E90 |
| **Fingerabdruck (SHA-256)** | 75C5B3F01FD1F51A2C447AB7C785D72E69FA9C472C08571E7EADF3B8EABAE70C |
| **CRL-URLs** | http://crl.entrust.net/g2ca.crl |
| **OCSP-URLs** | http://ocsp.entrust.net |

### <a name="microsoft-azure-tls-issuing-ca-01"></a>**Microsoft Azure TLS ausstellende Zertifizierungsstelle 01**

| **Betreff** | CN = Microsoft Azure TLS-Ausgabe-Zertifizierungsstelle 01<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globales Stammverzeichnis G2, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 0a: AF: A6: C5: ca: 63: C4:51:41: EA: 3B: E1: F7: C7:53:17 |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha384RSA |
| **Gültigkeit nicht vor** | Mittwoch, 29. Juli 2020 5:30 Uhr |
| **Gültigkeit nicht bis** | Donnerstag, 27. Juni 2024 4:59 Uhr |
| **ID des Antragstellerschlüssels** | 0F205DD7A15795DB92CF2BD0C7C27704CE728076 |
| **Autoritäts Schlüssel-ID** | KeyID: 4E: 22:54:20:18:95: E6: E3:6E: E6:: Fa: Fa: B9:12: Ed: 06:17:8F: 39 |
| **Fingerabdruck (SHA-1)** | 2F2877C5D778C31E0F29C7E371DF5471BD673173 |
| **Fingerabdruck (SHA-256)** | 24C7299864E0A2A6964F551C0E8DF2461532FA8C48E4DBBB6080716691F190E5 |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-02"></a>**Microsoft Azure TLS ausstellende CA 02**

| **Betreff** | CN = Microsoft Azure TLS ausstellende CA 02<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globales Stammverzeichnis G2, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 0C: 6a: e9:7C: CE: D5:99:83:86:90: a0:0A: 9e: A5:32:14 |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha384RSA |
| **Gültigkeit nicht vor** | Mittwoch, 29. Juli 2020 5:30 Uhr |
| **Gültigkeit nicht bis** | Donnerstag, 27. Juni 2024 4:59 Uhr |
| **ID des Antragstellerschlüssels** | 00AB91FC216226979AA8791B61419060A96267FD |
| **Autoritäts Schlüssel-ID** | KeyID: 4E: 22:54:20:18:95: E6: E3:6E: E6:: Fa: Fa: B9:12: Ed: 06:17:8F: 39 |
| **Fingerabdruck (SHA-1)** | E7EEA674CA718E3BEFD90858E09F8372AD0AE2AA |
| **Fingerabdruck (SHA-256)** | 15A98761EBE011554DA3A46D206B0812CB2EB69AE87AAA11A6DD4CB84ED5142A |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-05"></a>**Microsoft Azure TLS ausstellende CA 05**

| **Betreff** | CN = Microsoft Azure TLS ausstellende CA 05<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globales Stammverzeichnis G2, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 0d: 7B: Ed: e9:7D: 82:09:96:7a: 52:63:1B: 8B: DD: 18: BD |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha384RSA |
| **Gültigkeit nicht vor** | Mittwoch, 29. Juli 2020 5:30 Uhr |
| **Gültigkeit nicht bis** | Donnerstag, 27. Juni 2024 4:59 Uhr |
| **ID des Antragstellerschlüssels** | C7B29C7F1CE3B85AEFE9681AA85D94C126526A68 |
| **Autoritäts Schlüssel-ID** | KeyID: 4E: 22:54:20:18:95: E6: E3:6E: E6:: Fa: Fa: B9:12: Ed: 06:17:8F: 39 |
| **Fingerabdruck (SHA-1)** | 6C3AF02E7F269AA73AFD0EFF2A88A4A1F04ED1E5 |
| **Fingerabdruck (SHA-256)** | D6831BA43607F5AC19778D627531562AF55145F191CAB5EFAFA0E0005442B302 |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-azure-tls-issuing-ca-06"></a>**Microsoft Azure TLS ausstellende CA 06**

| **Betreff** | CN = Microsoft Azure TLS-Ausgabe-Zertifizierungsstelle 06<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globales Stammverzeichnis G2, ou = www. Digicert. com, O = Digicert Inc, C = US |
| **Seriennummer** | 02: E7:91:71: FB: 80:21: e9:3f: E2: D9:83:83:4C: 50: C0 |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha384RSA |
| **Gültigkeit nicht vor** | Mittwoch, 29. Juli 2020 5:30 Uhr |
| **Gültigkeit nicht bis** | Donnerstag, 27. Juni 2024 4:59 Uhr |
| **ID des Antragstellerschlüssels** | D5C1673AC2A39DF477525B59123829E65568BBA5 |
| **Autoritäts Schlüssel-ID** | KeyID: 4E: 22:54:20:18:95: E6: E3:6E: E6:: Fa: Fa: B9:12: Ed: 06:17:8F: 39 |
| **Fingerabdruck (SHA-1)** | 30E01761AB97E59A06B41EF20AF6F2DE7EF4F7B0 |
| **Fingerabdruck (SHA-256)** | 48FF8B494668C752304B48BFE818758987DEF6582E5F09B921F4B60BB3D6A8DD |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootG2.crl http://crl4.digicert.com/DigiCertGlobalRootG2.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-1"></a>**Microsoft IT TLS-Zertifizierungsstelle 1**

| **Betreff** | CN = Microsoft IT TLS-Zertifizierungsstelle 1<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 08: B8:7a: 50:1B: be: "9": da: 2D: 16:4D: 3E: 39:51: BF: 55 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 20 12:51:28 2016 UTC |
| **Gültigkeit nicht nach** | Mai 20 12:51:28 2024 UTC |
| **ID des Antragstellerschlüssels** | 58:88:9F: D6: DC: 9:: 48:22: B7:14:3E: FF: 84:88: E8: E6:85: FF: Fa: 7D |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 417E225037FBFAA4F95761D5AE729E1AEA7E3A42 |
| **Fingerabdruck (SHA-256)** | 4FF404F02E2CD00188F15D1C00F4B6D1E38B5A395CF85314EAEBA855B6A64B75 |
| **PIN (SHA-256)** | xjXxgkOYlag7jCtR5DreZm9b61iaIhd + G3 + b2LiybIw = |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-2"></a>**Microsoft IT TLS-Zertifizierungsstelle 2**

| **Betreff** | CN = Microsoft IT TLS-Zertifizierungsstelle 2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | in: 2C: 10: C9:5B: 06: C0:93:7F: B8: D4:49: F8:3E: 85:69 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 20 12:51:57 2016 UTC |
| **Gültigkeit nicht nach** | Mai 20 12:51:57 2024 UTC |
| **ID des Antragstellerschlüssels** | 91:9e: 3B: 44:6C: 3D: 57:9 c: 42:77:2a: 34: D7: Z4: D1: cc: 4a: 97:2C: da |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 54D9D20239080C32316ED9FF980A48988F4ADF2D |
| **Fingerabdruck (SHA-256)** | 4E107C981B42ACBE41C01067E16D44DB64814D4193E572317EA04B87C79C475F |
| **PIN (SHA-256)** | wBdPad95AU7OgLRs0FU/E6ILO1MSCM84kJ9y0H + TT7s = |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-4"></a>**Microsoft IT TLS-Zertifizierungsstelle 4**

| **Betreff** | CN = Microsoft IT TLS ca 4<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 0B: 6a: B3: B0:3E: B1: A9: F6: C4:60:92:6a: A8: CD: FE: B3 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 20 12:52:38 2016 UTC |
| **Gültigkeit nicht nach** | Mai 20 12:52:38 2024 UTC |
| **ID des Antragstellerschlüssels** | 7a: 7B: 8c: C1: CF: E7: a0: ca: 1C: D4:6b: Fa: FB: E1:33: C3: in: 1a: a2:9d |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 8A38755D0996823FE8FA3116A277CE446EAC4E99 |
| **Fingerabdruck (SHA-256)** | 5FFAC43E0DDC5B4AF2B696F6BC4DB7E91DF314BB8FE0D0713A0B1A7AD2A68FAC |
| **PIN (SHA-256)** | wUY9EOTJmS7Aj4fDVCu/KeE + + mV7FgIcbn4WhMz1I2k = |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-it-tls-ca-5"></a>**Microsoft IT TLS ca 5**

| **Betreff** | CN = Microsoft IT TLS ca 5<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 08:88: CD: 52:5f: 19:24:44:4D: 14: A5:82:91: de: B9:52 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 20 12:53:03 2016 UTC |
| **Gültigkeit nicht nach** | Mai 20 12:53:03 2024 UTC |
| **ID des Antragstellerschlüssels** | 08: FE: 25:9F: 74: EA: 87:04: C2: BC: BB: 8E: A8:38:5f: 33: C6: D1:6C: 65 |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | AD898AC73DF333EB60AC1F5FC6C4B2219DDB79B7 |
| **Fingerabdruck (SHA-256)** | F0EE5914ED94C7252D058B4E39808AEE6FA8F62CF0974FB7D6D2A9DF16E3A87F |
| **PIN (SHA-256)** | RCbqB + W8nwjznTeP4O6VjqcwdxIgI79eBpnBKRr32gc = |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-01"></a>**Microsoft RSA TLS-Zertifizierungsstelle 01**

| **Betreff** | CN = Microsoft RSA TLS-Zertifizierungsstelle 01<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust root, ou = Cybertrust, O = Baltimore, C = IE |
| **Seriennummer** | 5F: 14:96:: 20:20:69:99: Z4: D5: C7: AC: 78:89:41: E2 |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dienstag, 21. Juli 2020 4:00 Uhr |
| **Gültigkeit nicht bis** | Dienstag, 8. Oktober 2024 12:00 Uhr |
| **ID des Antragstellerschlüssels** | B5760C3011CEC792424D4CC75C2CC8A90CE80B64 |
| **Autoritäts Schlüssel-ID** | KeyID: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 703D7A8F0EBF55AAA59F98EAF4A206004EB2516A |
| **Fingerabdruck (SHA-256)** | 04EEEA8E50B4775B3C24797262917EE50002EC4C75B56CDF3EE1C18CFCA5BA52 |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="microsoft-rsa-tls-ca-02"></a>**Microsoft RSA TLS-Zertifizierungsstelle 02**

| **Betreff** | CN = Microsoft RSA TLS-Zertifizierungsstelle 02<br>O = Microsoft Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust root, ou = Cybertrust, O = Baltimore, C = IE |
| **Seriennummer** | Autobahn: A7:47:22: C5:3D: 88: C8:1f: 58:9e: FB: 1f: 9d: 4a: 3A |
| **Länge des öffentlichen Schlüssels** | RSA 4096-Bits |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dienstag, 21. Juli 2020 4:00 Uhr |
| **Gültigkeit nicht bis** | Dienstag, 8. Oktober 2024 12:00 Uhr |
| **ID des Antragstellerschlüssels** | FF2F7FE106F438F32DED258D98C2FE0EF66CFCFA |
| **Autoritäts Schlüssel-ID** | KeyID: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | B0C2D2D13CDD56CDAA6AB6E2C04440BE4A429C75 |
| **Fingerabdruck (SHA-256)** | 05E4005DB0C382F3BD66B47729E9011577601BF6F7B287E9A52CED710D258346 |
| **CRL-URLs** | http://crl3.digicert.com/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |
