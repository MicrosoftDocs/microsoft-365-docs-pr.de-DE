---
title: Suchen und untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden
keywords: TIMailData-Inline, Sicherheitsvorfall, Vorfall, ATP PowerShell, e-Mail-Schadsoftware, kompromittierte Benutzer, e-Mail-Phishing, e-Mail-Schadsoftware, e-Mail-Header lesen, Kopfzeilen lesen, offene e-Mail
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie mithilfe von Bedrohungs Ermittlungs-und-Antwortfunktionen böswillige e-Mails suchen und untersuchen.
ms.openlocfilehash: 57d419c291fdfed3a5d7237ae2021e9ef06723f5
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031900"
---
# <a name="find-and-investigate-malicious-email-that-was-delivered-in-office-365"></a>Suchen und untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden

[Office 365 Advanced Threat Protection](office-365-atp.md) ermöglicht es Ihnen, Aktivitäten zu untersuchen, die Personen in Ihrer Organisation gefährden, sowie Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Wenn Sie beispielsweise Teil des Sicherheitsteams Ihrer Organisation sind, können Sie nach verdächtigen e-Mail-Nachrichten suchen und diese untersuchen, die übermittelt wurden. Sie können dies mithilfe von [Threat Explorer (oder Echtzeiterkennung)](threat-explorer.md)durchführen.
  
## <a name="before-you-begin"></a>Bevor Sie beginnen...

Stellen Sie sicher, dass folgende Anforderungen erfüllt sind:
  
- Ihre Organisation verfügt über [Office 365 erweiterte Bedrohungsschutz](office-365-atp.md) und [Lizenzen werden Benutzern zugewiesen](https://docs.microsoft.com/office365/admin/subscriptions-and-billing/assign-licenses-to-users).
    
- [Office 365 Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) ist für Ihre Organisation aktiviert. 
    
- Ihre Organisation verfügt über Richtlinien, die für Antispam-, Antischadsoftware-und Anti-Phishing-Maßnahmen und so weiter definiert sind. Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).
    
- Sie sind ein Office 365 globaler Administrator oder haben dem Security &amp; Compliance Center entweder den Sicherheitsadministrator oder die Such-und Säuberungs Rolle zugewiesen. Siehe [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). Für einige Aktionen muss auch eine neue Vorschau Rolle zugewiesen sein. 

#### <a name="preview-role-permissions"></a>Vorschau der Rollen Berechtigungen

Um bestimmte Aktionen auszuführen, beispielsweise das Anzeigen von Nachrichtenkopfzeilen oder das Herunterladen von e-Mail-Nachrichteninhalten, müssen Sie eine neue Rolle mit dem Namen *Preview* haben, die einer anderen geeigneten Office 365 Rollengruppe hinzugefügt wird. In der folgenden Tabelle werden die erforderlichen Rollen und Berechtigungen erläutert.

|Aktivität  |Rollengruppe |Vorschau-Rolle erforderlich?  |
|---------|---------|---------|
|Verwenden von Threat Explorer (und Echtzeiterkennung) zum Analysieren von Bedrohungen     |Globaler Office 365-Administrator <br> Sicherheitsadministrator <br> Sicherheits Leser     | Nein   |
|Verwenden Sie Threat Explorer (und Echtzeiterkennung), um Kopfzeilen für e-Mail-Nachrichten anzuzeigen sowie e-Mail-Nachrichten, die in Quarantäne verschoben wurden, anzuzeigen und herunterzuladen.    |Globaler Office 365-Administrator <br> Sicherheitsadministrator <br>Sicherheits Leser   |       Nein  |
|Verwenden von Threat Explorer zum Anzeigen von Kopfzeilen und Herunterladen von an Postfächern zugestellten e-Mails     |Globaler Office 365-Administrator <br>Sicherheitsadministrator <br> Sicherheits Leser <br> Vorschau   |   Ja      |

