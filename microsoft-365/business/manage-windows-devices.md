---
title: Aktivieren der Domänen-Windows 10 geräte, die von Microsoft 365 verwaltet werden können
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
search.appverid:
- BCS160
- MET150
description: Erfahren Sie, wie Sie Microsoft 365 aktivieren, um lokale Active -Directory-Windows 10 in wenigen Schritten zu schützen.
ms.openlocfilehash: f16962dd3c33c3c228da507bc5c4a902d76a8a08
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593891"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivieren sie, dass Windows 10 der Domäne beigetretenen Geräte von der Microsoft 365 Business Premium

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen beibehalten, die eine lokale Authentifizierung erfordern.
Zum Einrichten dieses Schutzes können Sie Azure **AD-Hybridgeräte implementieren.** Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure Active Directory.

In diesem Video werden die Schritte zum Einrichten dieses Szenarios für das gängigste Szenario beschrieben, das auch in den folgenden Schritten beschrieben wird.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausführen:
- Synchronisieren Sie Benutzer mit Azure AD Verbinden.
- Schließen Sie die Synchronisierung Verbinden Organisationseinheit (Organizational Unit, OU) ab.
- Stellen Sie sicher, dass alle Domänenbenutzer, die Sie synchronisieren, über Lizenzen für Microsoft 365 Business Premium.

Die [Schritte finden Sie unter Synchronisieren von Domänenbenutzern](manage-domain-users.md) mit Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Überprüfen der MDM-Autorität in Intune

Wechseln Sie zu [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) und wählen Sie auf der Seite Microsoft Intune Geräteregistrierung **aus,** und stellen Sie dann auf der Seite Übersicht sicher, dass **die MDM-Autorität** **Intune ist.** 

- Wenn **die MDM-Autorität** **Keine ist,** klicken Sie auf die **MDM-Autorität,** um sie auf **Intune zu setzen.**
- Wenn **die MDM-Autorität** Microsoft Office 365 **ist,** wechseln Sie zu Geräte Registrieren von Geräten, und verwenden Sie das Dialogfeld   >   **MDM-Autorität** hinzufügen auf der rechten Seite, um **Intune MDM-Autorität** hinzuzufügen (das Dialogfeld **MDM-Autorität** hinzufügen ist nur verfügbar, wenn die **MDM-Autorität** auf Microsoft Office 365) festgelegt ist.

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Überprüfen, ob Azure AD für den Beitritt zu Computern aktiviert ist

- Wechseln Sie zum Admin Center <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **unter, und wählen Azure Active Directory** (wählen Sie Alle anzeigen aus, Azure Active Directory nicht sichtbar ist) in der Liste **Admin Center** aus. 
- Wechseln Sie **Azure Active Directory Admin Center** zu **Azure Active Directory** , wählen Sie **Geräte** und dann **Geräteeinstellungen aus.**
- Überprüfen,**ob Benutzer Geräte zu Azure AD beitreten können aktiviert** ist 
    1. Um alle Benutzer zu aktivieren, legen Sie auf **Alle .**
    2. Um bestimmte Benutzer zu aktivieren, legen Sie auf **Ausgewählt festgelegt,** um eine bestimmte Gruppe von Benutzern zu aktivieren.
        - Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe hinzu.](../admin/create-groups/create-groups.md)
        - Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Überprüfen, ob Azure AD für MDM aktiviert ist

- Wechseln Sie zum Admin Center unter, und wählen Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> **Endpoint Managemen** t aus (wählen Sie **Alle** anzeigen **aus, Endpoint Manager** nicht sichtbar ist)
- Wechseln Sie **Microsoft Endpoint Manager Admin Center** zu **Geräte**  >  **Windows**  >  **Windows Registrierung** automatische  >  **Registrierung**.
- Überprüfen Sie, ob der MDM-Benutzerbereich aktiviert ist.

    1. Wenn Sie alle Computer  registrieren möchten, legen Sie all fest, um alle Benutzercomputer, die Azure AD beigetreten sind, und neue Computer automatisch zu registrieren, wenn die Benutzer ein Arbeitskonto zu Windows.
    2. Wird auf **Einige festgelegt,** um die Computer einer bestimmten Gruppe von Benutzern zu registrieren.
        -  Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, einer [Sicherheitsgruppe hinzu.](../admin/create-groups/create-groups.md)
        -  Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="4-create-the-required-resources"></a>4. Erstellen der erforderlichen Ressourcen 

