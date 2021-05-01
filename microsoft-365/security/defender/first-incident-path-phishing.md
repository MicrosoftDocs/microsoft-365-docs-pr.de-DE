---
title: Beispiel für einen Phishing-E-Mail-Angriff
description: Gehen Sie durch eine Beispielanalyse eines Phishingangriffs.
keywords: Vorfälle, Warnungen, untersuchen, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: fb3656a9d3f67d979c012d9cc316a10e65a72042
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114642"
---
# <a name="example-of-a-phishing-email-attack"></a>Beispiel für einen Phishing-E-Mail-Angriff

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Microsoft 365 Defender kann dazu beitragen, schädliche Anlagen zu erkennen, die per E-Mail zugestellt werden. Da das [Office 365 Security and Compliance Center](https://protection.office.com/) in Microsoft 365 Defender integriert ist, können Sicherheitsanalysten Einblick in Bedrohungen von Office 365 haben, z. B. über E-Mail-Anlagen.

Beispielsweise wurde einem Analysten ein mehrstufiger Vorfall zugewiesen.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-incident.png" alt-text="Beispiel für einen mehrstufigen Vorfall"::: 

Auf der **Registerkarte Warnungen** des Vorfalls werden Warnungen von Defender für Office 365 und Microsoft Cloud App Security angezeigt. Der Analyst kann einen Drilldown in defender for Office 365, indem er die Warnungen für E-Mail-Nachrichten aus wählt. Die Details der Warnung werden im Seitenbereich angezeigt.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-alerts.png" alt-text="Beispiel für eine E-Mail-Warnung":::
 
Durch einen weiteren Bildlauf nach unten werden weitere Informationen angezeigt, in denen die schädlichen Dateien und der Benutzer angezeigt werden, die betroffen waren.

:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-impact.png" alt-text="Beispiel für die Auswirkungen einer E-Mail-Benachrichtigung auf Benutzer und Dateien":::
  
Wenn **Sie die Seite Benachrichtigung öffnen** auswählen, gelangen Sie zu der spezifischen Warnung, in der verschiedene Informationen ausführlicher angezeigt werden können, indem Sie den Link auswählen. Die tatsächliche E-Mail-Nachricht kann angezeigt werden, indem Sie nachrichten **im Explorer** am unteren Rand des Panels anzeigen auswählen.
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-event-explorer.png" alt-text="Beispiel für die Details einer Warnung"::: 

Dies führt den Analysten zur Seite Bedrohungsverwaltung, auf der die E-Mail Betreff, Empfänger, Absender und andere Informationen angezeigt werden. **Zap** unter **Sonderaktionen** teilt dem Analysten mit, dass das Feature für die automatische Reinigung der Nullstunde implementiert wurde. Zap erkennt und entfernt automatisch schädliche Nachrichten und Spamnachrichten aus Postfächern in der gesamten Organisation. Weitere Informationen finden Sie unter [Zero-Hour Auto Purge (ZAP) in Exchange Online](../office-365-security/zero-hour-auto-purge.md).

Andere Aktionen können für bestimmte Nachrichten durch Auswählen von **Aktionen ergriffen werden.** 
 
:::image type="content" source="../../media/first-incident-path-phishing/first-incident-phishing-actions.png" alt-text="Beispiel für die anderen Aktionen für E-Mail-Nachrichten"::: 

## <a name="next-step"></a>Nächster Schritt

Weitere Informationen finden Sie [unter Identitätsbasierter](first-incident-path-identity.md) Angriffsuntersuchungspfad.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Analysieren von Vorfällen](investigate-incidents.md)
- [Verwalten von Vorfällen](manage-incidents.md)
