---
title: Behebung bösartiger E-Mails, die in diesem Office 365
author: msfttracyp
ms.author: tracyp
manager: dansimp
ms.topic: article
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Bedrohungsbehebung
appliesto:
- Microsoft 365 Defender
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 202ebc8b79368c8d41fd3727b67359ddcb8a08fa
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51206614"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Behebung bösartiger E-Mails, die in Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](defender-for-office-365.md)

Korrektur bedeutet, eine vorgeschriebene Aktion gegen eine Bedrohung zu ergreifen. Bösartige E-Mails, die an Ihre Organisation gesendet werden, können entweder vom System, über die automatische Löschzeit (Zero-Hour Auto Purge, ZAP) oder von Sicherheitsteams durch Korrekturaktionen wie Verschieben in den *Posteingang,* Wechseln zu *Junk,* Verschieben zu gelöschten *Elementen,* soft *delete* oder hard *delete* bereinigt werden. Microsoft Defender for Office 365 P2/E5 ermöglicht Es Sicherheitsteams, Bedrohungen in E-Mail- und Zusammenarbeitsfunktionen durch manuelle und automatisierte Untersuchung zu beabwehren.

> [!NOTE]
> Zum Bereinigen bösartiger E-Mails benötigen Sicherheitsteams *die* Ihnen zugewiesene Such- und Bereinigungsrolle. Die Rollenzuweisung erfolgt über Berechtigungen im Security and Compliance Center.

## <a name="what-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie beginnen

Administratoren können die erforderlichen Aktionen für E-Mails ergreifen, aber  um diese Aktionen zu genehmigten, müssen ihnen die Such- und Bereinigungsrolle über Die Berechtigungen für das **Security & Compliance Center** \> **zugewiesen werden.** Ohne die Rolle "Suchen und Löschen", die einer der Rollengruppen hinzugefügt wurde, können sie die Aktion nicht ausführen.

## <a name="manual-and-automated-remediation"></a>Manuelle und automatisierte Korrektur

*Die manuelle Suche* erfolgt, wenn Sicherheitsteams Bedrohungen mithilfe der Such- und Filterfunktionen im Bedrohungs-Explorer manuell identifizieren. Manuelle E-Mail-Korrektur kann über eine beliebige E-Mail-Ansicht (*Schadsoftware,* *Phish* oder *Alle* E-Mails ) ausgelöst werden, nachdem Sie eine Reihe von E-Mails identifiziert haben, die behoben werden müssen.

