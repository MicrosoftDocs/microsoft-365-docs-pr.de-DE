---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
f1.keywords:
- NOCSH
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
- MSB365
- MARVEL_SEO_MAR
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Validieren von Microsoft 365 Business App Protection-Einstellungen auf Windows 10-Geräten und sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien oder nicht verwaltete apps kopieren können.
ms.openlocfilehash: 4d3d7e950311ac32606e700ebb35bf026ae091cc
ms.sourcegitcommit: 26e4d5091583765257b7533b5156daa373cd19fe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/06/2020
ms.locfileid: "42549995"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf Unternehmensgeräten kopieren können

Nachdem Sie [App-Schutzrichtlinien eingerichtet haben](protection-settings-for-windows-10-devices.md), kann es einige Stunden dauern, bis die Richtlinie für die Geräte der Benutzer wirksam wird. Wenn Sie das **Kopieren von Unternehmensdaten in persönliche Dateien durch Benutzer verhindern aktiviert haben und Sie zum Speichern von Arbeitsdateien in OneDrive für Unternehmen** Einstellung für unternehmenseigene Geräte zwingen, können Sie dies auf dem Gerät des Benutzers überprüfen, nachdem **Sie eine Verbindung** mit Azure AD hergestellt und sich angemeldet haben. 
  
 **Überprüfen der Verbindungseinstellungen**
  
1. After you sign in with Microsoft 365 Business credentials and connect to Azure AD as described in [Set up Windows devices for Microsoft 365 Business users](set-up-windows-devices.md), go to **Windows Settings** \> **Accounts** \> **Access work or school**. Choose **Connected to \<tenant name\> Azure AD**, and then choose **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Auf der Seite **verwaltet nach** \<Mandantenname\> werden die **Verbindungsinformationen** angezeigt, die eine **Verwaltungs Server Adresse** enthalten, wie in der folgenden Abbildung dargestellt. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Sicherstellen, dass keine Unternehmensdaten in eine nicht verwaltete app eingefügt werden können**
  
1. Öffnen Sie das von Microsoft 365 Business installierte Outlook 2016.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, die besagt, dass die APP nicht auf Inhalte zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf persönlichen Geräten kopieren können

 **Überprüfen der Verbindungseinstellungen**
  
1. Wechseln Sie auf Ihrem persönlichen Windows 10-Gerät, in dem Sie als lokaler Benutzer angemeldet sind, zu **Windows-Einstellungen**, und klicken oder tippen Sie auf **Konten** \> **Zugriff für Arbeit oder Schule**.
    
2. Klicken Sie unter **Auf Arbeits- oder Schulkonto zugreifen** auf **Verbinden**.
    
3. Enter your Microsoft 365 Business credential into the **Set up a work or school account dialog** \> **Sign in**.
    
4. Wählen Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** die Option **Geschäfts-, Schul- oder Unikonto** und dann **Informationen** aus.
    
    ![Klicken oder tippen Sie im Dialogfeld Arbeit oder Schulkonto auf Informationen.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Auf der Seite **Access work oder School** können Sie die **Verbindungsinformationen** sehen, die eine **Verwaltungs Server Adresse** enthalten, wie in der folgenden Abbildung dargestellt, und enthält die Wörter *WIP* und *MAM* in. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Sicherstellen, dass keine Unternehmensdaten in eine nicht verwaltete app eingefügt werden können**
  
1. Öffnen Sie Outlook 2016, und fügen Sie bei Bedarf Ihr Microsoft 365 Business-Konto hinzu. Melden Sie sich dann mit Ihren Microsoft 365 Business-Anmeldeinformationen an.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, dass besagt, dass APP nicht auf Inhalte zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    

