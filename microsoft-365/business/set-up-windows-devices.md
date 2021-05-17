---
title: Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer
f1.keywords:
- CSH
ms.author: sharik
author: skjerland
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- TRN_M365B
- OKR_SMB_Videos
- seo-marvel-mar
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Erfahren Sie, wie Sie Windows-Geräte mit Windows 10 Pro für Microsoft 365 Business Premium-Benutzer einrichten und zentrale Verwaltungs- und Sicherheitssteuerelemente aktivieren.
ms.openlocfilehash: 3e268d81ff6fb7113b7e0b0fe5d0545ff5c72b1e
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244774"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer

## <a name="prerequisites-for-setting-up-windows-devices-for-microsoft-365-business-premium-users"></a>Voraussetzungen für das Einrichten von Windows-Geräten für Microsoft 365 Business Premium-Benutzer

Bevor Sie Windows-Geräte für Microsoft 365 Business Premium-Benutzer einrichten können, stellen Sie sicher, dass auf allen Windows-Geräten Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird. Windows 10 Pro ist eine Voraussetzung für die Bereitstellung von Windows 10 Business, einer Reihe von Clouddiensten und Geräteverwaltungsfunktionen, die Windows 10 Pro ergänzen und die zentralisierten Verwaltungs- und Sicherheitskontrollen von Microsoft 365 Business Premium aktivieren.
  
Wenn Sie über Windows-Geräte mit Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro verfügen, berechtigt Sie Ihr Microsoft 365 Business Premium-Abonnement zu einem Windows 10-Upgrade.
  
