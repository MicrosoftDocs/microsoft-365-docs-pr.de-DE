---
title: Aktivieren der unbegrenzten Archivierung – Administratorhilfe
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
ms.assetid: e2a789f2-9962-4960-9fd4-a00aa063559e
description: 'Für Administratoren: Erfahren Sie, wie Sie die Archivierung mit automatischer Erweiterung aktivieren, wodurch Ihren Benutzern unbegrenzter Speicherplatz für ihre Exchange Online-Postfächer zur Verfügung steht. Sie können die Archivierung mit automatischer Erweiterung für die gesamte Organisation oder nur für bestimmte Benutzer aktivieren.'
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 237e3032b21f6fe0d3a97d2ae41c527e500fb2e0
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790083"
---
# <a name="enable-unlimited-archiving---admin-help"></a>Aktivieren der unbegrenzten Archivierung – Administratorhilfe

Mit der Automatisch erweiterten Archivierungsfunktion von Exchange Online können Sie unbegrenzten Speicherplatz für Archivpostfächer aktivieren. Wenn die Archivierung mit automatischer Erweiterung aktiviert ist, wird automatisch zusätzlicher Speicherplatz zum Archivpostfach eines Benutzers hinzugefügt, wenn der Speichergrenzwert erreicht wird. Das Ergebnis ist eine unbegrenzte Postfachspeicherkapazität. Sie können die Archivierung mit automatischer Erweiterung für alle Benutzer in Ihrer Organisation oder nur für bestimmte Benutzer aktivieren. Weitere Informationen zur automatisch erweiterten Archivierung finden Sie unter [Übersicht über die unbegrenzte Archivierung in Office 365.](unlimited-archiving.md)

## <a name="before-you-enable-auto-expanding-archiving"></a>Bevor Sie die Archivierung mit automatischer Erweiterung aktivieren

- Sie müssen ein globaler Administrator in Ihrer Organisation oder Mitglied der Rollengruppe "Organisationsverwaltung" in Ihrer Exchange Online-Organisation sein, um die Archivierung mit automatischer Erweiterung für Ihre gesamte Organisation oder für bestimmte Benutzer zu aktivieren. Alternativ müssen Sie Mitglied einer Rollengruppe sein, der die Rolle "E-Mail-Empfänger" zugewiesen ist, um die automatisch erweiterte Archivierung für bestimmte Benutzer zu aktivieren.

- Das Archivpostfach eines Benutzers muss aktiviert werden, bevor Sie die Archivierung mit automatischer Erweiterung aktivieren können. Einem Benutzer muss eine Exchange Online Plan 2-Lizenz zugewiesen sein, um das Archivpostfach zu aktivieren. Wenn einem Benutzer eine Exchange Online Plan 1-Lizenz zugewiesen ist, müssen Sie ihm eine separate Exchange Online-Archivierung zuweisen, um sein Archivpostfach zu aktivieren. Siehe [Aktivieren von Archivpostfächern im Security & Compliance Center](enable-archive-mailboxes.md).

