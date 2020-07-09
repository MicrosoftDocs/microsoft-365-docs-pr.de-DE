---
title: Beheben böswilliger e-Mails, die in Office 365 bereitgestellt wurden
author: MSFTTracyP
ms.author: tracyp
manager: dansimp
ms.topic: article
ms.service: Microsoft Threat Protection
audience: admin
f1.keywords:
- NOCSH
localization_priority: Normal
MS.collection: ''
search.appverid: MET150
description: Behebung von Bedrohungen
appliesto:
- Microsoft Threat Protection
ms.openlocfilehash: eb86c0b8e5368a42daa1002de5ac361613037090
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086691"
---
# <a name="remediate-malicious-email-that-was-delivered-in-office-365"></a>Beheben böswilliger e-Mails, die in Office 365 bereitgestellt wurden

Die Wiederherstellung bedeutet, dass eine vorgeschriebene Aktion gegen eine Bedrohung erfolgt. Böswillige e-Mails, die an Ihre Organisation gesendet werden, werden möglicherweise entweder durch das System, durch zap (Zero-Hour Auto-Purge) oder durch die Sicherheitsteams durch Korrekturaktionen wie Verschieben in den Posteingang, in Junk verschieben, in Ordner "Gelöschte Elemente", "Soft Delete" oder "hartes löschen" bereinigt. Office Advanced Threat Protection (Office ATP) P2/E5 bietet Sicherheitseinsatz Teams die Möglichkeit, Bedrohungen in e-Mails und Zusammenarbeits Problemen durch manuelle Jagd und automatisierte Untersuchungen zu vermitteln.

> [!NOTE]
> Damit Sicherheitsteams e-Mails korrigieren können, müssen Ihnen die Such-und Säuberungs Rolle zugewiesen sein. Die Rollenzuweisung erfolgt über Berechtigungen im Security and Compliance Center. <p>

## <a name="what-you-need-to-know-before-you-begin"></a>Was Sie wissen müssen, bevor Sie beginnen

Um bestimmte Aktionen auszuführen, beispielsweise das Anzeigen von Nachrichtenkopfzeilen oder das Herunterladen von e-Mail-Nachrichteninhalten, müssen Sie eine neue Rolle namens " *Preview* " zu einer anderen entsprechenden Rollengruppe hinzufügen. In der folgenden Tabelle werden die erforderlichen Rollen und Berechtigungen erläutert.

|Aktivität  |Rollengruppe |Vorschau-Rolle erforderlich?  |
|---------|---------|---------|
|Verwenden von Threat Explorer (und Echtzeiterkennung) zum Analysieren von Bedrohungen     |Globaler Administrator <br> Sicherheitsadministrator <br> Sicherheitsleseberechtigter     | Nein   |
|Verwenden Sie Threat Explorer (und Echtzeiterkennung), um Kopfzeilen für e-Mail-Nachrichten anzuzeigen sowie e-Mail-Nachrichten, die in Quarantäne verschoben wurden, anzuzeigen und herunterzuladen.    |Globaler Administrator <br> Sicherheitsadministrator <br>Sicherheitsleseberechtigter   |       Nein  |
|Verwenden von Threat Explorer zum Anzeigen von Kopfzeilen und Herunterladen von an Postfächern zugestellten e-Mails     |Globaler Administrator <br>Sicherheitsadministrator <br> Sicherheitsleseberechtigter <br> Vorschau   |   Ja      |

