---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
f1.keywords:
- NOCSH
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
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Überprüfen Sie die Microsoft 365 Business Premium-App-Schutzeinstellungen auf Windows 10-Geräten, und vergewissern Sie sich, dass Benutzer keine Unternehmensdaten in persönliche Dateien oder nicht verwaltete Apps kopieren können.
ms.openlocfilehash: e319ffa5149f055b5de45078facc8899acffc223
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579860"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf Unternehmensgeräten kopieren können

Nachdem Sie [App-Schutzrichtlinien eingerichtet haben](protection-settings-for-windows-10-devices.md), kann es einige Stunden dauern, bis die Richtlinie für die Geräte der Benutzer wirksam wird. Wenn Sie  die Einstellung Benutzer am Kopieren von Unternehmensdaten in persönliche Dateien hindern aktiviert haben und sie zwingen, Arbeitsdateien auf **OneDrive for #A0** für Geräte im Besitz des Unternehmens zu speichern, können Sie dies auf dem Gerät des Benutzers überprüfen, nachdem sie mit Azure AD verbunden und angemeldet sind. 
  
 **Überprüfen der Verbindungseinstellungen**
  
1. Nachdem Sie sich mit Microsoft 365 Business Premium-Anmeldeinformationen angemeldet haben und eine Verbindung mit Azure AD hergestellt haben, wie unter Einrichten von Windows-Geräten für [Microsoft 365 Business Premium-Benutzer](set-up-windows-devices.md)beschrieben, wechseln Sie zu **Windows Settings** \> **Accounts** \> **Access work or school**. Wählen **Sie Verbunden mit Azure \<tenant name\> AD** aus, und wählen Sie dann **Info aus.**
    
    ![Click or tap Info on the Connected to Azure AD dialog.](../media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Auf der **Seite Verwaltet nach** sehen Sie die Verbindungsinformationen, die eine \<tenant name\> **Verwaltungsserveradresse** wie die in der folgenden Abbildung gezeigte  enthalten. 
    
    ![Managed by page shows connection info of the device manager URL.](../media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Überprüfen, ob Sie Keine Unternehmensdaten in eine nicht verwaltete App einfügen können**
  
1. Öffnen Sie Outlook 2016, das von Microsoft 365 Business Premium installiert wurde.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, die besagt, dass die App nicht auf Inhalte zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf persönlichen Geräten kopieren können

 **Überprüfen der Verbindungseinstellungen**
  
1. Wechseln Sie auf Ihrem persönlichen Windows 10-Gerät, auf dem Sie als lokaler Benutzer angemeldet sind, zu Windows-Einstellungen, und klicken oder tippen Sie auf **KontenZugriff** auf Arbeit oder \> **Schule**.
    
2. Klicken Sie unter **Auf Arbeits- oder Schulkonto zugreifen** auf **Verbinden**.
    
3. Geben Sie Ihre Microsoft 365 Business Premium-Anmeldeinformationen im Dialogfeld Einrichten eines Geschäfts- oder **Schulkontos** \> **anmelden ein.**
    
4. Wählen Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** die Option **Geschäfts-, Schul- oder Unikonto** und dann **Informationen** aus.
    
    ![Klicken oder tippen Sie im Dialogfeld Arbeits- oder Schulkonto auf Info.](../media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Auf der **Seite Arbeits-** oder Schulzugriff sehen Sie die Verbindungsinformationen, die eine  **Verwaltungsserveradresse** wie in der folgenden Abbildung enthalten, und die Wörter *Wip* und *mam* enthalten. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](../media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Überprüfen, ob Sie Keine Unternehmensdaten in eine nicht verwaltete App einfügen können**
  
1. Öffnen Sie Outlook 2016, und fügen Sie bei Bedarf Ihr Microsoft 365 Business Premium-Konto hinzu, und melden Sie sich mit Ihren Microsoft 365 Business Premium-Anmeldeinformationen an.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, die besagt, dass App nicht auf Inhalte zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](../media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    

