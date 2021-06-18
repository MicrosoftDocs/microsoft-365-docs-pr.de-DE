---
title: Technische Details zur Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
- Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Erfahren Sie mehr über die verschiedenen Zertifikate, Technologien und TLS-Verschlüsselungssammlungen (Transport Layer Security), die für die Verschlüsselung in Office 365 und Microsoft 365 verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 2b2257338ab214ccdaa08f1aa8f322aad98d7c8b
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007549"
---
# <a name="technical-reference-details-about-encryption"></a>Technische Details zur Verschlüsselung

In diesem Artikel erfahren Sie mehr über Zertifikate, Technologien und TLS-Verschlüsselungssammlungen, die für [die Verschlüsselung in Office 365](encryption.md)verwendet werden. Dieser Artikel enthält auch Details zu geplanten Veralteten.
  
- Wenn Sie nach Übersichtsinformationen suchen, lesen Sie ["Verschlüsselung" in Office 365](encryption.md).
- Wenn Sie nach Setupinformationen suchen, lesen Sie "Einrichten der [Verschlüsselung" in Office 365 Enterprise](set-up-encryption.md).
- Informationen zu Verschlüsselungssammlungen, die von bestimmten Versionen von Windows unterstützt werden, finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigentümerschaft und Verwaltung des Microsoft Office 365-Zertifikats

Sie müssen keine Zertifikate für Office 365 erwerben oder verwalten. Stattdessen verwendet Office 365 eigene Zertifikate.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuelle Verschlüsselungsstandards und geplante Veraltete

Um eine erstklassige Verschlüsselung bereitzustellen, überprüft Office 365 regelmäßig unterstützte Verschlüsselungsstandards. Manchmal sind alte Standards veraltet, wenn sie veraltet und weniger sicher sind. In diesem Artikel werden derzeit unterstützte Verschlüsselungssammlungen und andere Standards sowie Details zu geplanten Veralteten beschrieben.

## <a name="fips-compliance-for-office-365"></a>FIPS-Compliance für Office 365

