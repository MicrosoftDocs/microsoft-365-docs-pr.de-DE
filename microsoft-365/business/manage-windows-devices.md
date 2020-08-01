---
title: Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 for Business verwaltet werden
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
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
description: In diesem Artikel erfahren Sie, wie Sie Microsoft 365 in wenigen Schritten zum Schutz von lokalen Active Directory-verbundenen Windows 10-Geräten aktivieren.
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533783"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivieren von Domänenbeitritt von Windows 10-Geräten, die von Microsoft 365 Business Premium verwaltet werden

Wenn Ihre Organisation Windows Server Active Directory lokal verwendet, können Sie Microsoft 365 Business Premium zum Schutz Ihrer Windows 10-Geräte einrichten und gleichzeitig den Zugriff auf lokale Ressourcen aufrecht erhalten, die lokale Authentifizierung erfordern.
Um diesen Schutz einzurichten, können Sie **hybride Azure AD verbundene Geräte**implementieren. Diese Geräte sind sowohl mit Ihrem lokalen Active Directory als auch mit Ihrem Azure-Active Directory verbunden.

In diesem Video werden die Schritte beschrieben, wie Sie dies für das am häufigsten verwendete Szenario einrichten, das auch in den folgenden Schritten detailliert erläutert wird.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Bevor Sie beginnen, stellen Sie sicher, dass Sie die folgenden Schritte ausführen:
- Synchronisieren von Benutzern mit dem Azure AD mit Azure AD Connect.
- Schließen Sie die Synchronisierung Azure AD Connect Organizational Unit (OU) ab.
- Stellen Sie sicher, dass alle von Ihnen synchronisierten Domänenbenutzer Lizenzen für Microsoft 365 Business Premium haben.

Die Schritte finden Sie unter [Synchronisieren von Domänenbenutzern mit Microsoft](manage-domain-users.md) .

## <a name="1-verify-mdm-authority-in-intune"></a>1. Überprüfen der MDM-Autorität in InTune

Wechseln Sie zu Portal.Azure.com, und klicken Sie oben auf der Seite auf die Suche nach InTune.
Wählen Sie auf der Seite Microsoft InTune die Option **Geräteregistrierung** aus, und stellen Sie auf der Seite **Übersicht** sicher, dass die **MDM-Autorität** **InTune**ist.

- Wenn **MDM Authority** **keine**ist, klicken Sie auf die **MDM-Autorität** , um Sie auf **InTune**festzulegen.
- Wenn **MDM Authority** **Microsoft Office 365**ist, wechseln Sie zu **Geräte**  >  **Registrieren von Geräten** , und verwenden Sie das Dialogfeld MDM- **Autorität hinzufügen** auf der rechten Seite zum Hinzufügen von **InTune-MDM** -Autorität (das Dialogfeld MDM- **Autorität hinzufügen** ist nur verfügbar, wenn die MDM- **Autorität** auf Microsoft Office 365 festgelegt ist).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. überprüfen, ob Azure AD für das Hinzufügen von Computern aktiviert ist

- Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie **Azure Active Directory** (Wählen Sie alle anzeigen, wenn Azure Active Directory nicht sichtbar ist) in der Liste **Admin** Center aus. 
- Wechseln Sie im **Azure Active Directory Admin Center**zu **Azure Active Directory** , wählen Sie **Geräte** und dann **Geräteeinstellungen**aus.
- Sicherstellen **, dass Benutzer Geräte an Azure AD** aktiviert werden können 
    1. Um alle Benutzer zu aktivieren, legen Sie **alle**fest.
    2. Um bestimmte Benutzer zu aktivieren, legen Sie auf **ausgewählt** fest, um eine bestimmte Gruppe von Benutzern zu aktivieren.
        - Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.
        - Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. überprüfen Azure AD für MDM aktiviert ist

- Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> , und wählen Sie " **Endpunkt Verwaltung**auswählen" aus (Wählen Sie **Alle anzeigen** aus, wenn **Endpunkt-Manager** nicht sichtbar ist)
- Wechseln Sie im **Microsoft Endpoint Manager Admin Center**zu **Geräte**  >  **Windows**  >  **Windows-Registrierung**für die  >  **automatische Registrierung**.
- Überprüfen Sie, dass der MDM-Benutzerbereich aktiviert ist.

    1. Wenn Sie alle Computer registrieren möchten, **legen Sie alle** fest, damit alle Benutzer Computer, die zu Azure AD und zu neuen Computern gehören, automatisch registriert werden, wenn die Benutzer ein Arbeitskonto zu Windows hinzufügen.
    2. Auf **einige** festlegen, um die Computer einer bestimmten Gruppe von Benutzern zu registrieren.
        -  Fügen Sie die gewünschten Domänenbenutzer, die in Azure AD synchronisiert wurden, zu einer [Sicherheitsgruppe](../admin/create-groups/create-groups.md)hinzu.
        -  Wählen **Sie Gruppen auswählen** aus, um den MDM-Benutzerbereich für diese Sicherheitsgruppe zu aktivieren.

## <a name="4-create-the-required-resources"></a>4. Erstellen der erforderlichen Ressourcen 

Das Ausführen der erforderlichen Aufgaben zum [Konfigurieren von Hybrid Azure AD Verknüpfung](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) wurde durch die Verwendung des Cmdlets [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) im PowerShell-Modul [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) vereinfacht. Wenn Sie dieses Cmdlet aufrufen, wird der erforderliche Dienst Verbindungspfad und die Gruppenrichtlinie erstellt und konfiguriert.

Sie können dieses Modul installieren, indem Sie aus einer Instanz von PowerShell Folgendes aufrufen:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Es wird empfohlen, dieses Modul auf dem Windows-Server mit Azure AD Connect zu installieren.

Zum Erstellen des erforderlichen Dienst Verbindungs Pfads und der Gruppenrichtlinie rufen Sie das Cmdlet [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) auf. Sie benötigen Ihre globalen Administratoranmeldeinformationen für Microsoft 365 Business Premium, wenn Sie diese Aufgabe ausführen. Wenn Sie bereit sind, die Ressourcen zu erstellen, rufen Sie Folgendes auf:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Mit dem ersten Befehl wird eine Verbindung mit der Microsoft-Cloud hergestellt, und wenn Sie dazu aufgefordert werden, geben Sie Ihre globalen Administratoranmeldeinformationen für Microsoft 365 Business Premium an.

## <a name="5-link-the-group-policy"></a>5. Verknüpfen der Gruppenrichtlinie

1. Klicken Sie in der Gruppenrichtlinien-Verwaltungskonsole (Group Policy Management Console, GPMC) mit der rechten Maustaste auf den Speicherort, an dem Sie die Richtlinie verknüpfen möchten, und wählen Sie im Kontextmenü die Option *vorhandenes GPO verknüpfen* aus.
2. Wählen Sie die im obigen Schritt erstellte Richtlinie aus, und klicken Sie dann auf **OK**.

## <a name="get-the-latest-administrative-templates"></a>Abrufen der neuesten administrativen Vorlagen

Wenn die Richtlinie **Automatische MDM-Registrierung mithilfe der Standard Azure AD Anmeldeinformationen nicht aktiviert**wird, kann dies daran liegen, dass Sie den ADMX nicht für Windows 10, Version 1803, Version 1809 oder Version 1903 installiert haben. Führen Sie die folgenden Schritte aus, um das Problem zu beheben (Hinweis: die neueste Version von MDM. ADMX ist abwärtskompatibel):

1.  Download: [Administrative Vorlagen (ADMX) für Windows 10 May 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installieren Sie das Paket auf dem primären Domänen Controller (PDC).
3.  Navigieren Sie je nach Version zum Ordner: **C:\Program Files (x86) \Microsoft Group Policy\Windows 10 May 2019 Update (1903) v3**.
4.  Benennen Sie den Ordner **Richtlinien Definitionen** im obigen Pfad in **PolicyDefinitions**um.
5.  Kopieren Sie **PolicyDefinitions** -Ordner in **C:\Windows\SYSVOL\domain\Policies**. 
    -   Wenn Sie einen zentralen Richtlinienspeicher für Ihre gesamte Domäne verwenden möchten, fügen Sie den Inhalt von PolicyDefinitions dort hinzu.
6.  Starten Sie den primären Domänen Controller neu, damit die Richtlinie zur Verfügung steht. Dieses Verfahren kann auch für zukünftige Versionen verwendet werden.

An dieser Position sollten Sie die **Automatische MDM-Registrierung mithilfe der standardmäßigen Azure AD** verfügbaren Anmeldeinformationen anzeigen können.