Weitere Informationen zum Upgrade von Windows-Geräten auf Windows 10 Pro Creators Update erhalten Sie, indem Sie die Schritte in diesem Thema ausführen: [Aktualisieren von Windows-Geräten auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
  
Weitere Informationen finden Sie unter Überprüfen, ob das Gerät mit [Azure AD](#verify-the-device-is-connected-to-azure-ad) verbunden ist, um sicherzustellen, dass das Upgrade ausgeführt wurde.

Sehen Sie sich ein kurzes Video zum Verbinden von Windows mit Microsoft 365 an.<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../business-video/index.yml) an.
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Verbinden von Windows 10-Geräten in Ihrer Organisation mit Azure AD

Wenn alle Windows-Geräte in Ihrer Organisation entweder auf Windows 10 Pro Creators Update aktualisiert wurden oder bereits Windows 10 Pro Creators Update ausgeführt werden, können Sie diese Geräte dem Azure Active Directory Ihrer Organisation hinzufügen. Sobald die Geräte beigetreten sind, werden sie automatisch auf Windows 10 Business aktualisiert, das Teil Ihres Microsoft 365 Business Premium-Abonnements ist.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Ganz neue oder neu aktualisierte Windows 10 Pro-Geräte

Führen Sie für ganze neue Geräte mit Windows 10 Pro Creators Update oder für Geräte, die auf Windows 10 Pro Creators Update aktualisiert wurden, für die die Windows 10-Geräteinstallation jedoch noch nicht ausgeführt wurde, die folgenden Schritte aus.
  
1. Führen Sie die Windows 10-Geräteinstallation aus, bis die Seite **Wie soll das Setup erfolgen** angezeigt wird. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Wählen Sie hier **Einrichten für eine Organisation aus,** und geben Sie dann Ihren Benutzernamen und Ihr Kennwort für Microsoft 365 Business Premium ein. 
    
3. Beenden Sie die Windows 10-Geräteinstallation.
    
   Sobald Sie fertig sind, wird der Benutzer in Ihrer Organisation mit Azure AD verbunden. Ziehen Sie zur Sicherheit [Sicherstellen, dass das Gerät mit Azure AD verbunden ist](#verify-the-device-is-connected-to-azure-ad) zurate. 
  
### <a name="for-a-device-already-set-up-and-running-windows-10-pro"></a>Geräte, die bereits eingerichtet wurden und Windows 10 Pro ausführen

 **Herstellen der Verbindung der Benutzer zu Azure AD:**
  
1. Klicken Sie auf dem Windows-PC des Benutzers, auf dem Windows 10 Pro, Version 1703 (Creators Update) ausgeführt wird (siehe [Voraussetzungen](pre-requisites-for-data-protection.md)), auf das Windows-Logo und dann auf das Symbol "Einstellungen".
  
   ![In the Start menu, click Windows Settings icon](../media/74e1ce9a-1554-4761-beb9-330b176e9b9d.png)
  
2. Wechseln Sie unter **Einstellungen** zu **Konten**.
  
   ![In Windows Settings, go to Accounts](../media/472fd688-d111-4788-9fbb-56a00fbdc24d.png)
  
3. Klicken Sie auf der Seite **Ihre Informationen** auf **Auf Arbeits- oder Schulkonto zugreifen** \> **Verbinden**.
  
   ![Choose Connect under Access work or school](../media/af3a4e3f-f9b9-4969-b3e2-4ef99308090c.png)
  
4. Wählen Sie im Dialogfeld **Geschäfts-, Schul- oder Unikonto einrichten** unter **Alternative Aktionen** die Option **Dieses Gerät in Azure Active Directory einbinden**.
  
   ![Click Join this device to Azure Active Directory](../media/fb709a1b-05a9-4750-9cb9-e097f4412cba.png)
  
5. On the **Let's get you signed in** page, enter your work or school account \> **Next**.
  
   On the **Enter password** page, enter your password \> **Sign in**.
  
   ![Enter your work or school email on the Let's get you signed in page](../media/f70eb148-b1d2-4ba3-be38-7317eaf0321a.png)
  
6. Überprüfen Sie **auf der** Seite Stellen Sie sicher, dass es sich um Ihre Organisation handelt, ob die Informationen korrekt sind, und wählen Sie Beitreten **aus.**
  
   Klicken Sie auf der Seite **Sie sind fertig!** page, chosse **Done**.
  
   ![Wählen Sie auf dem Bildschirm Stellen Sie sicher, dass dies Ihre Organisation ist, beitreten aus.](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Wenn Sie Dateien nach OneDrive for Business hochgeladen haben, synchronisieren Sie diese wieder. Wenn Sie ein Drittanbietertool zum Migrieren von Profil und Dateien verwendet haben, synchronisieren Sie diese auch mit dem neuen Profil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Stellen Sie sicher, dass das Gerät mit Azure AD verbunden ist

Um den Synchronisierungsstatus  zu überprüfen, wählen Sie auf der Seite Arbeits- oder Schulzugriff unter **Einstellungen** den Bereich Verbunden mit **_** _ aus, um die \<organization name\> Schaltflächen **Info** und Trennen **verfügbar zu machen.** Wählen **Sie Info** aus, um ihren Synchronisierungsstatus zu erhalten. 
  
Wählen Sie **auf der** Seite Synchronisierungsstatus die Option **Synchronisieren** aus, um die neuesten Verwaltungsrichtlinien für mobile Geräte auf dem PC zu erhalten.
  
Um mit der Verwendung des Microsoft 365 Business Premium-Kontos zu beginnen, wechseln Sie zur **Windows-Startschaltfläche,** klicken Sie mit der rechten Maustaste auf Ihr aktuelles Kontobild, und wechseln Sie **dann auf Konto wechseln.** Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihrer Organisation an.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Überprüfen, ob der PC auf Windows 10 Business aktualisiert wurde

Stellen Sie sicher, dass Ihre Azure AD-Geräte, die Windows 10-Geräten beigetreten sind, im Rahmen Ihres Microsoft 365 Business Premium-Abonnements auf Windows 10 Business aktualisiert wurden.
  
1. Wechseln Sie zu **Einstellungen** \> **System** \> **Info**.
    
2. Überprüfen Sie, ob unter **Edition** **Windows 10 Business** angezeigt wird.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Nächste Schritte

Informationen zum Einrichten Ihrer mobilen Geräte finden Sie unter Einrichten mobiler Geräte für [Microsoft 365 Business Premium-Benutzer](set-up-mobile-devices.md), Informationen zum Festlegen von Geräteschutz- oder App-Schutzrichtlinien finden Sie unter [Verwalten von Microsoft 365 Business](manage.md).
  
## <a name="for-more-on-setting-up-and-using-microsoft-365-business-premium"></a>Weitere Informationen zum Einrichten und Verwenden von Microsoft 365 Business Premium

[Microsoft 365 für Unternehmen-Schulungsvideos](../business-video/index.yml)
