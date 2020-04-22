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
description: Sie können ein inaktives Postfach in Microsoft 365 erstellen, indem Sie eine Aufbewahrungs-oder Aufbewahrungsrichtlinie auf das Postfach anwenden und dann das entsprechende Benutzerkonto löschen. Elemente in einem inaktiven Postfach werden für die Dauer des Haltestatus oder der Aufbewahrungsrichtlinie aufbewahrt, die auf Sie angewendet wurde, bevor Sie inaktiv gemacht wurde. Um ein inaktives Postfach endgültig zu löschen, entfernen Sie einfach die Aufbewahrungsrichtlinie.
ms.openlocfilehash: 9c34acb22e1be7f88d87d254c0fac34ca9ff8105
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43634207"
---
# <a name="create-and-manage-inactive-mailboxes"></a>Erstellen und Verwalten inaktiver Postfächer

Mit Microsoft 365 können Sie den Inhalt von gelöschten Postfächern beibehalten. Dieses Feature heißt [inaktive Postfächer](inactive-mailboxes-in-office-365.md). In inaktiven Postfächern können Sie E-Mails früherer Mitarbeiter aufbewahren, nachdem sie Ihre Organisation verlassen haben. Ein Postfach wird inaktiv, wenn ein Beweissicherungsverfahren oder eine Aufbewahrungsrichtlinie (erstellt im Security and Compliance Center in Office 365 oder Microsoft 365) auf das Postfach angewendet wird, bevor das entsprechende Benutzerkonto gelöscht wird. Die Inhalte eines inaktiven Postfachs werden für die Dauer der Archivierung beibehalten, die für das Postfach aktiviert wurde, bevor es inaktiv gemacht wurde. Auf diese Weise können Administratoren, Compliance Officer und Datensatzverwalter die Inhaltssuche verwenden, um die Inhalte eines inaktiven Postfachs zu durchsuchen und zu exportieren. Inaktive Postfächer können keine E-Mails empfangen und werden im freigegebenen Adressbuch Ihrer Organisation oder in anderen Listen nicht angezeigt.
  
