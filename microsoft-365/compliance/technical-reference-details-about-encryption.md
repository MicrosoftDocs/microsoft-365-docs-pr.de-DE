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
description: Erfahren Sie mehr über die verschiedenen Zertifikate, Technologien und TLS-Verschlüsselungssuiten (Transport Layer Security), die für die Verschlüsselung in Office 365 und Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e7e50ea399cd694f512e0538de3f7e67c63ee0e3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919351"
---
# <a name="technical-reference-details-about-encryption"></a>Technische Details zur Verschlüsselung

In diesem Artikel finden Sie Informationen zu Zertifikaten, Technologien und TLS-Verschlüsselungssuiten, die für die Verschlüsselung [in](encryption.md)Office 365. Dieser Artikel enthält auch Details zu geplanten Veraltetkeitsinformationen.
  
- Wenn Sie nach Übersichtsinformationen suchen, lesen Sie [Verschlüsselung in Office 365](encryption.md).
- Informationen zum Einrichten finden Sie unter [Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md).
- Informationen zu Verschlüsselungssuiten, die von bestimmten Versionen von Windows unterstützt werden, finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigentümerschaft und Verwaltung des Microsoft Office 365-Zertifikats

Sie müssen keine Zertifikate für die Office 365. Stattdessen verwendet Office 365 eigene Zertifikate.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuelle Verschlüsselungsstandards und geplante Veraltetkeit

Um eine erstklassige Verschlüsselung zu bieten, Office 365 die unterstützten Verschlüsselungsstandards regelmäßig überprüft. Manchmal sind alte Standards veraltet, wenn sie veraltet und weniger sicher sind. In diesem Artikel werden derzeit unterstützte Verschlüsselungssuiten sowie andere Standards und Details zu geplanten Veraltetkeitsanforderungen beschrieben.

## <a name="fips-compliance-for-office-365"></a>FIPS-Compliance für Office 365

Alle verschlüsselungsgestützten Office 365 verwenden Algorithmen, die unter FIPS 140-2 akzeptabel sind. Office 365 erbt FIPS-Überprüfungen von Windows (über Schannel). Weitere Informationen zu Schannel finden Sie [unter Cipher Suites in TLS/SSL (Schannel SSP)](/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Versionen

TLS und SSL, die vor TLS verfügbar waren, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk mithilfe von Sicherheitszertifikaten sichern, um eine Verbindung zwischen Computern zu verschlüsseln. Office 365 unterstützt TLS Version 1.2 (TLS 1.2).

TLS Version 1.3 (TLS 1.3) wird derzeit nicht unterstützt.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Unterstützung für TLS 1.0 und 1.1 veraltet

Office 365 TLS 1.0 und 1.1 wurde am 31. Oktober 2018 nicht mehr unterstützt. Wir haben die Deaktivierung von TLS 1.0 und 1.1 in GCC High- und DoD-Umgebungen abgeschlossen. Wir haben mit der Deaktivierung von TLS 1.0 und 1.1 für Umgebungen weltweit und GCC begonnen, die am 15. Oktober 2020 beginnen und in den nächsten Wochen und Monaten mit dem Rollout fortgesetzt werden.

Um eine sichere Verbindung zu Office 365 und Microsoft 365 zu gewährleisten, verwenden alle Client-Server- und Browser-Server-Kombinationen TLS 1.2 und moderne Verschlüsselungssuiten. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen. Informationen dazu, wie sich diese Änderung auf Sie aus wirkt, finden Sie unter [Preparing for the mandatory use of TLS 1.2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Veraltete Unterstützung für 3DES

Seit dem 31. Oktober 2018 unterstützt Office 365 nicht mehr die Verwendung von 3DES-Chiffresuiten für die Kommunikation Office 365. Genauer gesagt, Office 365 die Verschlüsselungssuite TLS_RSA_WITH_3DES_EDE_CBC_SHA unterstützt. Seit dem 28. Februar 2019 ist diese Verschlüsselungssuite in der Office 365. Clients und Server, die mit Office 365 kommunizieren, müssen mindestens eine der unterstützten Chiffren unterstützen. Eine Liste der unterstützten Chiffren finden Sie unter [TLS cipher suites supported by Office 365](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ende der SHA-1-Zertifikatunterstützung in Office 365

Seit Juni 2016 akzeptiert Office 365 kein SHA-1-Zertifikat mehr für ausgehende oder eingehende Verbindungen. Verwenden Sie SHA-2 (Secure Hash Algorithm 2) oder einen stärkeren Hashalgorithmus in der Zertifikatkette.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>TLS-Verschlüsselungssuiten, die von Office 365

TLS verwendet *Verschlüsselungssammlungen*, Sammlungen von Verschlüsselungsalgorithmen, um sichere Verbindungen herzustellen. Office 365 unterstützt die in der folgenden Tabelle aufgeführten Verschlüsselungssuiten. In der Tabelle sind die Verschlüsselungssuiten in der Reihenfolge ihrer Stärke aufgeführt, und zuerst wird die stärkste Verschlüsselungssuite aufgeführt.

Office 365 antwortet auf eine Verbindungsanforderung, indem zunächst versucht wird, eine Verbindung mit der sichersten Verschlüsselungssuite herzustellen. Wenn die Verbindung nicht funktioniert, versucht Office 365, die zweitsicherste Verschlüsselungssuite in der Liste zu verwenden, und so weiter. Der Dienst wird in der Liste fortgesetzt, bis die Verbindung akzeptiert wird. Wenn Office 365 eine Verbindung anfordern, wählt der empfangende Dienst aus, ob TLS verwendet wird und welche Verschlüsselungssuite verwendet werden soll.

> [!IMPORTANT]
> Beachten Sie, dass die TLS-Versionen veraltet sind  und dass veraltete Versionen nicht verwendet werden sollten, wenn neuere Versionen verfügbar sind. TLS 1.3 wird derzeit nicht unterstützt. Wenn Ihre Legacydienste TLS 1.0 oder 1.1 nicht benötigen, sollten Sie sie deaktivieren.

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

Diese Verschlüsselungssuiten unterstützten TLS 1.0- und 1.1-Protokolle bis zu ihrem Veraltetkeitsdatum. Für GCC High- und DoD-Umgebungen war das Veraltete Datum der 15. Januar 2020 und für Umgebungen weltweit und GCC der 15. Oktober 2020.

| Protokolle | Name der Verschlüsselungssammlung | Schlüsselaustauschalgorithmus/Stärke | Forward Secrecy-Unterstützung | Authentifizierungsalgorithmus/Stärke | Chiffre/Stärke |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Verwandte Artikel

[TLS Cipher Suites in Windows 10 v1903](/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Verschlüsselung in Office 365](encryption.md)
  
[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md)
  
[Schannel-Implementierung von TLS 1.0 in Windows Sicherheitsstatusupdate: 24. November 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL Cryptographic Enhancements (Windows IT Center)](/previous-versions/windows/it-pro/windows-vista/cc766285(v=ws.10))
  
[Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC](/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)