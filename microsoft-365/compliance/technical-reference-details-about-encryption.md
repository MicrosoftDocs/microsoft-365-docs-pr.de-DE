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
description: Erfahren Sie mehr über die verschiedenen Zertifikate, Technologien und TLS(Transport Layer Security)-Verschlüsselungssammlungen, die für die Verschlüsselung in Office 365 und Microsoft 365 verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 6e6b001b308519fb35e0cc835ac03fb4b27db260
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233141"
---
# <a name="technical-reference-details-about-encryption"></a>Technische Details zur Verschlüsselung

In diesem Artikel finden Sie Informationen zu Zertifikaten, Technologien und TLS-Verschlüsselungssammlungen, die für die Verschlüsselung [in Office 365 verwendet werden.](encryption.md) Dieser Artikel enthält auch Details zu geplanten Veralteten.
  
- Informationen zur Übersicht finden Sie unter ["Verschlüsselung in Office 365".](encryption.md)
- Informationen zum Einrichten finden Sie unter ["Einrichten der Verschlüsselung in Office 365 Enterprise".](set-up-encryption.md)
- Informationen zu Verschlüsselungssammlungen, die von bestimmten Versionen von Windows unterstützt werden, finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP).](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigentümerschaft und Verwaltung des Microsoft Office 365-Zertifikats

Sie müssen keine Zertifikate für Office 365 erwerben oder verwalten. Stattdessen verwendet Office 365 eigene Zertifikate.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuelle Verschlüsselungsstandards und geplante Veraltetkeit

Um eine erstklassige Verschlüsselung zu bieten, überprüft Office 365 regelmäßig unterstützte Verschlüsselungsstandards. Manchmal sind alte Standards veraltet, sobald sie veraltet und weniger sicher sind. In diesem Artikel werden derzeit unterstützte Verschlüsselungssammlungen und andere Standards sowie Details zu geplanten Veralteten beschrieben.

## <a name="fips-compliance-for-office-365"></a>FIPS-Compliance für Office 365

Alle von Office 365 unterstützten Verschlüsselungssammlungen verwenden Algorithmen, die unter FIPS 140-2 akzeptabel sind. Office 365 erbt die FIPS-Überprüfungen von Windows (über Schannel). Weitere Informationen zu Schannel finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP).](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel)
  
## <a name="versions-of-tls-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Versionen

TLS und SSL, die vor TLS verfügbar waren, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk mithilfe von Sicherheitszertifikaten zum Verschlüsseln einer Verbindung zwischen Computern sichern. Office 365 unterstützt TLS Version 1.2 (TLS 1.2).

TLS Version 1.3 (TLS 1.3) wird derzeit nicht unterstützt.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Unterstützung für die Veraltetkeit von TLS 1.0 und 1.1

Office 365 hat die Unterstützung von TLS 1.0 und 1.1 am 31. Oktober 2018 eingestellt. Wir haben die Deaktivierung von TLS 1.0 und 1.1 in GCC High- und DoD-Umgebungen abgeschlossen. Ab dem 15. Oktober 2020 haben wir mit der Deaktivierung von TLS 1.0 und 1.1 für umgebungen weltweit und GCC begonnen und werden in den nächsten Wochen und Monaten mit der Einführung fortfahren.

Um eine sichere Verbindung mit Office 365- und Microsoft 365-Diensten zu gewährleisten, verwenden alle Client-Server- und Browser-Server-Kombinationen TLS 1.2 und moderne Chiffresammlungen. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen. Informationen dazu, wie sich diese Änderung auf Sie aus wirkt, finden Sie unter Vorbereiten der obligatorischen Verwendung von [TLS 1.2 in Office 365.](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
  
## <a name="deprecating-support-for-3des"></a>Veraltete Unterstützung für 3DES

Seit dem 31. Oktober 2018 unterstützt Office 365 die Verwendung von 3DES-Verschlüsselungssammlungen nicht mehr für die Kommunikation mit Office 365. Genauer gesagt unterstützt Office 365 die TLS_RSA_WITH_3DES_EDE_CBC_SHA Verschlüsselungssuite nicht mehr. Seit dem 28. Februar 2019 ist diese Verschlüsselungssuite in Office 365 deaktiviert. Clients und Server, die mit Office 365 kommunizieren, müssen mindestens eine der unterstützten Verschlüsselungen unterstützen. Eine Liste der unterstützten Verschlüsselungen finden Sie unter [TLS-Verschlüsselungssammlungen, die von Office 365 unterstützt werden.](#tls-cipher-suites-supported-by-office-365)
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ende der SHA-1-Zertifikatunterstützung in Office 365

Seit Juni 2016 akzeptiert Office 365 kein SHA-1-Zertifikat mehr für ausgehende oder eingehende Verbindungen. Verwenden Sie SHA-2 (Secure Hash Algorithm 2) oder einen stärkeren Hashalgorithmus in der Zertifikatkette.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Verschlüsselungssammlungen

TLS verwendet *Verschlüsselungssammlungen*, Sammlungen von Verschlüsselungsalgorithmen, um sichere Verbindungen herzustellen. Office 365 unterstützt die in der folgenden Tabelle aufgeführten Verschlüsselungssammlungen. In der Tabelle sind die Verschlüsselungssammlungen nach Stärke aufgelistet, und die stärkste Verschlüsselungssuite wird zuerst aufgeführt.

Office 365 antwortet auf eine Verbindungsanforderung, indem es zuerst versucht, eine Verbindung mit der sichersten Verschlüsselungssuite herzustellen. Wenn die Verbindung nicht funktioniert, versucht Office 365 die zweitsicherste Verschlüsselungssuite in der Liste und so weiter. Der Dienst fährt in der Liste nach unten fort, bis die Verbindung angenommen wird. Wenn Office 365 eine Verbindung anfordert, entscheidet der empfangende Dienst, ob TLS verwendet wird und welche Verschlüsselungssuite verwendet werden soll.

> [!IMPORTANT]
> Beachten Sie, dass die Veraltetkeit von TLS-Versionen  veraltet ist und dass veraltete Versionen nicht verwendet werden sollten, wenn neuere Versionen verfügbar sind. TLS 1.3 wird derzeit nicht unterstützt. Wenn Ihre älteren Dienste TLS 1.0 oder 1.1 nicht benötigen, sollten Sie sie deaktivieren.

| Verschlüsselungssuite | Schlüsselaustauschalgorithmus/Stärke | Forward Secrecy | Chiffre/Stärke | Authentifizierungsalgorithmus |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Nein <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Nein <br/> |AES/256 <br/>|RSA/112 <br/> |

Diese Verschlüsselungssammlungen unterstützten TLS 1.0- und 1.1-Protokolle bis zu ihrem Veraltetkeitsdatum. Für GCC High- und DoD-Umgebungen, deren Veraltetkeitsdatum der 15. Januar 2020 war, und für umgebungen weltweit und GCC war das Datum der 15. Oktober 2020.

| Protokolle | Name der Verschlüsselungssammlung | Schlüsselaustauschalgorithmus/Stärke | Weiterleitungsgeheimnisunterstützung | Authentifizierungsalgorithmus/Stärke | Chiffre/Stärke |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Verwandte Artikel

[TLS Cipher Suites in Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Verschlüsselung in Office 365](encryption.md)
  
[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-Implementierung von TLS 1.0 im Windows-Sicherheitsstatusupdate: 24. November 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
