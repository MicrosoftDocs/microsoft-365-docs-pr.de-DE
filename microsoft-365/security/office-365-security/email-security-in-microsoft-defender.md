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
ms.openlocfilehash: f0326a51f14b402b9a579e8668ef2c026f9de789
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52877896"
---
# <a name="email-security-with-threat-explorer-in-microsoft-defender-for-office-365"></a>E-Mail-Sicherheit mit dem Sicherheitsrisiken-Explorer in Microsoft Defender für Office 365

Inhalt dieses Artikels:

- [Anzeigen von schadsoftware, die in E-Mails erkannt wurde](#view-malware-detected-in-email)
- [Phishing-URL anzeigen und auf Bewertungsdaten klicken](#view-phishing-url-and-click-verdict-data)
- [Starten der automatisierten Untersuchung und Reaktion](#start-automated-investigation-and-response)

> [!NOTE]
> Dies ist Teil einer **Drei-Artikel-Reihe** zu Den Grundlagen von **Bedrohungs-Explorer (Explorer),** **E-Mail-Sicherheit** und **Explorer und Echtzeiterkennungen** (z. B. Unterschiede zwischen den Tools und berechtigungen, die zum Ausführen dieser Tools erforderlich sind). Die beiden anderen Artikel in dieser Reihe sind [die Bedrohungssuche im Bedrohungs-Explorer](threat-hunting-in-threat-explorer.md) und [im Bedrohungs-Explorer sowie Grundlagen der Echtzeiterkennung.](real-time-detections.md) 

In diesem Artikel wird erläutert, wie Sie Schadsoftware- und Phishingversuche anzeigen und untersuchen, die in E-Mails von Microsoft 365 Sicherheitsfeatures erkannt werden. 

**Gilt für**

- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

## <a name="view-malware-detected-in-email"></a>Anzeigen von schadsoftware, die in E-Mails erkannt wurde

Um Schadsoftware in E-Mails nach Microsoft 365 Technologie sortiert anzuzeigen, verwenden Sie die [E-Mail-> Schadsoftwareansicht](threat-explorer-views.md#email--malware) des Explorers (oder Echtzeiterkennungen). Schadsoftware ist die Standardansicht, sodass sie möglicherweise ausgewählt wird, sobald Sie Explorer öffnen.

1. Wählen Sie im Security & Compliance Center ( <https://protection.office.com> ) den **Bedrohungsverwaltungs-Explorer** \>  (oder **Echtzeiterkennungen)** aus. (In diesem Beispiel wird Explorer verwendet.)

   Wenn Sie sich im zusammengeführten Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) befinden, scrollen Sie zu **E-Mail & Zusammenarbeits-Explorer.**  >  

   Beginnen Sie hier in der Ansicht, wählen Sie einen bestimmten Zeitrahmen für die Untersuchung (falls erforderlich) aus, und konzentrieren Sie ihre Filter gemäß der [exemplarischen Vorgehensweise](threat-hunting-in-threat-explorer.md#threat-explorer-walk-through)des Explorers.

2. Wählen Sie im Menü **Ansicht** **E-Mail-Schadsoftware** \> aus.

   > [!div class="mx-imgBorder"]
   > ![Ansichtsmenü für Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicken Sie auf **"Absender"** und dann auf **"Grundlegende** \> **Erkennungstechnologie".**

   Ihre Erkennungstechnologien sind jetzt als Filter für den Bericht verfügbar.

   > [!div class="mx-imgBorder"]
   > ![Schadsoftwareerkennungstechnologien](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Wählen Sie eine Option aus. Wählen Sie dann die Schaltfläche **"Aktualisieren"** aus, um diesen Filter anzuwenden.

   > [!div class="mx-imgBorder"]
   > ![Ausgewählte Erkennungstechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

   Der Bericht wird aktualisiert, um die Ergebnisse anzuzeigen, die Schadsoftware in E-Mails mithilfe der ausgewählten Technologieoption erkannt hat. Von hier aus können Sie weitere Analysen durchführen. 

## <a name="view-phishing-url-and-click-verdict-data"></a>Phishing-URL anzeigen und auf Bewertungsdaten klicken

Sie können Phishingversuche über URLs in E-Mails anzeigen, einschließlich einer Liste der URLs, die zugelassen, blockiert und überschrieben wurden. Um URLs zu identifizieren, auf die geklickt wurde, müssen [sichere Links](safe-links.md) konfiguriert sein. Stellen Sie sicher, dass Sie Richtlinien für [sichere Links](set-up-safe-links-policies.md) für Denkzeitschutz und Protokollierung von Klickbewertungen durch sichere Links einrichten.

Verwenden Sie die [ **E-Mail-Phishing-Ansicht**  > ](threat-explorer-views.md#email--phish) von Explorer- oder Echtzeiterkennungen, um Phishing-URLs in Nachrichten zu überprüfen und auf URLs in Phishingnachrichten zu klicken.

1. Wählen Sie im Security & Compliance Center ( <https://protection.office.com> ) den **Bedrohungsverwaltungs-Explorer** \>  (oder **Echtzeiterkennungen)** aus. (In diesem Beispiel wird Explorer verwendet.)

2. Wählen Sie im Menü **"Ansicht"** die Option **"E-Mail-Phishing"** \> **aus.**

   > [!div class="mx-imgBorder"]
   > ![Ansichtsmenü für Explorer im Phishingkontext](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicken Sie auf **"Absender",** und wählen Sie **"URLs** \> **Klicken Sie auf "Bewertung"** aus.

4. Wählen Sie eine oder mehrere Optionen aus, z. B. **"Blockiert"** und **"Blockieren",** und wählen Sie dann die Schaltfläche **"Aktualisieren"** in derselben Zeile wie die Optionen zum Anwenden dieses Filters aus. (Aktualisieren Sie das Browserfenster nicht.)

   > [!div class="mx-imgBorder"]
   > ![URLs und Klickbewertungen](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

   Der Bericht wird aktualisiert, um zwei verschiedene URL-Tabellen auf der Registerkarte "URL" unter dem Bericht anzuzeigen:

   - **Die häufigsten URLs** sind die URLs in den Nachrichten, nach denen Sie gefiltert haben, und die Anzahl der E-Mail-Zustellungsaktionen für jede URL. In der Phishing-E-Mail-Ansicht enthält diese Liste in der Regel legitime URLs. Angreifer enthalten eine Mischung aus guten und schlechten URLs in ihren Nachrichten, um zu versuchen, sie zuzustellen, aber sie machen die bösartigen Links interessanter. Die Tabelle der URLs wird nach der Gesamtzahl der E-Mails sortiert, aber diese Spalte ist ausgeblendet, um die Ansicht zu vereinfachen.

   - **Die häufigsten Klicks** sind die mit sicheren Links umschlossenen URLs, auf die geklickt wurde, sortiert nach der Gesamtzahl der Klicks. Diese Spalte wird auch nicht angezeigt, um die Ansicht zu vereinfachen. Die Gesamtanzahl nach Spalte gibt die Anzahl der Klickbewertungen für sichere Links für jede angeklickte URL an. In der Phishing-E-Mail-Ansicht handelt es sich dabei in der Regel um verdächtige oder bösartige URLs. Die Ansicht kann jedoch URLs enthalten, die keine Bedrohungen sind, sondern sich in Phishing-Nachrichten befinden. URL-Klicks auf nicht gepackte Links werden hier nicht angezeigt.

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
- **Blockiert außer Kraft gesetzt:** Der Benutzer wurde daran gehindert, direkt zur URL zu navigieren. Der Benutzer hat den Block jedoch überschrieben, um zur URL zu navigieren.
- **Ausstehendes Diktat umgangen:** Dem Benutzer wurde die Detonationsseite angezeigt. Der Benutzer hat die Nachricht jedoch überschrieben, um auf die URL zuzugreifen.
- **Fehler:** Dem Benutzer wurde die Fehlerseite angezeigt, oder beim Erfassen der Bewertung ist ein Fehler aufgetreten.
- **Fehler:** Beim Erfassen des Diktats ist eine unbekannte Ausnahme aufgetreten. Der Benutzer hat möglicherweise durch die URL geklickt.

## <a name="start-automated-investigation-and-response"></a>Starten der automatisierten Untersuchung und Reaktion

> [!NOTE]
> Automatisierte Untersuchungs- und Reaktionsfunktionen sind in *Microsoft Defender für Office 365 Plan 2* und Office 365 *E5* verfügbar.

[Eine automatisierte Untersuchung und Reaktion](automated-investigation-response-office.md) kann Ihrem Sicherheitsteam Zeit und Mühe bei der Untersuchung und Minderung von Cyberangriffen ersparen. Zusätzlich zum Konfigurieren von Warnungen, die ein Sicherheits-Playbook auslösen können, können Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer starten. Weitere Informationen finden Sie unter [Beispiel: Ein Sicherheitsadministrator löst eine Untersuchung im Explorer aus.](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer)

## <a name="other-articles"></a>Weitere Artikel

[Untersuchen von E-Mails mit der Seite "E-Mail-Entität"](mdo-email-entity-page.md)
