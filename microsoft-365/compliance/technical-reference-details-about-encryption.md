---
title: Technische Referenzdetails zur Verschlüsselung
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 03/29/2019
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Strat_O365_IP
search.appverid:
- MET150
- MOE150
ms.assetid: 862cbe93-4268-4ef9-ba79-277545ecf221
description: Erfahren Sie mehr über die verschiedenen Zertifikate, Technologien und TLS-Verschlüsselungs Pakete, die für die Verschlüsselung in Office 365 verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f15f55c4a66d579d547a164633613175f254640b
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44034529"
---
# <a name="technical-reference-details-about-encryption"></a>Technische Referenzdetails zur Verschlüsselung

In diesem Artikel erhalten Sie Informationen zu Zertifikaten, Technologien und TLS-Verschlüsselungs Paketen, die für die [Verschlüsselung in Office 365](encryption.md)verwendet werden. Dieser Artikel enthält auch Details zu geplanten veralteten Abschreibungen.
  
- Wenn Sie nach Übersichtsinformationen suchen, finden Sie unter [Encryption in Office 365](encryption.md).
- Informationen zum Einrichten finden Sie unter [Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md).
- Informationen zu Verschlüsselungs Paketen, die von bestimmten Versionen von Windows unterstützt werden, finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
    
## <a name="microsoft-office-365-certificate-ownership-and-management"></a>Eigentümerschaft und Verwaltung des Microsoft Office 365-Zertifikats

Sie müssen keine Zertifikate für Office 365 kaufen oder verwalten, da Microsoft eigene Zertifikate verwendet.
  
## <a name="current-encryption-standards-and-planned-deprecations"></a>Aktuelle Verschlüsselungsstandards und geplante veralteungen

Um weiterhin die Best-in-Class-Verschlüsselung für Office 365 bereitzustellen, überprüft Microsoft regelmäßig unterstützte Verschlüsselungsstandards. Manchmal müssen wir alte Standards veraltern, da sie veraltet und somit unsicherer werden. In diesem Thema werden derzeit unterstützte Verschlüsselungs Pakete und andere Standards sowie Details zu geplanten veralteten Informationen beschrieben. 

