---
title: Datenschutzinformationen – Microsoft Defender for Endpoint für iOS
ms.reviewer: ''
description: Beschreibt Datenschutzinformationen für Microsoft Defender for Endpoint für iOS
keywords: microsoft, defender, atp, ios, policy, overview
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
ms.openlocfilehash: 97d22cd8ff1c651bdab5c3613567b2a4778ec9d6
ms.sourcegitcommit: 987f70e44e406ab6b1dd35f336a9d0c228032794
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/05/2021
ms.locfileid: "51587575"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>Datenschutzinformationen – Microsoft Defender for Endpoint für iOS

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> Defender for Endpoint für iOS verwendet ein VPN, um das Web Protection-Feature zur Verfügung zu stellen. Dies ist kein normales VPN und ein lokales oder selbstschleifendes VPN, das keinen Datenverkehr außerhalb des Geräts über sich nimmt. **Microsoft oder Ihre Organisation wird Ihre Browseraktivität nicht sehen.**

Defender for Endpoint für iOS sammelt Informationen von Ihren konfigurierten iOS-Geräten und speichert sie im selben Mandanten, in dem Sie Defender for Endpoint haben. Die Informationen werden gesammelt, um Defender for Endpoint für iOS sicher, aktuell und wie erwartet zu halten und den Dienst zu unterstützen.

Weitere Informationen zur Datenspeicherung finden Sie unter [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

## <a name="required-data"></a>Erforderliche Daten 

Erforderliche Daten bestehen aus Daten, die erforderlich sind, damit Defender for Endpoint für iOS wie erwartet funktioniert. Diese Daten sind für den Betrieb des Diensts unerlässlich und können Daten im Zusammenhang mit dem Endbenutzer, der Organisation, dem Gerät und den Apps enthalten. 

Im Folgenden finden Sie eine Liste der Arten von Daten, die erfasst werden: 

### <a name="web-page-or-network-information"></a>Webseiten- oder Netzwerkinformationen 

- Domänenname der Website nur, wenn eine schädliche Verbindung oder Webseite erkannt wird. 

### <a name="device-and-account-information"></a>Geräte- und Kontoinformationen 

- Geräteinformationen, z. B. Datum & Uhrzeit, iOS-Version, CPU-Informationen und Geräte-ID, wobei gerätebezeichner einer der folgenden Punkte ist: 

    - Wi-Fi-MAC-Adresse des Adapters 

    - Nach dem Zufallsprinzip generierte GUID (Globally Unique Identifier) 

- Mandanten-, Geräte- und Benutzerinformationen 

    - Azure Active Directory (AD)-Geräte-ID und Azure-Benutzer-ID – Identifiziert das Gerät eindeutig, Benutzer bzw. Azure Active Directory. 

    - Azure-Mandanten-ID – GUID, die Ihre Organisation in Azure Active Directory identifiziert. 

    - Microsoft Defender for Endpoint Org ID – Eindeutige ID, die dem Unternehmen zugeordnet ist, zu dem das Gerät gehört. Ermöglicht Microsoft zu ermitteln, ob Probleme auftreten, die sich auf eine ausgewählte Gruppe von Unternehmen und die Anzahl betroffener Unternehmen auswirken. 

    - Benutzerprinzipalname – E-Mail-ID des Benutzers. 

### <a name="product-and-service-usage-data"></a>Produkt- und Dienstnutzungsdaten 

Die folgenden Informationen werden nur für die auf dem Gerät installierte Microsoft Defender for Endpoint-App gesammelt. 

- Informationen zum App-Paket, einschließlich Name, Version und App-Upgradestatus. 

- Aktionen, die in der App durchgeführt werden. 

- Absturzberichtsprotokolle, die von iOS generiert werden. 

- Speichernutzungsdaten. 

## <a name="optional-data"></a>Optionale Daten 

Optionale Daten umfassen Diagnosedaten und Feedbackdaten vom Client. Optionale Diagnosedaten sind zusätzliche Daten die uns helfen, Produktverbesserungen vorzunehmen, und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben. Diese Daten dienen nur zu Diagnosezwecken und sind nicht für den Dienst selbst erforderlich. 

Optionale Diagnosedaten umfassen: 

- App-, CPU- und Netzwerknutzung für Defender for Endpoint. 

- Vom Administrator für Defender for Endpoint konfigurierte Features. 

FeedbackDaten werden über in-App-Feedback gesammelt, das vom Benutzer bereitgestellt wird. 

- Die E-Mail-Adresse des Benutzers, wenn er sie angeben will.

- Feedbacktyp (Schmunzeln, Stirnrunzeln, Idee) und alle vom Benutzer übermittelten Feedbackkommentare. 

Weitere Informationen finden Sie unter [More on Privacy](https://aka.ms/mdatpiosprivacystatement).


