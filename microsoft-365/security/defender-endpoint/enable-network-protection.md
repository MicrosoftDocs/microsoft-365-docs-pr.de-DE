---
title: Netzwerkschutz aktivieren
description: Aktivieren Sie den Netzwerkschutz mit gruppenrichtlinien, PowerShell oder Mobile Device Management and Configuration Manager.
keywords: ANetwork-Schutz, Exploits, schädliche Website, IP, Domäne, Domänen, aktivieren, aktivieren
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: dansimp
ms.author: dansimp
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: b62659360e990467524ec632968dfea313d0b164
ms.sourcegitcommit: 3e971b31435d17ceeaa9871c01e88e25ead560fb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2021
ms.locfileid: "52861671"
---
# <a name="turn-on-network-protection"></a>Netzwerkschutz aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter beliebige Anwendungen verwenden, um auf gefährliche Domänen zuzugreifen, die Phishing-Angriffe, Exploits und andere schädliche Inhalte im Internet hosten können. Sie können [den Netzwerkschutz](evaluate-network-protection.md) in einer Testumgebung überwachen, um anzuzeigen, welche Apps blockiert werden, bevor Sie sie aktivieren.

[Weitere Informationen zu Konfigurationsoptionen für die Netzwerkfilterung](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Überprüfen, ob der Netzwerkschutz aktiviert ist

Überprüfen Sie mithilfe des Registrierungs-Editors, ob der Netzwerkschutz auf einem lokalen Gerät aktiviert wurde.

1. Wählen Sie die **Schaltfläche "Start"** in der Taskleiste aus, und geben Sie **"regedit" ein,** um den Registrierungs-Editor zu öffnen.

2. HKEY_LOCAL_MACHINE  aus dem Seitenmenü auswählen

3. Navigieren Sie durch die geschachtelten Menüs zu **SOFTWARE**  >  **Microsoft**  >  **Windows Defender**  >  **Windows Defender Exploit Guard** Network  >  **Protection**

4. Wählen Sie **"EnableNetworkProtection" aus,** um den aktuellen Status des Netzwerkschutzes auf dem Gerät anzuzeigen.

    * 0 oder **aus**
    * 1 oder **ein**
    * 2 oder **Überwachungsmodus**
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Netzwerkschutz aktivieren

Aktivieren Sie den Netzwerkschutz mithilfe einer der folgenden Methoden:

* [PowerShell](#powershell)
* [Verwaltung mobiler Geräte (Mobile Device Management, MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager/Intune](#microsoft-endpoint-manager-formerly-intune)
* [Gruppenrichtlinie](#group-policy)

### <a name="powershell"></a>PowerShell

1. Geben Sie **PowerShell** im Startmenü ein, klicken Sie mit der rechten Maustaste auf **Windows PowerShell,** und wählen Sie **"Als Administrator ausführen"** aus.
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Optional: Aktivieren Sie das Feature im Überwachungsmodus mit dem folgenden Cmdlet:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Verwenden Sie das Feature anstelle oder deaktivieren Sie `Disabled` `AuditMode` `Enabled` es.

### <a name="mobile-device-management-mdm"></a>Mobile Geräteverwaltung (MDM)

Verwenden Sie [den Konfigurationsdienstanbieter ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) (CSP), um den Netzwerkschutz zu aktivieren oder zu deaktivieren oder den Überwachungsmodus zu aktivieren.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (früher Intune)

1. Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com)

2. Erstellen oder Bearbeiten eines [Endpunktschutz-Konfigurationsprofils](/mem/intune/protect/endpoint-protection-configure)

3. Wechseln Sie unter **"Konfiguration Einstellungen** im Profilfluss" zu **Microsoft Defender Exploit Guard**  >  **Netzwerkfilterungsnetzwerkschutz**  >    >   aktivieren oder **nur überwachen**

### <a name="group-policy"></a>Gruppenrichtlinien

Verwenden Sie das folgende Verfahren, um den Netzwerkschutz auf Computern zu aktivieren, die einer Domäne beigetreten sind, oder auf einem eigenständigen Computer.

1. Wechseln Sie auf einem eigenständigen Computer zu **"Start",** geben Sie die Gruppenrichtlinie ein, und wählen Sie sie **aus.**

    *-Or-*

    Öffnen Sie auf einem in die Domäne eingebundenen Computer für die Gruppenrichtlinienverwaltung die [Gruppenrichtlinien-Verwaltungskonsole,](https://technet.microsoft.com/library/cc731212.aspx)klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten** aus.

2. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die Struktur bis Windows **Komponenten**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit**  >  **Guard-Netzwerkschutz.**

> [!NOTE]
> In älteren Versionen von Windows kann der Gruppenrichtlinienpfad "Windows Defender Antivirus" anstelle von "Microsoft Defender Antivirus" sagen.

4. Doppelklicken Sie auf die Einstellung **"Benutzer und Apps am Zugriff auf gefährliche Websites** hindern", und legen Sie die Option auf **"Aktiviert"** fest. Im Abschnitt "Optionen" müssen Sie eine der folgenden Optionen angeben:
    * **Blockieren** – Benutzer können nicht auf schädliche IP-Adressen und Domänen zugreifen
    * **Deaktivieren (Standard):** Das Netzwerkschutzfeature funktioniert nicht. Benutzer werden nicht am Zugriff auf schädliche Domänen gehindert
    * **Überwachungsmodus:** Wenn ein Benutzer eine schädliche IP-Adresse oder Domäne besucht, wird ein Ereignis im Windows-Ereignisprotokoll aufgezeichnet. Der Benutzer wird jedoch nicht daran gehindert, die Adresse zu besuchen.

> [!IMPORTANT]
> Um den Netzwerkschutz vollständig zu aktivieren, müssen Sie die Gruppenrichtlinienoption auf **"Aktiviert"** festlegen und im Dropdownmenü "Optionen" die Option **"Blockieren"** auswählen.

Stellen Sie sicher, dass der Netzwerkschutz auf einem lokalen Computer mithilfe des Registrierungs-Editors aktiviert ist:

1. Wählen Sie **"Start"** aus, und geben Sie **"regedit" ein,** um den **Registrierungs-Editor** zu öffnen.

2. Navigieren Sie zu **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\Windows Defender\Windows Defender Exploit Guard\Network Protection\EnableNetworkProtection**

3. Wählen Sie **"EnableNetworkProtection" aus,** und bestätigen Sie den Wert:
   * 0=Aus
   * 1=Ein
   * 2=Überwachung

## <a name="see-also"></a>Siehe auch

* [Netzwerkschutz](network-protection.md)
* [Auswerten des Netzwerkschutzes](evaluate-network-protection.md)
* [Problembehandlung beim Netzwerkschutz](troubleshoot-np.md)