## <a name="fips-compliance-for-office-365"></a>FIPS-Konformität für Office 365
Alle von Office 365 unterstützten Verschlüsselungs Pakete verwenden Algorithmen, die unter FIPS 140-2 akzeptabel sind. Office 365 erbt FIPS-Validierungen von Windows (über SChannel). Informationen zu SChannel finden Sie unter [Cipher Suites in TLS/SSL (Schannel SSP)](https://docs.microsoft.com/windows/desktop/SecAuthN/cipher-suites-in-schannel).
  
## <a name="versions-of-tls-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Versionen

Transport Layer Security (TLS) und SSL (vor TLS) sind kryptografische Protokolle, die die Kommunikation über ein Netzwerk mithilfe von Sicherheitszertifikaten sichern, die eine Verbindung zwischen Computern verschlüsseln. Office 365 unterstützt mehrere TLS-Versionen, darunter auch:
  
- TLS-Version 1.2 (TLS 1.2)
    
- TLS-Version 1.1 (TLS 1.1)
    
- TLS-Version 1.0 (TLS 1.0)
    
 Die TLS 1,0-und TLS 1,1-Unterstützung werden am 31. Oktober 2018 veraltet. Weitere Informationen finden Sie unter [deprecated Support for TLS 1,0 and 1,1 und was dies für Sie bedeutet](technical-reference-details-about-encryption.md#TLS11and12deprecation) . 
 
 TLS-Version 1,3 (TLS 1,3) wird derzeit nicht unterstützt.
  
## <a name="deprecating-support-for-tls-10-and-11-and-what-this-means-for-you"></a>Veraltete Unterstützung für TLS 1,0 und 1,1 und was dies für Sie bedeutet
<a name="TLS11and12deprecation"> </a>

Seit dem 31. Oktober 2018 unterstützt Office 365 nicht mehr TLS 1,0 und 1,1. Dies bedeutet, dass Microsoft keine neuen Probleme beheben wird, die in Clients, Geräten oder Diensten auftreten, die sich mit Office 365 über TLS 1.0 und 1.1 verbinden.

Hinweis Dies bedeutet nicht, dass Office 365 TLS 1,0-und 1,1-Verbindungen blockieren wird. 

TLS 1,0 und TLS 1,1 werden an den folgenden Tagen offiziell veraltet sein:
- 1. Juni 2020 für Kunden in den weltweiten und gcc-Umgebungen.
- 15. Januar 2020 für Kunden in den souveränen gcc-und DoD-Umgebungen. 

Sie sollten sicherstellen, dass alle Client-Server-und Browser Serverkombinationen TLS 1,2 und moderne Verschlüsselungs Anzüge verwenden, um eine sichere Verbindung mit Office 365 Diensten aufrechtzuerhalten. Möglicherweise müssen Sie bestimmte Client-Server-und Browser Serverkombinationen aktualisieren. Informationen dazu, wie sich dies auf Sie auswirkt, finden Sie unter [Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/en-us/help/4057306/preparing-for-tls-1-2-in-office-365).

Sie sollten sicherstellen, dass für alle Client-Server-und Browser Serverkombinationen TLS 1,2 (oder eine höhere Version) verwendet wird, um die Verbindung mit Office 365 Diensten aufrechtzuerhalten. Möglicherweise müssen Sie bestimmte Client-Server-und Browser Serverkombinationen aktualisieren. Informationen dazu, wie sich dies auf Sie auswirkt, finden Sie unter [Vorbereiten der obligatorischen Verwendung von TLS 1,2 in Office 365](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365).

  
## <a name="deprecating-support-for-3des"></a>Veraltete Unterstützung für 3DES
<a name="TLS11and12deprecation"> </a>

Seit dem 31. Oktober 2018 unterstützt Office 365 nicht mehr die Verwendung von 3DES-Verschlüsselungs Paketen für die Kommunikation mit Office 365. Genauer gesagt, unterstützt Office 365 nicht mehr die TLS_RSA_WITH_3DES_EDE_CBC_SHA-Verschlüsselungssuite. Seit dem 28. Februar 2019 wird diese Verschlüsselungssuite in Office 365 deaktiviert. Clients und Server, die nach diesem Datum mit O365 kommunizieren, müssen mindestens eine der in diesem Thema aufgelisteten sicheren Chiffren unterstützen (siehe [TLS-Verschlüsselungs Pakete, die von Office 365 unterstützt werden](technical-reference-details-about-encryption.md#TLSCipherSuites)).
  
## <a name="deprecating-sha-1-certificate-support-in-office-365"></a>Ende der SHA-1-Zertifikatunterstützung in Office 365
<a name="TLS11and12deprecation"> </a>

Ab dem 2016. Juni akzeptiert Office 365 kein SHA-1-Zertifikat mehr für ausgehende oder eingehende Verbindungen. Wenn Sie derzeit ein Zertifikat mit SHA-1 in der Zertifikatkette verwenden, müssen Sie die Kette so aktualisieren, dass SHA-2 (Secure Hash Algorithm 2) oder ein stärkerer Hashalgorithmus verwendet wird.
  
## <a name="tls-cipher-suites-supported-by-office-365"></a>Von Office 365 unterstützte TLS-Verschlüsselungs Pakete
<a name="TLSCipherSuites"> </a>

Bei einer Cipher Suite handelt es sich um eine Sammlung von Verschlüsselungsalgorithmen, mit denen TLS sichere Verbindungen herstellt. Von Office 365 unterstützte Verschlüsselungs Pakete werden in der folgenden Tabelle in der Reihenfolge der Stärke mit der stärksten Verschlüsselungssuite aufgeführt, die zuerst aufgeführt wird. Wenn Office 365 eine Verbindungsanforderung erhält, versucht Office 365 zunächst, eine Verbindung mit der obersten Verschlüsselungssuite herzustellen und dann, wenn Sie nicht erfolgreich ist, die zweite Verschlüsselungssuite in der Liste und so weiter unten in der Liste. Wenn Office 365 eine Verbindungsanforderung an einen anderen Server oder an einen Client sendet, ist es an dem empfangenden Server oder Client, die Verschlüsselungssuite auszuwählen, oder ob TLS überhaupt verwendet wird.

> [!IMPORTANT]
> Beachten Sie, dass TLS-Versionen veraltet sind und dass veraltete Versionen *nicht verwendet werden sollten* , wenn neuere Versionen verfügbar sind. In anderen Worten: überall dort, wo es aufgeführt ist, dass TLS 1,0, 1,1 und 1,2 unterstützt werden, wählen Sie die *neueste* unterstützte Version (TLS 1,2) aus. TLS wird derzeit nicht unterstützt. Wenn Ihre Vorgänger Dienste keine TLS 1,0 oder 1,1 benötigen, sollten Sie diese deaktivieren. 
  
|**Protokolle**|**Name der Verschlüsselungssammlung**|**Schlüsselaustauschalgorithmus/Stärke**|**Unterstützung für das perfekte Forward-Geheimnis**|**Authentifizierungsalgorithmus/Stärke**|**Chiffre/Stärke**|
|:-----|:-----|:-----|:-----|:-----|:-----|
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_GCM_SHA384  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_GCM_SHA256  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA384_P384  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA256_P256  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_256_CBC_SHA_P384  <br/> |ECDH/192  <br/> |Ja  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_ECDHE_RSA_WITH_AES_128_CBC_SHA_P256  <br/> |ECDH/128  <br/> |Ja  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA256  <br/> |RSA/112  <br/> |Nein  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA256  <br/> |RSA/112  <br/> |Nein  <br/> |RSA/112  <br/> |AES/128  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_256_CBC_SHA  <br/> |RSA/112  <br/> |Nein  <br/> |RSA/112  <br/> |AES/256  <br/> |
|TLS 1.0, 1.1, 1.2  <br/> |TLS_RSA_WITH_AES_128_CBC_SHA  <br/> |RSA/112  <br/> |Nein  <br/> |RSA/112  <br/> |AES/128  <br/> |
   
## <a name="related-topics"></a>Verwandte Themen
[TLS-Verschlüsselungs Pakete in Windows 10 v1903](https://docs.microsoft.com/windows/win32/secauthn/tls-cipher-suites-in-windows-10-v1903)

[Verschlüsselung in Office 365](encryption.md)
  
[Einrichten der Verschlüsselung in Office 365 Enterprise](set-up-encryption.md)
  
[SChannel-Implementierung von TLS 1,0 im Windows-Sicherheitsstatus Update: 24. November 2015](https://support.microsoft.com/kb/3117336)
  
[TLS/SSL-kryptografische Verbesserungen (Windows IT Center)](https://technet.microsoft.com/library/cc766285%28v=ws.10%29.aspx)
  
 [Vorbereiten auf TLS 1,2 in Office 365 und Office 365 gcc](https://docs.microsoft.com/office365/troubleshoot/security/prepare-tls-1.2-in-office-365)

