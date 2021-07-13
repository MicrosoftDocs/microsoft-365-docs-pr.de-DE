---
title: Aktivieren der Verwaltung von in die Domäne eingebundenen Windows 10 Geräten durch Microsoft 365 for Business
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
description: In nur wenigen Schritten erfahren Sie, wie Sie Microsoft 365 aktivieren, um lokale Active-Directory-verbundene Windows 10-Geräte zu schützen.
ms.openlocfilehash: 9cc7ca01cec667465e9114083fecdc56ef4e7ce7
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393377"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivieren der Verwaltung von in die Domäne eingebundenen Windows 10 Geräten durch Microsoft 365 Business Premium

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium einrichten, um Ihre Windows 10 Geräte zu schützen und gleichzeitig den Zugriff auf lokale Ressourcen beizubehalten, die eine lokale Authentifizierung erfordern.
Um diesen Schutz einzurichten, können Sie **in Azure AD eingebundene Hybridgeräte** implementieren. Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory verbunden.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Watch: Configure Hybrid Azure Active Directory join

In diesem Video werden die Schritte zum Einrichten dieses Szenarios für das gängigste Szenario beschrieben. Dies wird auch in den folgenden Schritten beschrieben.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Synchronisieren von Benutzern mit Azure AD mit Azure AD Verbinden.
- Führen Sie die Synchronisierung der Azure AD-Verbinden Organisationseinheit (ORGANIZATIONAL Unit, OU) durch.
- Stellen Sie sicher, dass alle domänenbenutzer, die Sie synchronisieren, über Lizenzen für Microsoft 365 Business Premium verfügen.

Die Schritte finden Sie unter [Synchronisieren von Domänenbenutzern mit Microsoft.](manage-domain-users.md)

## <a name="1-verify-mdm-authority-in-intune"></a>1. Überprüfen der MDM-Autorität in Intune

Wechseln Sie zu [Endpoint Manager,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) und wählen Sie auf der seite Microsoft Intune die **Geräteregistrierung** aus, und stellen Sie dann auf der Seite **"Übersicht"** sicher, dass die **MDM-Autorität** **Intune** ist.

- Wenn **die MDM-Autorität** **keine** ist, klicken Sie auf die **MDM-Autorität,** um sie auf **Intune** festzulegen.
- Wenn **die MDM-Autorität** **Microsoft Office 365** ist, wechseln Sie **zu**  >  **Geräte registrieren,** und verwenden Sie das Dialogfeld **"MDM-Autorität hinzufügen"** auf der rechten Seite, um eine **Intune MDM-Autorität** hinzuzufügen (das Dialogfeld **"MDM-Autorität hinzufügen"** ist nur verfügbar, wenn die **MDM-Autorität** auf Microsoft Office 365 festgelegt ist).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Überprüfen, ob Azure AD für die Teilnahme an Computern aktiviert ist

- Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> und wählen Sie **Azure Active Directory** (wählen Sie "Alle anzeigen" aus, wenn Azure Active Directory nicht sichtbar ist) in der Admin **Center-Liste.** 
- Wechseln **Sie** im Azure Active Directory Admin Center zu **Azure Active Directory,** wählen Sie **"Geräte"** und dann **"Geräteeinstellungen"** aus.
- Überprüfen, ob **Benutzer Geräte mit Azure AD verknüpfen können** 
    1. To enable all users, set to **All**.
    2. Um bestimmte Benutzer zu aktivieren, legen **Sie "Ausgewählt"** fest, um eine bestimmte Gruppe von Benutzern zu aktivieren.
        - Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.
        - Wählen Sie **"Gruppen auswählen"** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Überprüfen, ob Azure AD für MDM aktiviert ist

- Wechseln Sie zum Admin Center, <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> und wählen Sie **"Endpoint Managemen** t" aus (wählen Sie **"Alle anzeigen"** aus, wenn **Endpoint Manager** nicht sichtbar ist)
- Wechseln Sie im **Microsoft Endpoint Manager Admin Center** zu **"Geräte**  >  **Windows** automatische Registrierung Windows  >    >  **Registrierung".**
- Überprüfen Sie, ob der MDM-Benutzerbereich aktiviert ist.

    1. Um alle Computer zu registrieren, legen Sie **"Alle"** fest, um automatisch alle Benutzercomputer zu registrieren, die mit Azure AD verbunden sind, und neue Computer, wenn die Benutzer ein Geschäftskonto zu Windows hinzufügen.
    2. Legen Sie diesen Wert auf **"Einige"** fest, um die Computer einer bestimmten Benutzergruppe zu registrieren.
        -  Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.
        -  Wählen Sie **"Gruppen auswählen"** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="4-create-the-required-resources"></a>4. Erstellen der erforderlichen Ressourcen 

