---
title: Untersuchen von Warnungen in Microsoft 365 Defender
description: Untersuchen Sie Warnungen, die auf Geräten, Benutzern und Postfächern angezeigt werden.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reagieren, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
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
ms.openlocfilehash: 567916e9e1a1d96d77bc6c187b384a1ec3be72a5
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022708"
---
# <a name="investigate-alerts-in-microsoft-365-defender"></a>Untersuchen von Warnungen in Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Warnungen sind die Basis aller Vorfälle und weisen auf das Auftreten bösartiger oder verdächtiger Ereignisse in Ihrer Umgebung hin. Warnungen sind in der Regel Teil eines umfassenderen Angriffs und liefern Hinweise zu einem Vorfall.

In Microsoft 365 Defender werden zugehörige Warnungen zu [Vorfällen](incidents-overview.md)zusammengefasst. Vorfälle bieten immer den umfassenderen Kontext eines Angriffs, die Analyse von Warnungen kann jedoch hilfreich sein, wenn eine ausführlichere Analyse erforderlich ist. 

Die **Warnungswarteschlange** zeigt den aktuellen Satz von Warnungen an. Sie gelangen in der Schnellstartleiste des Microsoft 365 Defender-Portals ( security.microsoft.com ) von **Vorfällen & Warnungen > Warnungen** in die Warnungswarteschlange.[](https://security.microsoft.com)

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-queue.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-queue.png" alt-text="Beispiel für die Warnungswarteschlange":::

Hier werden Warnungen von verschiedenen Microsoft-Sicherheitslösungen wie Microsoft Defender für Endpunkt, Microsoft Defender für Office 365 und Microsoft 365 Defender angezeigt.

Standardmäßig zeigt die Warnungswarteschlange im Microsoft 365 Defender-Portal die neuen und laufenden Warnungen der letzten 30 Tage an. Die letzte Warnung befindet sich oben in der Liste, sodass Sie sie zuerst sehen können. 

In der Standardbenachrichtigungswarteschlange können Sie **Filter** auswählen, um einen **Filterbereich** anzuzeigen, aus dem Sie eine Teilmenge der Warnungen angeben können. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-filter.png" alt-text="Beispiel für den Filterbereich für die Warnungswarteschlange":::

Sie können Warnungen nach folgenden Kriterien filtern:

- Severity
- Status
- Kategorie
- Erkennungsquelle
- Tags
- Richtlinie
- Betroffene Ressourcen

## <a name="analyze-an-alert"></a>Analysieren einer Warnung

Um die Hauptwarnungsseite anzuzeigen, wählen Sie den Namen der Warnung aus. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Defender Portal":::

Sie können auch die Aktion **"Hauptwarnungsseite öffnen"** im **Warnungsbereich "Verwalten"** auswählen.

Eine Warnungsseite besteht aus folgenden Abschnitten: 

- Warnungsartikel, bei dem es sich um die Kette von Ereignissen und Warnungen im Zusammenhang mit dieser Warnung in chronologischer Reihenfolge handelt
- Zusammenfassungsdetails

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-main.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-main.png" alt-text="Beispiel für die Detailseite einer Warnung im Microsoft 365 Defender Portal":::

Auf einer Warnungsseite können Sie die Ellipsen (**...**) neben einer beliebigen Entität auswählen, um verfügbare Aktionen anzuzeigen, z. B. das Öffnen der Warnungsseite oder das Verknüpfen der Warnung mit einem anderen Vorfall.

### <a name="alert-sources"></a>Warnungsquellen
Microsoft 365 Defender Warnungen können von Lösungen wie Microsoft Defender für Endpunkt, Microsoft Defender für Office 365 und Microsoft Cloud App Security stammen. Möglicherweise werden Warnungen mit vorangestellten Zeichen in der Warnung angezeigt. Die folgende Tabelle enthält Anleitungen, die Ihnen dabei helfen, die Zuordnung von Warnungsquellen basierend auf dem vorangestellten Zeichen der Warnung zu verstehen.

> [!NOTE]
> - Die vorangestellten GUIDs sind nur für einheitliche Umgebungen wie einheitliche Warnungswarteschlange, Seite für einheitliche Warnungen, einheitliche Untersuchung und einheitliche Vorfälle spezifisch.<br>
> - Das vorangestellte Zeichen ändert nicht die GUID der Warnung. Die einzige Änderung an der GUID ist die vorangestellte Komponente.<br>


Warnungsquelle | Vorangestelltes Zeichen 
:---|:---
Microsoft Defender für Office 365 | `fa{GUID}` <br> Beispiel: `fa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Defender für Endpunkt | `da` oder `ed` für benutzerdefinierte Erkennungswarnungen <br> 
Microsoft Defender for Identity | `aa{GUID}` <br> Beispiel: `aa123a456b-c789-1d2e-12f1g33h445h6i` 
Microsoft Cloud App Security |`ca{GUID}` <br> Beispiel: `ca123a456b-c789-1d2e-12f1g33h445h6i` 

### <a name="analyze-affected-assets"></a>Analysieren betroffener Ressourcen

Der Abschnitt **"Durchgeführte Aktionen"** enthält eine Liste der betroffenen Ressourcen, z. B. Postfächer, Geräte und Benutzer, die von dieser Warnung betroffen sind. 

Sie können auch **im Info-Center** anzeigen auswählen, um die Registerkarte **"Verlauf"** des **Info-Centers** im Microsoft 365 Defender-Portal anzuzeigen. 

### <a name="trace-an-alerts-role-in-the-alert-story"></a>Nachverfolgen der Rolle einer Warnung im Warnungsartikel

Im Warnungsabschnitt werden alle Ressourcen oder Entitäten im Zusammenhang mit der Warnung in einer Prozessstrukturansicht angezeigt. Die Warnung im Titel steht im Fokus, wenn Sie zum ersten Mal auf der Seite der ausgewählten Warnung landen. Ressourcen im Warnungsartikel können erweitert und angeklickt werden. Sie stellen zusätzliche Informationen bereit und beschleunigen Ihre Antwort, indem sie Es Ihnen ermöglichen, direkt im Kontext der Warnungsseite Maßnahmen zu ergreifen. 

> [!NOTE]
> Der Abschnitt "Warnungsabschnitt" kann mehrere Warnungen enthalten, wobei zusätzliche Warnungen im Zusammenhang mit derselben Ausführungsstruktur vor oder nach der ausgewählten Warnung angezeigt werden.

### <a name="view-more-alert-information-on-the-details-page"></a>Weitere Warnungsinformationen auf der Detailseite anzeigen

Auf der Detailseite werden die Details der ausgewählten Warnung mit details und Aktionen im Zusammenhang mit der Warnung angezeigt. Wenn Sie eine der betroffenen Ressourcen oder Entitäten im Warnungsartikel auswählen, wird die Detailseite so geändert, dass kontextbezogene Informationen und Aktionen für das ausgewählte Objekt bereitgestellt werden.

Nachdem Sie eine interessante Entität ausgewählt haben, ändert sich die Detailseite, um Informationen zum ausgewählten Entitätstyp, historische Informationen, wenn diese verfügbar sind, und Optionen zum Ergreifen von Maßnahmen für diese Entität direkt über die Warnungsseite anzuzeigen.

## <a name="manage-alerts"></a>Verwalten von Warnungen

Um eine Warnung zu verwalten, wählen Sie die Warnung in der Warnungswarteschlange in der Zeile aus, um einen **Warnungsbereich verwalten** anzuzeigen. Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-manage.png" alt-text="Beispiel für den Zusammenfassungsbereich für eine Warnung":::

Im **Bereich "Warnung verwalten"** können Sie Folgendes angeben:

- Der Warnungsstatus (Neu, Aufgelöst, In Bearbeitung).
- Die Klassifizierung der Warnung (Nicht festgelegt, True-Warnung, False-Warnung).
- Für die Klassifizierung als echte Warnung gibt die Art der Bedrohung für die Warnung im Feld **"Bestimmung"** an.
- Ein Kommentar zur Warnung.

> [!NOTE]
> Eine Möglichkeit zum Verwalten von Warnungen durch die Verwendung von Tags. Die Taggingfunktion für Microsoft Defender für Office 365 wird inkrementell eingeführt und befindet sich derzeit in der Vorschau. <br>
> Derzeit werden geänderte Tagnamen nur auf Warnungen angewendet, die *nach* dem Update erstellt wurden. Warnungen, die vor der Änderung generiert wurden, geben den aktualisierten Tagnamen nicht wieder. 

In diesem Bereich können Sie auch die folgenden zusätzlichen Aktionen ausführen: 

- Öffnen der Hauptwarnungsseite
- Wenden Sie sich an einen Microsoft-Bedrohungsexperten
- Anzeigen der Übermittlung
- Link zu einem anderen Vorfall
- Anzeigen der Warnung auf einer Zeitachse
- Erstellen einer Unterdrückungsregel

Im Folgenden sehen Sie ein Beispiel.

:::image type="content" source="../../media/investigate-alerts/alerts-ss-alerts-actions.png" lightbox="../../media/investigate-alerts/alerts-ss-alerts-actions.png" alt-text="Beispiel für die Aktionen für eine Warnung im Microsoft 365 Defender Portal":::

Die Liste der zusätzlichen Aktionen hängt vom Typ der Warnung ab.

## <a name="resolve-an-alert"></a>Auflösen einer Warnung

Sobald Sie mit der Analyse einer Warnung fertig sind und sie aufgelöst werden kann, wechseln Sie zum **Warnungsbereich "Warnung verwalten"** für die Warnung, und markieren Sie den Status **"Gelöst",** und klassifizieren Sie sie als **"False"** oder **"True".** Geben Sie für echte Warnungen den Bedrohungstyp der Warnung im **Feld "Bestimmung"** an.

Das Klassifizieren von Warnungen und die Angabe ihrer Bestimmung hilft bei der Optimierung Microsoft 365 Defender, um mehr echte und weniger falsche Warnungen bereitzustellen.

## <a name="next-steps"></a>Nächste Schritte

Setzen Sie Ihre [Untersuchung](investigate-incidents.md)nach Bedarf für In-Process-Vorfälle fort.

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle](incidents-overview.md)
- [Verwalten von Vorfällen](manage-incidents.md)
- [Untersuchen von Vorfällen](investigate-incidents.md)