> [!NOTE]
> *Vorschau* ist eine Rolle und keine Rollengruppe; die Vorschau Rolle muss einer vorhandenen Rollengruppe für Office 365 hinzugefügt werden. Der Office 365 globalen Administrator Rolle wird das Microsoft 365 Admin Center ([https://admin.microsoft.com](https://admin.microsoft.com)) zugewiesen, und die Rollen Sicherheitsadministrator und Sicherheits Leser werden im Office 365 Security #a0 Compliance Center ([https://protection.office.com](https://protection.office.com)) zugewiesen. Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Berechtigungen im Office 365 Security #a0 Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-and-delete-suspicious-email-that-was-delivered"></a>Suchen und löschen verdächtiger e-Mails, die zugestellt wurden

Threat Explorer ist ein leistungsfähiger Bericht, der mehrere Zwecke wie das Suchen und Löschen von Nachrichten, das Identifizieren der IP-Adresse eines böswilligen e-Mail-Absenders oder das Starten eines Vorfalls zur weiteren Untersuchung dienen kann. Das folgende Verfahren konzentriert sich auf die Verwendung von Explorer zum Suchen und Löschen von böswilligen e-Mails aus Empfängerpostfächern.

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit Ihrem Arbeits-oder Schulkonto für Office 365 an. Dadurch gelangen Sie zum Security &amp; Compliance Center. 
    
2. Klicken Sie im linken Navigationsbereich auf **Threat Management** \> **Explorer**.

    ![Explorer mit Felder Zustellungs Aktion und Zustellungs Speicherort.](../media/ThreatExFields.PNG)

    Möglicherweise wird die Spalte neue **spezielle Aktionen** feststellen. Dieses Feature zielt darauf ab, den Administratoren das Ergebnis der Verarbeitung einer e-Mail mitzuteilen. Auf die Spalte **spezielle Aktionen** kann an derselben Stelle wie **Zustellungs Aktion** und **Zustellungs Speicherort**zugegriffen werden. Spezielle Aktionen können am Ende der e-Mail-Zeitachse von Threat Explorer aktualisiert werden, ein neues Feature, mit dem die Jagd Erfahrung für Administratoren besser gemacht werden soll.

3. Klicken Sie zum Anzeigen einer e-Mail-Zeitachse auf den Betreff einer e-Mail-Nachricht, und klicken Sie dann auf **e-Mail-Zeitplan**. (Es wird unter anderen Überschriften wie **Zusammenfassung** oder **Details**auf dem Panel angezeigt.)

    Nachdem Sie die e-Mail-Zeitachse geöffnet haben, sollten Sie eine Tabelle sehen, in der die Ereignisse nach der Zustellung für diese e-Mail mitgeteilt werden. Im Fall von keine weiteren Ereignisse für die e-Mail sollte ein einzelnes Ereignis für die ursprüngliche Zustellung angezeigt werden, die ein Ergebnis wie **blockiert** mit einem Urteil wie **Phish**angibt. Die Registerkarte hat auch die Möglichkeit, die gesamte e-Mail-Zeitachse zu exportieren, und exportiert alle Details auf der Registerkarte und Details zur e-Mail (Dinge wie Betreff, Absender, Empfänger, Netzwerk und Nachrichten-ID).

    Die e-Mail-Zeitachse schneidet nach dem Zufallsprinzip ab, da es bei der Überprüfung verschiedener Standorte kürzer ist, um zu versuchen, Ereignisse zu verstehen, die seit dem Eintreffen der e-Mail geschehen sind. Wenn mehrere Ereignisse bei oder nahe gleichzeitig in einer e-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. 
    
    Einige Ereignisse, die nach der Zustellung an Ihre e-Mails geschehen, werden in der Spalte **spezielle Aktionen** erfasst. Wenn Sie die Informationen aus der e-Mail-Zeitachse zusammen mit speziellen Aktionen für die e-Mail-nach Zustellung kombinieren, erhalten Administratoren einen Einblick in die Funktionsweise Ihrer Richtlinien, wo die e-Mail schließlich weitergeleitet wurde, und in einigen Fällen was die abschließende Bewertung war. 

4. Wählen Sie im Menü **Ansicht** die Option **alle e-Mails**aus.

    ![Verwenden des Menüs "Ansicht" zum Auswählen zwischen e-Mail-und Inhalts Berichten](../media/d39013ff-93b6-42f6-bee5-628895c251c2.png)
  
    Beachten Sie die Bezeichnungen, die im Bericht angezeigt werden, beispielsweise **zugestellt**, **unbekannt**oder **an Junk gesendet**.

    ![Threat Explorer mit Daten für alle e-Mails](../media/208826ed-a85e-446f-b276-b5fdc312fbcb.png)
    
    (Abhängig von den Aktionen, die für e-Mail-Nachrichten für Ihre Organisation durchgeführt wurden, werden möglicherweise andere Bezeichnungen wie " **blockiert** " oder " **ersetzt**" angezeigt.)
    
6. Wählen Sie im Bericht **zugestellt** aus, um nur e-Mail-Nachrichten anzuzeigen, die in den Posteingängen von Benutzern landeten.

    ![Durch Klicken auf "an Junk zugestellt" werden die Daten aus der Ansicht entfernt.](../media/e6fb2e47-461e-4f6f-8c65-c331bd858758.png)
  
7. Überprüfen Sie unter dem Diagramm die **e-Mail-** Liste unter dem Diagramm.

    ![Zeigen Sie unter dem Diagramm eine Liste der gefundenen e-Mail-Nachrichten an.](../media/dfb60590-1236-499d-97da-86c68621e2bc.png)
  
8. Wählen Sie in der Liste ein Element aus, um weitere Details zu dieser e-Mail-Nachricht anzuzeigen. Beispielsweise können Sie auf die Betreffzeile klicken, um Informationen über den Absender, Empfänger, Anlagen und ähnliche e-Mail-Nachrichten anzuzeigen.

    ![Sie können zusätzliche Informationen zu einem Element anzeigen.](../media/5a5707c3-d62a-4610-ae7b-900fff8708b2.png)
  
9. Nachdem Sie Informationen zu e-Mail-Nachrichten angezeigt haben, wählen Sie ein oder mehrere Elemente in der Liste aus, um **+-Aktionen**zu aktivieren.
    
10. Verwenden Sie die Liste **+ Aktionen** , um eine Aktion anzuwenden, beispielsweise " **zu gelöschten Elementen navigieren** ". Dadurch werden die ausgewählten Nachrichten aus den Postfächern der Empfänger gelöscht.

    ![Wenn Sie eine oder mehrere e-Mail-Nachrichten auswählen, können Sie aus mehreren verfügbaren Aktionen auswählen.](../media/ef12e10c-60a7-4f66-8f76-68d77ae26de1.png)

## <a name="dealing-with-suspicious-email-messages"></a>Umgang mit verdächtigen e-Mail-Nachrichten

Böswillige Angreifer senden möglicherweise e-Mails an Personen in Ihrer Organisation, um Ihre Anmeldeinformationen zu Phishing und Zugriff auf Ihre Unternehmensgeheimnisse zu erhalten. Um dies zu verhindern, verwenden Sie die Threat Protection-Dienste in Office 365, einschließlich [Exchange Online Schutz](exchange-online-protection-overview.md) und [erweitertem Bedrohungsschutz](office-365-atp.md). Es kommt jedoch gelegentlich vor, dass ein Angreifer e-Mails sendet, die einen Link (URL) enthalten, der nur später auf böswillige Inhalte (wie Schadsoftware) verweist. Oder Sie erkennen möglicherweise zu spät, dass jemand in Ihrer Organisation kompromittiert wurde, und während diese kompromittiert wurden, hat ein Angreifer sein Konto verwendet, um e-Mails an andere Personen in Ihrer Organisation zu senden. Im Rahmen des Umgangs mit beiden Szenarien können Sie verdächtige e-Mail-Nachrichten aus Benutzer Posteingängen entfernen. Dazu können Sie den [Threat Explorer](threat-explorer.md)verwenden.

## <a name="finding-re-routed-email-messages-after-actions-are-taken"></a>Suchen nach erneut geleiteten e-Mail-Nachrichten nach dem Ausführen von Aktionen

Threat Explorer stellt ihrem Sicherheits Betriebsteam die Details zur Verfügung, die Sie zur Untersuchung verdächtiger e-Mails benötigen. Ihr Security Operations-Team kann Folgendes ausführen:

- [Anzeigen der e-Mail-Header und Herunterladen des e-Mail-Texts](#view-the-email-headers-and-download-the-email-body) 

- [Überprüfen der Übermittlungsaktion und des Speicherorts](#check-the-delivery-action-and-location)

- [Anzeigen der Zeitachse Ihrer e-Mail](#view-the-timeline-of-your-email)

### <a name="view-the-email-headers-and-download-the-email-body"></a>Anzeigen der e-Mail-Header und Herunterladen des e-Mail-Texts

Die Möglichkeit zum Anzeigen von e-Mail-Kopfzeilen und zum Herunterladen des Texts eines e-Mail-Texts sind leistungsstarke Funktionen im Threat Explorer. Die entsprechenden [Berechtigungen](permissions-in-the-security-and-compliance-center.md) müssen zugewiesen werden. Siehe [Vorschau der Rollen Berechtigungen](#preview-role-permissions).

Führen Sie die folgenden Schritte aus, um auf die Nachrichtenkopf-und e-Mail-Downloadoptionen zuzugreifen: 

1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit Ihrem Arbeits-oder Schulkonto für Office 365 an. Dadurch gelangen Sie zum Security &amp; Compliance Center. 
    
2. Klicken Sie im linken Navigationsbereich auf **Threat Management** \> **Explorer**.

3. Klicken Sie auf einen Betreff in der Tabelle Threat Explorer. 

    Dadurch wird das Flyout geöffnet, in dem sowohl Kopfzeilen Vorschau-als auch e-Mail-Download Links positioniert sind.

    ![Bedrohungs-Explorer-Flyout mit Download-und Vorschau-Links auf der Seite.](../media/ThreatExplorerDownloadandPreview.PNG)

> [!IMPORTANT]
> Diese Funktion wird nicht für e-Mail-Nachrichten angezeigt, die im Postfach eines Benutzers nicht gefunden wurden, was passieren kann, wenn eine e-Mail gelöscht oder die Zustellung fehlgeschlagen ist. In Fällen, in denen e-Mail-Nachrichten aus den Postfächern der Benutzer gelöscht wurden, wird den Administratoren die Fehlermeldung "Mail not found" angezeigt.

### <a name="check-the-delivery-action-and-location"></a>Überprüfen der Übermittlungsaktion und des Speicherorts

In [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md)haben Sie nun die Spalten **Zustellungs Aktion** und **Zustellungs Speicherort** anstelle der früheren Spalte **Zustellungs Status** . Dadurch wird ein vollständigeres Bild davon erzielt, wo Ihre e-Mail-Nachrichten landen. Ein Teil des Ziels dieser Änderung besteht darin, die Suche für Sicherheitsvorgänge zu vereinfachen, aber das Ergebnis ist, dass der Speicherort der Problem-e-Mail-Nachrichten auf einen Blick zu erkennen ist.

Der Zustellungs Status wird nun in zwei Spalten aufgeteilt:

- **Zustellungs Aktion** – wie lautet der Status dieser e-Mail?

- **Zustellungs Speicherort** – wohin wurde diese e-Mail weitergeleitet?

Zustellungs Aktion ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen auf eine e-Mail angewendet wird. Hier sind die möglichen Aktionen, die eine e-Mail ausführen kann:

- **Zugestellt** – e-Mails wurden im Posteingang oder Ordner eines Benutzers zugestellt, und der Benutzer kann direkt darauf zugreifen.

- **Junked** – e-Mails wurden entweder an den Junk-Ordner des Benutzers oder den Ordner "gelöscht" gesendet, und der Benutzer hat Zugriff auf e-Mail-Nachrichten in seinem Junk-oder Deleted-Ordner.

- **Blockiert** – alle e-Mail-Nachrichten, die unter Quarantäne gestellt, fehlerhaft oder gelöscht wurden. (Für den Benutzer ist vollständig kein Zugriff möglich.)

- **Ersetzt** – jede e-Mail-Nachricht, bei der böswillige Anlagen durch txt-Dateien ersetzt werden, in denen der Anhang als böswillig bezeichnet wird.
 
Der Übermittlungsort zeigt die Ergebnisse von Richtlinien und Erkennungen an, die nach der Zustellung ausgeführt werden. Sie ist mit einer Zustellungs Aktion verknüpft. Dieses Feld wurde hinzugefügt, um Einblicke in die Aktion zu geben, die ausgeführt wird, wenn ein Problem mit e-Mails gefunden wird. Im folgenden sind die möglichen Werte für den Zustellungs Speicherort zu finden:

- **Posteingang oder Ordner** – die e-Mail befindet sich im Posteingang oder in einem Ordner (entsprechend Ihren e-Mail-Regeln).

- **On-Prem oder External** – das Postfach ist nicht in der Cloud vorhanden, sondern lokal.

- **Junk-Ordner** – die e-Mail befindet sich im Junk-Ordner eines Benutzers.

- **Ordner "Gelöschte Elemente"** – die e-Mail befindet sich im Ordner "Gelöschte Elemente" eines Benutzers.

- **Quarantine** – die e-Mail-Nachricht in Quarantäne und nicht im Postfach eines Benutzers.

- **Fehler** – die e-Mail konnte das Postfach nicht erreichen.

- **Fallen gelassen** – die e-Mail wird irgendwo im Nachrichtenfluss verloren.

### <a name="view-the-timeline-of-your-email"></a>Anzeigen der Zeitachse Ihrer e-Mail
  
**E-Mail-Zeitachse** ist ein Feld in Threat Explorer, das die Suche für Ihr Sicherheitsteam erleichtert. Wenn mehrere Ereignisse bei oder nahe gleichzeitig in einer e-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. Einige Ereignisse, die nach der Zustellung an e-Mails geschehen, werden in der Spalte **spezielle Aktionen** erfasst. Durch das Kombinieren von Informationen aus der Zeitachse einer e-Mail-Nachricht mit speziellen Aktionen, die nach der Zustellung vorgenommen wurden, erhalten Administratoren Einblicke in Richtlinien und die Bedrohungsbehandlung (beispielsweise, wohin die e-Mail weitergeleitet wurde, und in einigen Fällen was die abschließende Bewertung war).
  
## <a name="related-topics"></a>Verwandte Themen

[Office 365 Advanced Threat Protection](office-365-ti.md)
  
[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)
  
[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)
  

