---
title: Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Erfahren Sie, wie Sie Microsoft 365 Business einrichten, indem Sie vier Schritte ausführen.
ms.openlocfilehash: a1c8a41c3e291983276280a063248bdd10a7f85a
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32283901"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten

Führen Sie die Schritte 1-4 unten aus.
  
### <a name="set-up-microsoft-365-business"></a>Einrichten von Microsoft 365 Business

Sehen Sie sich ein Video zum Einrichten von Microsoft 365 Business an, wenn Sie nicht über ein lokales Active Directory verfügen:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
Die Schritte zum Einrichten von Setups beziehen sich auf die lokalen Active Directory-Installationen. Wenn Sie weiterhin auf Domänen verbundene Geräte zugreifen möchten, lesen Sie die folgenden Artikel, um dies zu ermöglichen, und führen Sie die Schritte aus, bevor Sie den Setup-Assistenten ausführen:
  
- [Aktivieren von Domänenbeitritt zu Windows 10-Geräten, die von Microsoft 365 Business verwaltet werden](manage-windows-devices.md)
    
    -Dies ist die empfohlene Methode.
    
- [Zugreifen auf lokale Ressourcen über ein Azure AD-verbundenes Gerät in Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Schritt 1: Personalisieren der Anmeldung

1. Melden Sie sich bei [Microsoft 365 Business](https://portal.microsoft.com) mit ihren globalen Administratoranmeldeinformationen an. Klicken Sie auf die Kachel **Admin**, um zum Admin Center zu wechseln. 
    
2. Wählen Sie **Setup starten** (abhängig von Ihrem Status wird möglicherweise stattdessen die Option **Setup weiter** angezeigt) im Admin Center, um den Assistenten zu starten. 
    
3. Geben Sie den Domänennamen ein, den Sie verwenden möchten (wie contoso.com).
    
    Gehen Sie vor, und geben Sie Ihre Domäne ein, auch wenn Sie dies bei der Verwendung von Azure AD Connect überprüft haben. Die folgenden beiden Schritte gelten nicht für Sie, wenn Sie Azure AD Connect zum Überprüfen Ihrer Domäne verwendet haben.
    
4. Führen Sie die Schritte im Assistenten aus, um [DNS-Einträge bei einem beliebigen DNS-Hostinganbieter für Office 365 zu erstellen](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , der überprüft, ob Sie die Domäne besitzen. 
    
    Sie können sich ein Beispiel Video von [Video ansehen: Einrichten von Office 365 im neuen Admin Center](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Beachten Sie, dass dieses Video nicht die Datenschutz Schritte von Microsoft 365 Business umfasst.
    
    ![Screenshot des Setup-Assistenten für die Business Cloud Suite.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Schritt 2: Hinzufügen von Benutzern und Zuweisen von Lizenzen

1. Sie können Benutzer hinzufügen, oder Sie können später im Admin Center [Benutzer hinzufügen](add-users-m365b.md) . 
    
    Allen Benutzern, die Sie hinzufügen, wird automatisch eine Microsoft 365 Business-Lizenz zugewiesen.
    
2. Wenn Ihr Microsoft 365 Business-Abonnement über vorhandene Benutzer verfügt (beispielsweise, wenn Sie Azure AD Connect verwendet haben), erhalten Sie jetzt die Option, Ihnen Lizenzen zuzuweisen. Gehen Sie vor, und fügen Sie Lizenzen hinzu.
    
3. Außerdem erhalten Sie eine Option zum Freigeben von Anmeldeinformationen für die neuen Benutzer, die Sie hinzugefügt haben. Sie können auswählen, ob Sie Sie ausdrucken, per e-Mail versenden oder herunterladen möchten.
    
4. Überspringen Sie die Migration von e-Mail-Nachrichten, und wählen Sie **weiter** auf Seite **e-Mails migrieren** . 
    
    Wenn Sie von einem anderen e-Mail-Anbieter wechseln und Ihre Daten später kopieren möchten, können Sie [e-Mails und Kontakte zu Office 365 migrieren](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot von zwei neuen Benutzern, die im Setup-Assistenten hinzugefügt wurden](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Schritt 3: Verbinden Ihrer Domäne

> [!NOTE]
> Wenn Sie die. onmicrosoft-Domäne oder Azure AD Connect verwendet haben, wird dieser Schritt nicht angezeigt. 
  
Um Dienste einzurichten, müssen Sie einige Datensätze bei Ihrem DNS-Host oder Ihrer Domänenregistrierungsstelle aktualisieren.
  
1. Der Setup-Assistent erkennt in der Regel Ihre Registrierungsstelle und gibt Ihnen einen Link zu Schritt-für-Schritt-Anweisungen zum Aktualisieren Ihrer NS-Einträge auf der Registrierungsstelle. Wenn dies nicht der Fall ist, [Ändern Sie die Namenserver, um Office 365 für eine beliebige Domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2)einzurichten.
    
2. E-Mails und andere Dienste werden für Sie eingerichtet.
    
### <a name="step-4-manage-devices-and-work-files"></a>Schritt 4: Verwalten von Geräten und Arbeitsdateien

1. Schützen Sie auf der Seite **Arbeitsdateien auf Ihren mobilen Geräten schützen** sowohl **Arbeitsdateien bei Verlust oder Diebstahl von Geräten** , und verwalten Sie, **wie Benutzer auf Office-Dateien auf mobilen Geräte** Einstellungen auf **on**zugreifen. Sie können auch auf jede unter Einstellung zugreifen, indem Sie auf die Chevrons neben jeder Einstellung klicken.
  
  Alle Arbeitsdateien ihrer lizenzierten Benutzer sind jetzt auf iOS-und Android-Geräten geschützt, sobald Sie [Office-Apps installieren](set-up-mobile-devices.md) (und sich mit ihren Microsoft 365 Business-Anmeldeinformationen authentifizieren). 
  
  ![Screenshot von Schutz von Arbeitsdateien auf der Seite "Mobile Geräte"](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Legen Sie auf der Seite **Windows 10-Gerätekonfiguration festlegen** die Einstellung für **sichere Windows 10-Geräte** auf **ein**fest.
  
   Sie können auch auf jede unter Einstellung zugreifen, indem Sie auf das Chevron daneben klicken.
  
3. Legen Sie die Einstellung **Office auf Windows 10-Geräten installieren** auf **Ja** fest, wenn alle Ihre Benutzer Windows 10-Computer und entweder keine vorhandenen Office-Installationen oder Klick-und-Los-Office-Installationen haben. Wenn dies nicht der Fall ist, legen Sie diese Option auf **Nein**fest. Sie können Office später im Admin Center [automatisch installieren](auto-install-or-uninstall-office.md) , nachdem Sie die Benutzer Computer vorbereitet haben. Anweisungen finden Sie unter [Prepare for Office Clientinstallation](prepare-for-office-client-deployment.md).
  
    Die Arbeitsdateien der lizenzierten Benutzer auf Windows 10-Geräten werden projiziert, sobald Sie [Ihr Windows 10-Gerät](set-up-windows-devices.md) mit einer Microsoft 365 Business Azure AD-Domäne verbinden oder [Windows 10 auf einem neuen Computer installieren](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) und gleichzeitig dem Microsoft 365 beitreten. Business Azure AD-Domäne. 
  
4. Klicken Sie auf **weiter** , und Sie sind mit Setup fertig. 
  
    Bitte geben Sie uns Feedback in diesem Schritt, um die Erfahrung zu verbessern.
  
    ![Screenshot der Seite "Vorbereiten von Windows 10-Geräten"](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Zusätzliche Sicherheitseinstellungen

Zusätzlich zur Sicherheits-und Konformitäts Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:
  
- Einrichten des Schutzes vor unsicheren Anlagen. **Erweiterter Bedrohungsschutz** (ATP) identifiziert bösartige Inhalte und blockiert dann die Bereitstellung von unsicheren Anlagen und schützt Sie vor Phishing-Schemata und Ransomware-Infektionen. Informationen zum Aktivieren des Anlagenschutzes finden Sie unter [Einrichten von Office 365 ATP Safe Attachments Policies](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Schützen Sie Ihre Umgebung, wenn Benutzer auf böswillige Links klicken. ATP untersucht Links in e-Mails zu dem Zeitpunkt, zu dem ein Benutzer darauf klickt. Wenn ein Link unsicher ist, wird der Benutzer gewarnt, die Website nicht zu besuchen oder zu benachrichtigen, dass die Website blockiert wurde. Dies schützt vor Phishing-Schemata. Einrichten [von office 365 ATP Safe Links](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) Policies oder [einrichten von Office 365 ATP Safe Links Policies](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Sie können alle Postfachinhalte, einschließlich gelöschter Elemente, beibehalten, indem Sie für ein vollständiges Postfach des Benutzers einen **Rechtsstreit halten**. Weitere Informationen finden Sie unter 
- [Einrichten der e-Mail-Aufbewahrung mit der Exchange Online-Archivierung](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Richten Sie angepasste **Aufbewahrungsrichtlinien**ein, um beispielsweise eine bestimmte Zeitdauer beizubehalten oder Inhalte dauerhaft am Ende des Aufbewahrungszeitraums zu löschen. Sie können angepasste Aufbewahrungsrichtlinien im Securities and Compliance Center aktivieren, zur **Aufbewahrung**von **Datenverwaltung** \> wechseln und dann die Schritte im Assistenten befolgen. Weitere Informationen finden Sie unter [Übersicht über Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Nächste Schritte

Für die Benutzer, die über Ihre Lizenzen verfügen, besteht der nächste Schritt darin, Geräte einzurichten.<br/> Weitere Informationen finden Sie unter [Einrichten von Windows-Geräten für microsoft 365-Geschäftsbenutzer](set-up-windows-devices.md) und [Einrichten von mobilen geräten für Microsoft 365 Business-Benutzer](set-up-mobile-devices.md). <br/>Weitere Informationen finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) für Links zu Themen zum Festlegen von Geräte-und App-Schutzrichtlinien und zum Entfernen von Daten von Benutzergeräten. 
  


