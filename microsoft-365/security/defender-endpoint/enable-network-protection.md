---
title: Netzwerkschutz aktivieren
description: Aktivieren Sie den Netzwerkschutz mit Gruppenrichtlinien, PowerShell oder Mobile Device Management and Configuration Manager.
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
ms.openlocfilehash: a2bc36f9d3a3e9179f07662da8d97f4c55e72a24
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52302052"
---
# <a name="turn-on-network-protection"></a>Netzwerkschutz aktivieren

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

[Der Netzwerkschutz](network-protection.md) verhindert, dass Mitarbeiter eine Anwendung verwenden, um auf gefährliche Domänen zu zugreifen, die Phishingbetrüger, Exploits und andere schädliche Inhalte im Internet hosten können. Sie können [den Netzwerkschutz](evaluate-network-protection.md) in einer Testumgebung überwachen, um zu sehen, welche Apps blockiert werden, bevor Sie ihn aktivieren.

[Weitere Informationen zu Konfigurationsoptionen für die Netzwerkfilterung](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)

## <a name="check-if-network-protection-is-enabled"></a>Überprüfen, ob der Netzwerkschutz aktiviert ist

Überprüfen Sie mithilfe des Registrierungs-Editors, ob der Netzwerkschutz auf einem lokalen Gerät aktiviert wurde.

1. Wählen Sie die **Schaltfläche Start** in der Aufgabenleiste aus, und geben Sie **regedit ein,** um den Registrierungs-Editor zu öffnen.

2. Wählen **HKEY_LOCAL_MACHINE** im Seitenmenü aus

3. Navigieren Sie durch die geschachtelten Menüs zu  >  **SOFTWARERichtlinien**  >  **Microsoft**  >  **Windows Defender**  >  **Policy Manager** 

4. Wählen **Sie EnableNetworkProtection** aus, um den aktuellen Status des Netzwerkschutzes auf dem Gerät zu sehen.

    * 0 oder **Aus**
    * 1 oder **Ein**
    * 2 oder **Überwachungsmodus**
    
    ![networkprotection](https://user-images.githubusercontent.com/3296790/95341270-b738b280-08d3-11eb-84a0-16abb140c9fd.PNG)

## <a name="enable-network-protection"></a>Aktivieren des Netzwerkschutzes

Aktivieren sie den Netzwerkschutz mithilfe einer der folgenden Methoden:

* [PowerShell](#powershell)
* [Mobile Geräteverwaltung (MDM)](#mobile-device-management-mdm)
* [Microsoft Endpoint Manager / Intune](#microsoft-endpoint-manager-formerly-intune)
* [Gruppenrichtlinie](#group-policy)

### <a name="powershell"></a>PowerShell

1. Geben **Sie powershell** im Menü Start ein, klicken Sie mit der rechten **maustaste Windows PowerShell** und wählen Sie Als Administrator ausführen **aus.**
2. Geben Sie das folgende Cmdlet ein:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection Enabled
    ```

3. Optional: Aktivieren Sie das Feature im Überwachungsmodus mithilfe des folgenden Cmdlets:

    ```PowerShell
    Set-MpPreference -EnableNetworkProtection AuditMode
    ```

    Verwenden `Disabled` Sie anstelle oder deaktivieren Sie das `AuditMode` `Enabled` Feature.

### <a name="mobile-device-management-mdm"></a>Verwaltung mobiler Geräte (Mobile Device Management, MDM)

Verwenden Sie [den ./Vendor/MSFT/Policy/Config/Defender/EnableNetworkProtection](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-enablenetworkprotection) Configuration Service Provider (CSP), um den Netzwerkschutz zu aktivieren oder zu deaktivieren oder den Überwachungsmodus zu aktivieren.

### <a name="microsoft-endpoint-manager-formerly-intune"></a>Microsoft Endpoint Manager (früher Intune)

1. Melden Sie sich beim Microsoft Endpoint Manager Admin Center an (https://endpoint.microsoft.com)

2. Erstellen oder Bearbeiten eines [Konfigurationsprofils für den Endpunktschutz](/mem/intune/protect/endpoint-protection-configure)

3. Wechseln **Sie Einstellungen** im Profilfluss unter Netzwerkfilterung Netzwerkschutz aktivieren oder überwachen zu  >    >    >   **Microsoft Defender Exploit Guard Netzwerkfilterung aktivieren** oder überwachen

### <a name="group-policy"></a>Gruppenrichtlinien

Verwenden Sie das folgende Verfahren, um den Netzwerkschutz auf Computern mit Domänenverbindung oder auf einem eigenständigen Computer zu aktivieren.

1. Wechseln Sie auf einem eigenständigen Computer zu **Start,** und geben Sie dann Gruppenrichtlinie **bearbeiten ein.**

    *-Or-*

    Öffnen Sie auf einem In der [](https://technet.microsoft.com/library/cc731212.aspx)Domäne beigetretenen Gruppenrichtlinienverwaltungscomputer die Gruppenrichtlinienverwaltungskonsole, klicken Sie mit der rechten Maustaste auf das Gruppenrichtlinienobjekt, das Sie konfigurieren möchten, und wählen Sie **Bearbeiten aus.**

2. Wechseln Sie im **Gruppenrichtlinien-Verwaltungs-Editor** zu **Computerkonfiguration**, und wählen Sie **Administrative Vorlagen** aus.

3. Erweitern Sie die **Struktur, Windows komponenten**  >  **Microsoft Defender Antivirus**  >  **Windows Defender Exploit Guard** Network Protection  >  **.**

> [!NOTE]
> Bei älteren Versionen von Windows kann der Gruppenrichtlinienpfad "Windows Defender Antivirus" statt "Microsoft Defender Antivirus" sagen.

4. Doppelklicken Sie auf die Einstellung Benutzer **und Apps am** Zugriff auf gefährliche Websites hindern, und legen Sie die Option auf Aktiviert **.** Im Abschnitt Optionen müssen Sie eine der folgenden Optionen angeben:
    * **Blockieren** – Benutzer können nicht auf schädliche IP-Adressen und Domänen zugreifen
    * **Disable (Standard)** – Das Netzwerkschutzfeature funktioniert nicht. Benutzer werden nicht am Zugriff auf schädliche Domänen blockiert
    * **Überwachungsmodus** – Wenn ein Benutzer eine schädliche IP-Adresse oder Domäne besucht, wird ein Ereignis im Ereignisprotokoll Windows aufgezeichnet. Der Benutzer wird jedoch nicht am Besuch der Adresse blockiert.

> [!IMPORTANT]
> Um den Netzwerkschutz vollständig zu aktivieren, müssen Sie  die Option Gruppenrichtlinie auf **Aktiviert** festlegen und im Dropdownmenü Optionen auch Blockieren auswählen.

Vergewissern Sie sich, dass der Netzwerkschutz auf einem lokalen Computer mithilfe des Registrierungs-Editors aktiviert ist:

1. Wählen **Sie Start** aus, und geben Sie **regedit ein,** um den **Registrierungs-Editor zu öffnen.**

2. Navigieren Sie zu **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Defender\Policy Manager\EnableNetworkProtection**

3. Wählen **Sie EnableNetworkProtection aus,** und bestätigen Sie den Wert:
   * 0=Aus
   * 1=Ein
   * 2=Überwachung

## <a name="see-also"></a>Siehe auch

* [Netzwerkschutz](network-protection.md)
* [Auswerten des Netzwerkschutzes](evaluate-network-protection.md)
* [Problembehandlung beim Netzwerkschutz](troubleshoot-np.md)
