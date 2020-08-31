---
title: Verschlüsselungs Ketten
f1.keywords:
- NOCSH
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/3/2020
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
description: Hier wird eine vollständige Liste der Stammzertifikate und Zertifizierungsstellen (CAS) in Office 365 angezeigt.
ms.openlocfilehash: c0f63f6e4ebc288f8b06d608af81a485e5f71e8a
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47307444"
---
# <a name="encryption-chains"></a>Verschlüsselungs Ketten

Office 365 nutzt eine Reihe unterschiedlicher Zertifikatanbieter. Im folgenden wird die vollständige Liste der bekannten Office 365 Stammzertifikate beschrieben, auf die Kunden beim Zugriff auf Office 365 stoßen können. Informationen zu den Zertifikaten, die Sie möglicherweise in ihrer eigenen Infrastruktur installieren müssen, finden Sie unter [Planen von Drittanbieter-SSL-Zertifikaten für Office 365](https://docs.microsoft.com/microsoft-365/enterprise/plan-for-third-party-ssl-certificates). Die folgenden Zertifikatinformationen gelten für alle globalen und nationalen Cloud-Instanzen von Office 365.

>[!NOTE]
>Informationen zu Zertifikaten, die für **DoD-und gcc-High** -Kunden gelten, finden Sie unter [Office 365 Encryption Chains-DoD und gcc High](encryption-office-365-certificate-chains-itar.md).

| **Zertifikattyp** | **P7B herunterladen** | **CRL-Endpunkte** | **OCSP-Endpunkte** | **AIA-Endpunkte** |
| --- | --- | --- | --- | --- |
| Öffentlich vertrauenswürdige Stammzertifikate | [Office 365-Stammzertifikat-Bundle (P7B)](https://download.microsoft.com/download/A/5/A/A5AE01F3-D19B-4A11-9407-801263CEF72C/O365_Root_Certs_20170321.p7b) | crl.globalsign.net<br>www.d-trust.net | Nicht zutreffend | Nicht zutreffend |
| Öffentlich vertrauenswürdige Zwischenzertifikate | [Office 365 Intermediate Certificate Bundle (P7B)](https://download.microsoft.com/download/4/D/5/4D5339A4-0A4A-46AB-AE52-B179DEDA4BEC/O365_Intermediate_Certs_20170321.p7b) | cdp1.public-trust.com<br>crl.cnnic.cn<br>crl.entrust.net<br>crl.globalsign.com<br>crl.globalsign.net<br>crl.identrust.com<br>crl.thawte.com<br>crl3.digicert.com<br>crl4.digicert.com<br>s1.symcb.com<br>www.d-trust.net | isrg.trustid.ocsp.identrust.com<br>ocsp.digicert.com<br>ocsp.entrust.net<br>ocsp.globalsign.com<br>ocsp.omniroot.com<br>ocsp.startssl.com<br>ocsp.thawte.com<br>ocsp2.globalsign.com<br>ocspcnnicroot.cnnic.cn<br>root-c3-ca2-2009.ocsp.d-trust.net<br>root-c3-ca2-ev-2009.ocsp.d-trust.net<br>s2.symcb.com | aia.startssl.com<br>apps.identrust.com<br>cacert.omniroot.com<br>www.cnnic.cn |

Erweitern Sie die unten aufgeführten Stamm-und zwischen Abschnitte, um weitere Details zu den Zertifikatanbietern anzuzeigen.

## <a name="office-365-root-certificate-details"></a>**Details zu Office 365 Stammzertifikaten**

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

### <a name="cnnic-root"></a>**CNNIC-Stamm**

| **Betreff** | CN = CNNIC-Stamm<br>O = CNNIC<br>C = CN |
| --- | --- |
| **Seriennummer** | 49:33:00:01 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Apr 16 07:09:14 2007 UTC |
| **Gültigkeit nicht nach** | Apr 16 07:09:14 2027 UTC |
| **ID des Antragstellerschlüssels** | 65: F2:31: AD: 2a: F7: F7: DD: 52:96:0A: C7:02: C1:0E: EF: A6: D5:3B: 11 |
| **Autoritäts Schlüssel-ID** | keyid: 65: F2:31: AD: 2a: F7: F7: DD: 52:96:0A: C7:02: C1:0E: EF: A6: D5:3B: 11 |
| **Fingerabdruck (SHA-1)** | 8BAF4C9B1DF02A92F7DA128EB91BACF498604B6F |
| **Fingerabdruck (SHA-256)** | E28393773DA845A679F2080CC7FB44A3B7A1C3792CB7EB7729FDCB6A8D99AEA7 |
| **PIN (SHA-256)** | H0IkzshPyZztiB/2/P0 + IfjFGcVHqmpd094kcwLOUNE = |

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

### <a name="d-trust-root-class-3-ca-2-2009"></a>**D-Trust-Stammklasse 3 ca 2 2009**

| **Betreff** | CN = D-Trust Stammklasse 3 ca 2 2009<br>O = D-Trust GmbH<br>C = de |
| --- | --- |
| **Seriennummer** | 09:83: F3 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Nov 05 08:35:58 2009 UTC |
| **Gültigkeit nicht nach** | Nov 05 08:35:58 2029 UTC |
| **ID des Antragstellerschlüssels** | FD: da: 14: C4:9F: 30: de: 21: BD: 1E: 42:39: FC: ab: 63:23:49: E0: F1:84 |
| **Fingerabdruck (SHA-1)** | 58E8ABB0361533FB80F79B1B6D29D3FF8D5F00F0 |
| **Fingerabdruck (SHA-256)** | 49E7A442ACF0EA6287050054B52564B650E4F49E42E348D6AA38E039E957B1C1 |
| **PIN (SHA-256)** | 7KDxgUAs56hlKzG00DbfJH46MLf0GlDZHsT5CwBrQ6E = |
| **CRL-URLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |

### <a name="d-trust-root-class-3-ca-2-ev-2009"></a>**D-Trust-Stammklasse 3 ca 2 EV 2009**

| **Betreff** | CN = D-Trust Stammklasse 3 ca 2 EV 2009<br>O = D-Trust GmbH<br>C = de |
| --- | --- |
| **Seriennummer** | 09:83: F4 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Nov 05 08:50:46 2009 UTC |
| **Gültigkeit nicht nach** | Nov 05 08:50:46 2029 UTC |
| **ID des Antragstellerschlüssels** | D3:94:8a: 4C: 62:13:2a: 19:2e: cc: AF: 72:8a: 7D: 36: D7:9a: 1C: DC: 67 |
| **Fingerabdruck (SHA-1)** | 96C91B0B95B4109842FAD0D82279FE60FAB91683 |
| **Fingerabdruck (SHA-256)** | EEC5496B988CE98625B934092EEC2908BED0B0F316C2D4730C84EAF1F3D34881 |
| **PIN (SHA-256)** | /zQvtsTIvTCkcG9zSJU58Z5uSMwF9GJUZU9mENvFQOk = |
| **CRL-URLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |

### <a name="dst-root-ca-x3"></a>**DST-Stammzertifizierungsstelle X3**

| **Betreff** | CN = DST-Stammzertifizierungsstelle X3<br>O = digitale Signatur Trust Co. |
| --- | --- |
| **Seriennummer** | 44: AF: B0:80: D6: a3:27: BA: 89:30:39:86:2e: F8:40:6B |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Sep 30 21:12:19 2000 UTC |
| **Gültigkeit nicht nach** | Sep 30 14:01:15 2021 UTC |
| **ID des Antragstellerschlüssels** | C4: A7: B1: A4:7B: 2C: 71: Fa: DB: E1:4B: 90:75: FF: C4:15:60:85:89:10 |
| **Fingerabdruck (SHA-1)** | DAC9024F54D8F6DF94935FB1732638CA6AD77C13 |
| **Fingerabdruck (SHA-256)** | 0687260331A72403D909F105E69BCF0D32E1BD2493FFC6D9206D11BCD6770739 |
| **PIN (SHA-256)** | Vjs8r4z + 80wjNcr1YKepWQboSIRi63WsWXhIMN + eWys = |

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

### <a name="globalsign"></a>**GlobalSign**

| **Betreff** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign-Stammzertifizierungsstelle-R2 |
| --- | --- |
| **Seriennummer** | 04:00:00:00:00:01: zu: 86:26: E6:0d |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Dec 15 08:00:00 2006 UTC |
| **Gültigkeit nicht nach** | Dec 15 08:00:00 2021 UTC |
| **ID des Antragstellerschlüssels** | 9 – 7: E2:07:57:67:1C: 1E: C0:6a: 06: de: 59: B4:9a: 2D: DF: DC: 19:86:2E |
| **Autoritäts Schlüssel-ID** | keyid: 9a: E2:07:57:67:1C: 1E: C0:6a: 06: de: 59: B4:9a: 2D: DF: DC: 19:86:2E |
| **Fingerabdruck (SHA-1)** | 75E0ABB6138512271C04F85FDDDE38E4B7242EFE |
| **Fingerabdruck (SHA-256)** | CA42DD41745FD0B81EB902362CF9D8BF719DA1BD1B1EFC946F5B4C99F42C1B9E |
| **PIN (SHA-256)** | iie1VXtL7HzAMF +/PVPR9xzT80kQxdZeJ + zduCB3uj0 = |
| **CRL-URLs** | http://crl.globalsign.net/root-r2.crl |

### <a name="globalsign-root-ca"></a>**GlobalSign Root CA**

| **Betreff** | CN = GlobalSign-Stammzertifizierungsstelle<br>OU = Stammzertifizierungsstelle<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Seriennummer** | 04:00:00:00:00:01:15:4B: 5A: C3:94 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Sep 01 12:00:00 1998 UTC |
| **Gültigkeit nicht nach** | Jan 28 12:00:00 2028 UTC |
| **ID des Antragstellerschlüssels** | 60:7B: 66:1a: 45:0d: 97: ca: 89:50:2F: 7D: 04: CD: 34: A8: FF: FC: FD: 4B |
| **Fingerabdruck (SHA-1)** | B1BC968BD4F49D622AA89A81F2150152A41D829C |
| **Fingerabdruck (SHA-256)** | EBD41040E4BB3EC742C9E381D31EF2A41A48B6685C96E7CEF3C1DF6CD4331C99 |
| **PIN (SHA-256)** | K87oWBWM9UZfyddvDfoxL + 8lpNyoUB2ptGtn0fv6G2Q = |

### <a name="thawte-primary-root-ca---g3"></a>**primäres Thawte-Stammverzeichnis ca-G3**

| **Betreff** | CN = Thawte Primary Root CA-G3<br>OU = &quot; (c) 2008 Thawte, Inc. – nur für autorisierte Verwendung&quot;<br>OU = Certification Services Division<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| --- | --- |
| **Seriennummer** | 60:01:97: B7:46: A7: EA: B4: B4:9a: D6:4B: 2F: F7:90: FB |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Apr 02 00:00:00 2008 UTC |
| **Gültigkeit nicht nach** | Dec 01 23:59:59 2037 UTC |
| **ID des Antragstellerschlüssels** | AD: 6C: AA: 94:60:9/9: Ed: E4: FF: Fa: 3E: 0A: 74:2B: 63:03: F7: B6:59: BF |
| **Fingerabdruck (SHA-1)** | F18B538D1BE903B6A6F056435B171589CAF36BF2 |
| **Fingerabdruck (SHA-256)** | 4B03F45807AD70F21BFC2CAE71C9FDE4604C064CF5FFB686BAE5DBAAD7FDD34C |
| **PIN (SHA-256)** | GQbGEk27Q4V40A4GbVBUxsN/D6YCjAVUXgmU7drshik = |

### <a name="verisign-class-3-public-primary-certification-authority---g5"></a>**VeriSign Class 3 Public Primary Certification Authority-G5**

| **Betreff** | CN = VeriSign Class 3 Public Primary Certification Authority-G5<br>OU = &quot; (c) 2006 VeriSign, Inc. – nur für autorisierte Verwendung&quot;<br>OU = VeriSign Trust-Netzwerk<br>O = &quot; VeriSign, Inc.&quot;<br>C = US |
| --- | --- |
| **Seriennummer** | 18: da: D1:9e: 26:7D: E8: BB: 4a: 21:58: CD: cc: 6b: 3B: 4a |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 08 00:00:00 2006 UTC |
| **Gültigkeit nicht nach** | Jul 16 23:59:59 2036 UTC |
| **ID des Antragstellerschlüssels** | 7F: D3:65: A7: C2: DD: EC: BB: F0:30:09: F3:43:39: Fa: 02: AF: 33:31:33 |
| **Fingerabdruck (SHA-1)** | 4EB6D578499B1CCF5F581EAD56BE3D9B6744A5E5 |
| **Fingerabdruck (SHA-256)** | 9ACFAB7E43C8D880D06B262A94DEEEE4B4659989C3D0CAF19BAF6405E41AB7DF |
| **PIN (SHA-256)** | JbQbUG5JMJUoI6brnx0x3vZF6jilxsapbXGVfjhN8Fg = |

## <a name="office-365-intermediate-certificate-details"></a>**Details zu Office 365 Zwischenzertifikaten**

### <a name="cnnic-sha256-ssl"></a>**CNNIC SHA256 SSL**

| **Betreff** | CN = CNNIC SHA256 SSL <br>O = CNNIC SHA256 SSL <br>C = CN |
| --- | --- |
| **Aussteller** | CN = CNNIC-Stamm <br>O = CNNIC <br>C = CN |
| **Seriennummer** | 49:33:00:7C |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dec 18 12:32:18 2014 UTC |
| **Gültigkeit nicht nach** | Dec 18 12:32:18 2024 UTC |
| **ID des Antragstellerschlüssels** | B7: D1:59:8B: 8c: 0d: 06:28:47:23:00:3A: 36:04: A5: EE: 38:76:53:3C |
| **Autoritäts Schlüssel-ID** | keyid: 65: F2:31: AD: 2a: F7: F7: DD: 52:96:0A: C7:02: C1:0E: EF: A6: D5:3B: 11 |
| **Fingerabdruck (SHA-1)** | FC844648FC708433921BE88B18C48787A3E2813E |
| **Fingerabdruck (SHA-256)** | FA8B9F99DBB94E7B772AA9190846E777047C15C7A3BF4A1AF9C0CA984A689511 |
| **PIN (SHA-256)** | dKZRcLDh7hBNZTmTIHOGJ6C2Om/ITjUCPkOnLTnrZXk = |
| **AIA-URLs** | http://www.cnnic.cn/download/cert/CNNICROOT.cer |
| **CRL-URLs** | ldap:///CN=crl1,%20OU=crl,%20O=CNNIC,%20C=CN?certificateRevocationList;binary,authorityRevocationList;binary,deltaRevocationList;binary<br>http://crl.cnnic.cn/download/rootsha2crl/CRL1.crl |
| **OCSP-URLs** | <http://ocspcnnicroot.cnnic.cn> |

### <a name="d-trust-ssl-class-3-ca-1-2009"></a>**D-Trust SSL-Klasse 3 ca 1 2009**

| **Betreff** | CN = D-Trust SSL-Klasse 3 ca 1 2009<br>O = D-Trust GmbH<br>C = de |
| --- | --- |
| **Aussteller** | CN = D-Trust Stammklasse 3 ca 2 2009<br>O = D-Trust GmbH<br>C = de |
| **Alternativer Antragsteller Name** | RFC822 Name=Info@d-Trust.net<br>URL =http://www.d-trust.net |
| **Seriennummer** | 09:90:63 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Nov 12 12:46:55 2009 UTC |
| **Gültigkeit nicht nach** | Nov 05 08:35:58 2029 UTC |
| **ID des Antragstellerschlüssels** | 50:19:32:94:9a: C4: B5:04:4D: 56: D0: C0:83:21: D5:35:55: B0: B1:7a |
| **Autoritäts Schlüssel-ID** | keyid: FD: da: 14: C4:9F: 30: de: 21: BD: 1E: 42:39: FC: ab: 63:23:49: E0: F1:84 |
| **Fingerabdruck (SHA-1)** | 2FC5DE6528CDBE50A14C382FC1DE524FAABF95FC |
| **Fingerabdruck (SHA-256)** | 6AC159B4C2BC8E729F3B84642EF1286BCC80D775FE278C740ADA468D59439025 |
| **PIN (SHA-256)** | 9w0QP9HzLXkfs + 4zENaUFq2XKcQON1oyksoJ + Gg2AZE = |
| **CRL-URLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_2009.crl |
| **OCSP-URLs** | http://root-c3-ca2-2009.ocsp.d-trust.net |

### <a name="d-trust-ssl-class-3-ca-1-ev-2009"></a>**D-Trust SSL-Klasse 3 ca 1 EV 2009**

| **Betreff** | CN = D-Trust SSL-Klasse 3 ca 1 EV 2009<br>O = D-Trust GmbH<br>C = de |
| --- | --- |
| **Aussteller** | CN = D-Trust Stammklasse 3 ca 2 EV 2009<br>O = D-Trust GmbH<br>C = de |
| **Alternativer Antragsteller Name** | RFC822 Name=Info@d-Trust.net<br>URL =http://www.d-trust.net |
| **Seriennummer** | 09:90:64 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Nov 12 12:52:43 2009 UTC |
| **Gültigkeit nicht nach** | Nov 05 08:50:46 2029 UTC |
| **ID des Antragstellerschlüssels** | AC: Ed: A5:9d: 7a: a2: B6:43: F1:18:8a: 25:6a: 6C: B1: cc: A8: F2:5A: D4 |
| **Autoritäts Schlüssel-ID** | keyid: D3:94:8a: 4C: 62:13:2a: 19:2e: cc: AF: 72:8a: 7D: 36: D7:9a: 1C: DC: 67 |
| **Fingerabdruck (SHA-1)** | 1069423D308D0FC54575059638560FC7556E32B3 |
| **Fingerabdruck (SHA-256)** | B0935DC04B4E60C0C42DEF7EC57A1B1D8F958D17988E71CC80A8CF5E635BA5B4 |
| **PIN (SHA-256)** | lv5BNZ5aWd27ooolULDolFTwIaaWjHvG4yyH3rss4X8 = |
| **CRL-URLs** | ldap://directory.d-trust.net/CN=D-TRUST%20Root%20Class%203%20CA%202%20EV%202009,O=D-Trust%20GmbH,C=DE?certificaterevocationlist<br>http://www.d-trust.net/crl/d-trust\_root\_class\_3\_ca\_2\_ev\_2009.crl |
| **OCSP-URLs** | http://root-c3-ca2-ev-2009.ocsp.d-trust.net |

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

### <a name="digicert-sha2-high-assurance-server-ca"></a>**Digicert SHA2 High Assurance Server-Zertifizierungsstelle**

| **Betreff** | CN = Digicert SHA2 High Assurance Server-Zertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert High Assurance EV-Stammzertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| **Seriennummer** | 04: E1: E7: A4: DC: 5C: F2: F3:4T: C0:2B: 42: B8:5D: 15:9F |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Oct 22 12:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Oct 22 12:00:00 2028 UTC |
| **ID des Antragstellerschlüssels** | 51:68: FF: 90: AF: 02:07:75:3C: cc: D9:65:64:62: a2:12: B8:59:72:3B |
| **Autoritäts Schlüssel-ID** | keyid: B1:3E: C3:69:03: F8: BF: 47:01: D4:98:26:1a: 08:02: EF: 63:64:2B: C3 |
| **Fingerabdruck (SHA-1)** | A031C46782E6E6C662C2C87C76DA9AA62CCABD8E |
| **Fingerabdruck (SHA-256)** | 19400BE5B7A31FB733917700789D2F0A2471C0C9D506C0E504C06C16D7CB17C0 |
| **PIN (SHA-256)** | k2v657xBsOVe1PQRwOsHsw3bsGT2VzIqz5K + 59sNQws = |
| **CRL-URLs** | http://crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="digicert-sha2-secure-server-ca"></a>**Digicert SHA2 Secure Server-Zertifizierungsstelle**

| **Betreff** | CN = Digicert SHA2 Secure Server-Zertifizierungsstelle<br>O = Digicert Inc.<br>C = US |
| --- | --- |
| **Aussteller** | CN = Digicert globale Stammzertifizierungsstelle<br>OU = www. Digicert. com<br>O = Digicert Inc.<br>C = US |
| **Seriennummer** | 01: FD: a3: EB: 6E: ca: 75: C8:88:43:8B: 72:4B: CF: BC: 91 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mär 08 12:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Mär 08 12:00:00 2023 UTC |
| **ID des Antragstellerschlüssels** | unsichere: 80:61:1C: 82:31:61: D5:2F: 28: E7:8-8:46:38: B4:2C: E1: C6: D9: E2 |
| **Autoritäts Schlüssel-ID** | keyid: 03: de: 50:35:56: D1:4C: BB: 66: F0: a3: E2:1B: 1B: C3:97: B2:3D: D1:55 |
| **Fingerabdruck (SHA-1)** | 1FB86B1168EC743154062E8C9CC5B171A4B7CCB4 |
| **Fingerabdruck (SHA-256)** | 154C433C491929C5EF686E838E323664A00E6A0D822CCC958FB4DAB03E49A08F |
| **PIN (SHA-256)** | 5kJvNEMw0KjrCAu7eXY5HZdvyCS13BbA0VJG1RSP91w = |
| **CRL-URLs** | http://crl3.digicert.com/DigiCertGlobalRootCA.crl<br>http://crl4.digicert.com/DigiCertGlobalRootCA.crl |
| **OCSP-URLs** | http://ocsp.digicert.com |

### <a name="entrust-certification-authority---l1c"></a>**Entrust-Zertifizierungsstelle – L1C**

| **Betreff** | CN = Entrust-Zertifizierungsstelle – L1C<br>OU = &quot; (c) 2009 Entrust, Inc.&quot;<br>OU = www. Entrust. net/RPA wird durch Verweis übernommen<br>O = &quot; Entrust, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Entrust. NET-Zertifizierungsstelle (2048)<br>OU = (c) 1999 Entrust.net Limited<br>OU = www. Entrust. net/CPS \_ 2048 incorp. durch Ref. (Limits liab.)<br>O = Entrust. net |
| **Seriennummer** | 4C: 0E: 8c: 39 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha1RSA |
| **Gültigkeit nicht vor** | Nov 11 15:40:40 2011 UTC |
| **Gültigkeit nicht nach** | Nov 12 02:51:17 2021 UTC |
| **ID des Antragstellerschlüssels** | 1E: F1: ab: 89:06: F8:49: undicht: 01:33:77: EE: 14:7a: EE: 19:7C: 93:28:4D |
| **Autoritäts Schlüssel-ID** | keyid: 55: E4:81: D1:11:80: be: D8:89: B9:08: a3:31: F9: a1:24:09:16: B9:70 |
| **Fingerabdruck (SHA-1)** | C53E73073F93CE7895DE7484126BC303DAB9E657 |
| **Fingerabdruck (SHA-256)** | 0EE4DAF71A85D842D23F4910FD4C909B7271861931F1D5FEAC868225F52700E2 |
| **PIN (SHA-256)** | VFv5NemtodoRftw8KsvFb8AoCWwOJL6bOJS + Ui0bQ94 = |
| **CRL-URLs** | http://crl.entrust.net/2048ca.crl |
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

### <a name="globalsign"></a>**GlobalSign**

| **Betreff** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign-Stammzertifizierungsstelle-R3 |
| --- | --- |
| **Aussteller** | CN = GlobalSign-Stammzertifizierungsstelle<br>OU = Stamm Cao = GlobalSign NV-SA<br>C = be |
| **Seriennummer** | 04:00:00:00:00:01:25:07:1D: F9: AF |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Nov 18 10:00:00 2009 UTC |
| **Gültigkeit nicht nach** | Mär 18 10:00:00 2019 UTC |
| **ID des Antragstellerschlüssels** | 8f: F0:4B: 7F: A8:2e: 45:24: AE: 4D: 50: Fa: 63:9a: 8B: de: E2: DD: 1B: BC |
| **Autoritäts Schlüssel-ID** | keyid: 60:7B: 66:1a: 45:0d: 97: ca: 89:50:2F: 7D: 04: CD: 34: A8: FF: FC: FD: 4B |
| **Fingerabdruck (SHA-1)** | 4765557AF418C68A641199146A7E556AA8242996 |
| **Fingerabdruck (SHA-256)** | FDFC6560B09C237F468B8130EB90996FF85FA13FA266239B8D5863798D6AB898 |
| **PIN (SHA-256)** | cGuxAXyFXFkWm61cF4HPWX8S0srS9j0aSqN0k4AP + 4a = |
| **CRL-URLs** | http://crl.globalsign.net/root.crl |
| **OCSP-URLs** | http://ocsp.globalsign.com/ExtendedSSLSHA256CACross |

### <a name="globalsign-extended-validation-ca---sha256---g2"></a>**GlobalSign Extended Validation-Zertifizierungsstelle-SHA256-G2**

| **Betreff** | CN = GlobalSign Extended Validation-Zertifizierungsstelle-SHA256-G2<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Aussteller** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign-Stammzertifizierungsstelle-R2 |
| **Seriennummer** | 04:00:00:00:00:01:44:4E: F0:4a: 55 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Feb 20 10:00:00 2014 UTC |
| **Gültigkeit nicht nach** | Dec 15 08:00:00 2021 UTC |
| **ID des Antragstellerschlüssels** | Da: 40:77:43:65:1C: F8: FE: A7: E3: F4:64:82:3E: 4D: 43:13:22:31:02 |
| **Autoritäts Schlüssel-ID** | keyid: 9a: E2:07:57:67:1C: 1E: C0:6a: 06: de: 59: B4:9a: 2D: DF: DC: 19:86:2E |
| **Fingerabdruck (SHA-1)** | 65BE102BE26928650E0EF54DC8F4F15AF5F98E8B |
| **Fingerabdruck (SHA-256)** | 24F91C0705A0A5338641B365FB0D9D9709B56297CFF1857E73C02C1636D486AA |
| **PIN (SHA-256)** | LvRiGEjRqfzurezaWuj8Wie2gyHMrW5Q06LspMnox7A = |
| **CRL-URLs** | http://crl.globalsign.net/root-r2.crl |
| **OCSP-URLs** | http://ocsp.globalsign.com/rootr2 |

### <a name="globalsign-extended-validation-ca---sha256---g3"></a>**GlobalSign Extended Validation-Zertifizierungsstelle-SHA256-G3**

| **Betreff** | CN = GlobalSign Extended Validation-Zertifizierungsstelle-SHA256-G3<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Aussteller** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign-Stammzertifizierungsstelle-R3 |
| **Seriennummer** | 48: A4:02: DD: 27:92:0d: a2:08:34:9d: D1:99:7B |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Sep 21 00:00:00 2016 UTC |
| **Gültigkeit nicht nach** | Sep 21 00:00:00 2026 UTC |
| **ID des Antragstellerschlüssels** | DD: B3: E7:4T: A8:2e: E8: C5:4E: 6E: CF: 74: E6:75:3C: 94:15: CE: E8:1D |
| **Autoritäts Schlüssel-ID** | keyid: 8F: F0:4B: 7F: A8:2e: 45:24: AE: 4D: 50: Fa: 63:9a: 8B: de: E2: DD: 1B: BC |
| **Fingerabdruck (SHA-1)** | 6023192FE7B59D2789130A9FE4094F9B5570D4A2 |
| **Fingerabdruck (SHA-256)** | AED5DD9A5339685DFB029F6D89A14335A96512C3CACC52B2994AF8B6B37FA4D2 |
| **PIN (SHA-256)** | 86fLIetopQLDNxFZ0uMI66Xpl1pFgLlHHn9v6kT0i4I = |
| **CRL-URLs** | http://crl.globalsign.com/root-r3.crl |
| **OCSP-URLs** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**GlobalSign-Organisationsüberprüfung-Zertifizierungsstelle-SHA256-G2**

| **Betreff** | CN = GlobalSign Organization Validation-Zertifizierungsstelle-SHA256-G2<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Aussteller** | CN = GlobalSign<br>O = GlobalSign<br>OU = GlobalSign-Stammzertifizierungsstelle-R3 |
| **Seriennummer** | 04:00:00:00:00:01:31:89: C6:44: C9 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Aug 02 10:00:00 2011 UTC |
| **Gültigkeit nicht nach** | Aug 02 10:00:00 2022 UTC |
| **ID des Antragstellerschlüssels** | 96: de: 61: F1: BD: 1C: 16:29:53:1C: C0: cc: 7D: 3B: 83:00:40: E6:1a: 7C |
| **Autoritäts Schlüssel-ID** | keyid: 8F: F0:4B: 7F: A8:2e: 45:24: AE: 4D: 50: Fa: 63:9a: 8B: de: E2: DD: 1B: BC |
| **Fingerabdruck (SHA-1)** | EF90B2B86F4756EBE7D36FF3015D63523A0076E9 |
| **Fingerabdruck (SHA-256)** | 0B339212D7CFF17A2C59E35669B58E77350133750A78DA9404770EDD470DEF76 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **CRL-URLs** | http://crl.globalsign.net/root-r3.crl |
| **OCSP-URLs** | http://ocsp2.globalsign.com/rootr3 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**GlobalSign-Organisationsüberprüfung-Zertifizierungsstelle-SHA256-G2**

| **Betreff** | CN = GlobalSign Organization Validation-Zertifizierungsstelle-SHA256-G2<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Aussteller** | CN = GlobalSign-Stammzertifizierungsstelle<br>OU = Stammzertifizierungsstelle<br>O = GlobalSign NV-SA<br>C = be |
| **Seriennummer** | 04:00:00:00:00:01:44:4E: F0:42:47 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Feb 20 10:00:00 2014 UTC |
| **Gültigkeit nicht nach** | Feb 20 10:00:00 2024 UTC |
| **ID des Antragstellerschlüssels** | 96: de: 61: F1: BD: 1C: 16:29:53:1C: C0: cc: 7D: 3B: 83:00:40: E6:1a: 7C |
| **Autoritäts Schlüssel-ID** | keyid: 60:7B: 66:1a: 45:0d: 97: ca: 89:50:2F: 7D: 04: CD: 34: A8: FF: FC: FD: 4B |
| **Fingerabdruck (SHA-1)** | 902EF2DEEB3C5B13EA4C3D5193629309E231AE55 |
| **Fingerabdruck (SHA-256)** | 74EF335E5E18788307FB9D89CB704BEC112ABD23487DBFF41C4DED5070F241D9 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **CRL-URLs** | http://crl.globalsign.net/root.crl |
| **OCSP-URLs** | http://ocsp.globalsign.com/rootr1 |

### <a name="globalsign-organization-validation-ca---sha256---g2"></a>**GlobalSign-Organisationsüberprüfung-Zertifizierungsstelle-SHA256-G2**

| **Betreff** | CN = GlobalSign Organization Validation-Zertifizierungsstelle-SHA256-G2<br>O = GlobalSign NV-SA<br>C = be |
| --- | --- |
| **Aussteller** | CN = GlobalSign-Stammzertifizierungsstelle<br>OU = Stammzertifizierungsstelle<br>O = GlobalSign NV-SA<br>C = be |
| **Seriennummer** | 04:00:00:00:00:01:44:4E: F0:42:47 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Feb 20 10:00:00 2014 UTC |
| **Gültigkeit nicht nach** | Feb 20 10:00:00 2024 UTC |
| **ID des Antragstellerschlüssels** | 96: de: 61: F1: BD: 1C: 16:29:53:1C: C0: cc: 7D: 3B: 83:00:40: E6:1a: 7C |
| **Autoritäts Schlüssel-ID** | keyid: 60:7B: 66:1a: 45:0d: 97: ca: 89:50:2F: 7D: 04: CD: 34: A8: FF: FC: FD: 4B |
| **Fingerabdruck (SHA-1)** | 902EF2DEEB3C5B13EA4C3D5193629309E231AE55 |
| **Fingerabdruck (SHA-256)** | 74EF335E5E18788307FB9D89CB704BEC112ABD23487DBFF41C4DED5070F241D9 |
| **PIN (SHA-256)** | IQBnNBEiFuhj + 8x6X8XLgh01V9Ic5/V3IRQLNFFc7v4 = |
| **CRL-URLs** | http://crl.globalsign.net/root.crl |
| **OCSP-URLs** | http://ocsp.globalsign.com/rootr1 |

### <a name="lets-encrypt-authority-x3"></a>**Lassen Sie uns die Autorität X3 verschlüsseln**

| **Betreff** | CN = Let es Encrypt Authority X3<br>O = verschlüsseln wir<br>C = US |
| --- | --- |
| **Aussteller** | CN = DST-Stammzertifizierungsstelle X3<br>O = digitale Signatur Trust Co. |
| **Seriennummer** | 0a: 01:41:42:00:00:01:53:85:73:6a: 0B: 85: EC: A7:08 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mär 17 16:40:46 2016 UTC |
| **Gültigkeit nicht nach** | Mär 17 16:40:46 2021 UTC |
| **ID des Antragstellerschlüssels** | A8:4a: 6a: 63:04:7D: DD: BA: E6: D1:39: B7: A6:45:65: EF: F3: A8: EC: a1 |
| **Autoritäts Schlüssel-ID** | keyid: C4: A7: B1: A4:7B: 2C: 71: Fa: DB: E1:4B: 90:75: FF: C4:15:60:85:89:10 |
| **Fingerabdruck (SHA-1)** | E6A3B45B062D509B3382282D196EFE97D5956CCB |
| **Fingerabdruck (SHA-256)** | 25847D668EB4F04FDD40B12B6B0740C567DA7D024308EB6C2C96FE41D9DE218D |
| **PIN (SHA-256)** | YLh1dUR9y6Kja30RrAn7JKnbQG/uEtLMkBgFF2Fuihg = |
| **AIA-URLs** | http://apps.identrust.com/roots/dstrootcax3.p7c |
| **CRL-URLs** | http://crl.identrust.com/DSTROOTCAX3CRL.crl |
| **OCSP-URLs** | http://isrg.trustid.ocsp.identrust.com |

### <a name="microsoft-it-ssl-sha2"></a>**Microsoft IT-SSL-SHA2**

| **Betreff** | CN = Microsoft IT-SSL-SHA2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 07:27:9a: A9 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Dec 19 20:07:32 2013 UTC |
| **Gültigkeit nicht nach** | Dec 19 20:06:55 2017 UTC |
| **ID des Antragstellerschlüssels** | 51: AF: 24:26: c!: F4:68:22:57:80:26:2B: 3B: 46:62:15:7B: 1E: cc: A5 |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 948E1652586240D453287AB69CAEB8F2F4F02117 |
| **Fingerabdruck (SHA-256)** | 34BD941A06ED10E2FAC8459F79E4748C1EA08F142C6DE5E557884D0D3CE249FA |
| **PIN (SHA-256)** | CzdPous1hY3sIkO55pUH7vklXyIHVZAl/UnprSQvpEI = |
| **CRL-URLs** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |

### <a name="microsoft-it-ssl-sha2"></a>**Microsoft IT-SSL-SHA2**

| **Betreff** | CN = Microsoft IT-SSL-SHA2<br>OU = Microsoft IT<br>O = Microsoft Corporation<br>L = Redmond<br>S = Washington<br>C = US |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 07:27: AA: 47 |
| **Länge des öffentlichen Schlüssels** | RSA 4096 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 07 17:04:09 2014 UTC |
| **Gültigkeit nicht nach** | Mai 07 17:03:30 2018 UTC |
| **ID des Antragstellerschlüssels** | 51: AF: 24:26: c!: F4:68:22:57:80:26:2B: 3B: 46:62:15:7B: 1E: cc: A5 |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 97EFF3028677894BDD4F9AC53F789BEE5DF4AD86 |
| **Fingerabdruck (SHA-256)** | 2399983E99703EBD01CEA466C10799810C4BA62A8D61B88170A334DCD61BB20F |
| **PIN (SHA-256)** | CzdPous1hY3sIkO55pUH7vklXyIHVZAl/UnprSQvpEI = |
| **CRL-URLs** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.omniroot.com/baltimoreroot |

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

### <a name="symantec-class-3-ev-ssl-ca---g3"></a>**Symantec Class 3 EV SSL CA-G3**

| **Betreff** | CN = Symantec Class 3 EV SSL CA-G3<br>OU = Symantec Trust-Netzwerk<br>O = Symantec Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = VeriSign Class 3 Public Primary Certification Authority-G5<br>OU = &quot; (c) 2006 VeriSign, Inc. – nur für autorisierte Verwendung&quot;<br>OU = VeriSign Trust-Netzwerk<br>O = &quot; VeriSign, Inc.&quot;<br>C = US |
| **Alternativer Antragsteller Name** | Verzeichnisadresse: CN = SymantecPKI-1-533 |
| **Seriennummer** | 7e: E1:4a: 6F: 6F: EF: F2: D3:7F: 3f: AD: 65:4D: 3A: da: B4 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Oct 31 00:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Oct 30 23:59:59 2023 UTC |
| **ID des Antragstellerschlüssels** | 01:59: ab: E7: DD: 3A: 0B: 59: A6:64:63: D6: CF: 20:07:57: D5:91: E7:6a |
| **Autoritäts Schlüssel-ID** | keyid: 7F: D3:65: A7: C2: DD: EC: BB: F0:30:09: F3:43:39: Fa: 02: AF: 33:31:33 |
| **Fingerabdruck (SHA-1)** | E3FC0AD84F2F5A83ED6F86F567F8B14B40DCBF12 |
| **Fingerabdruck (SHA-256)** | 9E6BC5F9ECC52460E8EDC02C644D1BE1CB9F2316F41DAF3B616A0B2058294B31 |
| **PIN (SHA-256)** | gMxWOrX4PMQesK9qFNbYBxjBfjUvlkn/vN1n + L9lE5E = |
| **CRL-URLs** | http://s1.symcb.com/pca3-g5.crl |
| **OCSP-URLs** | http://s2.symcb.com |

### <a name="symantec-class-3-secure-server-ca---g4"></a>**Symantec Class 3 Secure Server ca-G4**

| **Betreff** | CN = Symantec Class 3 Secure Server ca-G4<br>OU = Symantec Trust-Netzwerk<br>O = Symantec Corporation<br>C = US |
| --- | --- |
| **Aussteller** | CN = VeriSign Class 3 Public Primary Certification Authority-G5<br>OU = &quot; (c) 2006 VeriSign, Inc. – nur für autorisierte Verwendung&quot;<br>OU = VeriSign Trust-Netzwerk<br>O = &quot; VeriSign, Inc.&quot;<br>C = US |
| **Alternativer Antragsteller Name** | Verzeichnisadresse: CN = SymantecPKI-1-534 |
| **Seriennummer** | 51:3f: B9:74:38:70: B7:34:40:41:4D: 30:93:06:99: FF |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Oct 31 00:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Oct 30 23:59:59 2023 UTC |
| **ID des Antragstellerschlüssels** | 5F: 60: CF: 61:90:55: DF: 84:43:14:8a: 60:2a: B2: F5:7a: F4:43:18: EF |
| **Autoritäts Schlüssel-ID** | keyid: 7F: D3:65: A7: C2: DD: EC: BB: F0:30:09: F3:43:39: Fa: 02: AF: 33:31:33 |
| **Fingerabdruck (SHA-1)** | FF67367C5CD4DE4AE18BCCE1D70FDABD7C866135 |
| **Fingerabdruck (SHA-256)** | EAE72EB454BF6C3977EBD289E970B2F5282949190093D0D26F98D0F0D6A9CF17 |
| **PIN (SHA-256)** | 9n0izTnSRF + W4W4JTq51avSXkWhQB8duS2bxVLfzXsY = |
| **CRL-URLs** | http://s1.symcb.com/pca3-g5.crl |
| **OCSP-URLs** | http://s2.symcb.com |

### <a name="thawte-sha256-ssl-ca"></a>**Thawte-SHA256-SSL-Zertifizierungsstelle**

| **Betreff** | CN = Thawte SHA256 SSL-Zertifizierungsstelle<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| --- | --- |
| **Aussteller** | CN = Thawte Primary Root CA-G3<br>OU = &quot; (c) 2008 Thawte, Inc. – nur für autorisierte Verwendung&quot;<br>OU = Certification Services Division<br>O = &quot; Thawte, Inc.&quot;<br>C = US |
| **Alternativer Antragsteller Name** | Verzeichnisadresse: CN = VeriSignMPKI-2-415 |
| **Seriennummer** | 36:34:9e: 18: C9:9:: 26:69: B6:56:2e: 6C: E5: AD: 71:32 |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Mai 23 00:00:00 2013 UTC |
| **Gültigkeit nicht nach** | Mai 22 23:59:59 2023 UTC |
| **ID des Antragstellerschlüssels** | 2B: 9a: 35: AE: 01:18:38:30: E1:70:7a: 05: E0:11:76: a3: CE: BD: 90:14 |
| **Autoritäts Schlüssel-ID** | keyid: AD: 6C: AA: 94:60:9:: Ed: E4: FF: Fa: 3E: 0A: 74:2B: 63:03: F7: B6:59: BF |
| **Fingerabdruck (SHA-1)** | 67D147D5DAB7F28D663CA5B7A9568F087427B9F7 |
| **Fingerabdruck (SHA-256)** | 3F3AF9C9CC2C7599EF8F6DD7CA516CFC1797D7D12002254F3BFD0D4D0FE9DE86 |
| **PIN (SHA-256)** | /36ymPAVaJl3QDyB1lUkVf9GqJNug0R8JJPDN6348p8 = |
| **CRL-URLs** | http://crl.thawte.com/ThawtePCA-G3.crl |
| **OCSP-URLs** | http://ocsp.thawte.com |

### <a name="verizon-akamai-sureserver-ca-g14-sha2"></a>**Verizon Akamai SureServer ca G14-SHA2**

| **Betreff** | CN = Verizon Akamai SureServer ca G14-SHA2<br>OU = Cybertrust<br>O = Verizon Enterprise-Lösungen<br>L = Amsterdam<br>C = nl |
| --- | --- |
| **Aussteller** | CN = Baltimore Cybertrust-Stamm<br>OU = Cybertrust<br>O = Baltimore<br>C = IE |
| **Seriennummer** | 07:27: A4:6B |
| **Länge des öffentlichen Schlüssels** | RSA 2048 Bits (e 65537) |
| **Signaturalgorithmus** | sha256RSA |
| **Gültigkeit nicht vor** | Apr 02 14:36:10 2014 UTC |
| **Gültigkeit nicht nach** | Apr 02 14:35:52 2021 UTC |
| **ID des Antragstellerschlüssels** | F8: BD: Fa: AF: 73:77: C6: C7:1B: F9:4B: 4D: 11: A7: D1:33: AF: AF: 72:11 |
| **Autoritäts Schlüssel-ID** | keyid: E5:9d: 59:30:82:47:58: cc: AC: Fa: 08:54:36:86:7B: 3A: B5:04:4D: F0 |
| **Fingerabdruck (SHA-1)** | 6AD2B04E2196E48BF685752890E811CD2ED60606 |
| **Fingerabdruck (SHA-256)** | 7373D219B42547E41BCB752BCBCBE93F592FF6F99C340CE57B73D38C3EC0BA98 |
| **PIN (SHA-256)** | 8XFPrRr4VxmEIYKUu35QtR3oGbduX1AlrBzaBUHgp7c = |
| **AIA-URLs** | https://cacert.omniroot.com/baltimoreroot.crt<br>https://cacert.omniroot.com/baltimoreroot.der |
| **CRL-URLs** | http://cdp1.public-trust.com/CRL/Omniroot2025.crl |
| **OCSP-URLs** | http://ocsp.omniroot.com/baltimoreroot |

## <a name="additional-certificate-paths"></a>**Zusätzliche Zertifikat Pfade**

Die folgende Liste enthält ältere Zertifikate, die nicht oben enthalten sind und mit der obigen Liste im Laufe der Zeit zusammengeführt werden.

evsecure-aia.verisign.com<br>
sa.symcb.com<br>
sd.symcb.com<br>
\*. OmniRoot.com<br>
\*. VeriSign.com<br>
\*. symcb.com<br>
\*. symcd.com<br>
\*. VeriSign.net<br>
\*. GeoTrust.com<br>
\*. Entrust.net<br>
\*. Public-Trust.com<br>
EVIntl-ocsp.verisign.com<br>
EVSecure-ocsp.verisign.com<br>
isrg.trustid.ocsp.identrust.com<br>
ocsp.digicert.com<br>
ocsp.entrust.net<br>
ocsp.globalsign.com/ExtendedSSLSHA256CACross<br>
ocsp.globalsign.com/rootr1<br>
ocsp.globalsign.com/rootr2<br>
ocsp2.globalsign.com/rootr3<br>
ocsp.int-x3.letsencrypt.org/<br>
ocsp.msocsp.com<br>
ocsp.omniroot.com/baltimoreroot<br>
ocsp2.globalsign.com/gsextendvalsha2g3r3<br>
ocsp2.globalsign.com/gsorganizationvalsha2g2<br>
ocsp2.globalsign.com/gsorganizationvalsha2g3<br>
ocsp2.globalsign.com/rootr3<br>
ocspx.digicert.com<br>
s2.symcb.com<br>
sr.symcd.com<br>
su.symcd.com<br>
vassg142.ocsp.omniroot.com<br>
cdp1.public-trust.com/CRL/Omniroot2025.crl<br>
crl.entrust.net/2048ca.crl<br>
crl.entrust.net/g2ca.crl<br>
crl.entrust.net/level1k.crl<br>
crl.entrust.net/rootca1.crl<br>
crl.globalsign.com/gs/gsextendvalsha2g3r3.crl<br>
crl.globalsign.com/gs/gsorganizationvalsha2g2.crl<br>
crl.globalsign.com/gsorganizationvalsha2g3.crl<br>
crl.globalsign.com/root.crl<br>
crl.globalsign.net/root-r2.crl<br>
crl.globalsign.com/root-r3.crl<br>
crl.globalsign.net/root.crl<br>
crl.identrust.com/DSTROOTCAX3CRL.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
crl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
crl3.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl3.digicert.com/DigiCertGlobalRootCA.crl<br>
crl3.digicert.com/sha2-ev-server-g1.crl<br>
crl3.digicert.com/sha2-ha-server-g5.crl<br>
crl3.digicert.com/ssca-sha2-g5.crl<br>
crl4.digicert.com/DigiCertCloudServicesCA-1-g1.crl<br>
crl4.digicert.com/DigiCertGlobalRootCA.crl<br>
crl4.digicert.com/DigiCertHighAssuranceEVRootCA.crl<br>
crl4.digicert.com/sha2-ev-server-g1.crl<br>
crl4.digicert.com/sha2-ha-server-g5.crl<br>
crl4.digicert.com/ssca-sha2-g5.crl<br>
EVIntl-crl.verisign.com/EVIntl2006.crl<br>
EVSecure-crl.verisign.com/pca3-g5.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww1.crl<br>
mscrl.microsoft.com/pki/mscorp/crl/msitwww2.crl<br>
s1.symcb.com/pca3-g5.crl<br>
sr.symcb.com/sr.crl<br>
su.symcb.com/su.crl<br>
vassg142.crl.omniroot.com/vassg142.crl<br>
aia.entrust.net/l1k-chain256.cer<br>
apps.identrust.com/roots/dstrootcax3.p7c<br>
<https://cacert.a.omniroot.com/vassg142.crt><br>
<https://cacert.a.omniroot.com/vassg142.der><br>
<https://cacert.omniroot.com/baltimoreroot.crt><br>
<https://cacert.omniroot.com/baltimoreroot.der><br>
cacerts.digicert.com/DigiCertCloudServicesCA-1.crt<br>
cacerts.digicert.com/DigiCertSHA2ExtendedValidationServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2HighAssuranceServerCA.crt<br>
cacerts.digicert.com/DigiCertSHA2SecureServerCA.crt<br>
cert.int-x3.letsencrypt.org/<br>
EVIntl-aia.verisign.com/EVIntl2006.cer<br>
secure.globalsign.com/cacert/gsextendvalsha2g2r2.crt<br>
secure.globalsign.com/cacert/gsextendvalsha2g3r3.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g2r1.crt<br>
secure.globalsign.com/cacert/gsorganizationvalsha2g3.crt<br>
sr.symcb.com/sr.crt<br>
su.symcb.com/su.crt<br>
<https://www.digicert.com/CACerts/DigiCertGlobalRootCA.crt><br>
<https://www.digicert.com/CACerts/DigiCertHighAssuranceEVRootCA.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww1.crt><br>
<https://www.microsoft.com/pki/mscorp/msitwww2.crt><br>