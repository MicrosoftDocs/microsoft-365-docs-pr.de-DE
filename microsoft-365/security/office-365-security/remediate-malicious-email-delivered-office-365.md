---
title: Behebung bösartiger E-Mails, die in Office 365 zugestellt wurden
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
ms.openlocfilehash: 1b32982298a368dc435dad8b6c09188321d099e2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289233"
---
# <a name="remediate-malicious-email-delivered-in-office-365"></a>Behebung bösartiger E-Mails, die in Office 365 zugestellt wurden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 – Plan 2](office-365-atp.md)

Abhilfe bedeutet, eine vorgeschriebene Maßnahme gegen eine Bedrohung zu ergreifen. Bösartige E-Mails, die an Ihre Organisation gesendet werden, können entweder vom System, über zap (Zero-Hour Auto Purge) oder durch Sicherheitsteams durch Abhilfemaßnahmen wie das Verschieben in den *Posteingang,* das Verschieben in Junk-E-Mails, das Verschieben in gelöschte *Elemente,* das soft *delete* oder das löschen *bereinigt* werden. Microsoft Defender für Office 365 P2/E5 ermöglicht Sicherheitsteams die Behebung von Bedrohungen in E-Mail- und Zusammenarbeitsfunktionen durch manuelle und automatisierte Untersuchungen.

> [!NOTE]
> Um bösartige E-Mails zu bereinigen, benötigen Sicherheitsteams *die* Ihnen zugewiesene Rolle "Suchen und Löschen". Die Rollenzuweisung erfolgt über Berechtigungen im Security and Compliance Center.

## <a name="what-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie beginnen

Administratoren können die erforderlichen Maßnahmen für E-Mails ergreifen. Um  diese Aktionen zu genehmigten, müssen ihnen jedoch die Rolle "Suchen und Löschen" über die Berechtigungen des **Security & Compliance Center zugewiesen** \> **sein.** Ohne die Rolle "Suchen und Löschen", die einer der Rollengruppen hinzugefügt wurde, können sie die Aktion nicht ausführen.

## <a name="manual-and-automated-remediation"></a>Manuelle und automatisierte Wartung

*Die manuelle Suche* erfolgt, wenn Sicherheitsteams Bedrohungen mithilfe der Such- und Filterfunktionen im Bedrohungs-Explorer manuell erkennen. Manuelle E-Mail-Korrekturen können über eine beliebige E-Mail-Ansicht *(Schadsoftware,* Phishing oder alle E-Mails) ausgelöst werden, nachdem Sie eine Gruppe von E-Mails identifiziert haben, die behoben werden müssen.

