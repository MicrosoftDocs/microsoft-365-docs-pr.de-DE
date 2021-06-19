---
title: E-Mail-Sicherheit mit dem Sicherheitsrisiken-Explorer in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Anzeigen und Untersuchen von Phishingversuchen durch Schadsoftware.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: eb62961bb26b079c508cbd5bc559a95d172cff86
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029885"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>E-Mail-Sicherheit mit dem Sicherheitsrisiken-Explorer in Microsoft Defender für Office 365

Inhalt dieses Artikels:

- [Anzeigen von schadsoftware, die in E-Mails erkannt wurde](#view-malware-detected-in-email)
- [Phishing-URL anzeigen und auf Bewertungsdaten klicken](#view-phishing-url-and-click-verdict-data)
- [Starten der automatisierten Untersuchung und Reaktion](#start-automated-investigation-and-response)

> [!NOTE]
> Dies ist Teil einer **Drei-Artikel-Reihe** zu Den Grundlagen von **Bedrohungs-Explorer (Explorer),** **E-Mail-Sicherheit** und **Explorer und Echtzeiterkennungen** (z. B. Unterschiede zwischen den Tools und berechtigungen, die zum Ausführen dieser Tools erforderlich sind). Die beiden anderen Artikel in dieser Reihe sind [die Bedrohungssuche im Bedrohungs-Explorer](threat-hunting-in-threat-explorer.md) und [im Bedrohungs-Explorer sowie grundlagen der Echtzeiterkennung.](real-time-detections.md)

In diesem Artikel wird erläutert, wie Sie Schadsoftware- und Phishingversuche anzeigen und untersuchen, die in E-Mails von Microsoft 365 Sicherheitsfeatures erkannt werden.

**Gilt für:**

- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Anzeigen von schadsoftware, die in E-Mails erkannt wurde

Um Schadsoftware in E-Mails zu sehen, die nach Microsoft 365 Technologie sortiert sind, verwenden Sie die [E-Mail-> Schadsoftwareansicht](threat-explorer-views.md#email--malware) des Explorers (oder Echtzeiterkennungen). Schadsoftware ist die Standardansicht, sodass sie möglicherweise ausgewählt wird, sobald Sie Den Explorer öffnen.

1. Wählen Sie im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) **E-Mail-&** \> **Zusammenarbeits-Explorer (oder Echtzeiterkennungen) aus.**  In diesem Beispiel wird Explorer verwendet.

   Beginnen Sie hier in der Ansicht, wählen Sie einen bestimmten Zeitrahmen für die Untersuchung (falls erforderlich) aus, und konzentrieren Sie ihre Filter gemäß der [exemplarischen Vorgehensweise](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)des Explorers.

2. Überprüfen Sie in der Dropdownliste **"Ansicht",** ob **E-Mail-Schadsoftware** \>  ausgewählt ist.

3. Klicken Sie auf **"Absender"** und dann in der Dropdownliste auf **"Grundlegende** \> **Erkennungstechnologie".**

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech-newimg.png" alt-text="Schadsoftwareerkennungstechnologie":::

   Ihre Erkennungstechnologien sind jetzt als Filter für den Bericht verfügbar.

4. Wählen Sie eine Option aus, und klicken Sie dann auf **"Aktualisieren",** um diesen Filter anzuwenden (aktualisieren Sie das Browserfenster nicht).

   :::image type="content" source="../../media/exploreremailmalwaredetectiontech2-new.png" alt-text="Ausgewählte Erkennungstechnologie":::

   Der Bericht wird aktualisiert, um die Ergebnisse anzuzeigen, die Schadsoftware in E-Mails mithilfe der ausgewählten Technologieoption erkannt hat. Von hier aus können Sie weitere Analysen durchführen.

## <a name="view-phishing-url-and-click-verdict-data"></a>Phishing-URL anzeigen und auf Bewertungsdaten klicken

Sie können Phishingversuche über URLs in E-Mails anzeigen, einschließlich einer Liste der URLs, die zugelassen, blockiert und überschrieben wurden. Um URLs zu identifizieren, auf die geklickt wurde, müssen [Safe Links](safe-links.md) konfiguriert werden. Stellen Sie sicher, dass Sie [Safe Verknüpfungsrichtlinien](set-up-safe-links-policies.md) für Denkzeitschutz und Protokollierung von Klickbewertungen durch Safe Links einrichten.

1. Wählen Sie im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) **E-Mail-&** \> **Zusammenarbeits-Explorer (oder Echtzeiterkennungen) aus.**  In diesem Beispiel wird Explorer verwendet.

2. Wählen Sie in der Dropdownliste **Ansicht** **E-Mail-Phishing** \> aus.

   > [!div class="mx-imgBorder"]
   > ![Ansichtsmenü für Explorer im Phishingkontext](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicken Sie auf **"Absender"** und dann auf **"URLs** \> Klicken Sie in der Dropdownliste" auf **"Bewertung".**

4. Wählen Sie in angezeigten Optionen eine oder mehrere Optionen aus, z. B. **"Blockiert"** und **"Blockieren",** und klicken Sie dann auf **"Aktualisieren"** (aktualisieren Sie das Browserfenster nicht).

    :::image type="content" source="../../media/threatexploreremailphishclickverdict-new.png" alt-text="URLs und Klickbewertungen":::

   Der Bericht wird aktualisiert, um zwei verschiedene URL-Tabellen auf der Registerkarte **"URLs"** unter dem Bericht anzuzeigen:

   - **Die häufigsten URLs** sind die URLs in den Nachrichten, nach denen Sie gefiltert haben, und die Anzahl der E-Mail-Zustellungsaktionen für jede URL. In der Phishing-E-Mail-Ansicht enthält diese Liste in der Regel legitime URLs. Angreifer enthalten eine Mischung aus guten und schlechten URLs in ihren Nachrichten, um zu versuchen, sie zuzustellen, aber sie machen die bösartigen Links interessanter. Die Tabelle der URLs wird nach der Gesamtzahl der E-Mails sortiert, aber diese Spalte ist ausgeblendet, um die Ansicht zu vereinfachen.

   - **Die häufigsten Klicks** sind die Safe mit Links umschlossenen URLs, auf die geklickt wurde, sortiert nach der Gesamtzahl der Klicks. Diese Spalte wird auch nicht angezeigt, um die Ansicht zu vereinfachen. Die Gesamtanzahl nach Spalte gibt die Anzahl der Safe links click-Bewertung für jede angeklickte URL an. In der Phishing-E-Mail-Ansicht handelt es sich dabei in der Regel um verdächtige oder bösartige URLs. Die Ansicht kann jedoch URLs enthalten, die keine Bedrohungen sind, sondern sich in Phishing-Nachrichten befinden. URL-Klicks auf nicht gepackte Links werden hier nicht angezeigt.

   In den beiden URL-Tabellen werden die wichtigsten URLs in Phishing-E-Mail-Nachrichten nach Zustellungsaktion und Speicherort angezeigt. In den Tabellen werden URL-Klicks angezeigt, die trotz einer Warnung blockiert oder besucht wurden, sodass Sie sehen können, welche potenziellen fehlerhaften Links benutzern angezeigt wurden und auf die die Benutzer geklickt haben. Von hier aus können Sie weitere Analysen durchführen. Unterhalb des Diagramms können Sie beispielsweise die wichtigsten URLs in E-Mail-Nachrichten anzeigen, die in der Umgebung Ihrer Organisation blockiert wurden.

   > [!div class="mx-imgBorder"]
   > ![Explorer-URLs, die blockiert wurden](../../media/ExplorerPhishClickVerdictURLs.png)

   Wählen Sie eine URL aus, um ausführlichere Informationen anzuzeigen.

   > [!NOTE]
   > Im Dialogfeld "URL-Flyout&quot; wird die Filterung nach E-Mail-Nachrichten entfernt, um die vollständige Ansicht der Url-Belichtung in Ihrer Umgebung anzuzeigen. Auf diese Weise können Sie nach E-Mail-Nachrichten filtern, über die Sie sich im Explorer Gedanken machen, nach bestimmten URLs suchen, die potenzielle Bedrohungen sind, und dann Ihr Verständnis der URL-Gefährdung in Ihrer Umgebung erweitern (über das Dialogfeld &quot;URL-Details"), ohne der Explorer-Ansicht selbst URL-Filter hinzufügen zu müssen.

### <a name="interpretation-of-click-verdicts"></a>Interpretation von Klickbewertungen

In den Flyouts "E-Mail" oder "URL", "Häufigste Klicks" und in unseren Filterfunktionen werden unterschiedliche Klickbewertungswerte angezeigt:

- **Keine:** Das Diktat für die URL kann nicht erfasst werden. Der Benutzer hat möglicherweise durch die URL geklickt.
- **Zulässig:** Der Benutzer konnte zur URL navigieren.
- **Blockiert:** Der Benutzer wurde am Navigieren zur URL gehindert.
- **Ausstehende Bewertung:** Dem Benutzer wurde die Seite "Detonation ausstehend" angezeigt.
- **Blockiert außer Kraft gesetzt:** Der Benutzer wurde am direkten Navigieren zur URL gehindert. Der Benutzer hat den Block jedoch überschrieben, um zur URL zu navigieren.
- **Ausstehendes Diktat umgangen:** Dem Benutzer wurde die Detonationsseite angezeigt. Der Benutzer hat die Nachricht jedoch überschrieben, um auf die URL zuzugreifen.
- **Fehler:** Dem Benutzer wurde die Fehlerseite angezeigt, oder beim Erfassen der Bewertung ist ein Fehler aufgetreten.
- **Fehler:** Beim Erfassen des Diktats ist eine unbekannte Ausnahme aufgetreten. Der Benutzer hat möglicherweise durch die URL geklickt.

## <a name="start-automated-investigation-and-response"></a>Starten der automatisierten Untersuchung und Reaktion

> [!NOTE]
> Automatisierte Untersuchungs- und Reaktionsfunktionen sind in *Microsoft Defender für Office 365 Plan 2* und *Office 365 E5* verfügbar.

[Eine automatisierte Untersuchung und Reaktion](automated-investigation-response-office.md) kann Ihrem Sicherheitsteam Zeit und Mühe bei der Untersuchung und Minderung von Cyberangriffen ersparen. Zusätzlich zum Konfigurieren von Warnungen, die ein Sicherheits-Playbook auslösen können, können Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer starten. Weitere Informationen finden Sie unter [Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung im Explorer aus.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="other-articles"></a>Weitere Artikel

[Untersuchen von E-Mails mit der Seite "E-Mail-Entität"](mdo-email-entity-page.md)
