---
title: Aktivieren der Regeln zur Verringerung der Angriffsfläche
description: Aktivieren Sie Regeln zur Reduzierung der Angriffsfläche (Attack Surface Reduction, ASR), um Ihre Geräte vor Angriffen zu schützen, die Makros, Skripts und allgemeine Einspritztechniken verwenden.
keywords: Attack surface reduction, hips, host intrusion prevention system, protection rules, anti-exploit, antiexploit, exploit, infection prevention, enable, turn on
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: oogunrinde
manager: dansimp
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: b3460e2c9b6073c518bea46147be69d4b89cd96a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538639"
---
# <a name="enable-attack-surface-reduction-rules"></a>Aktivieren der Regeln zur Verringerung der Angriffsfläche

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Attack Surface Reduction Rules](attack-surface-reduction.md) (ASR-Regeln) helfen, Aktionen zu verhindern, die von Schadsoftware häufig missbraucht werden, um Geräte und Netzwerke zu gefährdeten.

**Anforderungen** Sie können Regeln zur Reduzierung der Angriffsfläche für Geräte festlegen, auf der eine der folgenden Editionen und Versionen von Windows:

- Windows 10 Pro, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows 10 Enterprise, Version [1709](/windows/whats-new/whats-new-windows-10-version-1709) oder höher
- Windows Server, [Version 1803 (Halbjährskanal)](/windows-server/get-started/whats-new-in-windows-server-1803) oder höher
- [Windows Server 2019](/windows-server/get-started-19/whats-new-19)

Obwohl Regeln zur Reduzierung der Angriffsfläche keine Windows [E5-Lizenz](/windows/deployment/deploy-enterprise-licenses)erfordern, erhalten Sie bei Windows E5 erweiterte Verwaltungsfunktionen. Diese Funktionen, die nur in Windows E5 verfügbar sind, umfassen Überwachung, Analysen und Workflows, die in [Defender for Endpoint](/microsoft-365/security/defender-endpoint/microsoft-defender-endpoint?view=o365-worldwide&preserve-view=true)verfügbar sind, sowie Berichterstellungs- und Konfigurationsfunktionen im Microsoft 365 Security [Center](/microsoft-365/security/defender/overview-security-center?view=o365-worldwide&preserve-view=true). Diese erweiterten Funktionen sind nicht mit einer Windows Professional oder Windows E3-Lizenz verfügbar. Wenn Sie jedoch über diese Lizenzen verfügen, können Sie die Ereignisanzeige verwenden und Microsoft Defender Antivirus protokollieren, um Die Regelereignisse der Angriffsfläche zu überprüfen.

Jede ASR-Regel enthält eine von vier Einstellungen:

- **Nicht konfiguriert:** Deaktivieren der ASR-Regel
- **Block**: Aktivieren der ASR-Regel
- **Überwachung**: Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre
- **Warn**: Aktivieren Sie die ASR-Regel, lassen Sie den Endbenutzer jedoch das Umgehen des Blocks zu.

