---
title: Datenschutzinformationen – Microsoft Defender für Endpunkt unter iOS
ms.reviewer: ''
description: Beschreibt Datenschutzinformationen für Microsoft Defender für Endpunkt unter iOS
keywords: Microsoft, Defender, Microsoft Defender für Endpunkt, ios, Richtlinie, Übersicht
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: a232bd8d600df37d5b9b01921859556476ced345
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822370"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-on-ios"></a>Datenschutzinformationen – Microsoft Defender für Endpunkt unter iOS

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender für Endpunkt unter iOS verwendet ein VPN, um das Web protection-Feature bereitzustellen. Dies ist kein reguläres VPN und ein lokales vpn oder selbstschleifend, das keinen Datenverkehr außerhalb des Geräts annimmt. **Microsoft oder Ihrer Organisation wird Ihre Browseraktivität nicht angezeigt.**

Defender für Endpunkt unter iOS sammelt Informationen von Ihren konfigurierten iOS-Geräten und speichert sie im selben Mandanten, in dem Sie Defender für Endpunkt haben. Die Informationen werden gesammelt, um Defender für Endpunkt unter iOS sicher, aktuell und erwartungsgemäß zu halten und den Dienst zu unterstützen.

Weitere Informationen zur Datenspeicherung finden Sie unter [Microsoft Defender für Endpunkt Datenspeicherung und Datenschutz.](data-storage-privacy.md)


Weitere Informationen zu den häufigsten Datenschutzfragen zu Microsoft Defender für Endpunkt auf mobilen Android- und iOS-Geräten finden Sie unter [Microsoft Defender für Endpunkt und Ihren Datenschutz auf mobilen Android- und iOS-Geräten.](https://support.microsoft.com/topic/microsoft-defender-for-endpoint-and-your-privacy-on-android-and-ios-mobile-devices-4109bc54-8ec5-4433-9c33-d359b75ac22a)

## <a name="required-data"></a>Erforderliche Daten 

Erforderliche Daten bestehen aus Daten, die erforderlich sind, damit Defender für Endpunkt unter iOS wie erwartet funktioniert. Diese Daten sind für den Betrieb des Diensts unerlässlich und können Daten im Zusammenhang mit dem Endbenutzer, der Organisation, dem Gerät und den Apps enthalten. 

Es folgt eine Liste der Arten von Daten, die gesammelt werden: 

### <a name="web-page-or-network-information"></a>Webseite oder Netzwerkinformationen 

- Domänenname und IP-Adresse der Website nur, wenn eine schädliche Verbindung oder Webseite erkannt wird. 

### <a name="device-and-account-information"></a>Geräte- und Kontoinformationen 

- Geräteinformationen wie Datum & Uhrzeit, iOS-Version, CPU-Informationen und Geräte-ID, wobei der Gerätebezeichner eine der folgenden ist: 

    - Wi-Fi Mac-Adresse des Adapters 

    - Nach dem Zufallsprinzip generierte GUID (Globally Unique Identifier) 

- Mandanten-, Geräte- und Benutzerinformationen 

    - Azure Active Directory (AD)-Geräte-ID und Azure-Benutzer-ID – Identifiziert das Gerät eindeutig bzw. den Benutzer im Azure Active Directory. 

    - Azure-Mandanten-ID – GUID, die Ihre Organisation innerhalb Azure Active Directory identifiziert. 

    - Microsoft Defender für Endpunkt-Organisations-ID : Eindeutiger Bezeichner, der dem Unternehmen zugeordnet ist, zu dem das Gerät gehört. Ermöglicht Microsoft zu erkennen, ob Probleme auftreten, die sich auf eine ausgewählte Gruppe von Unternehmen und die Anzahl der betroffenen Unternehmen auswirken. 

    - Benutzerprinzipalname – E-Mail-ID des Benutzers. 

### <a name="product-and-service-usage-data"></a>Produkt- und Dienstnutzungsdaten 

Die folgenden Informationen werden nur für die auf dem Gerät installierte Microsoft Defender für Endpunkt-App gesammelt. 

- App-Paketinformationen, einschließlich Name, Version und App-Upgradestatus. 

- Aktionen, die in der App ausgeführt werden. 

- Von iOS generierte Absturzberichtsprotokolle. 

- Speichernutzungsdaten. 

## <a name="optional-data"></a>Optionale Daten 

Optionale Daten umfassen Diagnosedaten und Feedbackdaten vom Client. Optionale Diagnosedaten sind zusätzliche Daten die uns helfen, Produktverbesserungen vorzunehmen, und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben. Diese Daten dienen nur zu Diagnosezwecken und sind nicht für den Dienst selbst erforderlich. 

Optionale Diagnosedaten umfassen: 

- App-, CPU- und Netzwerkauslastung für Defender für Endpunkt. 

- Features, die vom Administrator für Defender für Endpunkt konfiguriert wurden. 

Feedbackdaten werden durch In-App-Feedback gesammelt, das vom Benutzer bereitgestellt wird. 

- Die E-Mail-Adresse des Benutzers, wenn er sie bereitstellen möchte.

- Feedbacktyp (Gesichter, Stirnrunzeln, Idee) und feedbackkommentare, die der Benutzer übermittelt hat. 

Weitere Informationen finden Sie unter "Weitere Informationen [zum Datenschutz".](https://aka.ms/mdatpiosprivacystatement)


