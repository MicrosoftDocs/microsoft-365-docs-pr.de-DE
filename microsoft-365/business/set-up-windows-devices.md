---
title: Einrichten Windows Geräte für Microsoft 365 Business Premium Benutzer
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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
ms.assetid: 2d7ff45e-0da0-4caa-89a9-48cabf41f193
description: Richten Sie Windows Geräte ein, auf denen Windows 10 Pro für Microsoft 365 Business Premium Benutzer ausgeführt wird, und aktivieren Sie zentrale Verwaltungs- und Sicherheitskontrollen.
ms.openlocfilehash: a911414b1a7abef259f4c5fffbdd48e07f9ebfdd
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393357"
---
# <a name="set-up-windows-devices-for-microsoft-365-business-premium-users"></a>Einrichten Windows Geräte für Microsoft 365 Business Premium Benutzer

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Bevor Sie Windows Geräte für Microsoft 365 Business Premium Benutzer einrichten können, stellen Sie sicher, dass alle Windows Geräte Windows 10 Pro Version 1703 (Creators Update) ausgeführt werden. Windows 10 Pro ist eine Voraussetzung für die Bereitstellung von Windows 10 Business. Dabei handelt es sich um eine Reihe von Clouddiensten und Geräteverwaltungsfunktionen, die Windows 10 Pro ergänzen und die zentrale Verwaltung und Sicherheitskontrollen von Microsoft 365 Business Premium ermöglichen.
  
Wenn Windows Geräte Windows 7 Pro, Windows 8 Pro oder Windows 8.1 Pro ausgeführt werden, führt Ihr Microsoft 365 Business Premium Abonnement zu einem Windows 10 Upgrade.
  
Weitere Informationen zum Upgrade von Windows-Geräten auf Windows 10 Pro Creators Update erhalten Sie, indem Sie die Schritte in diesem Thema ausführen: [Aktualisieren von Windows-Geräten auf Windows Pro Creators Update](upgrade-to-windows-pro-creators-update.md).
  
Lesen [Sie "Überprüfen, ob das Gerät mit Azure AD verbunden ist",](#verify-the-device-is-connected-to-azure-ad) um zu überprüfen, ob Sie über das Upgrade verfügen, oder um sicherzustellen, dass das Upgrade funktioniert hat.

## <a name="watch-connect-your-pc-to-microsoft-365-business"></a>Watch: Verbinden Ihres PCs an Microsoft 365 Business

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3yXh3] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und diejenigen, für die Microsoft 365 neu ist](../business-video/index.yml) an.
  
## <a name="join-windows-10-devices-to-your-organizations-azure-ad"></a>Verbinden von Windows 10-Geräten in Ihrer Organisation mit Azure AD

Wenn alle Windows Geräte in Ihrer Organisation entweder auf Windows 10 Pro Creators Update aktualisiert wurden oder bereits Windows 10 Pro Creators Update ausgeführt werden, können Sie diese Geräte dem Azure Active Directory Ihrer Organisation hinzufügen. Sobald die Geräte verbunden sind, werden sie automatisch auf Windows 10 Business aktualisiert, das Teil Ihres Microsoft 365 Business Premium-Abonnements ist.
  
### <a name="for-a-brand-new-or-newly-upgraded-windows-10-pro-device"></a>Ganz neue oder neu aktualisierte Windows 10 Pro-Geräte

Führen Sie für ganze neue Geräte mit Windows 10 Pro Creators Update oder für Geräte, die auf Windows 10 Pro Creators Update aktualisiert wurden, für die die Windows 10-Geräteinstallation jedoch noch nicht ausgeführt wurde, die folgenden Schritte aus.
  
1. Führen Sie die Windows 10-Geräteinstallation aus, bis die Seite **Wie soll das Setup erfolgen** angezeigt wird. 
    
    ![On the How would you like to set up page, choose Set up for an organization](../media/1b0b2dba-00bb-4a99-a729-441479220cb7.png)
  
2. Wählen Sie hier **"Für eine Organisation einrichten"** aus, und geben Sie dann Ihren Benutzernamen und Ihr Kennwort für Microsoft 365 Business Premium ein. 
    
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
  
6. Überprüfen Sie auf der Seite **"Sicherstellen, dass dies Ihre Organisation ist",** ob die Informationen korrekt sind, und wählen Sie **"Beitreten"** aus.
  
   Klicken Sie auf der Seite **Sie sind fertig!** page, chosse **Done**.
  
   ![Wählen Sie auf dem Bildschirm "Make sure this is your organization" die Option "Beitreten" aus.](../media/c749c0a2-5191-4347-a451-c062682aa1fb.png)
  
Wenn Sie Dateien nach OneDrive for Business hochgeladen haben, synchronisieren Sie diese wieder. Wenn Sie ein Drittanbietertool zum Migrieren von Profilen und Dateien verwendet haben, synchronisieren Sie diese ebenfalls mit dem neuen Profil.
  
## <a name="verify-the-device-is-connected-to-azure-ad"></a>Stellen Sie sicher, dass das Gerät mit Azure AD verbunden ist

Um Ihren Synchronisierungsstatus zu überprüfen, wählen Sie auf der Seite **"Arbeit oder Schule** zugreifen" in **Einstellungen** den Bereich **Verbunden mit** _ _ \<organization name\> aus, um die Schaltflächen **"Info"** und **"Trennen"** verfügbar zu machen. Wählen Sie **"Info"** aus, um den Synchronisierungsstatus abzurufen. 
  
Wählen Sie auf der Seite **"Synchronisierungsstatus"** die Option **"Synchronisieren"** aus, um die neuesten Richtlinien für die Verwaltung mobiler Geräte auf dem PC abzurufen.
  
To start using the Microsoft 365 Business Premium account, go to the Windows **Start** button, right-click your current account picture, and then **Switch account**. Melden Sie sich mit der E-Mail-Adresse und dem Kennwort Ihrer Organisation an.
  
![Click Info button to view synchronization status](../media/818f7043-adbf-402a-844a-59d50034911d.png)
  
## <a name="verify-the-pc-is-upgraded-to-windows-10-business"></a>Überprüfen Sie, ob der PC auf Windows 10 Business aktualisiert wurde.

Stellen Sie sicher, dass Ihre in Azure AD eingebundenen Windows 10 Geräte im Rahmen Ihres Microsoft 365 Business Premium-Abonnements auf Windows 10 Business aktualisiert werden.
  
1. Wechseln Sie zu **Einstellungen** \> **System** \> **Info**.
    
2. Überprüfen Sie, ob unter **Edition** **Windows 10 Business** angezeigt wird.
    
    ![Verify that Windows edition is Windows 10 Business.](../media/ff660fc8-d3ba-431b-89a5-f5abded96c4d.png)
  
## <a name="next-steps"></a>Nächste Schritte

Informationen zum Einrichten Ihrer mobilen Geräte finden Sie unter ["Einrichten mobiler Geräte für Microsoft 365 Business Premium Benutzer".](set-up-mobile-devices.md)Informationen zum Festlegen von Richtlinien zum Geräteschutz oder zum Schutz von Apps finden Sie unter [Verwalten Microsoft 365 für Unternehmen.](manage.md)
  
## <a name="related-content"></a>Verwandte Inhalte

[Microsoft 365 für Business-Schulungsvideos](../business-video/index.yml) (Linkseite)
