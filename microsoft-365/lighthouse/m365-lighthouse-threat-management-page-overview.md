---
title: Microsoft 365 Lighthouse Übersicht über die Seite "Bedrohungsmanagement"
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: Informationen zu verwalteten Dienstanbietern (Managed Service Providers, MSPs), die Microsoft 365 Lighthouse verwenden, finden Sie auf der Seite "Bedrohungsmanagement".
ms.openlocfilehash: 10f39737bb69f4a5080b343cfbe6c6cfe5908d72
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395117"
---
# <a name="microsoft-365-lighthouse-threat-management-page-overview"></a>Microsoft 365 Lighthouse Übersicht über die Seite "Bedrohungsmanagement" 

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nur für Partner verfügbar, die die [Anforderungen](m365-lighthouse-requirements.md)erfüllen. Wenn Ihre Organisation nicht über Microsoft 365 Lighthouse verfügt, lesen Sie ["Registrieren für Microsoft 365 Lighthouse".](m365-lighthouse-sign-up.md)

**Gilt für:**

- Windows 10

Microsoft Defender Antivirus schützt Mandanten, Benutzer und Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware. Es ist ein robuster, fortlaufender Schutz, der in Windows 10 integriert und in Microsoft 365 Business Premium enthalten ist.  
  
Um auf die Seite "Bedrohungsmanagement" in Microsoft 365 Lighthouse zuzugreifen, wählen Sie im linken Navigationsbereich die **Bedrohungsverwaltung** aus, um den Sicherheitsstatus Ihrer Mandanten gegen Bedrohungen anzuzeigen. Sie sehen Mandanten, Benutzer und Geräte, die Ihre Aufmerksamkeit erfordern, und Empfehlungen, die Ihnen helfen, Risiken zu verringern.  
  
## <a name="overview-tab"></a>Registerkarte „Übersicht“  
  
Auf der Registerkarte "Übersicht" der Seite "Bedrohungsmanagement" können Sie den Antivirusstatus für alle Mandanten überwachen, um die Bereiche zu identifizieren, die Aufmerksamkeit erfordern.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-overview-tab.png" alt-text="Screenshot der Registerkarte &quot;Übersicht&quot;.>.":::

## <a name="threats-tab"></a>Registerkarte "Bedrohungen"

Auf der Registerkarte "Bedrohungen" auf der Seite "Bedrohungsmanagement" können Sie die aktiven, abgemilderten, behobenen und zulässigen Bedrohungen für alle Ihre Mandanten anzeigen. Sie können auch mehrere Bedrohungen gleichzeitig in allen Ihren Mandanten beheben, indem Sie nach jeder Bedrohung filtern und nach unten suchen, um zu erfahren, welche Geräte, Benutzer oder Mandanten betroffen sind.

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-threats-tab.png" alt-text="Screenshot der Standardmäßigen Basisplanseite.>.":::
  
Sie können Bedrohungen wie folgt filtern:

- Bedrohungsstatus
- Schweregrad der Bedrohung
- Bedrohungstyp
- Datumsbereich

In der folgenden Tabelle sind die verschiedenen Bedrohungsstatus und ihre Definition aufgeführt:<br><br>

| Bedrohungsstatus | Definition |
|--|--|
| Aktiv | Die Bedrohung ist auf dem Gerät aktiv. |
| Kein Status | Der Bedrohungsstatus ist nicht verfügbar. Führen Sie einen vollständigen Scan auf dem Gerät aus, um die Bedrohung Microsoft Defender Antivirus erneut erkannt zu haben. |
| Aktion fehlgeschlagen | Das Gerät ist nicht gefährdet. Eine Aktion ist fehlgeschlagen, aber eine potenzielle Bedrohung wurde beendet und ist auf dem Gerät nicht aktiv. Führen Sie einen vollständigen Scan auf dem Gerät aus. |
| Manuelle Schritte erforderlich | Die Bedrohung wurde beendet, erfordert jedoch einen manuellen Schritt, z. B. einen vollständigen Scan oder einen Neustart des Geräts. |
| Vollständiger Scan erforderlich | Eine vollständige Überprüfung des Geräts ist erforderlich. |
| Neustart erforderlich | Ein Neustart des Geräts ist erforderlich. |
| Behoben mit nicht kritischen Fehlern | Die Bedrohung wurde behoben, und es sind keine weiteren Aktionen erforderlich. |
| Isolierte | Die Bedrohung wurde in Quarantäne gestellt. Es sind keine weiteren Aktionen erforderlich. |
| Entfernt | Die Bedrohung wurde erfolgreich vom Gerät entfernt. Es sind keine weiteren Aktionen erforderlich. |
| Gereinigt | Microsoft Defender Antivirus dateien wiederhergestellt und verworfen hat. Es sind keine weiteren Aktionen erforderlich. |
| Zulässig | Die Bedrohung darf von einem Administrator auf dem Gerät verbleiben. | 

## <a name="antivirus-protection-tab"></a>Registerkarte "Antivirusschutz"

Auf der Registerkarte "Antivirusschutz" auf der Seite "Bedrohungsmanagement" werden die Geräte für alle Ihre Mandanten und deren Microsoft Defender Antivirus Schutzstatus angezeigt. Sie können den Status bewerten und Maßnahmen für ein oder mehrere Geräte ergreifen, die möglicherweise anfällig sind. Sie können auch ein Gerät auswählen, um weitere Informationen anzuzeigen, z. B. "Geräteübersicht", "Aktuelle Bedrohungen" und "Geräteaktionsstatus".

:::image type="content" source="../media/m365-lighthouse-threat-management-page-overview/threatmanagement-antivirus-tab.png" alt-text="Screenshot der Registerkarte &quot;Antivirus&quot;.":::

## <a name="related-content"></a>Verwandte Inhalte

[Bereitstellen Microsoft 365 Lighthouse Baselines](m365-lighthouse-deploy-baselines.md) (Artikel)\
[faq zu Microsoft 365 Lighthouse](m365-lighthouse-faq.yml) (Artikel)