> [!NOTE]
> *Vorschau* ist eine Rolle und keine Rollengruppe; die Vorschau Rolle muss einer vorhandenen Rollengruppe für Office 365 hinzugefügt werden. Der globalen Administrator Rolle wird das Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) ) zugewiesen, und die Rollen Sicherheitsadministrator und Sicherheits Leser werden im Security & Compliance Center zugewiesen ( [https://protection.office.com](https://protection.office.com) ). Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security & Compliance Center.](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center?view=o365-worldwide)

> [!NOTE]
> Administratoren können erforderliche Aktionen für e-Mails durchführen, aber um Ihre Aktion genehmigen zu lassen, muss Ihnen die Rolle "suchen und löschen" über das Security and Compliance Center > Berechtigungen zugewiesen sein.

## <a name="manual-and-automated-remediation"></a>Manuelle und automatische Korrektur

**Manuelle Jagd** findet statt, wenn Sicherheitsteams Bedrohungen manuell identifizieren, indem Sie die Such-und Filterfunktionen in Threat Explorer verwenden. Die manuelle Behebung von e-Mails kann über jede e-Mail-Ansicht (Schadsoftware, Phishing oder alle e-Mails) ausgelöst werden, nachdem eine Reihe von e-Mails gefunden wurde, die korrigiert werden müssen.

![Manuelle Suche in Office 365 Bedrohungs-Explorer nach Datum.](../../../media/tp-RemediationArticle1.png "Sicherheitsrisiken-Explorer")

Die Auswahl von e-Mails kann auf verschiedene Arten durch Threat Explorer erfolgen:

1. Auswählen von e-Mails per Hand: Dies bedeutet, dass Sicherheits Operations Teams Filter in entsprechenden Ansichten verwenden und einige e-Mails aus dem Threat Explorer auswählen können, die korrigiert werden müssen. Die obere Grenze für die Auswahl von e-Mails lautet 100 (100). Security Operations Teams können nicht manuell mehr als hundert e-Mails auswählen.

2. Abfrageauswahl: Sicherheits Operations Teams können eine gesamte Abfrage mithilfe der oberen Schaltfläche "Alle auswählen" auswählen. Die gleiche Abfrage wird auch in den Details zur Mailübermittlung von Action Center angezeigt.

3. Abfrageauswahl mit Ausschluss: Es kann vorkommen, dass sich Sicherheits Betriebsteams entschließen, e-Mails zu korrigieren, indem Sie eine gesamte Abfrage auswählen und einige e-Mails aus der Abfrage ausschließen, manuell. Dazu kann ein Administrator das Kontrollkästchen "Alle auswählen" verwenden und nach unten scrollen, um einige e-Mails manuell auszuschließen. Die maximale Anzahl von e-Mails, die die Abfrage enthalten kann, ist 1000 (1.000), und die maximale Anzahl von Ausschlüssen ist 100 (100), in diesem Fall.

Sobald e-Mails aus dem Threat Explorer ausgewählt wurden, kann die Korrektur Erstellung direkt oder durch anstehen von e-Mails für eine Aktion beginnen:

1. Direkte Genehmigung: Wenn Aktionen wie "in den Posteingang verschieben", "in Junk-e-Mail-Nachrichten verschieben", "weiches löschen", "hartes löschen" durch Sicherheitsmitarbeiter mit entsprechenden Berechtigungen ausgewählt wurden und die nächsten Schritte bis zur Korrektur Erstellung befolgt werden, beginnt der Behebungs Prozess mit der Ausführung einer ausgewählten Aktion. Ein temporäres Flyout zeigt eine laufende Wiederherstellung an.

2. Zweistufige Genehmigung: "zur Behebung hinzufügen" kann von einem Administrator ausgeführt werden, der nicht über die entsprechenden Berechtigungen verfügt oder der länger warten muss, um die Aktion auszuführen. In diesem Fall wird die Korrekturaktion nicht direkt ausgeführt. Stattdessen werden dem Behebungs Container e-Mails hinzugefügt, die für die Ausführung genehmigt werden müssen. Bis die Korrektur genehmigt wurde, wird die e-Mail-Nachricht nicht wiederhergestellt. Nachdem die Korrektur genehmigt wurde, werden die Aktionen in der e-Mail ausgeführt.

**Automatische Untersuchung und Reaktion (Air)** werden durch Warnungen oder durch Sicherheits Operations Teams im Threat Explorer ausgelöst. Sie können einige empfohlene Vermittlungen enthalten, die von Sicherheits Betriebsteams genehmigt werden müssen. Diese Korrekturaktionen sind auf der Registerkarte Aktion in der automatisierten Untersuchung enthalten.  

:::image type="content" source="../../../media/tp-RemediationArticle3.png" alt-text="E-Mail-Nachrichten mit Malware werden durch zappen angezeigt und zeigen Zeit für zap-Ausführung.":::

Die gesamte Vermittlung (entweder direkte Genehmigung oder Genehmigung im zweistufigen Verfahren), die über den Threat Explorer erstellt wurde, und genehmigte Aktionen, die aus automatisierten Untersuchungen stammen, werden im Action Center angezeigt, auf das über die linke Navigation unter *Review*- >  **Aktionscenter**zugegriffen werden kann.

:::image type="content" source="../../../media/tp-RemediationArticle4.png" alt-text="Das Aktionscenter mit einer Liste von Bedrohungen nach Datum und Schweregrad.":::

Das Wartungs Center zeigt alle Korrekturaktionen für die letzten 30 Tage an. Durch den Explorer ausgeführte Aktionen werden mit dem gleichen Namen angezeigt, der von den Sicherheits Betriebsteams bereitgestellt wurde, als die Korrektur erstellt wurde. Durch automatisierte Untersuchungen ausgeführte Aktionen werden mit Titeln angezeigt, die mit der zugehörigen Warnung beginnen, die die Untersuchung ausgelöst hat – beispielsweise "zap e-Mail-Cluster...".

Jedes Behebungs Element kann geöffnet werden, um Details dazu anzuzeigen. Wenn ein Behebungs Element geöffnet wird, werden grundlegende Korrektur Details, der Behebungs Name, das Erstellungsdatum, die Beschreibung, der Schweregrad und der Status der Bedrohung angezeigt. Außerdem werden zwei Registerkarten angezeigt. 

1. **Registerkarte "e-Mail-Übermittlung"**: Dies sind die Anzahl von e-Mails, die über den Threat Explorer oder automatisierte Untersuchungen übermittelt werden. Diese e-Mail-Nachrichten können sein:

**Aktionable**: e-Mails in den folgenden Cloud-Postfachspeicher Orten können bearbeitet und verschoben werden, d. h., alle e-Mails innerhalb der behebbaren Kategorie können von einem Standort an einen anderen verschoben werden:
  - Posteingang 
  - Junk-E-Mail  
  - Ordner gelöscht
  - Ordner "Soft Deleted"

>[!NOTE]
> Derzeit kann nur ein Endbenutzer mit Zugriff auf das Postfach Elemente aus einem Ordner für weiche Löschungen wiederherstellen.

**Keine Aktion**möglich: e-Mails an den folgenden Speicherorten können nicht im Rahmen der e-Mail-Aktionen bearbeitet oder verschoben werden, d. h. e-Mails in nicht behebbaren Kategorien können weder in der nicht behebbaren Kategorie noch in einer behebbaren Form verschoben werden. Nicht behebbare Speicherorte sind:

  - Quarantäne
  - Ordner "Hard Deleted"
  - On-Prem/extern
  - Fehlgeschlagen/gelöscht
  
Übermittelte verdächtige Nachrichten werden entweder als behebbar oder nicht behebbar klassifiziert. In den meisten Fällen sollten behebbare und nicht behebbare Nachrichten bis zu den insgesamt gesendeten Nachrichten summieren. Es kann jedoch in seltenen Fällen vorkommen, dass Nachrichten, die übermittelt werden, nicht die Summe der behebbaren und nicht behebbaren Elemente addieren und entweder höher oder niedriger als die Gesamtanzahl der gesendeten Nachrichten sein können. Dies kann aufgrund von System Verzögerungen, Timeouts oder abgelaufenen Nachrichten passieren. Nachrichten laufen basierend auf dem Aufbewahrungszeitraum des Explorers für Ihre Organisation ab.

Wenn Sie alte Nachrichten nicht nach dem Aufbewahrungszeitraum Ihres Unternehmens remediationieren, ist es ratsam, die Remediation von Elementen erneut zu versuchen, wenn Sie Inkonsistenzen in Zahlen sehen. Bei System Verzögerungen werden Korrektur Aktualisierungen in der Regel innerhalb weniger Stunden aktualisiert.

Wenn der Aufbewahrungszeitraum Ihres Unternehmens für e-Mails im Explorer 30 Tage beträgt und Sie e-Mails bereinigen, die 29-30 Tage zurückgehen, kann die Anzahl der e-Mail-Übermittlungs Intervalle möglicherweise nicht immer zusammengezählt werden, da die e-Mails möglicherweise bereits aus dem Aufbewahrungszeitraum verschoben wurden.

Wenn die Vermittlung für eine Weile in einem Status "in Bearbeitung" festgehalten wird, ist dies wahrscheinlich auf System Verzögerungen zurückzuführen. Es kann bis zu ein paar Stunden dauern, bis es behoben wurde. Es kann eine in e-Mail-Übermittlungs Zählungen beobachtete Variation geben, da einige der e-Mails aufgrund von System Verzögerungen nicht Teil der Abfrage waren, während die Korrektur gestartet wurde. Es empfiehlt sich, in diesen Fällen erneut zu versuchen, eine erneute Vermittlung durchführen zu können.  

Um optimale Ergebnisse zu erzielen, sollte die Korrektur in kleineren Batches mit etwa 50.000 oder weniger e-Mails durchgeführt werden.  

Von allen e-Mails in der e-Mail-Übermittlung sind nur behebbare e-Mails, die während der Wiederherstellung bearbeitet werden. Nicht behebbare e-Mails können nicht durch das Office 365-e-Mail-System behoben werden, da Sie nicht in Cloud-Postfächern gespeichert sind.

Bei e-Mails, die in Quarantäne gefunden werden, können Administratoren in Quarantäne wechseln, um bei Bedarf Aktionen für diese e-Mails auszuführen, die e-Mails laufen jedoch aus der Quarantäne, wenn Sie nicht manuell gelöscht werden. E-Mail-Nachrichten, die aufgrund schädlicher Inhalte isoliert wurden, sind von Endbenutzern nicht zugänglich, daher müssen Sicherheitsmitarbeiter keine spezifischen Maßnahmen ergreifen, um die Bedrohung in der Quarantäne loszuwerden. Wenn die e-Mails auf-Prem oder extern sind, kann der Endbenutzer kontaktiert werden, um die Verdächtigen e-Mails zu adressieren oder separate e-Mail-Server/Sicherheitstools zum Entfernen zu verwenden. Diese e-Mails können identifiziert werden, indem der Zustellungsort = on-Prem/externer Filter in Threat Explorer angewendet wird. Bei fehlgeschlagenen oder gelöschten e-Mails oder e-Mails, für die der Endbenutzer nicht zugänglich ist, sollte keine e-Mail zur Minderung erforderlich sein, da Sie das Postfach nicht erreichen.

Auf diese Weise wird eine Übermittlung im Wartungs Center angezeigt. Eine Korrektur kann mehrere Übermittlungen enthalten. Wenn mehrere Aktionen durch eine automatisierte Untersuchung genehmigt werden, wird jede e-Mail-oder e-Mail-Cluster Aktion in derselben Korrektur wie eine andere Übermittlung angezeigt.

:::image type="content" source="../../../media/tp-RemediationArticle6.png" alt-text="Zap-e-Mail-Cluster-Ausklappbereich.":::

Durch Klicken auf ein e-Mail-Übermittlungs Element werden Details zu dieser Korrektur angezeigt, beispielsweise die Abfrage (wenn die Korrektur durch automatische Untersuchungen oder Bedrohungs-Explorer durch Auswählen einer Abfrage ausgelöst wird), Startzeit und Endzeit der Wiederherstellung. Außerdem wird eine Liste der Nachrichten angezeigt, die zur Behebung übermittelt wurden. Wenn Nachrichten aus dem Aufbewahrungszeitraum für den Explorer entfernt werden, werden die Nachrichten aus dieser Liste ausgeblendet. In dieser Liste werden auch einzelne Nachrichten aus der Liste angezeigt, die behoben werden können.

2. **Registerkarte "Aktionsprotokolle"**: auf dieser Registerkarte wird das Ergebnis der Korrektur von Nachrichten angezeigt, einschließlich Details wie genehmigtes Datum, genehmigende Person (Administrator, der die Aktion genehmigt hat), Aktion, Status und Anzahl.  

Status ist der Gesamtstatus der Korrektur. Status kann wie folgt lauten:

  - **Started**: Wenn eine Korrektur ausgelöst wird.
  - In der **Warteschlange**: Wenn die Korrektur zur Minderung von e-Mails in die Warteschlange eingereiht wird.
  - **In Bearbeitung**: Wenn die Minderung ausgeführt wird.
  - **Abgeschlossen**: Wenn die Schadensminimierung für alle behebbaren e-Mails erfolgreich oder mit einigen Fehlern erfolgt ist. 
  - **Fehler**: Wenn keine Korrekturen erfolgreich sind.

Da nur behebbare e-Mails bearbeitet werden können, wird die Bereinigung jeder e-Mail als erfolgreich oder fehlgeschlagen betrachtet. Aus den insgesamt behebbaren e-Mail-Nachrichten können wir die erfolgreichen und fehlgeschlagenen Abhilfemaßnahmen aufdecken.

  - **Erfolg**: Wenn die gewünschte Aktion für behebbare e-Mails ausgeführt wird und der Absicht des Administrators entspricht. Beispiel: ein Administrator möchte e-Mails aus Postfächern entfernen, damit Sie die Aktion von e-Mails mit weichen Löschaktionen durchführen. Wenn im ursprünglichen Ordner keine behebbare e-Mail gefunden wird, nachdem die Aktion ausgeführt wurde, wird der Status als erfolgreich angezeigt.  

  - **Fehler**: Wenn die gewünschte Aktion bei behebbaren e-Mails fehlschlägt. Beispiel: ein Administrator möchte e-Mails aus Postfächern entfernen, damit er die Aktion zum Löschen von e-Mails durch Soft-e-Mails ausführt. Wenn noch eine behebbare e-Mail im Postfach gefunden wird, wird Status als Fehler angezeigt.

Durch Klicken auf ein beliebiges Element im Aktionsprotokoll werden Details zur Korrektur angezeigt. Für erfolgreiche Elemente bedeutet dies, dass das Element bereits aus dem Postfach entfernt wurde, wenn die Details sagen, erfolgreich oder nicht im Postfach gefunden wurden. Manchmal treten Fehler auf, die aufgrund eines Systemfehlers während der Wiederherstellung auftreten, und in diesen Fällen empfiehlt es sich, die Korrektur erneut zu versuchen.  

Die Wiederherstellung ist ein leistungsfähiges Tool zur Abwehr von Bedrohungen und zur Adressierung verdächtiger e-Mails. Es hilft, eine Organisation zu schützen und zu schützen.  

## <a name="more-info"></a>Weitere Informationen

Sieh<https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered?view=o365-worldwide>