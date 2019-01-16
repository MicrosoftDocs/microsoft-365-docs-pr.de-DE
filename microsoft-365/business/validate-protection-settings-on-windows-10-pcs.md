---
title: Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: fae8819d-7235-495f-9f07-d016f545887f
description: Erfahren Sie, wie Microsoft 365 Business app Protection Settings in Windows-10-Geräte zu überprüfen.
ms.openlocfilehash: f00dd380103ad9498d77b0e8814bace3de168df4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26867966"
---
# <a name="validate-app-protection-settings-on-windows-10-pcs"></a>Überprüfen der Einstellungen für den App-Schutz auf Windows 10-PCs

## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-corporate-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf Unternehmensgeräten kopieren können

Nachdem Sie [App-Schutzrichtlinien eingerichtet haben](protection-settings-for-windows-10-devices.md), kann es einige Stunden dauern, bis die Richtlinie für die Geräte der Benutzer wirksam wird. Wenn Sie die Einstellung **Benutzer daran hindern, Unternehmensdaten in persönliche Dateien zu kopieren und Benutzer zum Speichern aller Arbeitsdateien auf OneDrive for Business zwingen** für dem Unternehmen gehörende Geräte **aktiviert** haben, können Sie dies auf dem Gerät des Benutzers überprüfen, nachdem dieser die Verbindung mit Azure AD hergestellt und sich angemeldet hat. 
  
 **Überprüfen der Verbindungseinstellungen**
  
1. Nachdem Sie die melden Sie sich mit Microsoft 365 Business Anmeldeinformationen und wie unter [Einrichten von Geräten für Microsoft 365 Geschäftsbenutzer Windows](set-up-windows-devices.md)Azure AD verbinden, wechseln Sie zur **Windows-Einstellungen** \> **Konten** \> **Access Arbeit "oder" School **. Wählen Sie **verbunden mit \<Mandantennamen\> Azure AD**, und klicken Sie dann auf **Info**.
    
    ![Click or tap Info on the Connected to Azure AD dialog.](media/a36ede2b-d1a0-4d4e-8ea7-af39b4b63890.png)
  
2. Auf der Seite **Verwaltet von** \<Mandantenname\> werden die **Verbindungsinformationen** angezeigt, die eine **Verwaltungsserveradresse** enthalten, wie in der folgenden Abbildung dargestellt. 
    
    ![Managed by page shows connection info of the device manager URL.](media/47515a8e-2d0c-4bea-99f0-6b2545b88a11.png)
  
 **Sicherstellen, dass keine Unternehmensdaten in nicht verwaltete Apps eingefügt werden können**
  
1. Öffnen Sie das von Microsoft 365 Business installierte Outlook 2016.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, die besagt, dass die App nicht auf den Inhalt zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    
## <a name="verify-that-users-cannot-copy-company-data-to-personal-files-on-personal-devices"></a>Sicherstellen, dass Benutzer keine Unternehmensdaten in persönliche Dateien auf persönlichen Geräten kopieren können

 **Überprüfen der Verbindungseinstellungen**
  
1. Wechseln Sie auf Ihrem persönlichen Windows 10 Gerät, auf dem Sie als lokaler Benutzer angemeldet sind, zu **Windows-Einstellungen**, und klicken oder tippen Sie auf **Konten** \> **Auf Arbeits- oder Schulkonto zugreifen**.
    
2. Klicken Sie unter **Auf Arbeits- oder Schulkonto zugreifen** auf **Verbinden**.
    
3. Geben Sie die Anmeldeinformationen für das Microsoft 365 Business in der **Richten Sie ein Arbeit oder Schule Konto Dialogfeld** \> **Anmelden**.
    
4. Wählen Sie auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** die Option **Geschäfts-, Schul- oder Unikonto** und dann **Informationen** aus.
    
    ![Click or tap Info on the Work or school account dalog.](media/63bd8b32-cb32-4afa-8ce0-6070ac403abc.png)
  
5. Auf der Seite **Auf Arbeits- oder Schulkonto zugreifen** werden die **Verbindungsinformationen** angezeigt, die eine **Verwaltungsserveradresse** wie die in der folgenden Abbildung dargestellte Adresse mit den Zeichenfolgen  *wip*  und  *mam*  enthalten. 
    
    ![Managed by page shows connection info URL that includes the words mam and wpi.](media/abd4eaf4-44fa-4538-a3e8-1e0d331dfe1e.png)
  
 **Sicherstellen, dass keine Unternehmensdaten in nicht verwaltete Apps eingefügt werden können**
  
1. Öffnen Sie Outlook 2016, und fügen Sie bei Bedarf Ihr Microsoft 365 Business-Konto hinzu. Melden Sie sich dann mit Ihren Microsoft 365 Business-Anmeldeinformationen an.
    
2. Öffnen Sie eine E-Mail, und kopieren Sie einige Inhalt daraus.
    
    Öffnen Sie den Editor, und versuchen Sie, den Inhalt einzufügen.
    
    Sie erhalten eine Fehlermeldung, die besagt, dass die App nicht auf den Inhalt zugreifen kann.
    
    ![A dialog that states app can't access content when you paste into an unmanaged app.](media/5e82b154-cf2f-43c8-ae80-b45d8ad80e56.png)
  
    Sie können den gleichen Inhalt jedoch in Word 2016 einfügen.
    