> [!div class="mx-imgBorder"]
> [![Manuelle Suche im Office 365 Bedrohungs-Explorer nach Datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Sicherheitsteams können den Bedrohungs-Explorer verwenden, um E-Mails auf verschiedene Weise auszuwählen:

- Wählen Sie E-Mails von Hand aus: Verwenden Sie Filter in verschiedenen Ansichten. Wählen Sie bis zu 100 E-Mails zur Behebung aus.

- Abfrageauswahl: Wählen Sie eine gesamte Abfrage aus, indem Sie die Schaltfläche oben **alle** auswählen verwenden. Die gleiche Abfrage wird auch in den Details zur E-Mail-Übermittlung im Aktionscenter angezeigt.

- Abfrageauswahl mit Ausschluss: Manchmal möchten Sicherheitsteams E-Mails möglicherweise durch Auswählen einer gesamten Abfrage und manuelles Ausschließen bestimmter E-Mails aus der Abfrage löschen. Dazu kann ein Administrator das  Kontrollkästchen Alle auswählen verwenden und einen Bildlauf nach unten durchführen, um E-Mails manuell auszuschließen. Die Abfrage kann maximal 1.000 E-Mails speichern. Die maximale Anzahl von Ausschlüssen ist 100.

Sobald E-Mails über den Bedrohungs-Explorer ausgewählt wurden, können Sie mit der Korrektur beginnen, indem Sie direkte Maßnahmen ergreifen oder E-Mails für eine Aktion in die Warteschlange einreihen:

- Direkte Genehmigung: Wenn Aktionen wie das Verschieben in den *Posteingang,* das  Verschieben zu *Junk,* das Verschieben zu gelöschten *Elementen,* das soft *delete* oder das löschende Objekt von Sicherheitsmitarbeitern ausgewählt werden, die über entsprechende Berechtigungen verfügen, und die nächsten Schritte zur Behebung befolgt werden, beginnt der Korrekturvorgang mit der Ausführung der ausgewählten Aktion. Ein temporäres Flyout zeigt, dass die Korrektur ausgeführt wird.

- Genehmigung in zwei Stufen: Administratoren, die nicht über die entsprechenden Berechtigungen verfügen oder warten müssen, bis die Aktion ausgeführt wird, können eine Aktion "Zur Behebung hinzufügen" ausführen. In diesem Fall werden die gezielten E-Mails einem Behebungscontainer hinzugefügt. Bevor die Korrektur ausgeführt wird, ist eine Genehmigung erforderlich.

**Automatisierte Untersuchungs- und Reaktionsaktionen** werden durch Warnungen oder sicherheitsbetriebsteams aus dem Threat Explorer ausgelöst. Dazu können empfohlene Korrekturaktionen gehören, die von einem Sicherheitsbetriebsteam genehmigt werden müssen. Diese Aktionen sind in der **automatisierten Untersuchung** auf der Registerkarte Aktion enthalten.

> [!div class="mx-imgBorder"]
> [![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alle Im Bedrohungs-Explorer erstellten Korrekturen (entweder direkte Genehmigung oder genehmigung in zwei Stufen) sowie genehmigte Aktionen aus automatisierten Untersuchungen werden im Action Center angezeigt. Greifen Sie über das linke Navigationsbereich unter **Review** \> **Action Center auf diese zu.**

> [!div class="mx-imgBorder"]
> [![Das Aktionscenter mit einer Liste der Bedrohungen nach Datum und Schweregrad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Das Aktionscenter zeigt alle Korrekturaktionen für die letzten 30 Tage an. Aktionen, die über den Bedrohungs-Explorer ergriffen werden, werden durch den Namen aufgelistet, den das Sicherheitsbetriebsteam beim Erstellen der Korrektur bereitgestellt hat. Aktionen, die durch automatisierte Untersuchungen ausgeführt werden, haben Titel, die mit der zugehörigen Warnung beginnen, die die Untersuchung ausgelöst hat, z. B. "Zap-E-Mail-Cluster... ."

Öffnen Sie jedes Korrekturelement, um Details dazu anzuzeigen, einschließlich Name, Erstellungsdatum, Beschreibung, Bedrohungsschweregrad und Status. Außerdem werden die folgenden beiden Registerkarten angezeigt.

- **Registerkarte** E-Mail-Übermittlung: Zeigt die Anzahl der E-Mails an, die über den Bedrohungs-Explorer übermittelt wurden, oder automatisierte Untersuchungen, die behoben werden sollen. Diese E-Mails können aktionensfähig oder nicht aktionsfähig sein.

  > [!div class="mx-imgBorder"]
  > [![Das Aktionscenter mit Aktionen und nicht aktionenbaren Bedrohungen.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Aktionsfähig:** E-Mails in den folgenden Cloudpostfachspeicherorten können aktiviert und verschoben werden:
    - Posteingang
    - Junk-E-Mail
    - Ordner gelöscht
    - Ordner "Soft-deleted"

      > [!NOTE]
      > Derzeit kann nur ein Benutzer mit Zugriff auf das Postfach Elemente aus einem Ordner mit soft-deleted wiederherstellen.

  - **Nicht aktionsfähig:** E-Mails an den folgenden Speicherorten können nicht in Korrekturaktionen verwendet oder verschoben werden:
    - Quarantäne
    - Ordner "Fest gelöscht"
    - Lokal/extern
    - Failed/dropped

  Verdächtige Nachrichten werden als beh glich oder nicht beh glich kategorisiert. In den meisten Fällen entspricht die Kombination aus bearbeitbaren und nicht bearbeitbaren Nachrichten der Gesamtzahl der übermittelten Nachrichten. In seltenen Fällen ist dies jedoch möglicherweise nicht der Fall. Dies kann aufgrund von Systemverzögerungen, Timeouts oder abgelaufenen Nachrichten geschehen. Nachrichten laufen basierend auf dem Aufbewahrungszeitraum des Bedrohungs-Explorers für Ihre Organisation ab.

  Es sei denn, Sie löschen alte Nachrichten nach dem Aufbewahrungszeitraum von Threat Explorer in Ihrer Organisation, es empfiehlt sich, die Behebung von Elementen zu wiederholen, wenn Nummernkonsistenzen angezeigt werden. Bei Systemverzögerungen werden Korrekturupdates in der Regel innerhalb weniger Stunden aktualisiert.

  Wenn der Aufbewahrungszeitraum ihrer Organisation für E-Mails im Bedrohungs-Explorer 30 Tage beträgt und Sie E-Mails, die zwischen 29 und 30 Tage zurück gehen, wiederbestellen, werden die Anzahl der E-Mail-Übermittlungen möglicherweise nicht immer addiert. Möglicherweise haben die E-Mails bereits begonnen, den Aufbewahrungszeitraum zu verfingen.

  Wenn Korrekturen eine Weile im Status "In Bearbeitung" hängen bleiben, ist dies wahrscheinlich aufgrund von Systemverzögerungen. Die Behebung kann bis zu ein paar Stunden dauern. Möglicherweise werden Variationen bei der Anzahl der E-Mail-Übermittlungen angezeigt, da einige der E-Mails möglicherweise zu Beginn der Korrektur aufgrund von Systemverzögerungen nicht in die Abfrage einbezogen wurden. In solchen Fällen ist es eine gute Idee, die Behebung zu wiederholen.

  > [!NOTE]
  > Für optimale Ergebnisse sollte die Korrektur in Batches von 50.000 oder weniger durchgeführt werden.

  Während der Behebung werden nur bearbeitbare E-Mails verwendet. Nicht behHbare E-Mails können nicht vom E-Mail-Office 365 werden, da sie nicht in Cloudpostfächern gespeichert werden.

  Administratoren können bei Bedarf Aktionen für E-Mails in Quarantäne ausführen, aber diese E-Mails laufen aus der Quarantäne ab, wenn sie nicht manuell gelöscht werden. E-Mails, die aufgrund schädlicher Inhalte in Quarantäne gestellt werden, sind für Benutzer nicht zugänglich, daher müssen Sicherheitsmitarbeiter keine Maßnahmen ergreifen, um Bedrohungen in Quarantäne zu löschen. Wenn die E-Mails lokal oder extern sind, kann der Benutzer kontaktiert werden, um die verdächtigen E-Mails zu adressieren. Oder die Administratoren können separate E-Mail-Server-/Sicherheitstools zum Entfernen verwenden. Diese E-Mails können durch Anwenden des Zustellungsspeicherorts *= on-prem-externer* Filter im Bedrohungs-Explorer identifiziert werden. Bei fehlgeschlagenen oder verworfenen E-Mails oder E-Mails, auf die Benutzer nicht zugreifen können, gibt es keine E-Mails, die abgemildert werden sollen, da diese E-Mails das Postfach nicht erreichen.

  Die folgende Abbildung zeigt, wie eine Übermittlung im Action Center aussieht. Eine Korrektur kann mehrere Übermittlungen enthalten. Wenn mehrere Aktionen über eine automatisierte Untersuchung genehmigt werden, wird jede E-Mail- oder E-Mail-Clusteraktion in derselben Korrektur wie eine andere Übermittlung angezeigt.

  > [!div class="mx-imgBorder"]
  > [![ZAP-E-Mail-Cluster-Flyoutpanel.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Wählen Sie ein E-Mail-Übermittlungselement aus, um die Details dieser Korrektur anzuzeigen, z. B. die Abfrage (wenn die Korrektur durch automatisierte Untersuchungen ausgelöst wird oder der Bedrohungs-Explorer durch Auswahl einer Abfrage) sowie die Start- und Endzeiten der Korrektur. Außerdem wird eine Liste der Nachrichten angezeigt, die zur Behebung übermittelt wurden. Wenn Nachrichten aus dem Aufbewahrungszeitraum des Bedrohungs-Explorers entfernt werden, werden die Nachrichten aus dieser Liste ausgeblendet. In der Liste werden auch einzelne Nachrichten angezeigt, die bearbeitbar sind.

- **Aktionsprotokolle**: Auf dieser Registerkarte werden die Nachrichten angezeigt, die behoben wurden, einschließlich des genehmigten Datums, des Administrators, der die Aktion, die Aktion, den Status und die Anzahl genehmigt hat.

  Status kann sein:

  - **Started**: Remediation is triggered.
  - **In die** Warteschlange eingereiht: Die Korrektur wird zur Minderung von E-Mails in die Warteschlange eingereiht.
  - **In Bearbeitung:** Die Schadensminderung wird ausgeführt.
  - **Completed**: Mitigation on all remediable emails either completed successfully or with some failures.
  - **Fehler**: Es wurden keine Korrekturen erfolgreich abgeschlossen.

  Da nur bearbeitbare E-Mails verwendet werden können, wird die Bereinigung jeder E-Mail als erfolgreich oder fehlgeschlagen angezeigt. Aus den insgesamt bearbeitbaren E-Mails werden erfolgreiche und fehlgeschlagene Gegenmaßnahmen gemeldet.

  - **Erfolg**: Die gewünschte Aktion für bearbeitbare E-Mails wurde durchgeführt. Beispiel: Ein Administrator möchte E-Mails aus Postfächern entfernen, sodass der Administrator die Aktion des soft-deleting-E-Mails ergreift. Wenn eine bearbeitbare E-Mail nicht im ursprünglichen Ordner gefunden wird, nachdem die Aktion ergriffen wurde, wird der Status als erfolgreich angezeigt.

  - **Fehler:** Die gewünschte Aktion für bearbeitbare E-Mails ist fehlgeschlagen. Beispiel: Ein Administrator möchte E-Mails aus Postfächern entfernen, sodass der Administrator die Aktion des soft-deleting-E-Mails ergreift. Wenn eine bearbeitbare E-Mail nach dem Ergreifen der Aktion weiterhin im Postfach gefunden wird, wird der Status als fehlgeschlagen angezeigt.
  
  - **Bereits im Ziel**: Die gewünschte Aktion wurde bereits für die E-Mail oder die E-Mail bereits am Zielspeicherort vorhanden. Beispiel: Eine E-Mail wurde vom Administrator über Explorer am ersten Tag gelöscht. Dann werden ähnliche E-Mails am 2. Tag gezeigt, die wiederum vom Administrator soft gelöscht werden. Beim Auswählen dieser E-Mails wählt der Administrator einige E-Mails vom ersten Tag aus, die bereits soft gelöscht wurden. Nun werden diese E-Mails nicht erneut verwendet, sondern nur als "bereits am Zielort" angezeigt, da keine Aktion für sie ergriffen wurde, da sie am Zielspeicherort vorhanden waren.

  Wählen Sie ein beliebiges Element im Aktionsprotokoll aus, um Korrekturdetails anzuzeigen. Wenn die Details "erfolgreich" oder "im Postfach nicht gefunden" sagen, wurde dieses Element bereits aus dem Postfach entfernt. Manchmal tritt bei der Behebung ein systemischer Fehler auf. In diesen Fällen ist es eine gute Idee, die Korrektur zu wiederholen.

  Bei der Behebung großer Batches können Sie auch die zur Korrektur gesendeten Nachrichten über die E-Mail-Übermittlung und Nachrichten exportieren, die über Aktionsprotokolle behoben wurden. Der Exportgrenzwert wird auf 100.000 Datensätze erhöht.

Das Sicherheitsteam kann bis zu 50 manuelle Korrekturen gleichzeitig ausführen. Es ist jedoch kein Grenzwert für automatisierte Untersuchungs- und Reaktionsaktionen festgelegt.

  Die Korrektur ist ein leistungsfähiges Tool, um Bedrohungen zu mindern und verdächtige E-Mails zu adressieren. Es trägt dazu bei, eine Organisation zu schützen.
