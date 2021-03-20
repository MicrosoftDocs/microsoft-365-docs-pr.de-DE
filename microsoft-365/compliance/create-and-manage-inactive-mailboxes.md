---
title: Erstellen und Verwalten inaktiver Postfächer
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 296a02bd-ebde-4022-900e-547acf38ddd7
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie den Inhalt gelöschter Postfächer mithilfe der Funktion für inaktive Postfächer in Office 365 beibehalten.
ms.openlocfilehash: 45de882cf0931b85d3acd6368f619f94fce636d7
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908379"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Erstellen und Verwalten inaktiver Postfächer

Microsoft 365 ermöglicht es Ihnen, den Inhalt gelöschter Postfächer zu behalten. Dieses Feature heißt [inaktive Postfächer](inactive-mailboxes-in-office-365.md). In inaktiven Postfächern können Sie E-Mails früherer Mitarbeiter aufbewahren, nachdem sie Ihre Organisation verlassen haben. Ein Postfach wird inaktiv, wenn ein Aufbewahrungsverfahren oder eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das Postfach angewendet wird, bevor das entsprechende Benutzerkonto gelöscht wird. Die Inhalte eines inaktiven Postfachs werden für die Dauer der Archivierung beibehalten, die für das Postfach aktiviert wurde, bevor es inaktiv gemacht wurde. Auf diese Weise können Administratoren, Compliance officers und Datensatzmanager die Inhaltssuche verwenden, um die Inhalte eines inaktiven Postfachs zu durchsuchen und zu exportieren. Inaktive Postfächer können keine E-Mails empfangen und werden im freigegebenen Adressbuch Ihrer Organisation oder in anderen Listen nicht angezeigt.
  
> [!IMPORTANT]
> Da wir weiterhin auf unterschiedliche Weise investieren, um Postfachinhalte zu erhalten, wird der In-Place im Exchange Admin Center angekündigt. Das bedeutet, dass Sie zum Erstellen eines inaktiven Postfachs Aufbewahrungs- und Aufbewahrungsrichtlinien verwenden sollten. Ab dem 1. Juli 2020 können Sie keine neuen In-Place in Exchange Online erstellen. Sie können jedoch weiterhin die Haltedauer eines In-Place inaktiven Postfachs ändern. Ab dem 1. Oktober 2020 können Sie die Haltedauer jedoch nicht mehr ändern. Sie können nur ein inaktives Postfach löschen, indem Sie die In-Place entfernen. Vorhandene inaktive Postfächer, die sich im In-Place befinden, bleiben bis zum Entfernen des Haltespeichers erhalten. Weitere Informationen zum Austritt von In-Place finden Sie unter [Retirement of legacy eDiscovery tools](legacy-ediscovery-retirement.md).
  
## <a name="preparations-before-creating-an-inactive-mailbox"></a>Vorbereitungen vor dem Erstellen eines inaktiven Postfachs

