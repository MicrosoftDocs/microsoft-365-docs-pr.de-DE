---
title: Unbegrenzte Archivierung aktivieren – Administratorhilfe
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/29/2018
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Für Administratoren: Informationen zum Aktivieren der automatisch wachsenden Archivierung, die Ihren Benutzern unbegrenzten Speicherplatz für Ihre Exchange Online Postfächer bietet. Sie können die automatisch expandierende Archivierung für Ihre gesamte Organisation oder nur für bestimmte Benutzer aktivieren.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8d550e562e8226d586a9538f9f366e3283ad0437
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817824"
---
# <a name="enable-unlimited-archiving--admin-help"></a>Unbegrenzte Archivierung aktivieren – Administratorhilfe

Sie können die Exchange Online automatisch expandierende Archivierungsfunktion verwenden, um unbegrenzten Speicherplatz für Archivpostfächer zu aktivieren. Wenn die automatisch expandierende Archivierung aktiviert ist, wird dem Archivpostfach eines Benutzers automatisch zusätzlicher Speicherplatz hinzugefügt, wenn er sich dem Speichergrenzwert nähert. Das Ergebnis ist eine unbegrenzte Speicherkapazität für Postfächer. Sie können die automatisch expandierende Archivierung für jeden in Ihrer Organisation oder nur für bestimmte Benutzer aktivieren. Weitere Informationen zur automatischen Erweiterung der Archivierung finden Sie unter [Overview of Unlimited Archiving in Office 365](unlimited-archiving.md).

## <a name="before-you-enable-auto-expanding-archiving"></a>Vor dem Aktivieren der automatisch wachsenden Archivierung

- Sie müssen ein globaler Administrator in Ihrer Organisation oder ein Mitglied der Rollengruppe Organisationsverwaltung in Ihrer Exchange Online Organisation sein, um die automatische Erweiterung der Archivierung für Ihre gesamte Organisation oder für bestimmte Benutzer zu aktivieren. Alternativ müssen Sie Mitglied einer Rollengruppe sein, der die Rolle "e-Mail-Empfänger" zugewiesen ist, um die automatisch erweiterte Archivierung für bestimmte Benutzer zu aktivieren.
    
- Das Archivpostfach eines Benutzers muss aktiviert sein, damit die automatisch erweiterte Archivierung aktiviert werden kann. Einem Benutzer muss eine Exchange Online Plan 2-Lizenz zugewiesen sein, um das Archivpostfach zu aktivieren. Wenn einem Benutzer eine Exchange Online Plan 1-Lizenz zugewiesen ist, müssen Sie ihm eine separate Exchange Online Archivierungslizenz zuweisen, um das Archivpostfach zu aktivieren. Weitere Informationen finden Sie unter [Aktivieren von archivpostfächern im Security & Compliance Center](enable-archive-mailboxes.md).
    
