---
title: Anpassen des kontrollierten Ordnerzugriffs
description: Fügen Sie andere Ordner hinzu, die durch kontrollierten Ordnerzugriff geschützt werden sollen, oder erlauben Sie Apps, die Änderungen an wichtigen Dateien fälschlicherweise blockieren.
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner, anpassen, Ordner hinzufügen, App hinzufügen, zulassen, ausführbare Datei hinzufügen
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199909"
---
# <a name="customize-controlled-folder-access"></a>Anpassen des kontrollierten Ordnerzugriffs

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


Der kontrollierte Ordnerzugriff hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen. Der kontrollierte Ordnerzugriff wird auf Windows Server 2019- und Windows 10-Clients unterstützt.

In diesem Artikel wird beschrieben, wie Sie die Funktionen für den kontrollierten Ordnerzugriff anpassen und die folgenden Abschnitte umfassen:

- [Schützen zusätzlicher Ordner](#protect-additional-folders)
- [Hinzufügen von Apps, die auf geschützte Ordner zugreifen dürfen sollten](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen](#allow-signed-executable-files-to-access-protected-folders)
- [Anpassen der Benachrichtigung](#customize-the-notification)

> [!IMPORTANT]
> Der kontrollierte Ordnerzugriff überwacht Apps auf Aktivitäten, die als schädlich erkannt werden. Manchmal werden legitime Apps am Vornehmen von Änderungen an Ihren Dateien blockiert. Wenn sich der kontrollierte Ordnerzugriff auf die Produktivität [](audit-windows-defender.md) Ihrer Organisation auswirken sollte, können Sie die Ausführung dieses Features im Überwachungsmodus in Betracht ziehen, um die Auswirkungen vollständig zu bewerten.

## <a name="protect-additional-folders"></a>Schützen zusätzlicher Ordner

Der kontrollierte Ordnerzugriff gilt für viele Systemordner und Standardspeicherorte, einschließlich Ordner wie **Dokumente,** **Bilder** und **Filme.** Sie können zusätzliche ordner hinzufügen, die geschützt werden sollen, aber Sie können die Standardordner in der Standardliste nicht entfernen.

Das Hinzufügen anderer Ordner zum kontrollierten Ordnerzugriff kann für Fälle hilfreich sein, in denen Sie keine Dateien in den standardmäßigen Windows-Bibliotheken speichern oder den Standardspeicherort Ihrer Bibliotheken geändert haben.

Sie können auch Netzwerkfreigaben und zugeordnete Laufwerke angeben. Umgebungsvariablen und Platzhalter werden unterstützt. Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).

Sie können die Windows-Sicherheits-App, Gruppenrichtlinien, PowerShell-Cmdlets oder Konfigurationsdienstanbieter für die Mobile Geräteverwaltung verwenden, um zusätzliche geschützte Ordner hinzuzufügen und zu entfernen.

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a>Verwenden der Windows Security-App zum Schutz zusätzlicher Ordner

1. Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen oder im Startmenü nach **Sicherheit suchen.**

2. Wählen **Sie Virenschutz & bedrohungsschutz** aus, und scrollen Sie dann zum **Abschnitt Ransomware-Schutz.**

3. Wählen **Sie Ransomware-Schutz verwalten aus,** um den **Bereich Ransomware-Schutz zu** öffnen.

4. Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option **Geschützte Ordner aus.**

5. Wählen **Sie in** der **Eingabeaufforderung für die Benutzerzugriffssteuerung Ja** aus. Der **Bereich Geschützte Ordner** wird angezeigt.

4. Wählen **Sie Geschützten Ordner hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Ordnern.

### <a name="use-group-policy-to-protect-additional-folders"></a>Verwenden von Gruppenrichtlinien zum Schutz zusätzlicher Ordner

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie dann Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.

4. Doppelklicken Sie **auf Konfigurierte geschützte Ordner,** und legen Sie die Option auf **Aktiviert .** Wählen **Sie Anzeigen** aus, und geben Sie die einzelnen Ordner ein.

### <a name="use-powershell-to-protect-additional-folders"></a>Verwenden von PowerShell zum Schutz zusätzlicher Ordner

1. Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**

2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. Wiederholen Sie Schritt 2, bis Sie alle Ordner hinzugefügt haben, die Sie schützen möchten. Hinzugefügte Ordner sind in der Windows-Sicherheits-App sichtbar.

   ![Screenshot eines PowerShell-Fensters mit dem oben eingegebenen Cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste. Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.

### <a name="use-mdm-csps-to-protect-additional-folders"></a>Verwenden von MDM-CSPs zum Schutz zusätzlicher Ordner

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) Configuration Service Provider (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a>Zulassen, dass bestimmte Apps Änderungen an kontrollierten Ordnern vornehmen

Sie können angeben, ob bestimmte Apps immer als sicher gelten und Schreibzugriff auf Dateien in geschützten Ordnern erhalten. Das Zulassen von Apps kann hilfreich sein, wenn eine bestimmte App, die Sie kennen und der Sie vertrauen, durch das Feature für den kontrollierten Ordnerzugriff blockiert wird.

> [!IMPORTANT]
> Standardmäßig fügt Windows Apps hinzu, die als benutzerfreundlich für die liste zulässig gelten. Solche Apps, die automatisch hinzugefügt werden, werden nicht in der Liste aufgezeichnet, die in der Windows Security-App oder mithilfe der zugeordneten PowerShell-Cmdlets angezeigt wird. Sie sollten die meisten Apps nicht hinzufügen. Fügen Sie apps nur hinzu, wenn sie blockiert werden, und Sie können ihre Vertrauenswürdigkeit überprüfen.

Wenn Sie eine App hinzufügen, müssen Sie den Speicherort der App angeben. Nur die App an diesem Speicherort darf auf die geschützten Ordner zugreifen. Wenn sich die App (mit demselben Namen) an einem anderen Speicherort befindet, wird sie nicht zur Liste der zulässigen Apps hinzugefügt und kann durch kontrollierten Ordnerzugriff blockiert werden.

Eine zulässige Anwendung oder ein zulässiger Dienst hat nur nach dem Start Schreibzugriff auf einen kontrollierten Ordner. Ein Updatedienst löst beispielsweise weiterhin Ereignisse aus, nachdem er zugelassen ist, bis er beendet und neu gestartet wird.

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a>Verwenden der Windows Defender-Sicherheits-App zum Zulassen bestimmter Apps

1. Öffnen Sie die Windows Security-App, indem Sie im Startmenü nach **Sicherheit suchen.**

2. Wählen Sie die Kachel **& Bedrohungsschutz** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz verwalten aus.**

3. Wählen Sie **im Abschnitt Kontrollierter Ordnerzugriff** die Option App über kontrollierten **Ordnerzugriff zulassen aus.**

4. Wählen **Sie Zugelassene App hinzufügen aus,** und folgen Sie den Aufforderungen zum Hinzufügen von Apps.

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Hinzufügen einer zugelassenen App-Schaltfläche":::

### <a name="use-group-policy-to-allow-specific-apps"></a>Verwenden von Gruppenrichtlinien zum Zulassen bestimmter Apps

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard**  >  **Kontrollierter Ordnerzugriff**.

4. Doppelklicken Sie auf die Einstellung **Zugelassene Anwendungen konfigurieren,** und legen Sie die Option auf **Aktiviert .** Wählen **Sie Anzeigen** aus, und geben Sie jede App ein.

### <a name="use-powershell-to-allow-specific-apps"></a>Verwenden von PowerShell zum Zulassen bestimmter Apps

1. Geben **Sie PowerShell** im Menü Start ein, klicken Sie mit der rechten Maustaste **auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    Wenn Sie beispielsweise die  ausführbare Dateitest.exeim Ordner *C:\apps* hinzufügen möchten, würde das Cmdlet wie folgt aussehen:

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   Verwenden Sie `Add-MpPreference -ControlledFolderAccessAllowedApplications` weiterhin, um der Liste weitere Apps hinzuzufügen. Apps, die mit diesem Cmdlet hinzugefügt wurden, werden in der Windows Security-App angezeigt.

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="PowerShell-Cmdlet zum Zulassen einer App":::

> [!IMPORTANT]
> Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste. Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.

### <a name="use-mdm-csps-to-allow-specific-apps"></a>Verwenden von MDM-CSPs zum Zulassen bestimmter Apps

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) Configuration Service Provider (CSP), damit Apps Änderungen an geschützten Ordnern vornehmen können.

## <a name="allow-signed-executable-files-to-access-protected-folders"></a>Zugriff auf geschützte Ordner durch signierte ausführbare Dateien zulassen

Microsoft Defender for Endpoint-Zertifikat- und Dateiindikatoren können signierten ausführbaren Dateien den Zugriff auf geschützte Ordner ermöglichen. Implementierungsdetails finden Sie unter [Erstellen von Indikatoren basierend auf Zertifikaten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).

> [!Note]
> Dies gilt nicht für Skriptmodule, einschließlich Powershell.

## <a name="customize-the-notification"></a>Anpassen der Benachrichtigung

Weitere Informationen zum Anpassen der Benachrichtigung, wenn eine Regel ausgelöst wird, und zum Sperren einer App oder Datei finden Sie unter [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).

## <a name="see-also"></a>Siehe auch

- [Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff](controlled-folders.md)
- [Aktivieren des kontrollierten Ordnerzugriffs](enable-controlled-folders.md)
- [Bewerten von Regeln zur Reduzierung der Angriffsfläche](evaluate-attack-surface-reduction.md)
