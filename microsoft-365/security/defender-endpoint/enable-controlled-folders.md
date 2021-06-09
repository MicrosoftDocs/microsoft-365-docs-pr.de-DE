---
title: Kontrollierte Ordnerzugriff aktivieren
keywords: Kontrollierter Ordnerzugriff, Windows 10, Windows Defender, Ransomware, schützen, Dateien, Ordner, aktivieren, aktivieren, aktivieren, verwenden
description: Erfahren Sie, wie Sie Ihre wichtigen Dateien schützen, indem Sie den kontrollierten Ordnerzugriff aktivieren.
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
audience: ITPro
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 1d09eaf04999478a0cd0b4907667a522a23fb39f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841978"
---
# <a name="enable-controlled-folder-access"></a>Kontrollierte Ordnerzugriff aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Der kontrollierte Ordnerzugriff](controlled-folders.md) hilft Ihnen, wertvolle Daten vor schädlichen Apps und Bedrohungen wie Ransomware zu schützen. Der kontrollierte Ordnerzugriff ist in Windows 10 und Windows Server 2019 enthalten.

Sie können den kontrollierten Ordnerzugriff mithilfe einer der folgenden Methoden aktivieren:

* [Windows-Sicherheit-App](#windows-security-app)
* [Microsoft Intune](#intune)
* [Verwaltung mobiler Geräte (Mobile Device Management, MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Configuration Manager](#microsoft-endpoint-configuration-manager)
* [Gruppenrichtlinie](#group-policy)
* [PowerShell](#powershell)

Im [Überwachungsmodus](evaluate-controlled-folder-access.md) können Sie testen, wie das Feature funktioniert (und Ereignisse überprüfen), ohne die normale Verwendung des Geräts zu beeinträchtigen.

Gruppenrichtlinieneinstellungen, die das Zusammenführen von lokalen Administratorlisten deaktivieren, setzen die Einstellungen für den kontrollierten Ordnerzugriff außer Kraft. Sie setzen auch geschützte Ordner und zulässige Apps außer Kraft, die vom lokalen Administrator durch kontrollierten Ordnerzugriff festgelegt wurden. Zu diesen Richtlinien gehören:

* Microsoft Defender Antivirus Konfigurieren **des Zusammenführungsverhaltens lokaler Administratoren für Listen**
* System Center Endpoint Protection Benutzern **das Hinzufügen von Ausschlüssen und Außerkraftsetzungen gestatten**

Weitere Informationen zum Deaktivieren der lokalen Listenzusammenführung finden Sie unter "Verhindern oder Zulassen der lokalen Änderung von [Microsoft Defender AV-Richtlinieneinstellungen durch Benutzer".](/windows/security/threat-protection/microsoft-defender-antivirus/configure-local-policy-overrides-microsoft-defender-antivirus#configure-how-locally-and-globally-defined-threat-remediation-and-exclusions-lists-are-merged)

## <a name="windows-security-app"></a>Windows-Sicherheit-App

1. Öffnen Sie die Windows-Sicherheit App, indem Sie das Schildsymbol in der Taskleiste auswählen. Sie können auch das Startmenü nach **Defender** durchsuchen.

2. Wählen Sie die Kachel **"Viren- & Bedrohungsschutz"** (oder das Schildsymbol auf der linken Menüleiste) aus, und wählen Sie dann **Ransomware-Schutz** aus.

3. Legen Sie den Schalter für **den kontrollierten Ordnerzugriff** auf **"Ein"** fest.

> [!NOTE]
> Wenn der kontrollierte Ordnerzugriff mit Gruppenrichtlinien, PowerShell oder MDM-CSPs konfiguriert ist, ändert sich der Status in der Windows-Sicherheit-App nach einem Neustart des Geräts.
> Wenn das Feature mit einem dieser Tools auf den **Überwachungsmodus** festgelegt ist, zeigt die Windows-Sicherheit App den Status **"Aus"** an.
> Wenn Sie Benutzerprofildaten schützen, wird empfohlen, dass sich das Benutzerprofil auf dem Standardmäßigen Windows Installationslaufwerk befindet.

## <a name="intune"></a>Intune

1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com) an, und öffnen Sie Intune.

2. Wechseln Sie zu **"Gerätekonfigurationsprofile**  >    >  **erstellen".**

3. Benennen Sie das Profil, wählen Sie **Windows 10 und höher und** **Endpunktschutz** aus. <br/> ![Erstellen eines Endpunktschutzprofils](/microsoft-365/security/defender-endpoint/images/create-endpoint-protection-profile) <br/>

4. Wechseln **Sie** zu Configure  >  **Windows Defender Exploit Guard**  >  **Controlled folder access**  >  **Enable**.

5. Geben Sie den Pfad zu jeder Anwendung ein, die Zugriff auf geschützte Ordner hat, und den Pfad zu allen zusätzlichen Ordnern, die Schutz benötigen. Wählen Sie **Hinzufügen**.<br/> ![Aktivieren des kontrollierten Ordnerzugriffs in Intune](/microsoft-365/security/defender-endpoint/images/enable-cfa-intune)<br/>

   > [!NOTE]
   > Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt. Unterordner sind nicht geschützt. Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.

6. Klicken Sie auf **"OK",** um jedes geöffnete Blatt zu speichern und **zu erstellen.**

7. Wählen Sie die **Profilzuweisungen aus,** weisen Sie **alle Benutzer & Alle Geräte** zu, und speichern **Sie**.

## <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/ControlledFolderAccessProtectedFolders](/windows/client-management/mdm/policy-csp-defender#defender-controlledfolderaccessprotectedfolders) (CSP), um Apps das Vornehmen von Änderungen an geschützten Ordnern zu ermöglichen.

## <a name="microsoft-endpoint-configuration-manager"></a>Microsoft Endpoint Configuration Manager

1. Wechseln Sie in Microsoft Endpoint Configuration Manager zu **Assets and Compliance**  >  **Endpoint Protection** Windows Defender  >  **Exploit Guard**.

2. Wählen Sie **"Home**  >  **Create Exploit Guard Policy" aus.**

3. Geben Sie einen Namen und eine Beschreibung ein, wählen Sie **"Kontrollierter Ordnerzugriff"** aus, und wählen Sie **"Weiter"** aus.

4. Wählen Sie aus, ob Änderungen blockiert oder überwacht werden sollen, andere Apps zulassen oder andere Ordner hinzufügen, und wählen Sie **"Weiter"** aus.
   > [!NOTE]
   > Wilcard wird für Anwendungen, aber nicht für Ordner unterstützt. Unterordner sind nicht geschützt. Zulässige Apps lösen weiterhin Ereignisse aus, bis sie neu gestartet werden.

5. Überprüfen Sie die Einstellungen, und wählen Sie **"Weiter"** aus, um die Richtlinie zu erstellen.

6. Nachdem die Richtlinie erstellt wurde, **schließen Sie**.

## <a name="group-policy"></a>Gruppenrichtlinien

1. Öffnen Sie auf Ihrem Gerät für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die Struktur bis Windows **Komponenten > Microsoft Defender Antivirus > Windows Defender Exploit Guard > kontrollierten Ordnerzugriff.**

4. Doppelklicken Sie auf die Einstellung **"Kontrollierten Ordnerzugriff konfigurieren",** und legen Sie die Option auf **"Aktiviert"** fest. Im Abschnitt "Optionen" müssen Sie eine der folgenden Optionen angeben:
    * **Aktivieren –** Schädliche und verdächtige Apps dürfen keine Änderungen an Dateien in geschützten Ordnern vornehmen. Eine Benachrichtigung wird im Windows Ereignisprotokoll bereitgestellt.
    * **Deaktivieren (Standard)** – Das Feature für den kontrollierten Ordnerzugriff funktioniert nicht. Alle Apps können Änderungen an Dateien in geschützten Ordnern vornehmen.
    * **Überwachungsmodus:** Änderungen sind zulässig, wenn eine schädliche oder verdächtige App versucht, eine Änderung an einer Datei in einem geschützten Ordner vorzunehmen. Es wird jedoch im Windows Ereignisprotokoll aufgezeichnet, in dem Sie die Auswirkungen auf Ihre Organisation bewerten können.
    * **Nur Datenträgeränderung blockieren** – Versuche nicht vertrauenswürdiger Apps, in Datenträgerbereiche zu schreiben, werden Windows Ereignisprotokoll protokolliert. Diese Protokolle finden Sie in **den Anwendungs- und Dienstprotokollen** > Microsoft > Windows > Windows Defender > Operational > ID 1123.
    * **Nur Datenträgeränderung überwachen** – Nur Versuche, in geschützte Datenträgerbereiche zu schreiben, werden im ereignisprotokoll Windows aufgezeichnet (unter **Anwendungs- und Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >    >  **Betriebs-ID 1124).** Versuche, Dateien in geschützten Ordnern zu ändern oder zu löschen, werden nicht aufgezeichnet.

      ![Screenshot der in der Dropdownliste ausgewählten Gruppenrichtlinienoption "Aktiviert" und "Überwachungsmodus"](/microsoft-365/security/defender-endpoint/images/cfa-gp-enable)

> [!IMPORTANT]
> Um den kontrollierten Ordnerzugriff vollständig zu aktivieren, müssen Sie die Gruppenrichtlinienoption auf **"Aktiviert"** festlegen und im Dropdownmenü "Optionen" die Option **"Blockieren"** auswählen.

## <a name="powershell"></a>PowerShell

1. Geben Sie **powershell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **Als Administrator ausführen** aus.

2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableControlledFolderAccess Enabled
    ```

Sie können das Feature im Überwachungsmodus aktivieren, indem Sie `AuditMode` anstelle von `Enabled` .

Wird `Disabled` verwendet, um das Feature zu deaktivieren.

## <a name="see-also"></a>Siehe auch

* [Schützen wichtiger Ordner mit kontrollierten Ordnerzugriff](controlled-folders.md)
* [Kontrollierte Ordnerzugriff anpassen](customize-controlled-folders.md)
* [Auswerten des Microsoft Defender für Endpunkt](evaluate-mde.md)
