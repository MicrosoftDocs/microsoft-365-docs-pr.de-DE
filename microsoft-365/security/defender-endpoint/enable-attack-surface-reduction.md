---
title: Aktivieren von Regeln zur Reduzierung der Angriffsfläche
description: Aktivieren Sie Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR), um Ihre Geräte vor Angriffen zu schützen, die Makros, Skripts und allgemeine Einspritztechniken verwenden.
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: levinec
ms.author: ellevin
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1deec767c6af777b23ab5a91c9e719f690e0c048
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165141"
---
# <a name="enable-attack-surface-reduction-rules"></a>Aktivieren von Regeln zur Reduzierung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Attack Surface Reduction Rules](attack-surface-reduction.md) (ASR-Regeln) helfen, Aktionen zu verhindern, die von Schadsoftware häufig missbraucht werden, um Geräte und Netzwerke zu gefährdeten. Sie können ASR-Regeln für Geräte mit einer der folgenden Editionen und Versionen von Windows festlegen:
- Windows 10 Pro, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, [Version 1709](https://docs.microsoft.com/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährskanal)](https://docs.microsoft.com/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](https://docs.microsoft.com/windows-server/get-started-19/whats-new-19)

Jede ASR-Regel enthält eine von drei Einstellungen:

- Nicht konfiguriert: Deaktivieren der ASR-Regel
- Block: Aktivieren der ASR-Regel
- Überwachung: Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre

Es wird dringend empfohlen, dass Sie ASR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen zu nutzen, die in [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) (Defender for Endpoint) verfügbar sind. Für andere Lizenzen wie Windows Professional oder E3, die keinen Zugriff auf erweiterte Überwachungs- und Berichtsfunktionen haben, können Sie jedoch eigene Überwachungs- und Berichterstellungstools neben den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignis forwarding).

