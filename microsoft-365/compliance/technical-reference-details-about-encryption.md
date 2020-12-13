---
title: Technische Details zur Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 06/15/2020
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
description: Erfahren Sie mehr über die verschiedenen Zertifikate, Technologien und TLS-Verschlüsselungs Pakete (Transport Layer Security), die für die Verschlüsselung in Office 365 und Microsoft 365 verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 244d7a6cef6d77322475245435dafb6c89ab5353
ms.sourcegitcommit: 47de4402174c263ae8d70c910ca068a7581d04ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/12/2020
ms.locfileid: "49663428"
---
# <a name="technical-reference-details-about-encryption"></a>Technische Details zur Verschlüsselung

In diesem Artikel erhalten Sie Informationen zu Zertifikaten, Technologien und TLS-Verschlüsselungs Paketen, die für die [Verschlüsselung in Office 365](encryption.md)verwendet werden. Dieser Artikel enthält auch Details zu geplanten veralteten Abschreibungen.
  
- Wenn Sie nach Übersichtsinformationen suchen, finden Sie unter [Encryption in Office 365](encryption.md).
- Informationen zum Einrichten finden Sie unter [Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md).
- Informationen zu Verschlüsselungs Paketen, die von bestimmten Versionen von Windows unterstützt werden, finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).

## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigentümerschaft und Verwaltung des Microsoft Office 365-Zertifikats

Zertifikate für Office 365 müssen nicht erworben oder verwaltet werden. Stattdessen verwendet Office 365 eigene Zertifikate.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuelle Verschlüsselungsstandards und geplante veralteungen

Um die Best-in-Class-Verschlüsselung bereitzustellen, überprüft Office 365 regelmäßig unterstützte Verschlüsselungsstandards. In einigen Fällen sind alte Standards veraltet und werden nicht mehr so sicher wie bisher. In diesem Artikel werden derzeit unterstützte Verschlüsselungs Pakete und andere Standards und Details zu geplanten veralteten Informationen beschrieben.

## <a name="fips-compliance-for-office-365"></a>FIPS-Konformität für Office 365

Alle von Office 365 unterstützten Verschlüsselungs Pakete verwenden Algorithmen, die unter FIPS 140-2 akzeptabel sind. Office 365 erbt FIPS-Validierungen von Windows (über SChannel). Informationen zu SChannel finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Versionen

TLS und SSL, die vor TLS stammen, sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk mit Sicherheitszertifikaten zum Verschlüsseln einer Verbindung zwischen Computern sichern. Office 365 unterstützt TLS-Version 1,2 (TLS 1,2).

TLS-Version 1,3 (TLS 1,3) wird derzeit nicht unterstützt.
  
## <a name="support-for-tls-10-and-11-deprecation"></a>Unterstützung für TLS 1,0 und 1,1 veraltet

Office 365 nicht mehr unterstützt TLS 1,0 und 1,1 am 31. Oktober 2018. Neue Probleme, die in Clients, Geräten oder Diensten gefunden werden, die eine Verbindung mit Office 365 über TLS 1,0 und 1,1 herstellen, werden nicht behoben. Die offizielle veraltete Leistung für gcc High-und DoD-Umgebungen begann am 15. Januar 2020. Die veralteten TLS 1,0 und 1,1 für die weltweiten und gcc-Umgebungen begannen mit dem 15. Oktober 2020.

Um eine sichere Verbindung mit Office 365-und Microsoft 365-Diensten zu gewährleisten, verwenden alle Kombinationen von Client-Server-und Browser-Servern TLS 1,2 und moderne Verschlüsselungs Pakete. Dies erfordert möglicherweise Updates für bestimmte Client-Server- bzw. Browser-Server-Kombinationen. Informationen dazu, wie sich diese Änderung auf Sie auswirkt, finden Sie unter [Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).
  
## <a name="deprecating-support-for-3des"></a>Veraltete Unterstützung für 3DES