> [!div class="mx-imgBorder"]
> [![Manuelle Suche im Office 365 Threat Explorer nach Datum.](../../media/tp-RemediationArticle1.png)](../../media/tp-RemediationArticle1.png#lightbox)

Sicherheitsteams können den Bedrohungs-Explorer verwenden, um E-Mails auf verschiedene Weise auszuwählen:

- Wählen Sie E-Mails von Hand aus: Verwenden Sie Filter in verschiedenen Ansichten. Wählen Sie bis zu 100 E-Mails zur Behebung aus.

- Abfrageauswahl: Wählen Sie eine gesamte Abfrage aus, indem Sie die Schaltfläche "Alle oben **auswählen"** verwenden. Dieselbe Abfrage wird auch in den Details zur E-Mail-Übermittlung im Action Center angezeigt.

- Abfrageauswahl mit Ausschluss: Manchmal möchten Sicherheitsteams E-Mails möglicherweise durch Auswählen einer vollständigen Abfrage und manuelles Ausschließen bestimmter E-Mails aus der Abfrage entfernen. Dazu kann ein Administrator das Kontrollkästchen "Alle **auswählen"** verwenden und einen Bildlauf nach unten durchführen, um E-Mails manuell auszuschließen. Die Abfrage kann maximal 1.000 E-Mails speichern. Die maximale Anzahl von Ausschlüssen beträgt 100.

Sobald E-Mails über den Bedrohungs-Explorer ausgewählt wurden, können Sie mit der Problembehebung beginnen, indem Sie direkte Maßnahmen ergreifen oder E-Mails für eine Aktion in die Warteschlange einreihen:

- Direkte Genehmigung: Wenn Von Sicherheitsmitarbeitern, die über die entsprechenden Berechtigungen verfügen, Aktionen wie das Verschieben in den *Posteingang,* das Verschieben in Junk-E-Mails, das Verschieben zu gelöschten *Elementen,* das "Soft *Delete"* oder das hard *delete* ausgewählt werden und die nächsten Schritte zur Behebung ausgeführt werden, beginnt der Korrekturprozess mit der Ausführung der ausgewählten Aktion. Ein temporäres Flyout zeigt Korrekturen an.

- Genehmigung in zwei Schritt: Eine Aktion zum Hinzufügen zur Problembehebung kann von Administratoren ausgeführt werden, die nicht über die entsprechenden Berechtigungen verfügen oder mit der Ausführung der Aktion warten müssen. In diesem Fall werden die gezielten E-Mails einem Wartungscontainer hinzugefügt. Bevor die Korrektur ausgeführt wird, ist eine Genehmigung erforderlich.

**Automatisierte Untersuchungs- und Reaktionsaktionen** werden durch Warnungen oder von Sicherheitsteams aus dem Bedrohungs-Explorer ausgelöst. Dazu können empfohlene Abhilfemaßnahmen gehören, die von einem Sicherheitsteam genehmigt werden müssen. Diese Aktionen sind in der **automatischen** Untersuchung auf der Registerkarte "Aktion" enthalten.

> [!div class="mx-imgBorder"]
> [![Mail with malware in "Zapped" page showing time of Zap execution.](../../media/tp-RemediationArticle3.png)](../../media/tp-RemediationArticle3.png#lightbox)

Alle Korrekturen (entweder die direkte Genehmigung oder die Genehmigung in zwei Stufen), die im Bedrohungs-Explorer erstellt wurden, sowie genehmigte Aktionen aus automatisierten Untersuchungen werden im Action Center angezeigt. Greifen Sie über den linken Navigationsbereich im **Review Action** Center auf \> **diese zu.**

> [!div class="mx-imgBorder"]
> [![Das Action Center mit einer Liste der Bedrohungen nach Datum und Schweregrad.](../../media/tp-RemediationArticle4.png)](../../media/tp-RemediationArticle4.png#lightbox)

Im Action Center werden alle Korrekturaktionen für die letzten 30 Tage gezeigt. Aktionen, die über den Bedrohungs-Explorer ergriffen werden, werden nach dem Namen aufgelistet, den das Sicherheitsteam beim Erstellen der Problembehebung bereitgestellt hat. Aktionen, die durch automatisierte Untersuchungen ausgeführt werden, haben Titel, die mit der zugehörigen Warnung beginnen, die die Untersuchung ausgelöst hat, z. B. "Zap-E-Mail-Cluster... ".

Öffnen Sie ein Korrekturelement, um Details dazu anzuzeigen, einschließlich Name, Erstellungsdatum, Beschreibung, Schweregrad der Bedrohung und Status. Außerdem werden die folgenden beiden Registerkarten angezeigt.

- **Registerkarte** "E-Mail-Übermittlung": Zeigt die Anzahl der E-Mails an, die über den Bedrohungs-Explorer oder automatisierte Untersuchungen übermittelt wurden, die behoben werden sollen. Diese E-Mails können aktionensfähig oder nicht aktionsfähig sein.

  > [!div class="mx-imgBorder"]
  > [![Das Action Center mit Aktionen und nicht umsetzbaren Bedrohungen.](../../media/tp-RemediationArticle5.png)](../../media/tp-RemediationArticle5.png#lightbox)

  - **Aktionen: E-Mails** in den folgenden Cloudpostfachspeicherorten können verwendet und verschoben werden:
    - Posteingang
    - Junk-E-Mail
    - Ordner gelöscht
    - Ordner "Soft-deleted"

      > [!NOTE]
      > Derzeit kann nur ein Benutzer mit Zugriff auf das Postfach Elemente aus einem nicht gelöschten Ordner wiederherstellen.

  - **Nicht aktionsfähig:** E-Mails an den folgenden Speicherorten können nicht in Abhilfemaßnahmen verwendet oder verschoben werden:
    - Quarantäne
    - Gelöschter Ordner
    - Lokal/extern
    - Failed/dropped

  Verdächtige Nachrichten werden entweder als "behbar" oder "nicht behbbar" kategorisiert. In den meisten Fällen entspricht eine Kombination aus beh wiederbearbeitbaren und nicht beh nbaren Nachrichten der Gesamtzahl der übermittelten Nachrichten. In seltenen Fällen ist dies jedoch möglicherweise nicht der Fall. Dies kann aufgrund von Systemverzögerungen, Timeouts oder abgelaufenen Nachrichten geschehen. Nachrichten laufen basierend auf dem Aufbewahrungszeitraum des Bedrohungs-Explorers für Ihre Organisation ab.

  Wenn Sie alte Nachrichten nach dem Aufbewahrungszeitraum des Threat Explorer Ihrer Organisation nicht beheumdern, ist es ratsam, die Behebung von Elementen zu wiederholen, wenn Inkonsistenzen von Nummern angezeigt werden. Bei Systemverzögerungen werden Wartungsupdates in der Regel innerhalb weniger Stunden aktualisiert.

  Wenn der Aufbewahrungszeitraum für E-Mails in Ihrer Organisation im Bedrohungs-Explorer 30 Tage beträgt und Sie E-Mails 29 bis 30 Tage zurückbestellen, wird die Anzahl der E-Mail-Übermittlungen möglicherweise nicht immer addiert. Möglicherweise sind die E-Mails bereits aus dem Aufbewahrungszeitraum herausgelaufen.

  Wenn Korrekturen eine Weile im Status "In Bearbeitung" hängen bleiben, liegt dies wahrscheinlich an Systemverzögerungen. Die Behebung kann bis zu ein paar Stunden dauern. Möglicherweise werden Variationen bei der Anzahl der E-Mail-Übermittlungen angezeigt, da einige der E-Mails möglicherweise zu Beginn der Korrektur aufgrund von Systemverzögerungen nicht in die Abfrage einbezogen wurden. In solchen Fällen ist es eine gute Idee, die Behebung zu wiederholen.

  > [!NOTE]
  > Für optimale Ergebnisse sollten Korrekturen in Batches von 50.000 oder weniger durchgeführt werden.

  Während der Korrektur werden nur behbare E-Mails verwendet. Nicht behierbare E-Mails können nicht vom Office 365-E-Mail-System behoben werden, da sie nicht in Cloudpostfächern gespeichert werden.

  Administratoren können bei Bedarf Aktionen für E-Mails in Quarantäne ergreifen, aber diese E-Mails laufen aus der Quarantäne, wenn sie nicht manuell gelöscht werden. E-Mails, die aufgrund schädlicher Inhalte isoliert wurden, sind für Benutzer nicht zugänglich, sodass Sicherheitsmitarbeiter keine Maßnahmen ergreifen müssen, um Bedrohungen in Quarantäne zu löschen. Wenn die E-Mails lokal oder extern sind, kann der Benutzer kontaktiert werden, um die verdächtige E-Mail zu adressieren. Oder die Administratoren können separate E-Mail-Server-/Sicherheitstools zum Entfernen verwenden. Diese E-Mails können identifiziert werden, indem sie den Zustellungsort *= den* externen Filter vor Ort im Bedrohungs-Explorer anwenden. Bei fehlgeschlagenen oder verworfenen E-Mails oder E-Mails, auf die Benutzer nicht zugreifen können, gibt es keine E-Mail, die abgemildert werden kann, da diese E-Mails nicht das Postfach erreichen.

  Die folgende Abbildung zeigt, wie eine Übermittlung im Action Center aussieht. Eine Korrektur kann mehrere Übermittlungen enthalten. Wenn mehrere Aktionen über eine automatisierte Untersuchung genehmigt werden, wird jede E-Mail- oder E-Mail-Clusteraktion in derselben Korrektur wie eine andere Übermittlung angezeigt.

  > [!div class="mx-imgBorder"]
  > [![ZAP-E-Mail-Cluster-Flyoutpanel.](../../media/tp-RemediationArticle6.png)](../../media/tp-RemediationArticle6.png#lightbox)

  Wählen Sie ein E-Mail-Übermittlungselement aus, um die Details dieser Korrektur anzuzeigen, z. B. die Abfrage (wenn die Korrektur durch automatisierte Untersuchungen oder den Bedrohungs-Explorer durch Auswahl einer Abfrage ausgelöst wird) und die Start- und Endzeiten der Korrektur. Außerdem wird eine Liste der Nachrichten angezeigt, die zur Behebung übermittelt wurden. Wenn Nachrichten aus dem Aufbewahrungszeitraum des Bedrohungs-Explorers entfernt werden, werden die Nachrichten aus dieser Liste entfernt. In der Liste werden auch einzelne Meldungen angezeigt, die wiederherstellungsfähig sind.

- **Aktionsprotokolle:** Auf dieser Registerkarte werden die Nachrichten angezeigt, die behoben wurden, einschließlich genehmigten Datums, Administrator, der die Aktion genehmigt hat, Aktion, Status und Anzahl.

  Status kann sein:

  - **Gestartet:** Die Korrektur wird ausgelöst.
  - **In die** Warteschlange eingereiht: Die Problembehebung wird zur Behebung von E-Mails in die Warteschlange eingereiht.
  - **In Bearbeitung:** Die Gegenmaßnahmen werden ausgeführt.
  - **Abgeschlossen:** Ausgleich für alle behierbaren E-Mails, die entweder erfolgreich oder mit einigen Fehlern abgeschlossen wurden.
  - **Fehler:** Es wurden keine Korrekturen erfolgreich abgeschlossen.

  Da nur behbare E-Mails reagiert werden können, wird die Bereinigung jeder E-Mail als erfolgreich oder fehlgeschlagen angezeigt. Aus den insgesamt behierbaren E-Mails werden erfolgreiche und fehlgeschlagene Gegenmaßnahmen gemeldet.

  - **Erfolg:** Die gewünschte Aktion für beh wiederbehbare E-Mails wurde durchgeführt. Beispiel: Ein Administrator möchte E-Mails aus Postfächern entfernen, sodass der Administrator die Aktion zum soft-deleting von E-Mails ergreift. Wenn eine behbare E-Mail im ursprünglichen Ordner nicht gefunden wird, nachdem die Aktion abgeschlossen wurde, wird der Status als erfolgreich angezeigt.

  - **Fehler:** Die gewünschte Aktion für beh wiederbearbeitbare E-Mails ist fehlgeschlagen. Beispiel: Ein Administrator möchte E-Mails aus Postfächern entfernen, sodass der Administrator die Aktion zum soft-deleting von E-Mails ergreift. Wenn eine behbare E-Mail im Postfach gefunden wird, nachdem die Aktion ergriffen wurde, wird der Status als fehlgeschlagen angezeigt.

  Wählen Sie ein beliebiges Element im Aktionsprotokoll aus, um Korrekturdetails anzuzeigen. Wenn die Details "erfolgreich" oder "im Postfach nicht gefunden" sagen, wurde dieses Element bereits aus dem Postfach entfernt. Manchmal tritt während der Wartung ein Fehler auf. In diesen Fällen ist es eine gute Idee, die Problembehebung zu wiederholen.

  Bei der Behebung großer Batches können Sie auch die zur Korrektur gesendeten Nachrichten über die E-Mail-Übermittlung und Nachrichten exportieren, die über Aktionsprotokolle behoben wurden. Der Exportgrenzwert wird auf 100.000 Datensätze erhöht.

  Die Problembehebung ist ein leistungsstarkes Tool, um Bedrohungen zu mindern und verdächtige E-Mails zu adressieren. Dies trägt dazu bei, eine Organisation zu schützen.