- Damit ein Postfach inaktiv wird, muss ihm eine Exchange Online Plan 2-Lizenz zugewiesen werden, damit ein Aufbewahrungsverfahren oder eine Aufbewahrungsrichtlinie auf das Postfach angewendet werden kann, bevor es gelöscht wird. Exchange Online Plan 2-Lizenzen sind Teil eines Office 365 Enterprise E3- und E5-Abonnements. Wenn einem Postfach eine Exchange Online Plan 1- oder Exchange Online-Kiosk-Lizenz zugewiesen ist (die Teil eines Office 365 E1- bzw. F1-Abonnements sind), müssen Sie ihm eine separate Exchange Online-Archivierung-Lizenz zuweisen, damit dem Postfach ein Halteraum zugewiesen werden kann, bevor es gelöscht wird. Weitere Informationen finden Sie unter [Exchange Online-Archivierung](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- Die Lizenzen, die dem gelöschten Exchange Online-Postfach zugeordnet sind, sind verfügbar, nachdem Sie das entsprechende Benutzerkonto gelöscht haben. Sie können diese [Lizenzen dann einem anderen Benutzer zuweisen.](../admin/manage/assign-licenses-to-users.md)

- Wenn ein Aufbewahrungsverfahren oder eine Aufbewahrungsrichtlinie (die so konfiguriert ist, dass Inhalte aufbewahrt oder aufbewahrt und dann gelöscht werden) nicht auf ein Postfach angewendet wird, bevor es gelöscht wird, wird der Inhalt des Postfachs nicht beibehalten oder auf deren Entdeckung angezeigt. Das gelöschte Postfach kann jedoch innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden, aber das Postfach und sein Inhalt werden nach 30 Tagen endgültig gelöscht, wenn es nicht wiederhergestellt wird.

- Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [In-Place Hold and Litigation Hold](/exchange/security-and-compliance/in-place-and-litigation-holds). Weitere Informationen zu Aufbewahrungsrichtlinien finden Sie [unter Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen.](retention.md)
  
## <a name="create-an-inactive-mailbox"></a>Erstellen eines inaktiven Postfachs

Das Inaktivieren eines Postfachs umfasst zwei Schritte: 1) Das Verschieben des Postfachs in das Aufbewahrungsverfahren oder das Anwenden einer Aufbewahrungsrichtlinie auf das Postfach und 2) das Löschen des Postfachs oder des entsprechenden Benutzerkontos. Nachdem das Postfach deaktiviert wurde, bleiben die Inhalte erhalten, bis die Archivierung beendet oder die Aufbewahrungsrichtlinie entfernt wird.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Schritt 1: Platzieren eines Postfachs in das Aufbewahrungsverfahren für Rechtsstreitigkeiten oder Anwenden einer Aufbewahrungsrichtlinie

Wenn Sie ein Postfach in das Aufbewahrungsverfahren für Rechtsstreitigkeiten setzen oder eine Aufbewahrungsrichtlinie anwenden (die so konfiguriert ist, dass Inhalte beibehalten oder gespeichert und dann gelöscht werden), werden die Inhalte im Postfach beibehalten, bevor es gelöscht wird. Bei beiden Verfahren bleiben sämtliche Postfachinhalte einschließlich gelöschter Elemente und Originalversionen geänderter Elemente erhalten. Gelöschte und geänderte Elemente verbleiben für einen bestimmten Zeitraum im inaktiven Postfach oder solange, bis das inaktive Postfach endgültig gelöscht wird, indem die Archivierung deaktiviert wird oder die auf das inaktive Postfach angewendete Aufbewahrungsrichtlinie entfernt wird.
  
Wenn für ein Postfach bereits eine Aufbewahrungsrichtlinie vorhanden ist oder eine Aufbewahrungsrichtlinie bereits auf ein Postfach angewendet wurde, müssen Sie nur das entsprechende Benutzerkonto löschen, wie in Schritt 2 erläutert.
  
Schritt-für-Schritt-Verfahren zum Platzieren eines Postfachs in der Aufbewahrungsaufbewahrung oder zum Anwenden einer Aufbewahrungsrichtlinie finden Sie unter:
  
- [Aktivieren des Beweissicherungsverfahrens für ein Postfach](./create-a-litigation-hold.md)
    
- [Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen in Office 365](retention.md)
    
> [!NOTE]
> Für Aufbewahrungs- und Aufbewahrungsrichtlinien für Rechtsstreitigkeiten können Sie eine unbegrenzte Aufbewahrungszeit oder einen zeitbasierten Halteraum erstellen. Bei einer dauerhaften Aufbewahrung werden die Inhalte des inaktiven Postfachs dauerhaft oder so lange beibehalten, bis die Aufbewahrung aufgehoben oder ihre Dauer geändert wird. Nachdem die Aufbewahrung beendet oder die Aufbewahrungsrichtlinie deaktiviert wurde (vorausgesetzt, das Postfach wurde vor mehr als 30 Tagen gelöscht), wird das inaktive Postfach für das endgültige Löschen markiert, und die Inhalte des Postfachs werden nicht aufbewahrt und können nicht gefunden werden. In einer zeitbasierten Aufbewahrungs- oder Aufbewahrungsrichtlinie geben Sie die Dauer der Aufbewahrung an. Diese Dauer wird pro Element festgelegt und wird von dem Datum ab berechnet, an dem ein Postfachelement empfangen oder erstellt wurde. Nachdem die Archivierung für ein Postfachelement abgelaufen ist und sich dieses Element im Ordner „Wiederherstellbare Elemente" im inaktiven Postfach befindet, wird das Element dauerhaft aus dem inaktiven Postfach gelöscht, nachdem die Aufbewahrungsdauer für das gelöschte Element abgelaufen ist. 
  