Die Ausführung der [](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) erforderlichen Aufgaben zum Konfigurieren der Azure AD-Hybrid-Verknüpfung wurde durch die Verwendung des [Cmdlets Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-Modul vereinfacht. Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienstverbindungspunkt und die Gruppenrichtlinie erstellt und konfiguriert.

Sie können dieses Modul installieren, indem Sie folgendes aus einer Instanz von PowerShell aufrufen:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Es wird empfohlen, dieses Modul auf dem Windows Server zu installieren, auf dem Azure AD Verbinden.

Zum Erstellen der erforderlichen Dienstverbindungspunkt- und Gruppenrichtlinie rufen Sie das  [Cmdlet Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf. Sie benötigen ihre Microsoft 365 Business Premium anmeldeinformationen für den globalen Administrator, wenn Sie diese Aufgabe ausführen. Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Mit dem ersten Befehl wird eine Verbindung mit der Microsoft-Cloud erstellt, und wenn Sie dazu aufgefordert werden, geben Sie Microsoft 365 Business Premium Anmeldeinformationen für den globalen Administrator an.

## <a name="5-link-the-group-policy"></a>5. Verknüpfen der Gruppenrichtlinie

1. Klicken Sie in der Gruppenrichtlinienverwaltungskonsole (GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü *Link ein* vorhandenes Gruppenrichtlinienobjekt... aus.
2. Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **OK**.

## <a name="get-the-latest-administrative-templates"></a>Die neuesten administrativen Vorlagen erhalten

Wenn die Richtlinie Automatische **MDM-Registrierung** mit standardmäßigen Azure AD-Anmeldeinformationen aktivieren nicht angezeigt wird, liegt dies möglicherweise daran, dass ADMX nicht für Windows 10, Version 1803 oder höher, installiert ist. Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: Die neueste MDM.admx ist abwärtskompatibel):

1.  Download: [Administrative Templates (.admx) for Windows 10 October 2020 Update (20H2)](https://www.microsoft.com/download/102157).
2.  Installieren Sie das Paket auf einem Domänencontroller.
3.  Navigieren Sie in Abhängigkeit von der Version administrative Vorlagen zum Ordner: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 October 2020 Update (20H2)**.
4.  Benennen Sie **den Ordner Richtliniendefinitionen** im obigen Pfad in **PolicyDefinitions um.**
5.  Kopieren Sie **den Ordner PolicyDefinitions** in Ihre SYSVOL-Freigabe, die sich standardmäßig unter **C:\Windows\SYSVOL\domain\Policies befindet.** 
    -   Wenn Sie planen, einen zentralen Richtlinienspeicher für Ihre gesamte Domäne zu verwenden, fügen Sie dort den Inhalt von PolicyDefinitions hinzu.
6.  Für den Fall, dass Mehrere Domänencontroller vorhanden sind, warten Sie, bis SYSVOL repliziert wird, bis die Richtlinien verfügbar sind. Dieses Verfahren funktioniert auch für jede zukünftige Version der administrativen Vorlagen.

An diesem Punkt sollte die Richtlinie Automatische MDM-Registrierung aktivieren mit standardmäßig verfügbaren **Azure AD-Anmeldeinformationen angezeigt** werden.

## <a name="related-content"></a>Verwandte Inhalte

[Synchronisieren von Domänenbenutzern mit Microsoft 365](manage-domain-users.md) (Artikel)

[Erstellen einer Gruppe im Admin Center](../admin/create-groups/create-groups.md) (Artikel)

[Lernprogramm: Konfigurieren der Azure Active Directory für verwaltete Domänen](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (Artikel)