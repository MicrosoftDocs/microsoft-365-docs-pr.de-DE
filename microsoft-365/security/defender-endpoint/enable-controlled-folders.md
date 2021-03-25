---
title: Aktivieren des kontrollierten Ordnerzugriffs
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, Protect, Dateien, Ordner, aktivieren, aktivieren, verwenden
description: Erfahren Sie, wie Sie Ihre wichtigen Dateien schützen, indem Sie den kontrollierten Ordnerzugriff aktivieren.
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
ms.openlocfilehash: 6d07e2a21bb01794990160cf02837fc524008098
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218760"
---
# <a name="enable-controlled-folder-access"></a>Aktivieren des kontrollierten Ordnerzugriffs

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Der kontrollierte Ordnerzugriff](controlled-folders.md) hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen. Der kontrollierte Ordnerzugriff ist in Windows 10 und Windows Server 2019 enthalten.

Sie können den kontrollierten Ordnerzugriff mithilfe einer der folgenden Methoden aktivieren:

* [Windows Security App](#windows-security-app)
* [Microsoft Intune](#intune)
* [Mobile Geräteverwaltung (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Gruppenrichtlinie](#group-policy)
* [PowerShell](#powershell)

[Im Überwachungsmodus](evaluate-controlled-folder-access.md) können Sie testen, wie das Feature funktionieren würde (und Ereignisse überprüfen), ohne sich auf die normale Verwendung des Geräts auswirken zu müssen.

Gruppenrichtlinieneinstellungen, die das Zusammenführen lokaler Administratorlisten deaktivieren, setzen die Einstellungen für den kontrollierten Ordnerzugriff außer Kraft. Außerdem überschreiben sie geschützte Ordner und zugelassene Apps, die vom lokalen Administrator über den kontrollierten Ordnerzugriff festgelegt wurden. Zu diesen Richtlinien gehören:

* Microsoft Defender Antivirus **Konfigurieren des Zusammenführungsverhaltens lokaler Administratoren für Listen**
* System Center Endpoint Protection **Benutzern das Hinzufügen von Ausschlüssen und Außerkraftsetzungen ermöglichen**

Weitere Informationen zum Deaktivieren des Zusammenführens lokaler Listen finden Sie unter [Prevent or allow users to local modify Microsoft Defender AV policy settings](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged).

## <a name="windows-security-app"></a>Windows Security App

1. Öffnen Sie die Windows Security-App, indem Sie das Schildsymbol in der Taskleiste auswählen. Sie können auch im Startmenü nach **Defender suchen.**

2. Wählen Sie **die Kachel & Virenschutz** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz aus.**

3. Legen Sie die Option für **kontrollierten Ordnerzugriff auf** **Ein .**

> [!NOTE]
> Wenn der kontrollierte Ordnerzugriff mit Gruppenrichtlinien, PowerShell- oder MDM-CSPs konfiguriert ist, ändert sich der Status in der Windows Security-App nach einem Neustart des Geräts.
> Wenn das Feature  mit einem dieser Tools auf den Überwachungsmodus festgelegt ist, zeigt die Windows-Sicherheits-App den Status **Aus an.**
> Wenn Sie Benutzerprofildaten schützen, wird empfohlen, dass sich das Benutzerprofil auf dem Standardmäßigen Windows-Installationslaufwerk befinden sollte.

## <a name="intune"></a>Intune

1. Melden Sie sich beim [Azure-Portal an, und](https://portal.azure.com) öffnen Sie Intune.

2. Wechseln Sie zu **Gerätekonfigurationsprofile**  >    >  **Profil erstellen.**

3. Benennen Sie das Profil, wählen **Sie Windows 10 und höher und** Endpoint Protection **aus.** <br/> ![Erstellen eines Endpunktschutzprofils](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Wechseln Sie **zu Configure** Windows Defender  >  **Exploit Guard** Controlled folder  >  **access**  >  **Enable**.

5. Geben Sie den Pfad zu jeder Anwendung ein, die Zugriff auf geschützte Ordner hat, und den Pfad zu jedem zusätzlichen Ordner, der Schutz benötigt. Klicken Sie auf **Hinzufügen**.<br/> ![Aktivieren des kontrollierten Ordnerzugriffs in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt. Unterordner sind nicht geschützt. Zugelassene Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.

6. Wählen **Sie OK** aus, um jedes geöffnete Blatt zu speichern, und erstellen **.**

7. Wählen Sie die **Profilzuweisungen** aus, weisen **Sie allen Benutzern & Alle Geräte** zu, und speichern **.**

## <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders-Konfigurationsdienstanbieter (CSP),](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) damit Apps Änderungen an geschützten Ordnern vornehmen können.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance** Endpoint  >  **Protection** Windows Defender  >  **Exploit Guard**.

2. Wählen **Sie Home** Create Exploit Guard Policy  >  **aus.**

3. Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **kontrollierten** Ordnerzugriff aus, und wählen Sie **Weiter aus.**

4. Wählen Sie aus, ob Änderungen blockiert oder überwacht werden, andere Apps zulassen oder andere Ordner hinzugefügt werden, und wählen Sie **Weiter aus.**
   > [!NOTE]
   > Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt. Unterordner sind nicht geschützt. Zugelassene Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.

5. Überprüfen Sie die Einstellungen, und wählen **Sie Weiter** aus, um die Richtlinie zu erstellen.

6. Nachdem die Richtlinie erstellt wurde, schließen **Sie**.

## <a name="group-policy"></a>Gruppenrichtlinien

1. Öffnen Sie auf Ihrem Gruppenrichtlinienverwaltungsgerät die [Gruppenrichtlinienverwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie Bearbeiten **aus.**

2. Wechseln Sie **im Gruppenrichtlinienverwaltungs-Editor** zu **Computerkonfiguration,** und wählen Sie **Administrative Vorlagen aus.**

3. Erweitern Sie die Struktur auf **Windows-Komponenten > Microsoft Defender Antivirus > Windows Defender Exploit Guard > Kontrollierter Ordnerzugriff**.

4. Doppelklicken Sie auf **die Einstellung Kontrollierten Ordnerzugriff** konfigurieren, und legen Sie die Option auf **Aktiviert .** Im Abschnitt Optionen müssen Sie eine der folgenden Optionen angeben:
    * **Aktivieren** – Bösartige und verdächtige Apps dürfen keine Änderungen an Dateien in geschützten Ordnern vornehmen. Im Windows-Ereignisprotokoll wird eine Benachrichtigung bereitgestellt.
    * **Disable (Standard)** – Das Feature für den kontrollierten Ordnerzugriff funktioniert nicht. Alle Apps können Änderungen an Dateien in geschützten Ordnern vornehmen.
    * **Überwachungsmodus** – Änderungen sind zulässig, wenn eine schädliche oder verdächtige App versucht, eine Datei in einem geschützten Ordner zu ändern. Sie wird jedoch im Windows-Ereignisprotokoll aufgezeichnet, in dem Sie die Auswirkungen auf Ihre Organisation bewerten können.
    * **Nur Datenträgeränderung blockieren** – Versuche nicht vertrauenswürdiger Apps, auf Datenträgersektoren zu schreiben, werden im Windows-Ereignisprotokoll protokolliert. Diese Protokolle finden Sie unter **Applications and Services Logs** > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Nur Datenträgeränderung** überwachen – Nur Versuche, in geschützte Datenträgersektoren zu schreiben, werden im Windows-Ereignisprotokoll aufgezeichnet (unter **Anwendungs-** und Dienstprotokolle  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**  >  **ID 1124**). Versuche, Dateien in geschützten Ordnern zu ändern oder zu löschen, werden nicht aufgezeichnet.

      ![Screenshot der in der Dropdownliste ausgewählten Gruppenrichtlinienoption "Aktiviert" und "Überwachungsmodus"](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Um den kontrollierten Ordnerzugriff vollständig zu aktivieren, müssen Sie die Option Gruppenrichtlinie auf **Aktiviert** festlegen und **im** Dropdownmenü Optionen blockieren auswählen.

## <a name="powershell"></a>PowerShell

1. Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **Maustaste auf Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**

2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Sie können das Feature im Überwachungsmodus aktivieren, indem Sie anstelle von `AuditMode` `Enabled` angeben.

Verwenden `Disabled` Sie, um das Feature zu deaktivieren.

## <a name="see-also"></a>Siehe auch

* [Schützen wichtiger Ordner mit kontrolliertem Ordnerzugriff](controlled-folders.md)
* [Anpassen des kontrollierten Ordnerzugriffs](customize-controlled-folders.md)
* [Bewerten von Microsoft Defender for Endpoint](evaluate-mde.md)