Alle cipher suites supported by Office 365 use algorithms acceptable under FIPS 140-2. Office 365 erbt FIPS-Überprüfungen von Windows (über Schannel). Informationen zu Schannel finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP).](/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Versionen

TLS und SSL, die vor TLS aufgetreten sind, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk mithilfe von Sicherheitszertifikaten sichern, um eine Verbindung zwischen Computern zu verschlüsseln. Office 365 unterstützt TLS Version 1.2 (TLS 1.2).

TLS Version 1.3 (TLS 1.3) wird derzeit nicht unterstützt.

> [!IMPORTANT]
> Beachten Sie, dass TLS-Versionen veraltet sind und dass veraltete Versionen *nicht verwendet werden sollten,* wenn neuere Versionen verfügbar sind. Wenn Ihre Legacydienste TLS 1.0 oder 1.1 nicht benötigen, sollten Sie sie deaktivieren.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Unterstützung für tls 1.0 und 1.1 veraltet

Office 365 die Unterstützung von TLS 1.0 und 1.1 am 31. Oktober 2018 eingestellt. Wir haben die Deaktivierung von TLS 1.0 und 1.1 in GCC High- und DoD-Umgebungen abgeschlossen. Wir haben mit der Deaktivierung von TLS 1.0 und 1.1 für weltweite umgebungen und GCC umgebungen am 15. Oktober 2020 begonnen und werden in den nächsten Wochen und Monaten mit dem Rollout fortfahren.

Um eine sichere Verbindung mit Office 365 und Microsoft 365 Diensten aufrechtzuerhalten, verwenden alle Clientserver- und Browserserverkombinationen TLS 1.2 und moderne Verschlüsselungssammlungen. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen. Informationen dazu, wie sich diese Änderung auf Sie auswirkt, finden Sie unter [Vorbereiten der obligatorischen Verwendung von TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Veraltete Unterstützung für 3DES

Seit dem 31. Oktober 2018 unterstützt Office 365 die Verwendung von 3DES-Verschlüsselungssammlungen für die Kommunikation mit Office 365 nicht mehr. Genauer gesagt, unterstützt Office 365 die TLS_RSA_WITH_3DES_EDE_CBC_SHA Cipher Suite nicht mehr. Seit dem 28. Februar 2019 wurde diese Verschlüsselungssuite in Office 365 deaktiviert. Clients und Server, die mit Office 365 kommunizieren, müssen eine oder mehrere der unterstützten Chiffren unterstützen. Eine Liste der unterstützten Verschlüsselungen finden Sie unter [TLS-Verschlüsselungssammlungen, die von Office 365 unterstützt werden.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ende der SHA-1-Zertifikatunterstützung in Office 365

Seit Juni 2016 akzeptiert Office 365 kein SHA-1-Zertifikat mehr für ausgehende oder eingehende Verbindungen. Verwenden Sie SHA-2 (Secure Hash Algorithm 2) oder einen stärkeren Hashalgorithmus in der Zertifikatkette.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>VON Office 365 unterstützte TLS-Verschlüsselungssammlungen

TLS verwendet *Verschlüsselungssammlungen*, Sammlungen von Verschlüsselungsalgorithmen, um sichere Verbindungen herzustellen. Office 365 unterstützt die in der folgenden Tabelle aufgeführten Verschlüsselungssammlungen. In der Tabelle sind die Chiffresammlungen in der Reihenfolge der Stärke aufgeführt, wobei zuerst die stärkste Verschlüsselungssuite aufgeführt wird.

Office 365 antwortet auf eine Verbindungsanforderung, indem zuerst versucht wird, eine Verbindung mithilfe der sichersten Verschlüsselungssuite herzustellen. Wenn die Verbindung nicht funktioniert, versucht Office 365 die zweite sicherste Verschlüsselungssuite in der Liste usw. Der Dienst setzt die Liste nach unten fort, bis die Verbindung akzeptiert wird. Ebenso wählt der empfangende Dienst, wenn Office 365 eine Verbindung anfordert, aus, ob TLS verwendet wird und welche Verschlüsselungssuite verwendet werden soll.

| Name der Verschlüsselungssammlung | Schlüsselaustauschalgorithmus/-stärke | Weiterleitungsgeheimnis | Chiffre/Stärke | Authentifizierungsalgorithmus/-stärke |
|:-----|:-----|:-----|:-----|:-----|
| TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA     <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA     <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_256_GCM_SHA384        <br/> | RSA/112   <br/> | Nein   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS_RSA_WITH_AES_128_GCM_SHA256        <br/> | RSA/112   <br/> | Nein   <br/> | AES/256  <br/> | RSA/112  <br/> |

Die folgenden Verschlüsselungssammlungen unterstützten TLS 1.0- und 1.1-Protokolle bis zu ihrem Veralteten Datum. Für GCC High- und DoD-Umgebungen war das Veraltete Datum der 15. Januar 2020. Für weltweite und GCC Umgebungen, deren Datum der 15. Oktober 2020 war.

| Protokolle | Name der Verschlüsselungssammlung | Schlüsselaustauschalgorithmus/-stärke | Weiterleitungsgeheimnis | Chiffre/Stärke | Authentifizierungsalgorithmus/-stärke | 
|:-----|:-----|:-----|:-----|:-----|:-----|
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> | ECDH/192  <br/> | Ja  <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> | ECDH/128  <br/> | Ja  <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA        <br/> | RSA/112   <br/> | Nein   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA        <br/> | RSA/112   <br/> | Nein   <br/> | AES/128  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> | RSA/112   <br/> | Nein   <br/> | AES/256  <br/> | RSA/112  <br/> |
| TLS 1.0, 1.1, 1.2  <br/> | TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> | RSA/112   <br/> | Nein   <br/> | AES/256  <br/> | RSA/112  <br/> |

Bestimmte Office 365 Produkte (einschließlich Microsoft Teams) verwenden [Azure Front Door,](/azure/frontdoor/front-door-overview) um TLS-Verbindungen zu beenden und den Netzwerkdatenverkehr effizient weiterzuleiten. Mindestens eine der [Verschlüsselungssammlungen, die von Azure Front Door über TLS 1.2 unterstützt](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-) werden, muss aktiviert sein, um eine erfolgreiche Verbindung mit diesen Produkten herzustellen. Für Windows 10 und höher wird empfohlen, eine oder beide ECDHE-Verschlüsselungssammlungen für eine bessere Sicherheit zu aktivieren. Windows 7, 8 und 8.1 sind nicht mit den ECDHE-Verschlüsselungssammlungen von Azure Front Door kompatibel, und die DHE-Verschlüsselungssammlungen wurden aus Gründen der Kompatibilität mit diesen Betriebssystemen bereitgestellt.

## <a name="related-articles"></a>Verwandte Artikel

[TLS Cipher Suites in Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Verschlüsselung in Office 365](encryption.md)
  
[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-Implementierung von TLS 1.0 in Windows Sicherheitsupdates: 24. November 2015](https://support.microsoft.com/kb/3117336)
  
[Tls/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

[Was werden die aktuellen Verschlüsselungssammlungen von Azure Front Door unterstützt?](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)