- Sie können auch PowerShell zum Aktivieren von archivpostfächern verwenden. Im Abschnitt [Weitere Informationen](#more-information) finden Sie ein Beispiel für den PowerShell-Befehl, mit dem Sie Archivpostfächer für alle Benutzer in Ihrer Organisation aktivieren können. 
    
- Die Archivierung mit automatischer Erweiterung unterstützt auch freigegebene Postfächer. Um das Archiv für ein freigegebenes Postfach zu aktivieren, ist eine Exchange Online Plan 2-Lizenz oder eine Exchange Onlineplan 1-Lizenz mit einer Exchange Online-Archivierungslizenz erforderlich.
    
- Sie können das Exchange-Verwaltungskonsole oder das Security & Compliance Center nicht zum Aktivieren der automatisch wachsenden Archivierung verwenden. Sie müssen Exchange Online PowerShell verwenden. Informationen zum Herstellen einer Verbindung mit Ihrer Exchange Online Organisation mithilfe von Remote-PowerShell finden Sie unter [Connect to Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
  
## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Aktivieren der automatisch wachsenden Archivierung für Ihre gesamte Organisation

Sie können die automatisch expandierende Archivierung für Ihre gesamte Organisation aktivieren. Nachdem Sie es aktiviert haben, wird die automatisch expandierende Archivierung für vorhandene Benutzerpostfächer und für neue Benutzerpostfächer, die erstellt werden, aktiviert. Achten Sie beim Erstellen von Benutzerpostfächern darauf, das Hauptarchiv Postfach des Benutzers zu aktivieren, damit die automatisch expandierende Archivierungsfunktion für das neue Benutzerpostfach funktioniert.
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
2. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die automatisch erweiterte Archivierung für Ihre gesamte Organisation zu aktivieren.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Aktivieren der automatisch wachsenden Archivierung für bestimmte Benutzer

Anstatt die automatische Erweiterung der Archivierung für jeden Benutzer in Ihrer Organisation zu aktivieren, können Sie ihn nur für bestimmte Benutzer aktivieren. Dies ist möglicherweise der Grund, weshalb nur einige Benutzer eine große Speicherkapazität für Archive benötigen.
  
Wenn Sie die automatisch expandierende Archivierung für einen bestimmten Benutzer aktivieren und das Postfach des Benutzers in on Hold oder einer Aufbewahrungsrichtlinie zugewiesen ist, werden die folgenden zwei Konfigurationsänderungen vorgenommen:
  
- Das Speicherkontingent für das primäre Archivpostfach des Benutzers wird um 10 GB (von 100 GB auf 110 GB) erhöht. Das Kontingent für die Archiv Warnung wird ebenfalls um 10 GB (von 90 GB auf 100 GB) erhöht.
    
- Das Speicherkontingent für den Ordner "refundable Items" im primären Postfach des Benutzers wird um 10 GB (auch von 100 GB auf 110 GB) erhöht. Das Warn Kontingent für das Wiederherstellungselement wird ebenfalls um 10 GB (von 90 GB auf 100 GB) erhöht. Diese Änderungen gelten nur, wenn das Postfach in on gespeichert oder einer Aufbewahrungsrichtlinie zugewiesen ist.
    
Dieser zusätzliche Speicherplatz wurde hinzugefügt, um Speicherprobleme zu vermeiden, die auftreten können, bevor das automatisch expandierende Archiv bereitgestellt wird. Zusätzlicher Speicherplatz *wird nicht* hinzugefügt, wenn Sie die automatisch expandierende Archivierung für Ihre gesamte Organisation aktivieren, wie im vorherigen Abschnitt beschrieben. 
  
1. [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554).
    
2. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die automatisch erweiterte Archivierung für einen bestimmten Benutzer zu aktivieren. Wie bereits erläutert, muss das Archivpostfach des Benutzers (das Hauptarchiv) aktiviert sein, damit Sie die automatisch expandierende Archivierung für diesen Benutzer aktivieren können.
    
    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```


> [!IMPORTANT]
> In einer Exchange-hybridbereitstellung können Sie den Befehl **Enable-Mailbox-AutoExpandingArchive** nicht verwenden, um die automatisch expandierende Archivierung für einen bestimmten Benutzer zu aktivieren, dessen primäres Postfach lokal ist und das Archivpostfach auf Cloud-Basis basiert. Zum Aktivieren der automatisch wachsenden Archivierung für Cloud-basierte Archivpostfächer in einer Exchange-hybridbereitstellung müssen Sie den Befehl " **OrganizationConfig-AutoExpandingArchive** " in Exchange Online PowerShell ausführen, um die automatisch erweiterte Archivierung für die gesamte Organisation zu aktivieren. Wenn die primären und Archivpostfächer eines Benutzers Cloud-basiert sind, können Sie den Befehl **Enable-Mailbox-AutoExpandingArchive** verwenden, um die automatisch expandierende Archivierung für diesen bestimmten Benutzer zu aktivieren. 
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Überprüfen, ob die automatisch expandierende Archivierung aktiviert ist

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um zu überprüfen, ob die automatisch expandierende Archivierung für Ihre Organisation aktiviert ist.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Ein Wert von `True` gibt an, dass die automatisch expandierende Archivierung für die Organisation aktiviert ist. 
  
Um zu überprüfen, ob die automatisch expandierende Archivierung für einen bestimmten Benutzer aktiviert ist, führen Sie den folgenden Befehl in Exchange Online PowerShell aus.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Ein Wert von `True` gibt an, dass die automatisch expandierende Archivierung für den Benutzer aktiviert ist. 
  
Beachten Sie nach Aktivierung der automatisch expandierenden Archivierung Folgendes:
  
- Wenn Sie den Befehl " **OrganizationConfig-AutoExpandingArchive** " ausführen, um die automatisch expandierende Archivierung für Ihre Organisation zu aktivieren, müssen Sie das **Enable-Mailbox-AutoExpandingArchive-** Steuergerät nicht für einzelne Postfächer ausführen. Wenn Sie das Cmdlet " **OrganizationConfig** " ausführen, um die automatisch expandierende Archivierung für Ihre Organisation zu aktivieren, ändert sich die *AutoExpandingArchiveEnabled* -Eigenschaft für Benutzerpostfächer nicht in `True` .
    
- Dementsprechend werden die Werte für die Postfacheigenschaften *ArchiveQuota* und *para ArchiveWarningQuota* nicht geändert, wenn Sie die automatisch expandierende Archivierung aktivieren. Wenn Sie die automatisch expandierende Archivierung für ein Benutzerpostfach aktivieren und die *AutoExpandingArchiveEnabled* -Eigenschaft auf festgelegt ist `True` , werden die Eigenschaften *ArchiveQuota* und *para ArchiveWarningQuota* ignoriert. Im folgenden finden Sie ein Beispiel für diese Postfacheigenschaften, nachdem die automatisch erweiterte Archivierung für das Postfach eines Benutzers aktiviert wurde. 
    
    ![ArchiveQuota-und para ArchiveWarningQuota-Eigenschaften werden ignoriert, nachdem Sie die automatisch erweiterte Archivierung aktiviert haben.](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

  
## <a name="more-information"></a>Weitere Informationen

- Sie können auch PowerShell zum Aktivieren von archivpostfächern verwenden. Sie können beispielsweise den folgenden Befehl in Exchange Online PowerShell ausführen, um Archivpostfächer für alle Benutzer zu aktivieren, deren Archivpostfach noch nicht aktiviert ist.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Nachdem Sie die automatisch expandierende Archivierung für Ihre Organisation oder für einen bestimmten Benutzer aktiviert haben, wird ein Archivpostfach in ein automatisch expandierendes Archiv konvertiert, wenn das Archivpostfach (einschließlich des Ordners "Wiederherstellbare Elemente") 90 GB erreicht. Es kann bis zu 30 Tage dauern, bis der zusätzliche Speicherplatz zur Verfügung gestellt wird.
    
- Nachdem Sie die automatisch expandierende Archivierung aktiviert haben, kann Sie nicht deaktiviert werden.
    
- Die automatisch expandierende Archivierung wird für Cloud-basierte Archivpostfächer in einer Exchange-hybridbereitstellung für Benutzer unterstützt, die über ein lokales primäres Postfach verfügen. Nachdem die automatische Erweiterung der Archivierung für ein cloudbasierten Archivpostfach aktiviert wurde, können Sie dieses Archivpostfach jedoch nicht mehr an die lokale Exchange-Organisation zurück an Bord nehmen. Die automatisch expandierende Archivierung wird in Exchange Server 2010 nicht für lokale Postfächer unterstützt.
    
- Eine Liste der Outlook-Clients, die Benutzer für den Zugriff auf Elemente im zusätzlichen Speicherbereich in Ihrem Archivpostfach verwenden können, finden Sie im Abschnitt "Outlook-Anforderungen für den Zugriff auf Elemente in einem automatisch erweiterten Archiv" in [Overview of Unlimited](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)Archiving.
    
- Wie bereits erläutert, wird dem Speicherkontingent des primären Archivpostfachs des Benutzers 10 GB hinzugefügt (und dem Ordner "refundable Items", wenn das Postfach in der Warteschleife steht), wenn Sie den Befehl **Enable-Mailbox-AutoExpandingArchive** ausführen. Dadurch wird ein zusätzlicher Speicherplatz bereitgestellt, bis der automatisch erweiterte Speicherplatz (der bis zu 30 Tage dauern kann) bereitgestellt wird. Dieser zusätzliche Speicherplatz wird nicht hinzugefügt, wenn Sie das **Paket-OrganizationConfig-AutoExpandingArchive** ausführen, um die automatisch expandierende Archivierung für alle Postfächer in Ihrer Organisation zu aktivieren. Wenn Sie die automatische Erweiterung der Archivierung für die gesamte Organisation aktiviert haben, jedoch zusätzliche 10 GB Speicherplatz für einen bestimmten Benutzer hinzufügen müssen, können Sie den Befehl **Enable-Mailbox-AutoExpandingArchive** für dieses Postfach ausführen. Es wird eine Fehlermeldung angezeigt, die besagt, dass die automatisch expandierende Archivierung bereits aktiviert wurde, der zusätzliche Speicherplatz wird jedoch dem Postfach hinzugefügt. 

- Administratoren können das Speicherkontingent nicht anpassen.

> [!IMPORTANT]
> Die automatisch expandierende Archivierung wird nur für Postfächer unterstützt, die für einzelne Benutzer oder freigegebene Postfächer mit einer Wachstumsrate von nicht mehr als 1 GB pro Tag verwendet werden. Das Verwenden von Journaling, Transportregeln oder Regeln für die automatische Weiterleitung zum Kopieren von Nachrichten in ein Archivpostfach ist für Archivierungszwecke nicht zulässig. Das Archivpostfach eines Benutzers ist nur für diesen Benutzer vorgesehen. Microsoft behält sich das Recht vor, eine unbegrenzte Archivierung in Fällen zu verweigern, in denen das Archivpostfach eines Benutzers zum Speichern von Archivdaten für andere Benutzer oder in anderen Fällen ungeeigneter Verwendung verwendet wird.