> [!IMPORTANT]
> Derzeit wird der Warnmodus für drei ASR-Regeln nicht unterstützt, wenn Sie asr rules in Microsoft Endpoint Manager (MEM) konfigurieren. Weitere Informationen finden Sie unter [Fälle, in denen der Warnmodus nicht unterstützt wird.](attack-surface-reduction.md#cases-where-warn-mode-is-not-supported)

Es wird dringend empfohlen, asR-Regeln mit einer Windows E5-Lizenz (oder einer ähnlichen Lizenzierungs-SKU) zu verwenden, um die erweiterten Überwachungs- und Berichtsfunktionen zu nutzen, die in Microsoft Defender for Endpoint (Defender for [Endpoint)](https://docs.microsoft.com/windows/security/threat-protection) verfügbar sind. Für andere Lizenzen wie Windows Professional oder E3, die keinen Zugriff auf erweiterte Überwachungs- und Berichtsfunktionen haben, können Sie jedoch eigene Überwachungs- und Berichterstellungstools neben den Ereignissen entwickeln, die an jedem Endpunkt generiert werden, wenn ASR-Regeln ausgelöst werden (z. B. Ereignis forwarding).

> [!TIP]
> Weitere Informationen zur lizenzierung Windows finden Sie [unter Windows 10 Licensing](https://www.microsoft.com/licensing/product-licensing/windows10?activetab=windows10-pivot:primaryr5) and get the Volume Licensing guide for [Windows 10](https://download.microsoft.com/download/2/D/1/2D14FE17-66C2-4D4C-AF73-E122930B60F6/Windows-10-Volume-Licensing-Guide.pdf).

Sie können Regeln zur Reduzierung der Angriffsfläche mithilfe einer der folgenden Methoden aktivieren:

- [Microsoft Intune](#intune)
- [Mobile Geräteverwaltung (MDM)](#mdm)
- [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
- [Gruppenrichtlinie](#group-policy)
- [PowerShell](#powershell)

Enterprise verwaltung wie Intune oder Microsoft Endpoint Manager wird empfohlen. Enterprise Verwaltung auf Ebene überschreibt alle in Konflikt enden Gruppenrichtlinien oder PowerShell-Einstellungen beim Start.

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

1. Wählen **Sie Gerätekonfigurationsprofile**  >  **aus.** Wählen Sie ein vorhandenes Endpunktschutzprofil aus, oder erstellen Sie ein neues. Um ein neues Profil zu erstellen, wählen Sie **Profil erstellen aus,** und geben Sie Informationen für dieses Profil ein. Wählen **Sie für Profiltyp** **Endpunktschutz aus.** Wenn Sie ein vorhandenes Profil ausgewählt haben, wählen Sie **Eigenschaften** aus, und wählen Sie **dann Einstellungen**.

2. Wählen Sie **im Bereich** Endpunktschutz die option Windows Defender **Exploit Guard** aus, und wählen Sie dann Attack Surface **Reduction aus.** Wählen Sie die gewünschte Einstellung für jede ASR-Regel aus.

3. Geben **Sie unter Attack Surface Reduction exceptions** einzelne Dateien und Ordner ein. Sie können auch **Importieren auswählen,** um eine CSV-Datei zu importieren, die Dateien und Ordner enthält, die von DEN REGELN ausgeschlossen werden sollen. Jede Zeile in der CSV-Datei sollte wie folgt formatiert werden:

   `C:\folder`, `%ProgramFiles%\folder\file`, `C:\path`

4. Wählen **Sie in** den drei Konfigurationsfenstern OK aus. Wählen Sie dann **Erstellen** aus, wenn Sie eine neue Endpunktschutzdatei erstellen, oder **Speichern,** wenn Sie eine vorhandene Datei bearbeiten.

## <a name="mem"></a>MEM

Sie können den Microsoft Endpoint Manager (MEM) OMA-URI verwenden, um benutzerdefinierte ASR-Regeln zu konfigurieren. Im folgenden Verfahren wird die Regel Missbrauch von ausgebeuteten [gefährdeten signierten](attack-surface-reduction.md#block-abuse-of-exploited-vulnerable-signed-drivers) Treibern blockieren verwendet.

1. Öffnen Sie Microsoft Endpoint Manager (MEM) Admin Center. Klicken Sie **im Menü Start** auf **Geräte,** wählen Sie **Konfigurationsprofil** aus, und klicken Sie dann auf **Profil erstellen.**

   > [!div class="mx-imgBorder"]
   > ![MEM-Profil erstellen](images/mem01-create-profile.png)

2. Wählen **Sie in Erstellen eines** Profils in den folgenden beiden Dropdownlisten Folgendes aus:

   - Wählen **Sie unter Plattform** Windows 10 und höher **aus.**
   - Wählen **Sie im Profiltyp** Vorlagen **aus.**

   Wählen **Sie Benutzerdefinierte**, und klicken Sie dann auf **Erstellen**.

   > [!div class="mx-imgBorder"]
   > ![Attribute des MEM-Regelprofils](images/mem02-profile-attributes.png)

3. Das Benutzerdefinierte Vorlagentool wird zu Schritt **1 Grundlagen geöffnet.** Geben **Sie in 1 Grundlagen** unter **Name** einen Namen für Ihre Vorlage ein, und in **Beschreibung** können Sie eine Beschreibung eingeben (optional).

   > [!div class="mx-imgBorder"]
   > ![GRUNDLEGENDE ATTRIBUTE von MEM](images/mem03-1-basics.png)

4. Klicken Sie auf **Weiter**. Schritt **2 Konfigurationseinstellungen** werden geöffnet. Klicken Sie für OMA-URI-Einstellungen auf **Hinzufügen**. Es werden nun zwei Optionen angezeigt: **Hinzufügen** und **Exportieren**.

   > [!div class="mx-imgBorder"]
   > ![Einstellungen für die MEM-Konfiguration](images/mem04-2-configuration-settings.png)

5. Klicken Sie **erneut auf** Hinzufügen. Die **Add Row OMA-URI-Einstellungen** geöffnet. Gehen **Sie unter Zeile** hinzufügen wie folgt vor:

   - Geben **Sie unter Name** einen Namen für die Regel ein.
   - Geben **Sie unter Beschreibung** eine kurze Beschreibung ein.
   - Geben **Sie in OMA-URI** den spezifischen OMA-URI-Link für die Regel ein, die Sie hinzufügen.
   - Wählen **Sie unter Datentyp** die Option Zeichenfolge **aus.**
   - Geben **Sie in Wert** den GUID-Wert, das Zeichen und den Statuswert ohne Leerzeichen ein ( \= _GUID=StateValue_). Where: {0 : Disable (Disable the ASR rule)}, {1 : Block (Enable the ASR rule)}, {2 : Audit (Evaluate how the ASR rule would impact your organization if enabled)}, {6 : Warn (Enable the ASR rule but allow the end-user to bypass the block)}

   > [!div class="mx-imgBorder"]
   > ![MEM OMA-URI-Konfiguration](images/mem05-add-row-oma-uri.png)

6. Klicken Sie auf **Speichern**. **Zeile hinzufügen** wird geschlossen. Klicken **Sie in Custom** auf **Weiter**. In Schritt **3 Bereichstags** sind Bereichstags optional. Führen Sie einen der folgenden Schritte aus:

   - Klicken **Sie auf Bereichstags auswählen,** wählen Sie das Bereichstag (optional) aus, und klicken Sie dann auf **Weiter**.
   - Oder klicken Sie auf **Weiter**

7. Wählen Sie in Schritt **4 Zuordnungen** unter Eingeschlossene **Gruppen** – für die Gruppen, die diese Regel anwenden soll – aus den folgenden Optionen aus:

   - **Hinzufügen von Gruppen**
   - **Hinzufügen aller Benutzer**
   - **Hinzufügen aller Geräte**

   > [!div class="mx-imgBorder"]
   > ![MEM-Zuordnungen](images/mem06-4-assignments.png)

8. Wählen **Sie unter** Ausgeschlossene Gruppen alle Gruppen aus, die Sie aus dieser Regel ausschließen möchten, und klicken Sie dann auf **Weiter**.

9. Gehen Sie in Schritt **5 Anwendbarkeitsregeln** für die folgenden Einstellungen wie folgt vor:

   - Wählen **Sie in Regel** entweder Profil **zuweisen, wenn**, oder Profil nicht zuweisen **aus, wenn**
   - Wählen **Sie in Property** die Eigenschaft aus, auf die diese Regel angewendet werden soll.
   - Geben **Sie unter Wert** den entsprechenden Wert oder Wertbereich ein.

   > [!div class="mx-imgBorder"]
   > ![MEM-Anwendbarkeitsregeln](images/mem07-5-applicability-rules.png)

10. Klicken Sie auf **Weiter**. Überprüfen Sie in Schritt **6 Überprüfen + Erstellen** die von Ihnen ausgewählten und eingegebenen Einstellungen und Informationen, und klicken Sie dann auf **Erstellen**.

    > [!div class="mx-imgBorder"]
    > ![MEM Überprüfen und Erstellen](images/mem08-6-review-create.png)

    > [!NOTE]
    > Regeln sind aktiv und innerhalb von Minuten live.

>[!NOTE]
> Konfliktbehandlung:
> 
> Wenn Sie einem Gerät zwei unterschiedliche AsR-Richtlinien zuweisen, werden Konflikte in Regeln behandelt, denen unterschiedliche Zustände zugewiesen sind, es gibt keine Konfliktverwaltung, und das Ergebnis ist ein Fehler.
> 
> Nicht in Konflikt stehende Regeln führen nicht zu einem Fehler, und die Regel wird ordnungsgemäß angewendet. Das Ergebnis ist, dass die erste Regel angewendet wird, und nachfolgende regeln, die keine Konflikte haben, werden mit der Richtlinie zusammengeführt.

## <a name="mdm"></a>MDM

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductionrules) Configuration Service Provider (CSP), um den Modus für jede Regel einzeln zu aktivieren und festlegen.

Im Folgenden finden Sie ein Referenzbeispiel unter Verwendung von [GUID-Werten für ASR-Regeln.](attack-surface-reduction.md#attack-surface-reduction-rules)

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionRules`

`Value: 75668C1F-73B5-4CF0-BB93-3ECF5CB7CC84=2|3B576869-A4EC-4529-8536-B80A7769E899=1|D4F940AB-401B-4EfC-AADC-AD5F3C50688A=2|D3E037E1-3EB8-44C8-A917-57927947596D=1|5BEB7EFE-FD9A-4556-801D-275E5FFC04CC=0|BE9BA2D9-53EA-4CDC-84E5-9B1EEEE46550=1`

Die Werte zum Aktivieren (Blockieren), Deaktivieren, Warnen oder Aktivieren im Überwachungsmodus sind:

- 0 : Disable (Disable the ASR rule)
- 1 : Block (Aktivieren der ASR-Regel)
- 2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)
- 6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen). Der Warnmodus ist jetzt für die meisten ASR-Regeln verfügbar.

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-attacksurfacereductiononlyexclusions) Configuration Service Provider (CSP), um Ausschlüsse hinzuzufügen.

Beispiel:

`OMA-URI path: ./Vendor/MSFT/Policy/Config/Defender/AttackSurfaceReductionOnlyExclusions`

`Value: c:\path|e:\path|c:\Exclusions.exe`

> [!NOTE]
> Geben Sie unbedingt OMA-URI-Werte ohne Leerzeichen ein.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Wechseln Microsoft Endpoint Configuration Manager zu Assets **and Compliance**  >  **Endpoint Protection**  >  **Windows Defender Exploit Guard**.

2. Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**

3. Geben Sie einen Namen und eine Beschreibung ein, wählen **Sie Attack Surface Reduction** aus, und wählen Sie Weiter **aus.**

4. Wählen Sie aus, welche Regeln Aktionen blockieren oder überwachen sollen, und wählen Sie **Weiter aus.**

5. Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.

6. Nachdem die Richtlinie erstellt wurde, schließen **Sie**.

## <a name="group-policy"></a>Gruppenrichtlinien

> [!WARNING]
> Wenn Sie Ihre Computer und Geräte mit Intune, Configuration Manager oder einer anderen Verwaltungsplattform auf Unternehmensebene verwalten, überschreibt die Verwaltungssoftware beim Start alle In konflikt enden Gruppenrichtlinieneinstellungen.

1. Öffnen Sie auf dem Computer, der Ihre Gruppenrichtlinie verwaltet, die [Gruppenrichtlinien-Verwaltungskonsole](https://technet.microsoft.com/library/cc731212.aspx), klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die **Struktur, Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Microsoft Defender Exploit Guard**  >  **Attack surface reduction .**

4. Wählen **Sie Attack surface reduction rules konfigurieren aus,** und wählen Sie Aktiviert **aus.** Anschließend können Sie den einzelnen Status für jede Regel im Abschnitt Optionen festlegen.

   Wählen **Sie Anzeigen...** aus, und geben Sie die Regel-ID in der Spalte **Wertname** und den ausgewählten Status in der **Spalte Wert** wie folgt ein:

   - 0 : Disable (Disable the ASR rule)
   - 1 : Block (Aktivieren der ASR-Regel)
   - 2 : Überwachung (Bewerten, wie sich die ASR-Regel auf Ihre Organisation auswirken würde, wenn sie aktiviert wäre)
   - 6 : Warnen (Aktivieren Sie die ASR-Regel, aber erlauben Sie dem Endbenutzer, den Block zu umgehen)

   :::image type="content" source="images/asr-rules-gp.png" alt-text="ASR-Regeln in Gruppenrichtlinien":::

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

    Verwenden Sie das folgende Cmdlet, um ASR-Regeln im Warnmodus zu aktivieren:

    ```PowerShell
    Add-MpPreference -AttackSurfaceReductionRules_Ids <rule ID> -AttackSurfaceReductionRules_Actions Warn
    ```

    Verwenden Sie das folgende Cmdlet, um den Missbrauch ausgenutzter gefährdeter signierter Treiber zu aktivieren:

   ```PowerShell
   "& {&'Add-MpPreference' -AttackSurfaceReductionRules_Ids 56a863a9-875e-4185-98a7-b882c64b5ce5 -AttackSurfaceReductionRules_Actions Enabled"}
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
    > `Set-MpPreference` überschreibt immer den vorhandenen Satz von Regeln. Wenn Sie dem vorhandenen Satz hinzufügen möchten, verwenden Sie `Add-MpPreference` stattdessen.
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

- [FAQ zu Verringerung der Angriffsfläche](attack-surface-reduction.md)
