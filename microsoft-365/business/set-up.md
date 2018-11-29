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
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Erfahren Sie, wie Microsoft 365 Business einrichten, indem Sie vier Schritte ausführen.
ms.openlocfilehash: f57239b884bd2e186c0bc01973130a10fa4cfe84
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867565"
---
# <a name="set-up-microsoft-365-business-by-using-the-setup-wizard"></a>Einrichten von Microsoft 365 Business mithilfe des Setup-Assistenten

Führen Sie die Schritte 1 bis 4 unten.
  
### <a name="set-up-microsoft-365-business"></a>Einrichten von Microsoft 365 Business

Sehen Sie sich ein Video über das Microsoft 365 Business einrichten, wenn Sie nicht über einen lokalen Active Directory verfügen:
  
> [!VIDEO https://www.microsoft.com/videoplayer/embed/0705c337-f3e8-4d28-bb6c-530cd28e99f2?autoplay=false]
  
Die Installationsschritte enthalten Informationen für Installationen, die lokale Active Directory enthalten. Wenn Sie weiterhin auf die Domäne eingebundener Geräte zugreifen möchten, lesen Sie die folgenden Artikel für zwei neue Art und Weise aktivieren, und führen Sie die Schritte aus, bevor Sie den Setup-Assistenten ausführen:
  
- [Aktivieren Sie in die Domäne eingebundener Windows 10 Geräte von Microsoft 365 Business verwaltet werden](manage-windows-devices.md)
    
    -Dies ist die empfohlene Option.
    
- [Zugriff auf lokale Ressourcen von einem Azure AD gehörenden Gerät in Microsoft 365 Business](access-resources.md)
    
### <a name="step-1-personalize-sign-in"></a>Schritt 1: Personalisieren Sie-Anmeldung

1. Melden Sie sich mit Ihren Anmeldeinformationen globaler Administrator [Microsoft 365 Business](https://portal.microsoft.com) an. Wählen Sie die Kachel " **Admin** ", fahren Sie mit der Verwaltungskonsole. 
    
2. Wählen Sie **Setup starten** (je nach Ihrem Status mangelndes **Weiter Setup** stattdessen) in der Verwaltungskonsole, um den Assistenten zu starten. 
    
3. Geben Sie den Domänennamen ein, den Sie (wie "contoso.com") verwenden möchten.
    
    Fahren Sie fort, und geben Sie Ihre Domäne, auch wenn Sie es bei Verwendung von Azure Active Directory verbinden, beispielsweise überprüft haben. Die folgenden beiden Schritte gelten nicht für Sie, wenn Sie Azure AD-Verbindung verwendet, um Ihre Domäne zu überprüfen.
    
4. Führen Sie die Schritte im Assistenten zum [Erstellen von DNS-Datensätze an alle DNS-Hostinganbieter für Office 365](https://support.office.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166) , die überprüft, ob Sie die Domäne besitzen. 
    
    Sehen Sie ein Beispiel Video des [Video: Setup Office 365 in der neuen Verwaltungskonsole](https://support.office.com/article/a8c2002a-34bc-4ab3-93d8-9b5156c48bf8). Beachten Sie, dass in diesem Video die Schritte zum Data Protection Microsoft 365 Business nicht enthalten ist.
    
    ![Screenshot des Business Cloud Suite Setup-Assistenten.](media/3c4fd40c-2de1-4a87-8ee0-78d3928c7bb7.png)
  
### <a name="step-2-add-users-and-assign-licenses"></a>Schritt 2: Hinzufügen von Benutzern und Zuweisen von Lizenzen

1. Sie können hier Benutzer hinzufügen, oder können Sie in der Verwaltungskonsole [Benutzer später hinzufügen](add-users-m365b.md) . 
    
    Alle Benutzer, die Sie hinzufügen möchten automatisch Microsoft 365 Business Lizenz zugewiesen.
    
2. Wenn das Microsoft 365 Business-Abonnement umfasst vorhandener Benutzer (beispielsweise, wenn Sie Azure AD-Connect verwendet), erhalten Sie eine Option zum Zuweisen von Lizenzen für diese jetzt. Fahren Sie fort, und fügen Sie Lizenzen für diese ebenfalls.
    
3. Sie erhalten auch eine Option, um Anmeldeinformationen für die neue Benutzer freizugeben, die Sie hinzugefügt haben. Sie können auch auszudrucken, per e-Mail senden oder herunterladen.
    
4. Überspringen Sie migrieren von e-Mail-Nachrichten, und wählen Sie auf der Seite **Migration e-Mail-Nachrichten** **Weiter** . 
    
    Wenn Sie aus einer anderen e-Mail-Anbieter verschieben und Ihre Daten später kopieren möchten, können Sie [e-Mail-Migration und Kontakte zu Office 365](https://support.office.com/article/a3e3bddb-582e-4133-8670-e61b9f58627e).
    
    ![Screenshot des zwei neue Benutzer im Setup-Assistenten hinzugefügt](media/8f729967-5c65-4ceb-b737-18119db40564.png)
  
### <a name="step-3-connect-your-domain"></a>Schritt 3: Verbinden Sie Ihrer Domäne

> [!NOTE]
> Wenn Sie, verwenden Sie die Domäne .onmicrosoft möchten oder Azure AD-Verbindung verwendet, wird dieser Schritt nicht angezeigt. 
  
Um-Dienste einrichten zu können, müssen Sie einige Datensätze an Ihrer DNS-Host oder Domäne Registrierungsstelle zu aktualisieren.
  
1. Der Setup-Assistent wird in der Regel erkennt die zu Ihrer Registrierungsstelle und bietet Ihnen eine Verknüpfung, eine schrittweise Anleitung zum Aktualisieren von Ihrer NS-Datensätzen auf der Website der Registrierungsstelle. Wenn dies nicht der Fall, [Änderung Namens-Server zum Einrichten von Office 365 mit jeder domänenregistrierungsstelle](https://support.office.com/article/a8b487a9-2a45-4581-9dc4-5d28a47010a2).
    
2. E-Mail und andere Dienste werden für Sie eingerichtet werden
    
### <a name="step-4-manage-devices-and-work-files"></a>Schritt 4: Verwalten von Geräten und Arbeitsdateien

1. Seite festlegen auf die **Protect Arbeitsdateien auf Ihren mobilen Geräten** **Protect Arbeitsdateien bei verlorenen oder gestohlenen Geräten sind** und Einstellungen für **den Zugriff von Benutzern auf Office-Dateien auf mobilen Geräten verwalten** auf **aktiviert**. Sie können auch die einzelnen untergeordneten festlegen durch Klicken auf die Richtungspfeile neben jede Einstellung zugreifen.
  
  Alle Ihre lizenzierten Benutzern Arbeitsdateien sind jetzt geschützt auf iOS und Android-Geräte, sobald sie [Installieren von Office-apps](set-up-mobile-devices.md) (und die Authentifizierung mit den Anmeldeinformationen ihres Microsoft 365 Business). 
  
  ![Screenshot des schützen Arbeitsdateien auf der Seite für mobile Geräte](media/3139a9aa-6228-4e74-8166-c6a886d7319f.PNG)
  
2. Setzen Sie **Secure Windows 10 Geräte** Einstellung auf **aktiviert**, auf der Seite **Gerätekonfiguration Windows 10 festgelegt** .
  
   Sie können auch die einzelnen untergeordneten festlegen durch Klicken auf den Doppelpfeil daneben zugreifen.
  
3. Legen Sie die Einstellung für die **Installation von Office auf Windows 10 Geräte** auf **Ja** , wenn alle Benutzer verfügen über Windows 10 Computer und entweder keine vorhandenen Office installiert, oder Klick-und-Los-Office-Installationen. Wenn dies nicht der Fall ist, legen Sie diese Option auf **Nein**. Sie können später aus dem Administrationscenter [automatisch installieren von Office](auto-install-or-uninstall-office.md) , nachdem Sie auf dem Computer des Benutzers vorbereitet haben. Anweisungen finden Sie unter [Vorbereiten der Installation von Office-Client](prepare-for-office-client-deployment.md).
  
    Sobald sie die lizenzierte Benutzer Arbeitsdateien auf Geräten mit Windows 10 projiziert werden für eine Microsoft 365 Business Azure AD-Domäne oder [Windows 10 auf einem neuen Computer installieren](https://support.office.com/article/c654bd23-d256-4ac7-8fba-0c993bf5a771.aspx) , während gleichzeitig teilnehmen an der Microsoft 365 [Teilnehmen an ihrem Windows-10-Gerät](set-up-windows-devices.md) Business Azure AD-Domäne. 
  
4. Klicken Sie auf **Weiter** und Sie mit dem Setup fertig sind. 
  
    Lassen Sie uns Feedback an dieser Stelle zu helfen, der zu optimieren.
  
    ![Screenshot von vorbereiten Windows 10 Geräte-Seite](media/bff701c1-48a3-44f4-aa95-9d959d57c85b.PNG)
  
## <a name="additional-security-settings"></a>Zusätzliche Sicherheitseinstellungen

Zusätzlich zu den Sicherheit und Compliance-Einstellung im Setup-Assistenten können Sie auch die folgenden zusätzlichen Einstellungen einrichten:
  
- Einrichten von Schutz gegen unsichere Anlagen. **Erweiterte Schutz** (ATP) identifiziert schädlichem Inhalt und klicken Sie dann blockiert die Übermittlung von unsicheren Anlagen Schutz gegen Phishing-Methoden und Ransomware Infektionen. Zum Schutz der Anlage zu aktivieren, finden Sie unter [Einrichten von Richtlinien für Office 365 ATP sichere Anlagen](https://support.office.com/article/078eb946-819a-4e13-8673-fe0c0ad3a775#setpolicy).
    
- Schützen Sie Ihre Umgebung aus, wenn Benutzer auf böswillige Links klicken. ATP untersucht Links in e-Mails an die Zeit, die ein Benutzer darauf klickt. Wenn eine Verknüpfung nicht sicher ist, wird der Benutzer gewarnt, nicht auf die Website zugreifen oder darüber informiert, dass die Website blockiert wurde. Dies bietet Schutz vor Phishing-Methoden. [Einrichten von Richtlinien für sichere Links zu Office 365 ATP](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#reveddefaultscc) oder [Richten Sie sichere Links zu Office 365 ATP-Richtlinien](https://support.office.com/article/bdd5372d-775e-4442-9c1b-609627b94b5d#addemailpolscc).
    
- Sie können den gesamten Inhalt des Postfachs einschließlich gelöschte Elemente durch die Bereitstellung der gesamte Postfach eines Benutzers auf **Rechtsstreitigkeiten halten**beibehalten. Anweisungen finden Sie unter 
- [Einrichten von e-Mail-Archivierung mit Exchange Online-Archivierung](security-features.md#set-up-email-retention-with-exchange-online-archiving).
    
- Einrichten von benutzerdefinierten **Aufbewahrungsrichtlinien**, beispielsweise für eine bestimmte Zeitspanne beibehalten oder Löschen von Inhalt dauerhaft am Ende des Aufbewahrungszeitraums. Sie können benutzerdefinierte Aufbewahrungsrichtlinien in die Sicherheit und Compliance Center, klicken Sie auf **Daten Governance** aktivieren \> **Aufbewahrung**, und folgen Sie den Schritten im Assistenten. Finden Sie weitere Informationen finden Sie unter [Overview of Aufbewahrungsrichtlinien](https://support.office.com/article/5e377752-700d-4870-9b6d-12bfc12d2423).
    
## <a name="next-steps"></a>Nächste Schritte

Für Benutzer, die ihre Lizenzen haben, ist im nächste Schritt richten Sie Geräte ein.<br/> Finden Sie unter [Einrichten von Windows-Geräte für Microsoft 365 Geschäftsbenutzer](set-up-windows-devices.md) und [Einrichten von mobilen Geräten für Microsoft 365 Geschäftsbenutzer](set-up-mobile-devices.md). <br/>Finden Sie unter [Verwalten von Microsoft 365 Business](manage.md) Richtlinien von Links zu Themen über das Gerät und app-Schutz festlegen und wie Sie Daten von Benutzer-Geräten zu entfernen. 
  


