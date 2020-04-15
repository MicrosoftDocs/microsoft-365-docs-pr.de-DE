---
title: Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 043807b2-21db-4d5c-b430-c8a6dee0e6ba
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie mehr über die mehrstufige Authentifizierung in Office 365 und die Schritte, die Sie für die Einrichtung durchführen müssen.
ms.openlocfilehash: 715baeb0355ab203e890f2c87cf0751eff69e7f8
ms.sourcegitcommit: dbbdeca5a6cd048e1bde9e820a8b8a0d6022c7a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43503995"
---
# <a name="plan-for-multi-factor-authentication-for-office-365-deployments"></a>Planen der mehrstufigen Authentifizierung für Office 365-Bereitstellungen

[] Bei der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) handelt es sich um eine Authentifizierungsmethode, bei der mehr als eine Überprüfungsmethode verwendet werden muss und Benutzeranmeldungen und Transaktionen eine zweite Sicherheitsebene hinzugefügt wird. Sie erfordert einen zusätzlichen Überprüfungsschritt mit Informationen, die über das Kennwort des Benutzerkontos hinausgehen, beispielsweise:
  
- Ein zufällig generierter Passcode
    
- Ein Telefonanruf
    
- Eine Smartcard (virtuell oder physisch) 
    
- Ein biometrisches Gerät 
    
## <a name="mfa-in-office-365"></a>MFA in Office 365

Office 365 verwendet MFA für zusätzliche Anmeldesicherheit und kann für jedes einzelne Benutzerkonto im Microsoft 365 Admin Center verwaltet werden. Office 365 bietet die folgende Teilmenge der Azure mehrstufigen Authentifizierungsfunktionen als Bestandteilihres Abonnements: 
  
- Möglichkeit zum Aktivieren und Erzwingen von MFA für Endbenutzer
    
- Die Verwendung einer mobilen App - online und mit Einmalkennwort (One-Time Password, OTP) - als zweiten Authentifizierungsfaktor
    
- Die Verwendung eines Telefonanrufs als zweiten Authentifizierungsfaktor
    
- Die Verwendung einer SMS als zweiten Authentifizierungsfaktor
    
- Anwendungs Kennwörter für Clients ohne Browser (beispielsweise die Microsoft lync 2013 Kommunikationssoftware)
    
- Microsoft-Standardbegrüßungen bei Authentifizierungstelefonanrufen
    