- Sie können auch PowerShell verwenden, um Archivpostfächer zu aktivieren. Im Abschnitt ["Weitere Informationen"](#more-information) finden Sie ein Beispiel für den PowerShell-Befehl, mit dem Sie Archivpostfächer für alle Benutzer in Ihrer Organisation aktivieren können.

- Die Archivierung mit automatischer Erweiterung unterstützt auch freigegebene Postfächer. Zum Aktivieren des Archivs für ein freigegebenes Postfach ist eine Exchange Online Plan 2- oder eine Exchange Online Plan 1-Lizenz mit Exchange Online-Archivierung erforderlich.

- Sie können das Exchange Admin Center oder das Security & Compliance Center nicht verwenden, um die Archivierung mit automatischer Erweiterung zu aktivieren. Sie müssen Exchange Online PowerShell verwenden. Informationen zum Herstellen einer Verbindung mit Ihrer Exchange Online-Organisation mithilfe der Remote-PowerShell finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell.](https://go.microsoft.com/fwlink/p/?linkid=396554)

## <a name="enable-auto-expanding-archiving-for-your-entire-organization"></a>Aktivieren der automatisch erweiterten Archivierung für die gesamte Organisation

Sie können die Archivierung mit automatischer Erweiterung für die gesamte Organisation aktivieren. Nach dem Aktivieren wird die Archivierung mit automatischer Erweiterung für vorhandene Benutzerpostfächer und neue erstellte Benutzerpostfächer aktiviert. Wenn Sie Benutzerpostfächer erstellen, müssen Sie das Hauptarchivpostfach des Benutzers aktivieren, damit die Automatisch erweiterte Archivierungsfunktion für das neue Benutzerpostfach funktioniert.
  
1. [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die Archivierung mit automatischer Erweiterung für Ihre gesamte Organisation zu aktivieren.

    ```powershell
    Set-OrganizationConfig -AutoExpandingArchive
    ```

## <a name="enable-auto-expanding-archiving-for-specific-users"></a>Aktivieren der automatisch erweiterten Archivierung für bestimmte Benutzer

Anstatt die Archivierung mit automatischer Erweiterung für jeden Benutzer in Ihrer Organisation zu aktivieren, können Sie sie nur für bestimmte Benutzer aktivieren. Dies ist möglicherweise der Grund, dass nur einige Benutzer eine große Archivspeicherkapazität benötigen.
  
Wenn Sie die Archivierung mit automatischer Erweiterung für einen bestimmten Benutzer aktivieren und das Postfach des Benutzers archiviert oder einer Aufbewahrungsrichtlinie zugewiesen ist, werden die folgenden beiden Konfigurationen geändert:
  
- Das Speicherkontingent für das primäre Archivpostfach des Benutzers wird um 10 GB erhöht (von 100 GB auf 110 GB). Das Kontingent für Archivierungswarnungen wird ebenfalls um 10 GB erhöht (von 90 GB auf 100 GB).

- Das Speicherkontingent für den Ordner "Wiederherstellbare Elemente" im primären Postfach des Benutzers wird um 10 GB erhöht (auch von 100 GB auf 110 GB). Das Warnungskontingent für wiederherstellbare Elemente wird ebenfalls um 10 GB erhöht (von 90 GB auf 100 GB). Diese Änderungen gelten nur, wenn das Postfach in der Aufbewahrungszeit ist oder einer Aufbewahrungsrichtlinie zugewiesen ist.

Dieser zusätzliche Speicherplatz wird hinzugefügt, um Speicherprobleme zu verhindern, die vor der Bereitstellung des automatisch erweiterten Archivs auftreten können. Es wird  *kein*  zusätzlicher Speicherplatz hinzugefügt, wenn Sie die Archivierung mit automatischer Erweiterung für die gesamte Organisation aktivieren, wie im vorherigen Abschnitt beschrieben.
  
1. [Herstellen einer Verbindung mit Exchange Online PowerShell](https://go.microsoft.com/fwlink/p/?linkid=396554)

2. Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um die Archivierung mit automatischer Erweiterung für einen bestimmten Benutzer zu aktivieren. Wie zuvor erläutert, muss das Archivpostfach (Hauptarchiv) des Benutzers aktiviert sein, bevor Sie die Archivierung mit automatischer Erweiterung für den Benutzer aktivieren können.

    ```powershell
    Enable-Mailbox <user mailbox> -AutoExpandingArchive
    ```

> [!IMPORTANT]
> In einer Hybridbereitstellung von Exchange können Sie den Befehl **"Enable-Mailbox -AutoExpandingArchive"** nicht verwenden, um die Archivierung mit automatischer Erweiterung für einen bestimmten Benutzer zu aktivieren, dessen primäres Postfach lokal ist und dessen Archivpostfach cloudbasiertes Postfach ist. Zum Aktivieren der automatisch erweiterten Archivierung für cloudbasierte Archivpostfächer in einer Exchange-Hybridbereitstellung müssen Sie den Befehl **"Set-OrganizationConfig -AutoExpandingArchive"** in Exchange Online PowerShell ausführen, um die Archivierung mit automatischer Erweiterung für die gesamte Organisation zu aktivieren. Wenn die primären und Archivpostfächer eines Benutzers cloudbasierte Postfächer sind, können Sie den Befehl **"Enable-Mailbox -AutoExpandingArchive"** verwenden, um die automatisch erweiterte Archivierung für diesen bestimmten Benutzer zu aktivieren.
  
## <a name="verify-that-auto-expanding-archiving-is-enabled"></a>Überprüfen, ob die Archivierung mit automatischer Erweiterung aktiviert ist

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um zu überprüfen, ob die Archivierung mit automatischer Erweiterung für Ihre Organisation aktiviert ist.

```powershell
Get-OrganizationConfig | FL AutoExpandingArchiveEnabled
```

Der Wert gibt an, dass die Archivierung mit  `True` automatischer Erweiterung für die Organisation aktiviert ist. 
  
Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um zu überprüfen, ob die Archivierung mit automatischer Erweiterung für einen bestimmten Benutzer aktiviert ist.
  
```powershell
Get-Mailbox <user mailbox> | FL AutoExpandingArchiveEnabled
```

Der Wert  `True` "Gibt an, dass die Archivierung mit automatischer Erweiterung für den Benutzer aktiviert ist." 
  
Beachten Sie die folgenden Punkte, nachdem Sie die Archivierung mit automatischer Erweiterung aktiviert haben:
  
- Wenn Sie den Befehl **"Set-OrganizationConfig -AutoExpandingArchive"** ausführen, um die Archivierung mit automatischer Erweiterung für Ihre Organisation zu aktivieren, müssen Sie **"Enable-Mailbox -AutoExpandingArchive"** nicht für einzelne Postfächer ausführen. Durch Ausführen des **Cmdlets "Set-OrganizationConfig"** zum Aktivieren der automatisch erweiterten Archivierung für Ihre Organisation wird die Eigenschaft  *"AutoExpandingArchiveEnabled"*  für Benutzerpostfächer nicht in `True` " geändert.

- Ebenso werden die Werte für die Postfacheigenschaften  *"ArchiveQuota"*  und  *"ArchiveWarningQuota"*  nicht geändert, wenn Sie die Archivierung mit automatischer Erweiterung aktivieren. Wenn Sie die Archivierung mit automatischer Erweiterung für ein Benutzerpostfach aktivieren und die Eigenschaft  *"AutoExpandingArchiveEnabled"*  auf "festgelegt" ist, werden die Eigenschaften  `True`  *"ArchiveQuota"*  und  *"ArchiveWarningQuota"*  ignoriert. Im Folgenden finden Sie ein Beispiel für diese Postfacheigenschaften, nachdem die automatisch erweiterte Archivierung für das Postfach eines Benutzers aktiviert wurde. 

    ![Die Eigenschaften "ArchiveQuota" und "ArchiveWarningQuota" werden ignoriert, nachdem Sie die Archivierung mit automatischer Erweiterung aktiviert haben.](../media/6a1c1b69-5c4c-4267-aac8-53577667f03e.png)

## <a name="more-information"></a>Weitere Informationen

- Sie können auch PowerShell verwenden, um Archivpostfächer zu aktivieren. Sie können beispielsweise den folgenden Befehl in Exchange Online PowerShell ausführen, um Archivpostfächer für alle Benutzer zu aktivieren, deren Archivpostfach noch nicht aktiviert ist.

    ```powershell
    Get-Mailbox -Filter {ArchiveStatus -Eq "None" -AND RecipientTypeDetails -eq "UserMailbox"} | Enable-Mailbox -Archive
    ```

- Nachdem Sie die Archivierung mit automatischer Erweiterung für Ihre Organisation oder einen bestimmten Benutzer aktiviert haben, wird ein Archivpostfach in ein automatisch erweitertes Archiv konvertiert, wenn das Archivpostfach (einschließlich des Ordners "Wiederherstellbare Elemente") 90 GB erreicht. Es kann bis zu 30 Tage dauern, bis der zusätzliche Speicherplatz bereitgestellt wird.

- Nachdem Sie die Archivierung mit automatischer Erweiterung aktiviert haben, kann sie nicht deaktiviert werden.

- Die Archivierung mit automatischer Erweiterung wird für cloudbasierte Archivpostfächer in einer Hybridbereitstellung von Exchange für Benutzer unterstützt, die über ein lokales primäres Postfach verfügen. Nachdem die automatisch erweiterte Archivierung für ein cloudbasiertes Archivpostfach aktiviert wurde, können Sie dieses Archivpostfach jedoch nicht wieder an die lokale Exchange-Organisation ausliefern. Die Archivierung mit automatischer Erweiterung wird für lokale Postfächer in jeder Version von Exchange Server.

- Eine Liste der Outlook-Clients, die Benutzer für den Zugriff auf Elemente im zusätzlichen Speicherbereich in ihrem Archivpostfach verwenden können, finden Sie im Abschnitt "Outlook-Anforderungen für den Zugriff auf Elemente in einem automatisch erweiterten Archiv" in [Übersicht](unlimited-archiving.md#outlook-requirements-for-accessing-items-in-an-auto-expanded-archive)über die unbegrenzte Archivierung.

- Wie zuvor erläutert, werden 10 GB zum Speicherkontingent des primären Archivpostfachs des Benutzers (und zum Ordner "Wiederherstellbare Elemente" hinzugefügt, wenn das Postfach archiviert ist), wenn Sie den Befehl **"Enable-Mailbox -AutoExpandingArchive"** ausführen. Dadurch wird zusätzlicher Speicher bereitgestellt, bis der automatisch erweiterte Speicherplatz bereitgestellt wird (was bis zu 30 Tage dauern kann). Dieser zusätzliche Speicherplatz wird nicht hinzugefügt, wenn Sie **"Set-OrganizationConfig -AutoExpandingArchive"** ausführen, um die automatisch erweiterte Archivierung für alle Postfächer in Ihrer Organisation zu aktivieren. Wenn Sie die Archivierung mit automatischer Erweiterung für die gesamte Organisation aktiviert haben, aber die zusätzlichen 10 GB Speicherplatz für einen bestimmten Benutzer hinzufügen müssen, können Sie den Befehl **"Enable-Mailbox -AutoExpandingArchive"** für dieses Postfach ausführen. Es wird eine Fehlermeldung angezeigt, dass die Archivierung mit automatischer Erweiterung bereits aktiviert wurde, aber der zusätzliche Speicherplatz wird dem Postfach hinzugefügt.

- Administratoren können das Speicherkontingent nicht anpassen.

> [!IMPORTANT]
> Die Archivierung mit automatischer Erweiterung wird nur für Postfächer unterstützt, die für einzelne Benutzer oder freigegebene Postfächer mit einer Wachstumsrate von nicht mehr als 1 GB pro Tag verwendet werden. Das Verwenden von Journalen, Transportregeln oder Regeln für die automatische Weiterleitung zum Kopieren von Nachrichten in ein Archivpostfach zum Zweck der Archivierung ist nicht zulässig. Das Archivpostfach eines Benutzers ist nur für diesen Benutzer vorgesehen. Microsoft behält sich das Recht vor, die unbegrenzte Archivierung in Fällen zu verweigern, in denen das Archivpostfach eines Benutzers zum Speichern von Archivdaten für andere Benutzer oder in anderen Fällen unangemessener Verwendung verwendet wird.