### <a name="step-2-delete-the-mailbox"></a>Schritt 2: Löschen des Postfachs

Nachdem das Postfach in der Aufbewahrungsaufbewahrung platziert oder eine Aufbewahrungsrichtlinie angewendet wurde, besteht der nächste Schritt im Löschen des Postfachs. Die beste Möglichkeit zum Löschen eines Postfachs ist das Löschen des entsprechenden Benutzerkontos im Microsoft 365 Admin Center. Informationen zum Löschen von Benutzerkonten finden Sie unter [Löschen eines Benutzers aus Ihrer Organisation](../admin/add-users/delete-a-user.md).
  
> [!NOTE]
> Sie können das Postfach auch mit dem **Remove-Mailbox** -Cmdlet in Exchange Online PowerShell löschen. Weitere Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Anzeigen einer Liste inaktiver Postfächer

So zeigen Sie eine Liste der inaktiven Postfächer in Ihrer Organisation an:
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie **auf Aufbewahrung von Information Governance**  >  .
    
3. Klicken Sie **auf der** Seite Aufbewahrung auf **Weitere** ![ Navigationsleiste-Ellipsen, und klicken Sie dann auf ](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif) **Inaktive Postfächer**.
    
    ![Klicken Sie auf der Seite Aufbewahrung auf Mehr, und klicken Sie dann auf Inaktive Postfächer, um eine Liste der inaktiven Postfächer anzeigen zu können.](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Die **Seite Inaktive Postfächer** wird angezeigt. Beachten Sie, dass die Gesamtzahl der inaktiven Postfächer in Ihrer Organisation angezeigt wird. 
    
    ![Eine Liste aller inaktiven Postfächer in Ihrer Organisation wird angezeigt.](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Alternativ können Sie den folgenden Befehl in Exchange Online PowerShell ausführen, um die Liste der inaktiven Postfächer anzeigen.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Sie können auf Suchergebnisse exportieren klicken Symbol Exportieren, um eine CSV-Datei mit zusätzlichen Informationen zu den inaktiven Postfächern in Ihrer Organisation anzeigen oder ![ ](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)  herunterladen. 
  
Sie können auch den folgenden Befehl ausführen, um die Liste der inaktiven Postfächer und anderer Informationen in eine CSV-Datei zu exportieren. In diesem Beispiel wird die CSV-Datei im aktuellen Verzeichnis erstellt.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Es ist möglich, dass ein inaktives Postfach die gleiche SMTP-Adresse wie ein aktives Benutzerpostfach hat. In diesem Fall kann der Wert der **DistinguishedName-** oder **ExchangeGuid-Eigenschaft** verwendet werden, um ein inaktives Postfach eindeutig zu identifizieren. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Durchsuchen und Exportieren der Inhalte eines inaktiven Postfachs

Sie können auf den Inhalt des inaktiven Postfachs mithilfe des Inhaltssuchtools im Security & Compliance Center zugreifen. Wenn Sie ein inaktives Postfach durchsuchen, können Sie eine Schlüsselwort-Suchabfrage erstellen, um nach bestimmten Elementen zu suchen, oder Sie können den gesamten Inhalt des inaktiven Postfachs zurückgeben. Sie können die Suchergebnisse in einer Vorschau anzeigen oder die Suchergebnisse in eine Outlook-Datendatei (.pst) oder als einzelne E-Mail-Nachrichten exportieren. Eine Schritt-für-Schritt-Anleitung zum Durchsuchen von Postfächern und Exportieren der Suchergebnisse finden Sie in den folgenden Themen:
  
- [Inhaltssuche in Office 365](content-search.md)
    
- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)
    
Folgende Dinge sollten beim Durchsuchen inaktiver Postfächer beachtet werden:
  
- Wenn eine Inhaltssuche ein Benutzerpostfach enthält und dieses Postfach inaktiv gemacht wird, sucht die Inhaltssuche weiterhin nach dem inaktiven Postfach, wenn Sie die Suche erneut ausführen, nachdem es inaktiv wurde.
    
- In einigen Fällen kann ein Benutzer über ein aktives Postfach und ein inaktives Postfach mit derselben SMTP-Adresse verfügen. In diesem Fall wird nur das bestimmte Postfach durchsucht, das Sie als Speicherort für eine Inhaltssuche auswählen. Anders ausgedrückt: Wenn Sie das Postfach eines Benutzers zu einer Suche hinzufügen, können Sie nicht davon ausgehen, dass sowohl die aktiven als auch die inaktiven Postfächer durchsucht werden. Nur das Postfach, das Sie der Suche explizit hinzufügen, wird durchsucht.
    
- Es wird dringend empfohlen, die Verwendung der gleichen SMTP-Adresse für ein aktives und ein inaktives Postfach zu vermeiden. Wenn Sie die SMTP-Adresse wiederverwenden müssen, die derzeit einem inaktiven Postfach zugewiesen ist, wird empfohlen, das inaktive Postfach wiederherzustellen oder den Inhalt eines inaktiven Postfachs in einem aktiven Postfach (oder im Archiv eines aktiven Postfachs) wiederherzustellen und dann das inaktive Postfach zu löschen.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Ändern der Aufbewahrungsdauer für ein inaktives Postfach

Nachdem ein Postfach inaktiv gemacht wurde, können Sie die Aufbewahrungsdauer oder die Aufbewahrungsrichtlinie ändern, die auf das inaktive Postfach angewendet wird. Schrittweise Verfahren finden Sie unter Ändern der Haltedauer für ein [inaktives Postfach in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

Wenn der ehemalige Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach umgewandelt, wobei Inhalt und Ordnerstruktur des inaktiven Postfachs beibehalten werden und das Postfach mit einem neuen Benutzerkonto verknüpft wird. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schrittweise Verfahren und weitere Informationen zu Vorgängen beim Wiederherstellen eines inaktiven Postfachs finden Sie unter [Recover an inactive mailbox in Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Wiederherstellen des Inhalts eines inaktiven Postfachs in einem anderen Postfach

Wenn ein anderer Mitarbeiter die Aufgaben eines ehemaligen Mitarbeiters übernimmt oder wenn eine andere Person Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Wenn Sie ein inaktives Postfach wiederherstellen, werden die Inhalte in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Das inaktive Postfach kann weiterhin mithilfe von eDiscovery durchsucht werden, seine Inhalte können in einem anderen Postfach wiederhergestellt oder zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden. Schrittweise Verfahren finden Sie unter [Restore an inactive mailbox in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Löschen eines inaktiven Postfachs

Wenn Sie den Inhalt eines inaktiven Postfachs nicht mehr beibehalten müssen, können Sie das inaktive Postfach dauerhaft löschen, indem Sie die Aufbewahrungsrichtlinie entfernen oder die Aufbewahrungsrichtlinie für das inaktive Postfach entfernen. Wenn das Postfach vor über 30 Tagen gelöscht wurde, wird das Postfach nach Aufheben der Deaktivierung für das endgültige Löschen markiert, und das Postfach kann nicht wiederhergestellt werden. Wenn das Postfach in den letzten 30 Tagen gelöscht wurde, können Sie das Postfach nach Aufheben der Archivierung oder Entfernen der Aufbewahrungsrichtlinie wiederherstellen. Schrittweise Verfahren zum Entfernen einer Aufbewahrungs- oder Aufbewahrungsrichtlinie zum dauerhaften Löschen eines inaktiven Postfachs finden Sie unter [Delete an inactive mailbox](delete-an-inactive-mailbox.md).