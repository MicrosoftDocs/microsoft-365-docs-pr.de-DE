---
title: Übersicht über den Informationsschutz in Windows
ms.reviewer: ''
description: Erfahren Sie, wie der Informationsschutz in Windows funktioniert, um vertrauliche Informationen zu identifizieren und zu schützen.
keywords: Informationen, Schutz, DLP, Daten, Verlust, Verhinderung, schützen
search.product: eADQiWindows 10XVcnh
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
ms.openlocfilehash: 9d68f879fe8fd9379b286c106ed9229895f91b9a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841107"
---
# <a name="information-protection-in-windows-overview"></a>Übersicht über den Informationsschutz in Windows

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink) 


[!include[Prerelease information](../../includes/prerelease.md)]

Informationsschutz ist ein integraler Bestandteil Microsoft 365 Enterprise Suite und bietet intelligenten Schutz, um vertrauliche Daten zu schützen und gleichzeitig die Produktivität am Arbeitsplatz zu ermöglichen.


>[!TIP]
> Lesen Sie unseren Blogbeitrag über die Integration von Microsoft Defender für Endpunkt in Microsoft Information Protection, um vertrauliche Daten auf Windows Geräten zu [ermitteln, zu schützen und zu überwachen.](https://cloudblogs.microsoft.com/microsoftsecure/2019/01/17/windows-defender-atp-integrates-with-microsoft-information-protection-to-discover-protect-and-monitor-sensitive-data-on-windows-devices/)

Defender für Endpunkt wendet die folgenden Methoden an, um Daten zu ermitteln, zu klassifizieren und zu schützen:

- **Datenermittlung** – Identifizieren vertraulicher Daten auf Windows gefährdeten Geräten
- **Datenklassifizierung** – Automatische Klassifizierung von Daten basierend auf allgemeinen Microsoft Information Protection (MIP)-Richtlinien, die im Office 365 Security & Compliance Center verwaltet werden. Mithilfe der automatischen Klassifizierung können Sie vertrauliche Daten auch dann schützen, wenn der Endbenutzer sie nicht manuell klassifiziert hat.


## <a name="data-discovery-and-data-classification"></a>Datenermittlung und Datenklassifizierung

Defender für Endpunkt erkennt automatisch Dateien mit Vertraulichkeitsbezeichnungen und Dateien, die vertrauliche Informationstypen enthalten.

Vertraulichkeitsbezeichnungen klassifizieren und schützen vertrauliche Inhalte.

Typen vertraulicher Informationen in der Implementierung Office 365 Verhinderung von Datenverlust (Data Loss Prevention, DLP) werden in zwei Kategorien unterteilt:

- Standard
- Benutzerdefiniert

Zu den standardmäßigen Typen vertraulicher Informationen gehören Informationen wie Bankkontonummern, Sozialversicherungsnummern oder nationale IDs. Weitere Informationen finden Sie unter ["Wonach der Typ vertraulicher Informationen sucht".](/office365/securitycompliance/what-the-sensitive-information-types-look-for)

Benutzerdefinierte Typen sind typen, die Sie definieren und die einen anderen Typ vertraulicher Informationen schützen sollen (z. B. Mitarbeiter-IDs oder Projektnummern). Weitere Informationen finden Sie unter [Erstellen eines benutzerdefinierten vertraulichen Informationstyps.](/office365/securitycompliance/create-a-custom-sensitive-information-type)

Wenn eine Datei auf einem Windows Gerät erstellt oder bearbeitet wird, überprüft Defender für Endpunkt den Inhalt, um zu bewerten, ob er vertrauliche Informationen enthält.

Aktivieren Sie die Azure Information Protection-Integration, sodass eine Datei, die vertrauliche Informationen enthält, von Defender für Endpunkt über Bezeichnungen oder Informationstypen erkannt wird, automatisch vom Gerät an Azure Information Protection weitergeleitet wird.

![Abbildung der Einstellungsseite mit Azure Information Protection](images/atp-settings-aip.png)

Die gemeldeten Signale können im Azure Information Protection – Data Discovery-Dashboard angezeigt werden.

## <a name="azure-information-protection---data-discovery-dashboard"></a>Azure Information Protection – Datenermittlungs-Dashboard

Dieses Dashboard enthält eine Zusammenfassung der Ermittlungsinformationen von Daten, die sowohl von Defender für Endpunkt als auch von Azure Information Protection ermittelt wurden. Daten aus Defender für Endpunkt sind mit Standorttyp – Endpunkt gekennzeichnet.

![Abbildung von Azure Information Protection – Datenermittlung](images/azure-data-discovery.png)

Beachten Sie die Spalte "Geräterisiko" auf der rechten Seite, dieses Geräterisiko wird direkt von Defender für Endpunkt abgeleitet und gibt die Risikostufe des Sicherheitsgeräts an, auf dem die Datei erkannt wurde, basierend auf den aktiven Sicherheitsbedrohungen, die von Defender für Endpunkt erkannt wurden.

Klicken Sie auf ein Gerät, um eine Liste der auf diesem Gerät beobachteten Dateien mit ihren Vertraulichkeitsbezeichnungen und Informationstypen anzuzeigen.

>[!NOTE]
>Bitte lassen Sie ca. 15-20 Minuten zu, damit die Azure Information Protection Dashboard Discovery ermittelte Dateien wiedergibt.

## <a name="log-analytics"></a>Log Analytics

Die auf Defender für Endpunkt basierende Datenermittlung ist auch in [Azure Log Analytics](/azure/log-analytics/log-analytics-overview)verfügbar, wo Sie komplexe Abfragen über die Rohdaten ausführen können.

Weitere Informationen zu Azure Information Protection-Analysen finden Sie unter ["Zentrale Berichterstellung für Azure Information Protection".](/azure/information-protection/reports-aip)

Öffnen Sie Azure Log Analytics im Azure-Portal, und öffnen Sie einen Abfrage-Generator (Standard oder klassisch).

Führen Sie zum Anzeigen von Defender für Endpunkt-Daten eine Abfrage aus, die Folgendes enthält:

```
InformationProtectionLogs_CL
| where Workload_s == "Windows Defender"
```

**Voraussetzungen:**

- Kunden müssen über ein Abonnement für Azure Information Protection verfügen.
- Aktivieren Sie die Azure Information Protection-Integration in Microsoft Defender Security Center:
    - Wechseln Sie zu **Einstellungen** in Microsoft Defender Security Center, klicken Sie auf **"Erweitert" Einstellungen** unter **"Allgemein".**