Das Ausführen der erforderlichen Aufgaben zum Konfigurieren der [Azure AD-Hybridverknüpfung](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) wurde durch die Verwendung des Cmdlets [Initialize-SecMgmtHy hybridDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-Modul vereinfacht. Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienstverbindungspunkt und die erforderliche Gruppenrichtlinie erstellt und konfiguriert.

Sie können dieses Modul installieren, indem Sie Folgendes aus einer Instanz von PowerShell aufrufen:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Es wird empfohlen, dieses Modul auf dem Windows Server zu installieren, auf dem Azure AD Verbinden ausgeführt wird.

Zum Erstellen des erforderlichen Dienstverbindungspunkts und der Gruppenrichtlinie rufen Sie das Cmdlet  ["Initialize-SecMgmtHy flyDeviceEnrollment"](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf. Sie benötigen ihre Microsoft 365 Business Premium globalen Administratoranmeldeinformationen, wenn Sie diese Aufgabe ausführen. Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Mit dem ersten Befehl wird eine Verbindung mit der Microsoft-Cloud hergestellt. Wenn Sie dazu aufgefordert werden, geben Sie Ihre Microsoft 365 Business Premium globalen Administratoranmeldeinformationen an.

## <a name="5-link-the-group-policy"></a>5. Verknüpfen der Gruppenrichtlinie

1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü die Option *"Vorhandenes Gruppenrichtlinienobjekt verknüpfen"* aus.
2. Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **"OK".**

## <a name="get-the-latest-administrative-templates"></a>Abrufen der neuesten administrativen Vorlagen

Wenn die Richtlinie **"Automatische MDM-Registrierung mit azure AD-Standardanmeldeinformationen aktivieren"** nicht angezeigt wird, liegt dies möglicherweise daran, dass die ADMX für Windows 10, Version 1803 oder höher, nicht installiert ist. Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: die neueste MDM.admx ist abwärtskompatibel):

1. Download: [Administrative Vorlagen (ADMX) für Windows 10 Update vom Oktober 2020 (20H2)](https://www.microsoft.com/download/102157).
2. Installieren Sie das Paket auf einem Domänencontroller.
3. Navigieren Sie je nach Version der administrativen Vorlagen zum Ordner: **C:\Programme (x86)\Microsoft-Gruppenrichtlinie\Windows 10 Update vom Oktober 2020 (20H2)**.
4. Benennen Sie den Ordner **"Richtliniendefinitionen"** im obigen Pfad in **"PolicyDefinitions"** um.
5. Kopieren Sie den **Ordner "PolicyDefinitions"** in die SYSVOL-Freigabe, die sich standardmäßig unter **"C:\Windows\SYSVOL\domain\Policies"** befindet.
   - Wenn Sie beabsichtigen, einen zentralen Richtlinienspeicher für Ihre gesamte Domäne zu verwenden, fügen Sie dort den Inhalt von PolicyDefinitions hinzu.
6. Falls Mehrere Domänencontroller vorhanden sind, warten Sie, bis SYSVOL repliziert wurde, damit die Richtlinien verfügbar sind. Dieses Verfahren funktioniert auch für jede zukünftige Version der administrativen Vorlagen.

An diesem Punkt sollten Sie in der Lage sein, die Richtlinie zum Aktivieren der **automatischen MDM-Registrierung mit den standardmäßig verfügbaren Azure AD-Anmeldeinformationen** anzuzeigen.

## <a name="related-content"></a>Verwandte Inhalte

[Synchronisieren von Domänenbenutzern mit Microsoft 365](manage-domain-users.md) (Artikel)\
[Erstellen einer Gruppe im Admin Center](../admin/create-groups/create-groups.md) (Artikel)\
[Lernprogramm: Konfigurieren der Hybrid-Azure Active Directory-Verknüpfung für verwaltete Domänen](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (Artikel)