> [!TIP]
> Weitere Informationen zur Windows-Lizenzierung finden Sie unter [Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) und im Handbuch zur [Volumenlizenzierung für Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

Sie können Regeln zur Reduzierung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:

- [Microsoft Intune](#intune)
- [Mobile Geräteverwaltung (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Gruppenrichtlinie](#group-policy)
- [PowerShell](#powershell)

Die Unternehmensverwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen. Die Unternehmensverwaltung überschreibt beim Start alle in Konflikt enden Gruppenrichtlinien oder PowerShell-Einstellungen.

## <a name="exclude-files-and-folders-from-asr-rules"></a>Ausschließen von Dateien und Ordnern aus ASR-Regeln

Sie können ausschließen, dass Dateien und Ordner von den meisten Regeln zur Reduzierung der Angriffsfläche ausgewertet werden. Dies bedeutet, dass selbst wenn eine ASR-Regel bestimmt, dass die Datei oder der Ordner schädliches Verhalten enthält, die Ausführung der Datei nicht blockiert wird. Dadurch können möglicherweise unsichere Dateien ausgeführt und Ihre Geräte infizieren.

Sie können #A0 auch von der Auslösung basierend auf Zertifikat- und Dateihashes ausschließen, indem Sie bestimmte Defender for Endpoint-Datei- und Zertifikatindikatoren zulassen. (Siehe [Verwalten von Indikatoren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-indicators).)

> [!IMPORTANT]
> Das Ausschließen von Dateien oder Ordnern kann den von den ASR-Regeln bereitgestellten Schutz erheblich verringern. Ausgeschlossene Dateien können ausgeführt werden, und es werden keine Berichte oder Ereignisse aufgezeichnet.
> Wenn ASR-Regeln Dateien erkennen, die Ihrer Meinung nach nicht erkannt werden sollten, sollten Sie zuerst den Überwachungsmodus verwenden, um die [Regel zu testen.](evaluate-attack-surface-reduction.md)


Sie können einzelne Dateien oder Ordner angeben (mithilfe von Ordnerpfaden oder vollqualifizierten Ressourcennamen), Sie können jedoch nicht angeben, für welche Regeln die Ausschlüsse gelten. Ein Ausschluss wird nur angewendet, wenn die ausgeschlossene Anwendung oder der ausgeschlossene Dienst gestartet wird. Wenn Sie beispielsweise einen Ausschluss für einen bereits ausgeführten Updatedienst hinzufügen, löst der Updatedienst weiterhin Ereignisse aus, bis der Dienst beendet und neu gestartet wird.

ASR-Regeln unterstützen Umgebungsvariablen und Platzhalter. Informationen zur Verwendung von Platzhaltern finden Sie unter Verwenden von Platzhaltern in den Listen für Dateinamen und Ordnerpfad oder [Erweiterungsausschluss](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).

Die folgenden Verfahren zum Aktivieren von ASR-Regeln enthalten Anweisungen zum Ausschließen von Dateien und Ordnern.

## <a name="intune"></a>Intune

1. Wählen **Sie Gerätekonfigurationsprofile**  >  **aus.** Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues. Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen aus,** und geben Sie Informationen für dieses Profil ein. Wählen **Sie für Profiltyp** **Endpunktschutz aus.** Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** und dann **Einstellungen aus.**

2. Wählen Sie **im Bereich** Endpunktschutz die option Windows Defender **Exploit Guard** aus, und wählen Sie dann Attack Surface **Reduction aus.** Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.

3. Geben **Sie unter Attack Surface Reduction exceptions** einzelne Dateien und Ordner ein. Sie können auch **Importieren auswählen,** um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von DEN REGELN ausgeschlossen werden sollen. Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Wählen **Sie in** den drei Konfigurationsfenstern OK aus. Wählen Sie dann **Erstellen** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **Speichern,** wenn Sie eine vorhandene Datei bearbeiten.

## <a name="mdm"></a>MDM

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) Configuration Service Provider (CSP), um den Modus für jede Regel einzeln zu aktivieren und festlegen.

Im Folgenden finden Sie ein Referenzbeispiel unter Verwendung von [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

Die Werte, die im Überwachungsmodus aktiviert, deaktiviert oder aktiviert werden sollen, sind:

- Disable = 0
- Block (Aktivieren der ASR-Regel) = 1
- Audit = 2

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.

Beispiel:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Geben Sie unbedingt OMA-URI-Werte ohne Leerzeichen ein.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.

2. Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**

3. Geben Sie einen Namen und eine Beschreibung ein, wählen **Sie Attack Surface Reduction** aus, und wählen Sie Weiter **aus.**

4. Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **Weiter aus.**

5. Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.

6. Nachdem die Richtlinie erstellt wurde, schließen **Sie**.

## <a name="group-policy"></a>Gruppenrichtlinien

> [!WARNING]
> Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle In konflikt enden Gruppenrichtlinieneinstellungen.

1. Öffnen Sie auf dem Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur **auf Windows-Komponenten**  >  **Microsoft Defender Antivirus** Windows Defender Exploit  >  **Guard** Attack Surface  >  **Reduction**.

4. Wählen **Sie Attack surface reduction rules konfigurieren aus,** und wählen Sie Aktiviert **aus.** Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt Optionen festlegen.

   Wählen **Sie Anzeigen...** aus, und geben Sie die Regel-ID in der Spalte **Wertname** und den ausgewählten Status in der **Spalte Wert** wie folgt ein:

   - Disable = 0
   - Block (Aktivieren der ASR-Regel) = 1
   - Audit = 2

   ![Gruppenrichtlinieneinstellung mit einer leeren Regel-ID für die Reduzierung der Angriffsfläche und dem Wert 1](/microsoft-365/security/defender-endpoint/images/asr-rules-gp)

5. Um Dateien und Ordner von ASR-Regeln auszuschließen, wählen Sie die Einstellung Dateien und Pfade von Attack **surface reduction rules** ausschließen aus, und legen Sie die Option auf Aktiviert **.** Wählen **Sie Anzeigen** aus, und geben Sie jede Datei oder jeden Ordner in der Spalte **Wertname** ein. Geben **Sie 0** in die **Spalte Wert** für jedes Element ein.

> [!WARNING]
> Verwenden Sie keine Anführungszeichen, da sie weder für die Spalte **Wertname** noch für die **Spalte Wert unterstützt** werden.

## <a name="powershell"></a>PowerShell

> [!WARNING]
> Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle in Konflikt enden PowerShell-Einstellungen. Um Benutzern das Definieren des Werts mithilfe von PowerShell zu ermöglichen, verwenden Sie die Option "Benutzerdefiniert" für die Regel in der Verwaltungsplattform.

1. Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **Maustaste auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**

2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Enabled
    ```

    Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Überwachungsmodus zu aktivieren:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions AuditMode
    ```

    Verwenden Sie das folgende Cmdlet, um ASR-Regeln zu deaktivieren:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Disabled
    ```

    > [!IMPORTANT]
    > Sie müssen den Status für jede Regel einzeln angeben, aber Sie können Regeln und Zustände in einer durch Kommas getrennten Liste kombinieren.
    >
    > Im folgenden Beispiel werden die ersten beiden Regeln aktiviert, die dritte Regel deaktiviert, und die vierte Regel wird im Überwachungsmodus aktiviert:
    >
    > ```PowerShell
    > Set-MpPreference -AttackSurfaceReductionRules_Ids <rule ID 1>,<rule ID 2>,<rule ID 3>,<rule ID 4> -AttackSurfaceReductionRules_Actions Enabled, Enabled, Disabled, AuditMode
    > ```

    Sie können auch das `Add-MpPreference` PowerShell-Verb verwenden, um der vorhandenen Liste neue Regeln hinzuzufügen.

    > [!WARNING]
    > `Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln. Wenn Sie dem vorhandenen Satz hinzufügen möchten, sollten Sie stattdessen `Add-MpPreference` verwenden.
    > Mithilfe von können Sie eine Liste der Regeln und deren aktuellen Status `Get-MpPreference` abrufen.

3. Verwenden Sie das folgende Cmdlet, um Dateien und Ordner von ASR-Regeln auszuschließen:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionOnlyExclusions "<fully qualified path or resource>"
    ```

    Verwenden Sie `Add-MpPreference -AttackSurfaceReductionOnlyExclusions` weiterhin, um der Liste weitere Dateien und Ordner hinzuzufügen.

    > [!IMPORTANT]
    > Verwenden `Add-MpPreference` Sie zum Anfügen oder Hinzufügen von Apps zur Liste. Wenn Sie `Set-MpPreference` das Cmdlet verwenden, wird die vorhandene Liste überschrieben.

## <a name="related-articles"></a>Verwandte Artikel

- [Reduzieren von Angriffsoberflächen mit Regeln zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)

- [Bewerten der Reduzierung der Angriffsfläche](evaluate-attack-surface-reduction.md)

- [Häufig gestellte Fragen zur Reduzierung der Angriffsfläche](attack-surface-reduction.md)