Seit dem 31. Oktober 2018 unterstützt Office 365 nicht mehr die Verwendung von 3DES-Verschlüsselungs Paketen für die Kommunikation mit Office 365. Genauer gesagt, unterstützt Office 365 nicht mehr die TLS_RSA_WITH_3DES_EDE_CBC_SHA-Verschlüsselungssuite. Seit dem 28. Februar 2019 wurde diese Verschlüsselungssuite in Office 365 deaktiviert. Clients und Server, die mit Office 365 kommunizieren, müssen mindestens eine der unterstützten Chiffren unterstützen. Eine Liste unterstützter Chiffren finden Sie unter [von Office 365 unterstützte TLS-Verschlüsselungs Pakete](#tls-cipher-suites-supported-by-office-365).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ende der SHA-1-Zertifikatunterstützung in Office 365

Seit Juni 2016 akzeptiert Office 365 kein SHA-1-Zertifikat mehr für ausgehende oder eingehende Verbindungen. Verwenden Sie SHA-2 (Secure Hash Algorithm 2) oder einen stärkeren Hashalgorithmus in der Zertifikatkette.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Verschlüsselungs Pakete

TLS verwendet *Verschlüsselungs Pakete*, Sammlungen von Verschlüsselungsalgorithmen, um sichere Verbindungen herzustellen. Office 365 unterstützt die in der folgenden Tabelle aufgelisteten Verschlüsselungs Pakete. In der Tabelle werden die Verschlüsselungs Pakete in der Reihenfolge ihrer Stärke aufgelistet, wobei die stärkste Verschlüsselungssuite zuerst aufgeführt wird.

Office 365 reagiert auf eine Verbindungsanforderung, indem zunächst versucht wird, eine Verbindung mit der sichersten Verschlüsselungssuite herzustellen. Wenn die Verbindung nicht funktioniert, versucht Office 365 die zweite sicherste Verschlüsselungssuite in der Liste usw. Der Dienst wird in der Liste so lange fortgesetzt, bis die Verbindung akzeptiert wird. Wenn Office 365 eine Verbindung anfordert, wählt der empfangende Dienst ebenfalls aus, ob TLS verwendet wird und welche Verschlüsselungssuite verwendet werden soll.

> [!IMPORTANT]
> Beachten Sie, dass TLS-Versionen veraltet sind und dass veraltete Versionen *nicht verwendet werden sollten* , wenn neuere Versionen verfügbar sind. TLS 1,3 wird derzeit nicht unterstützt. Wenn Ihre Vorgänger Dienste keine TLS 1,0 oder 1,1 benötigen, sollten Sie diese deaktivieren.

| Cipher Suite | Schlüsselaustauschalgorithmus/Stärke | Perfektes Forward-Geheimnis | Chiffre/Stärke | Authentifizierungsalgorithmus |
|:-----|:-----|:-----|:-----|:-----|
|TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384 <br/>     |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256 <br/>     |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA <br/>        |ECDH/192 <br/>|Ja <br/>|AES/256 <br/>|RSA/112 <br/> |
|TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA <br/>        |ECDH/128 <br/>|Ja <br/>|AES/128 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_256_GCM_SHA384 <br/>           |RSA/112 <br/> |Nein <br/> |AES/256 <br/>|RSA/112 <br/> |
|TLS_RSA_WITH_AES_128_GCM_SHA256 <br/>           |RSA/112 <br/> |Nein <br/> |AES/256 <br/>|RSA/112 <br/> |

Diese Verschlüsselungs Pakete unterstützten TLS 1,0-und 1,1-Protokolle bis zum veralteten Datum. Für gcc-High-und DoD-Umgebungen, in denen das veraltete Datum am 15. Januar 2020, und für die weltweiten und gcc-Umgebungen war dieser Termin 15. Oktober 2020.

| Protokolle | Name der Verschlüsselungssammlung | Schlüsselaustauschalgorithmus/Stärke | Unterstützung für das perfekte Forward-Geheimnis | Authentifizierungsalgorithmus/Stärke | Chiffre/Stärke |
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA        <br/> |RSA/112  <br/>  |Nein  <br/>  |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256     <br/> |RSA/112  <br/>  |Nein   <br/> |RSA/112  <br/> |AES/256  <br/> |

## <a name="related-articles"></a>Verwandte Artikel

[TLS-Verschlüsselungs Pakete in Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Verschlüsselung in Office 365](encryption.md)
  
[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md)
  
[SChannel-Implementierung von TLS 1,0 im Windows-Sicherheitsstatus Update: 24. November 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL-kryptografische Verbesserungen (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
[Vorbereiten von TLS 1.2 in Office 365 und Office 365 GCC](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)
