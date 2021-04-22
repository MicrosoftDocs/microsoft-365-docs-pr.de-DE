---
title: Microsoft Defender für Endpunkt unter Android – Datenschutzinformationen
description: Datenschutzsteuerelemente, Konfigurieren von Richtlinieneinstellungen, die sich auf den Datenschutz auswirken, sowie Informationen zu den diagnosedaten, die in Microsoft Defender for Endpoint auf Android gesammelt werden.
keywords: microsoft, defender, Microsoft Defender for Endpoint, android, privacy, diagnostic
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
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 1aaae2970cfb2f6da82507eefa87c8d0e2227661
ms.sourcegitcommit: 4076b43a4b661de029f6307ddc1a989ab3108edb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51939624"
---
#  <a name="microsoft-defender-for-endpoint-on-android---privacy-information"></a>Microsoft Defender für Endpunkt unter Android – Datenschutzinformationen

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


Defender for Endpoint unter Android sammelt Informationen von Ihren konfigurierten Android-Geräten und speichert sie im selben Mandanten, in dem Sie Defender for Endpoint haben. Die Informationen werden gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.

Weitere Informationen zur Datenspeicherung finden Sie unter [Microsoft Defender for Endpoint data storage and privacy](data-storage-privacy.md).

Es werden Informationen gesammelt, um Defender for Endpoint für Android sicher, auf dem neuesten Stand zu halten, wie erwartet zu gewährleisten und den Dienst zu unterstützen.

## <a name="required-data"></a>Erforderliche Daten 

Erforderliche Daten bestehen aus Daten, die erforderlich sind, damit Defender for Endpoint für Android wie erwartet funktioniert. Diese Daten sind für den Betrieb des Diensts unerlässlich und können Daten im Zusammenhang mit dem Endbenutzer, der Organisation, dem Gerät und den Apps enthalten. Im Folgenden finden Sie eine Liste der Arten von Daten, die erfasst werden:

### <a name="app-information"></a>App-Informationen

Informationen zu **schädlichen** Android-Anwendungspaketen (APKs) auf dem Gerät, einschließlich

-  Installationsquelle
-  Speicherort (Dateipfad) der APK
-  Zeitpunkt der Installation, Größe der APK und Berechtigungen

### <a name="web-page--network-information"></a>Webseiten-/Netzwerkinformationen

- Vollständige URL der Website nur, wenn eine schädliche Verbindung oder Webseite erkannt wird.
- Verbindungsinformationen
- Protokolltyp (z. B. HTTP, HTTPS usw.)


### <a name="device-and-account-information"></a>Geräte- und Kontoinformationen

- Geräteinformationen wie Datum &, Android-Version, OEM-Modell, CPU-Informationen und Geräte-ID
- Die Geräte-ID ist eine der folgenden:
    - Wi-Fi-MAC-Adresse des Adapters
    - [Android-ID](https://developer.android.com/reference/android/provider/Settings.Secure#ANDROID_ID) (wie von Android beim ersten Start des Geräts generiert)
    - Nach dem Zufallsprinzip generierte GUID (Globally Unique Identifier)

- Mandanten-, Geräte- und Benutzerinformationen
    -   Azure Active Directory (AD)-Geräte-ID und Azure-Benutzer-ID: Identifiziert das Gerät eindeutig, Benutzer bzw. Azure Active Directory.

    -   Azure-Mandanten-ID – GUID, die Ihre Organisation in Azure Active Directory identifiziert

    -   Microsoft Defender for Endpoint Org ID – Eindeutige ID, die dem Unternehmen zugeordnet ist, zu dem das Gerät gehört. Ermöglicht Microsoft zu ermitteln, ob sich Probleme auf eine ausgewählte Gruppe von Unternehmen auswirken und wie viele Unternehmen betroffen sind 

    -   Benutzerprinzipalname – E-Mail-ID des Benutzers

### <a name="product-and-service-usage-data"></a>Produkt- und Dienstnutzungsdaten

Die folgenden Informationen werden nur für die auf dem Gerät installierte Microsoft Defender for Endpoint-App gesammelt. 

-   Informationen zum App-Paket, einschließlich Name, Version und Status des App-Upgrades

-   In der App ausgeführte Aktionen

-   Informationen zur Bedrohungserkennung, z. B. Bedrohungsname, Kategorie usw.

-   Von Android generierte Absturzberichtsprotokolle

## <a name="optional-data"></a>Optionale Daten

Optionale Daten umfassen Diagnosedaten und Feedbackdaten. Optionale Diagnosedaten sind zusätzliche Daten die uns helfen, Produktverbesserungen vorzunehmen, und erweiterte Informationen liefern, die uns helfen, Probleme zu erkennen, zu diagnostizieren und zu beheben. Optionale Diagnosedaten umfassen:

-   App-, CPU- und Netzwerknutzung

-   Status des Geräts aus App-Sicht, einschließlich Scanstatus, Scanzeit, erteilten App-Berechtigungen und Upgradestatus

-   Vom Administrator konfigurierte Features

-   Grundlegende Informationen zu den Browsern auf dem Gerät

**Feedbackdaten** werden über in-App-Feedback gesammelt, das vom Benutzer bereitgestellt wird.

-   Die E-Mail-Adresse des Benutzers, wenn er sie angeben will

-   Feedbacktyp (Schmunzeln, Stirnrunzeln, Idee) und alle vom Benutzer übermittelten Feedbackkommentare