Die vollständige Liste der hinzugefügten Features finden Sie unter [Funktionsweise von Azure Multi-Factor Authentication, Funktionsvergleich der Versionen](https://go.microsoft.com/fwlink/?LinkId=506927). Wenn Sie den Azure Multi-Factor Authentication-Dienst erwerben, können Sie den vollen Funktionsumfang nutzen. 
  
Je nachdem, ob Sie über eine Cloud-oder Hybrid Identität für Office 365 oder Verbundauthentifizierung mit Active Directory Verbunddiensten (AD FS) verfügen, erhalten Sie eine andere Teilmenge der Funktionen. 
  
|**Wo verwalten Sie Ihren Office 365 Mandanten?** | **MFA-zweit Faktor Optionen**|

|:-----|:-----| | Nur Cloud  <br/> | Azure-mehrstufige Authentifizierung (Text oder Telefonanruf)  <br/> | | Hybrides Setup, lokal verwaltet  <br/> | Wenn Sie die Benutzeridentität lokal verwalten, haben Sie die folgenden Möglichkeiten:  <br/>  Physische oder virtuelle Smartcard (bei Verwendung von AD FS)  <br/> [Azure-mehr](https://go.microsoft.com/fwlink/p/?LinkId=526677) stufige Authentifizierung (Modul für AD FS)  <br/>  Azure Active Directory (Azure AD) mehrstufige Authentifizierung  <br/> |
   
  
In der folgenden Abbildung wird veranschaulicht, wie die aktualisierten Office 2013-Geräte-Apps (unter Windows) Benutzern das Anmelden mit der MFA ermöglichen. 

![Modern authentication for Office 2013 device apps.](../../media/dc37645c-b899-4715-b162-d7653bd0aebd.png)

Die Office 2013 Geräte-apps unterstützen die mehrstufige Authentifizierung durch die Verwendung der [Active Directory-Authentifizierungsbibliothek (Adal)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure AD hostet eine Webseite, auf der sich Benutzer anmelden können. Der Identitätsanbieter kann Azure AD oder ein Verbundidentitätsanbieter wie AD FS sein. Bei der Authentifizierung für Verbundbenutzer werden die folgenden Schritte ausgeführt:
  
1. Azure AD leitet den Benutzer zu der Anmeldewebseite weiter, die vom im Eintrag vermerkten Identitätsanbieter für den Office 365-Mandanten gehostet wird. Der Identitätsanbieter wird durch die im Anmeldenamen des Benutzers angegebene Domäne bestimmt.
    
2. Der Benutzer meldet sich über sein Gerät auf der Anmeldeseite an. 
    
3. Wenn der Benutzer erfolgreich angemeldet wurde, gibt der Identitätsanbieter ein Token an Azure AD zurück.
    
4. Azure AD gibt ein JSON-Webtoken (JWT) an die Office-Geräte-App zurück, und die Geräte-App wird mithilfe eines JWT mit Office 365 authentifiziert. 
    
  
## <a name="requirements-for-office-2013-client-apps"></a>Anforderungen für Office 2013 Client-apps

Zum Aktivieren der MFA für Office 2013-Client-Apps muss die folgende Software in Abhängigkeit davon installiert sein (die nachstehend aufgeführte oder eine höhere Version), ob Sie über eine [Klick-und-Los-basierte Installationen](#click-to-run-based-installations) oder eine [MSI-basierte Installationen](#msi-based-installations) verfügen.
  
So ermitteln Sie, ob Ihre Office-Installation auf Klick-und-Los oder MSI basiert
  
1. Starten Sie Outlook 2013.
    
2. Wählen Sie im Menü **Datei** die Option **Office-Konto**aus.
    
3. Für Klick-und-Los-Installationen von Outlook 2013 wird der Eintrag **Updateoptionen** angezeigt. Für MSI-basierte Installationen wird der Eintrag **Updateoptionen** nicht angezeigt. 
    
    ![Vorgehensweise feststellen, ob Ihre Office 2013 Installation Klick-und-Los oder MSI-basiert ist](../../media/1e75143f-9e37-4e0c-9610-43a80771571e.png)

Weitere Informationen finden Sie in den [FAQ zum Wiki-Artikel "moderne Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=530064)".
  
### <a name="click-to-run-based-installations"></a>Klick-und-Los-basierte Installationen

Für Klick-und-Los-basierte Installationen muss die folgende Software installiert sein, mit der unten aufgeführten Dateiversion oder einer späteren Dateiversion. Wenn Ihre Dateiversion nicht der aufgeführten Dateiversion entspricht oder höher ist, aktualisieren Sie Ihre Version mithilfe der folgenden Schritte.
  
|**Dateiname**|**Installationspfad auf Ihrem Computer**|**Dateiversion**|
|:-----|:-----|:-----|
|MSO. DLL  <br/> |C:\Programme\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |CSI.DLL C:\Programme\Microsoft Office 15\root\office15\csi.dll  <br/> |15.0.4753.1000  <br/> |
|Groove. exe  <br/> |C:\Programme\Microsoft Office 15\root\office15\GROOVE.exe  <br/> |15.0.4763.1000  <br/> |
|Outlook. exe  <br/> |C:\Programme\Microsoft Office 15\root\office15\OUTLOOK.exe  <br/> |15.0.4753.1002  <br/> |
|Adal. DLL  <br/> |C:\Programme\Microsoft Office 15\root\vfs\ProgramFilesCommonx86\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Programme\Internet Explorer  <br/> |Variierend  <br/> |
   
### <a name="msi-based-installations"></a>MSI-basierte Installationen

Für MSI-basierte Installationen muss die folgende Software mit der unten aufgeführten oder einer höheren Dateiversion installiert sein. Wenn Ihre Dateiversion nicht der aufgeführten Dateiversion entspricht oder höher ist, aktualisieren Sie Ihre Version mithilfe des Links in der Spalte "KB-Artikel aktualisieren".
  
|**Dateiname**|**Installationspfad auf Ihrem Computer**|**Wo das Update abgerufen werden kann**|**Version**|
|:-----|:-----|:-----|:-----|
|MSO. DLL  <br/> |C:\Programme\Gemeinsame Dateien\Microsoft Shared\OFFICE15\MSO.DLL  <br/> |[KB3085480](https://support.microsoft.com/kb/3085480) <br/> |15.0.4753.1001  <br/> |
|CSI. DLL  <br/> |C:\Programme\Gemeinsame Dateien\Microsoft Shared\OFFICE15\Csi.dll  <br/> |[KB3085504](https://support.microsoft.com/kb/3085504) <br/> |15.0.4753.1000  <br/> |
|Groove. exe  <br/> |C:\Programme\Microsoft Office\Office15\GROOVE.EXE  <br/> |[KB3085509](https://support.microsoft.com/kb/3085509) <br/> |15.0.4763.1000  <br/> |
|Outlook. exe  <br/> |C:\Programme\Microsoft Office\Office15\OUTLOOK.EXE  <br/> |[KB3085495](https://support.microsoft.com/kb/3085495) <br/> |15.0.4753.1002  <br/> |
|Adal. DLL  <br/> |C:\Programme\Gemeinsame Dateien\Microsoft Shared\OFFICE15\ADAL.DLL  <br/> |[KB3055000](https://support.microsoft.com/kb/3055000) <br/> |1.0.2016.624  <br/> |
|Iexplore. exe  <br/> |C:\Programme\Internet Explorer  <br/> |[MS14-052](https://support.microsoft.com/kb/2977629) <br/> |Nicht anwendbar  <br/> |
   
## <a name="enable-mfa"></a>Aktivieren von MFA

Führen Sie die folgenden Schritte aus, um MFA für Ihr Office 365-Abonnement zu aktivieren:
  
1. Aktivieren Sie bei Bedarf die [moderne Authentifizierung für Office 2013 auf Windows-Geräten](enable-modern-authentication.md).
    
2. Für die Verbundauthentifizierung richten Sie die Azure Multi-Factor Authentication mit Ihrem Drittanbieter-Verzeichnisdienst ein.
    
    Informationen zu bestimmten Identitätsanbietern, die für dieses Programm akzeptiert werden, finden Sie unter [Erweiterte Szenarien mit mehrstufiger Azure-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) . 
    
3. [Einrichten der mehrstufigen Authentifizierung für Office 365](set-up-multi-factor-authentication.md).
    
4. Informieren Sie die Benutzer darüber, wie Sie [MFA für Ihr Office 365-Benutzerkonto einrichten](https://support.office.com/article/set-up-2-step-verification-for-office-365-ace1d096-61e5-449b-a875-58eb3d74de14). Nachdem Sie Ihre sekundäre Authentifizierungsmethode eingerichtet haben, benötigen Ihre zukünftigen Anmeldungen einen MFA.
    
> [!IMPORTANT]
> Wenn Sie Ihre Benutzer für die Azure-mehrstufige Authentifizierung aktiviert haben und alle Geräte Office 2013 werden, die nicht für die moderne Authentifizierung aktiviert sind, müssen Sie App-Kennwörter verwenden. Weitere Informationen zu app-Kennwörtern und wann/wo/wie Sie verwendet werden sollten, finden Sie hier: [App-Kennwörter mit Azure Multi_Factor-Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=528178). 
  
## <a name="known-issues"></a>Bekannte Probleme
  
[Office 2013 und Office 365 ProPlus moderne Authentifizierung: Wissenswerte vor dem Onboarding](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Beheben von Problemen bei der Azure Multi-Factor Authentication:**
  
Weitere Informationen finden Sie unter [Problembehandlung bei Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Behandlung von Anmeldeproblemen bei der modernen Authentifizierung in Office 2013 bei Verwendung von AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Wenn alternative IDs nicht funktionieren:**
  
[Verwenden von PowerShell zum Korrigieren von doppelten Benutzerprinzipalnamen (User Principal Name, UPN)](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Skript zum Beheben von doppelten Benutzerprinzipalnamen (User Principal Name, UPN)](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Clientzugriffsfilterung:**
  
[Richtlinien für die moderne Authentifizierung und für die Clientzugriffsfilterung in Office 2013 und Office 365 ProPlus: Wichtige Informationen vor dem Onboarding](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Welche Apps unterstützen MFA?**
  
|**Windows**|**Mac**|**iOS**|**Android-Smartphone**|**Android-Tablet**|
|:-----|:-----|:-----|:-----|:-----|
|Die moderne Authentifizierung für Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 und Skype for Business wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word 2016 für Mac, Excel 2016 für Mac und PowerPoint 2016 für Mac wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für iPad, Excel für iPad und PowerPoint für iPad wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für Android, Excel für Android und PowerPoint für Android wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für Android, Excel für Android und PowerPoint für Android wird in dieser Version unterstützt.  <br/> |
|Die moderne Authentifizierung für Outlook 2013 und Outlook 2016 wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Outlook 2016 für Mac wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Outlook für iPad wird in dieser Version unterstützt.  <br/> |||
   