> [!IMPORTANT]
> Da wir weiterhin auf verschiedene Arten investieren, um Postfachinhalte beizubehalten, kündigen wir den Ruhestand von in-Place-Speicher in der Exchange-Verwaltungskonsole an. Das heißt, Sie sollten Beweissicherungsverfahren und Aufbewahrungsrichtlinien verwenden, um ein inaktives Postfach zu erstellen. Ab dem 1. Juli 2020 können Sie in Exchange Online keine neuen in-Place-Aufbewahrungsorte erstellen. Sie können jedoch weiterhin die Aufbewahrungsdauer eines in-situ-Speichers ändern, der in einem inaktiven Postfach platziert wird. Ab dem 1. Oktober 2020 können Sie die Aufbewahrungsdauer jedoch nicht ändern. Sie können ein inaktives Postfach nur löschen, indem Sie den in-situ-Speicher entfernen. Vorhandene inaktive Postfächer, die sich im Compliance-Archiv befinden, werden weiterhin beibehalten, bis die Aufbewahrung aufgehoben wird. Weitere Informationen zum Ruhestand von in-Place-Archiven finden Sie unter [Retirement of Legacy eDiscovery Tools](legacy-ediscovery-retirement.md).
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Um ein Postfach inaktiv zu machen, muss ihm eine Exchange Online Plan 2-Lizenz zugewiesen sein, damit ein Beweissicherungsverfahren oder eine Aufbewahrungsrichtlinie auf das Postfach angewendet werden kann, bevor es gelöscht wird. Exchange Online Plan 2-Lizenzen sind Teil eines Office 365 Enterprise E3-und E5-Abonnements. Wenn einem Postfach eine Exchange Online Plan 1 oder Exchange Online Kiosk Lizenz (die Teil eines Office 365 E1-und F1-Abonnements sind) zugewiesen ist, müssen Sie ihm eine separate Exchange Online Archivierungslizenz zuweisen, damit ein Aufbewahrungsspeicher auf das Postfach angewendet werden kann, bevor es gelöscht wird. Weitere Informationen finden Sie unter [Exchange Online-Archivierung](https://go.microsoft.com/fwlink/p/?LinkId=286153).

- Die dem gelöschten Exchange Online Postfach zugeordneten Lizenzen sind verfügbar, nachdem Sie das entsprechende Benutzerkonto gelöscht haben. Sie können [Diese Lizenzen dann einem anderen Benutzer zuweisen](https://support.office.com/article/997596b5-4173-4627-b915-36abac6786dc). 

- Wenn ein Beweissicherungsverfahren oder eine Aufbewahrungsrichtlinie (die so konfiguriert ist, dass Inhalte beibehalten oder beibehalten und dann gelöscht werden) nicht auf ein Postfach angewendet wird, bevor es gelöscht wird, wird der Inhalt des Postfachs nicht beibehalten oder kann nicht erkannt werden. Das gelöschte Postfach kann jedoch innerhalb von 30 Tagen nach dem Löschen wiederhergestellt werden, aber das Postfach und dessen Inhalte werden nach 30 Tagen endgültig gelöscht, wenn es nicht wiederhergestellt wird.

- Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [In-Place Hold and Litigation Hold](https://go.microsoft.com/fwlink/p/?LinkId=846124). Weitere Informationen zu Aufbewahrungsrichtlinien finden Sie unter [Übersicht über Aufbewahrungsrichtlinien in Microsoft 365](retention-policies.md).
  
## <a name="create-an-inactive-mailbox"></a>Erstellen eines inaktiven Postfachs

Das Deaktivieren eines Postfachs umfasst zwei Schritte: 1) Platzieren des Postfachs für das Beweissicherungsverfahren oder Anwenden einer Aufbewahrungsrichtlinie und 2) Löschen des Postfachs oder des entsprechenden Benutzerkontos. Nachdem das Postfach deaktiviert wurde, bleiben die Inhalte erhalten, bis die Archivierung beendet oder die Aufbewahrungsrichtlinie entfernt wird.
  
### <a name="step-1-place-a-mailbox-on-litigation-hold-or-apply-a-retention-policy"></a>Schritt 1: aufbewahren eines Postfachs für das Beweissicherungsverfahren oder Anwenden einer Aufbewahrungsrichtlinie

Wenn Sie ein Postfach auf ein Beweissicherungsverfahren setzen oder eine Aufbewahrungsrichtlinie anwenden (die so konfiguriert ist, dass Inhalte beibehalten oder beibehalten und anschließend gelöscht werden), werden die Inhalte im Postfach beibehalten, bevor Sie gelöscht werden. Bei beiden Verfahren bleiben sämtliche Postfachinhalte einschließlich gelöschter Elemente und Originalversionen geänderter Elemente erhalten. Gelöschte und geänderte Elemente verbleiben für einen bestimmten Zeitraum im inaktiven Postfach oder solange, bis das inaktive Postfach endgültig gelöscht wird, indem die Archivierung deaktiviert wird oder die auf das inaktive Postfach angewendete Aufbewahrungsrichtlinie entfernt wird.
  
Wenn ein Haltestatus bereits in einem Postfach gespeichert ist oder wenn bereits eine Aufbewahrungsrichtlinie auf ein Postfach angewendet wurde, müssen Sie lediglich das entsprechende Benutzerkonto löschen, wie in Schritt 2 erläutert.
  
Eine schrittweise Anleitung für das Platzieren eines Postfachs für das Beweissicherungsverfahren oder das Anwenden einer Aufbewahrungsrichtlinie finden Sie unter:
  
- [Place a mailbox on Litigation Hold](https://go.microsoft.com/fwlink/?linkid=856286)
    
- [Übersicht über Aufbewahrungsrichtlinien in Office 365](retention-policies.md)
    
> [!NOTE]
> Für Beweissicherungsverfahren und Aufbewahrungsrichtlinien können Sie ein unbefristetes Archiv oder einen zeitbasierten Haltestatus erstellen. Bei einer dauerhaften Aufbewahrung werden die Inhalte des inaktiven Postfachs dauerhaft oder so lange beibehalten, bis die Aufbewahrung aufgehoben oder ihre Dauer geändert wird. Nachdem die Aufbewahrung beendet oder die Aufbewahrungsrichtlinie deaktiviert wurde (vorausgesetzt, das Postfach wurde vor mehr als 30 Tagen gelöscht), wird das inaktive Postfach für das endgültige Löschen markiert, und die Inhalte des Postfachs werden nicht aufbewahrt und können nicht gefunden werden. In einer zeitbasierten Speicherung oder Aufbewahrungsrichtlinie geben Sie die Dauer des Haltestatus an. Diese Dauer wird pro Element festgelegt und wird von dem Datum ab berechnet, an dem ein Postfachelement empfangen oder erstellt wurde. Nachdem die Archivierung für ein Postfachelement abgelaufen ist und sich dieses Element im Ordner „Wiederherstellbare Elemente" im inaktiven Postfach befindet, wird das Element dauerhaft aus dem inaktiven Postfach gelöscht, nachdem die Aufbewahrungsdauer für das gelöschte Element abgelaufen ist. 
  
### <a name="step-2-delete-the-mailbox"></a>Schritt 2: Löschen des Postfachs

Nachdem das Postfach gespeichert wurde oder eine Aufbewahrungsrichtlinie angewendet wurde, besteht der nächste Schritt darin, das Postfach zu löschen. Die beste Möglichkeit zum Löschen eines Postfachs ist das Löschen des entsprechenden Benutzerkontos im Microsoft 365 Admin Center. Informationen zum Löschen von Benutzerkonten finden Sie unter [Löschen eines Benutzers aus Ihrer Organisation](https://support.office.com/article/d5155593-3bac-4d8d-9d8b-f4513a81479e).
  
> [!NOTE]
> Sie können das Postfach auch mit dem **Remove-Mailbox** -Cmdlet in Exchange Online PowerShell löschen. Weitere Informationen finden Sie unter [Löschen oder Wiederherstellen von Benutzerpostfächern in Exchange Online](https://go.microsoft.com/fwlink/?linkid=856287). 
  

## <a name="view-a-list-of-inactive-mailboxes"></a>Anzeigen einer Liste inaktiver Postfächer

So zeigen Sie eine Liste der inaktiven Postfächer in Ihrer Organisation an:
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie auf **Informations Verwaltungs** > **Beibehaltung**.
    
3. Klicken Sie auf der Seite **Aufbewahrung** auf **Weitere**![Ellipsen der](../media/9723029d-e5cd-4740-b5b1-2806e4f28208.gif)Navigationsleiste, und klicken Sie dann auf **inaktive Postfächer**.
    
    ![Klicken Sie auf der Seite Aufbewahrung auf mehr und dann auf inaktive Postfächer, um eine Liste der inaktiven Postfächer anzuzeigen.](../media/761bd90c-3e37-48f9-b1b9-479e90fea267.png)
  
    Die Seite **inaktive Postfächer** wird angezeigt. Hinweis Die Gesamtzahl der inaktiven Postfächer in Ihrer Organisation wird angezeigt. 
    
    ![Es wird eine Liste aller inaktiven Postfächer in Ihrer Organisation angezeigt.](../media/57d9d183-0c6c-4bd8-82e7-115f7b7b6de7.png)
  
Alternativ können Sie den folgenden Befehl in Exchange Online PowerShell ausführen, um die Liste der inaktiven Postfächer anzuzeigen.

```powershell
 Get-Mailbox -InactiveMailboxOnly | FT DisplayName,PrimarySMTPAddress,WhenSoftDeleted
```

Sie können auf ![Export Suchergebnisse Symbol](../media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **exportieren** klicken, um eine CSV-Datei anzuzeigen oder herunterzuladen, die zusätzliche Informationen zu den inaktiven Postfächern in Ihrer Organisation enthält. 
  
Sie können auch den folgenden Befehl ausführen, um die Liste der inaktiven Postfächer und anderer Informationen in eine CSV-Datei zu exportieren. In diesem Beispiel wird die CSV-Datei im aktuellen Verzeichnis erstellt.

```powershell
Get-Mailbox -InactiveMailboxOnly | Select Displayname,PrimarySMTPAddress,DistinguishedName,ExchangeGuid,WhenSoftDeleted | Export-Csv InactiveMailboxes.csv -NoType
```

> [!NOTE]
> Möglicherweise hat ein inaktives Postfach die gleiche SMTP-Adresse wie ein aktives Benutzerpostfach. In diesem Fall kann der Wert der **distinguishedName** -oder **ExchangeGuid** -Eigenschaft verwendet werden, um ein inaktives Postfach eindeutig zu identifizieren. 
  
## <a name="search-and-export-the-contents-of-an-inactive-mailbox"></a>Durchsuchen und Exportieren der Inhalte eines inaktiven Postfachs

Sie können auf die Inhalte des inaktiven Postfachs mithilfe des Tools zur Inhaltssuche im Security & Compliance Center zugreifen. Wenn Sie ein inaktives Postfach durchsuchen, können Sie eine Schlüsselwort-Suchabfrage erstellen, um nach bestimmten Elementen zu suchen, oder Sie können den gesamten Inhalt des inaktiven Postfachs zurückgeben. Sie können die Suchergebnisse in einer Vorschau anzeigen oder die Suchergebnisse in eine Outlook-Datendatei (.pst) oder als einzelne E-Mail-Nachrichten exportieren. Eine Schritt-für-Schritt-Anleitung zum Durchsuchen von Postfächern und Exportieren der Suchergebnisse finden Sie in den folgenden Themen:
  
- [Inhaltssuche in Office 365](content-search.md)
    
- [Exportieren von Inhaltssuchergebnissen ](export-search-results.md)
    
Folgende Dinge sollten beim Durchsuchen inaktiver Postfächer beachtet werden:
  
- Wenn eine Inhaltssuche ein Benutzerpostfach enthält und dieses Postfach dann inaktiv gemacht wird, wird durch die Inhaltssuche weiterhin das inaktive Postfach durchsucht, wenn Sie die Suche erneut ausführen, nachdem Sie inaktiv geworden ist.
    
- In einigen Fällen verfügt ein Benutzer möglicherweise über ein aktives Postfach und ein inaktives Postfach mit der gleichen SMTP-Adresse. In diesem Fall wird nur das bestimmte Postfach durchsucht, das Sie als Speicherort für eine Inhaltssuche ausgewählt haben. Wenn Sie also das Postfach eines Benutzers zu einer Suche hinzufügen, können Sie nicht davon ausgehen, dass sowohl die aktiven als auch die inaktiven Postfächer durchsucht werden. nur das Postfach, das Sie explizit zur Suche hinzufügen, wird durchsucht.
    
- Es wird dringend empfohlen, die Verwendung der gleichen SMTP-Adresse für ein aktives und ein inaktives Postfach zu vermeiden. Wenn Sie die SMTP-Adresse, die derzeit einem inaktiven Postfach zugewiesen ist, wieder verwenden müssen, wird empfohlen, das inaktive Postfach wiederherzustellen oder den Inhalt eines inaktiven Postfachs in einem aktiven Postfach (oder im Archiv eines aktiven Postfachs) wiederherzustellen und dann das inaktive Postfach zu löschen.
    
## <a name="change-the-hold-duration-for-an-inactive-mailbox"></a>Ändern der Aufbewahrungsdauer für ein inaktives Postfach

Nachdem ein Postfach deaktiviert wurde, können Sie die Dauer des Haltestatus oder die auf das inaktive Postfach angewendete Aufbewahrungsrichtlinie ändern. Eine schrittweise Anleitung finden Sie unter [Ändern der Aufbewahrungsdauer für ein inaktives Postfach in Office 365](change-the-hold-duration-for-an-inactive-mailbox.md).
  
## <a name="recover-an-inactive-mailbox"></a>Wiederherstellen eines inaktiven Postfachs

Wenn der ehemalige Mitarbeiter in Ihre Organisation zurückkehrt oder ein neuer Mitarbeiter eingestellt wird, der die Zuständigkeiten des ehemaligen Mitarbeiters übernimmt, können Sie den Inhalt des inaktiven Postfachs wiederherstellen. Wenn Sie ein inaktives Postfach wiederherstellen, wird das Postfach in ein neues Postfach umgewandelt, wobei Inhalt und Ordnerstruktur des inaktiven Postfachs beibehalten werden und das Postfach mit einem neuen Benutzerkonto verknüpft wird. Nach der Wiederherstellung ist das inaktive Postfach nicht mehr vorhanden. Schritt-für-Schritt-Verfahren und weitere Informationen zu Vorgängen, wenn Sie ein inaktives Postfach wiederherstellen, finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](recover-an-inactive-mailbox.md).
  
## <a name="restore-the-contents-of-an-inactive-mailbox-to-another-mailbox"></a>Wiederherstellen des Inhalts eines inaktiven Postfachs in einem anderen Postfach

Wenn ein anderer Mitarbeiter die Aufgaben eines ehemaligen Mitarbeiters übernimmt oder eine andere Person Zugriff auf die Inhalte des inaktiven Postfachs benötigt, können Sie den Inhalt des inaktiven Postfachs in einem vorhandenen Postfach wiederherstellen (oder zusammenführen). Wenn Sie ein inaktives Postfach wiederherstellen, werden die Inhalte in ein anderes Postfach kopiert. Das inaktive Postfach wird beibehalten und bleibt ein inaktives Postfach. Das inaktive Postfach kann weiterhin mithilfe von eDiscovery durchsucht werden, dessen Inhalt kann in einem anderen Postfach wiederhergestellt werden, oder es kann zu einem späteren Zeitpunkt wiederhergestellt oder gelöscht werden. Eine schrittweise Anleitung finden Sie unter [Wiederherstellen eines inaktiven Postfachs in Office 365](restore-an-inactive-mailbox.md).
  
## <a name="delete-an-inactive-mailbox"></a>Löschen eines inaktiven Postfachs

Wenn Sie den Inhalt eines inaktiven Postfachs nicht mehr aufbewahren müssen, können Sie das inaktive Postfach endgültig löschen, indem Sie den Haltestatus entfernen oder die Aufbewahrungsrichtlinie entfernen, die auf das inaktive Postfach angewendet wird. Wenn das Postfach vor über 30 Tagen gelöscht wurde, wird das Postfach nach Aufheben der Deaktivierung für das endgültige Löschen markiert, und das Postfach kann nicht wiederhergestellt werden. Wenn das Postfach in den letzten 30 Tagen gelöscht wurde, können Sie das Postfach nach Aufheben der Archivierung oder Entfernen der Aufbewahrungsrichtlinie wiederherstellen. Eine schrittweise Anleitung zum Entfernen eines Haltestatus oder einer Aufbewahrungsrichtlinie zum endgültigen Löschen eines inaktiven Postfachs finden Sie unter [Löschen eines inaktiven Postfachs](delete-an-inactive-mailbox.md).
