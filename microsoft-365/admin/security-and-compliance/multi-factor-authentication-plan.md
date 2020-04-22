---
title: Planen der mehrstufigen Authentifizierung für Microsoft 365-Bereitstellungen
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
description: Erfahren Sie mehr über die mehrstufige Authentifizierung in Microsoft 365 und die Schritte, die Sie für die Einrichtung durchführen müssen.
ms.openlocfilehash: 035a79c9db44990dbce09de540e3e483b3cea8df
ms.sourcegitcommit: 7c0470fd7a98911d142bac060c228947c46a6be7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2020
ms.locfileid: "43665668"
---
# <a name="plan-for-multi-factor-authentication-for-microsoft-365-deployments"></a>Planen der mehrstufigen Authentifizierung für Microsoft 365-Bereitstellungen

[] Bei der mehrstufigen Authentifizierung (Multi-Factor Authentication, MFA) handelt es sich um eine Authentifizierungsmethode, bei der mehr als eine Überprüfungsmethode verwendet werden muss und Benutzeranmeldungen und Transaktionen eine zweite Sicherheitsebene hinzugefügt wird. Sie erfordert einen zusätzlichen Überprüfungsschritt mit Informationen, die über das Kennwort des Benutzerkontos hinausgehen, beispielsweise:
  
- Ein zufällig generierter Verifizierungscode, der an Ihr Smartphone gesendet wird
    
- Ein Telefonanruf
    
- Eine Smartcard (virtuell oder physisch) 
    
- Ein biometrisches Gerät 
    
## <a name="mfa-in-microsoft-365"></a>MFA in Microsoft 365

Microsoft 365 verwendet MFA, um die zusätzliche Sicherheit bereitzustellen, und wird über das Microsoft 365 Admin Center verwaltet. Microsoft 365 bietet die folgende Teilmenge der [Azure mehrstufigen Authentifizierungs](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks) Funktionen als Teil des Abonnements an: 
  
- Möglichkeit zum Aktivieren und Erzwingen von MFA für Endbenutzer
    
- Die Verwendung einer mobilen App - online und mit Einmalkennwort (One-Time Password, OTP) - als zweiten Authentifizierungsfaktor
    
- Die Verwendung eines Telefonanrufs als zweiten Authentifizierungsfaktor
    
- Die Verwendung einer SMS-Textnachricht (Short Message Service) als zweiter Authentifizierungs Faktor
    
- Anwendungs Kennwörter für Clients ohne Browser (beispielsweise die Microsoft lync 2013 Kommunikationssoftware)
    
- Microsoft-Standardbegrüßungen bei Authentifizierungstelefonanrufen
    
Eine vollständige Liste der hinzugefügten Features finden Sie unter [Azure Multi-Factor Authentication](https://go.microsoft.com/fwlink/?LinkId=506927). Sie können die vollständige Funktionalität immer erhalten, indem Sie [Azure Multi-Factor Authentication licenses](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-licensing)kaufen. 
  
Sie erhalten eine andere Teilmenge von Funktionen, je nachdem, ob Sie nur die Cloud-Identität verwenden, bei der die Benutzerkonten in Microsoft 365 vorhanden sind, oder Hybride mit einmaligem Anmelden und Active Directory Verbunddiensten (AD FS) einrichten. 
  
|**Wo wird Microsoft 365 verwaltet?**|**MFA-Optionen für den zweiten Authentifizierungsfaktor**|
|:-----|:-----|
|Nur für die Cloud  <br/> | Azure-mehrstufige Authentifizierung (Text oder Telefonanruf)  <br/> |
|Hybride Einrichtung, lokal verwaltet  <br/> | Wenn Sie Benutzeridentitäten lokal verwalten, sind die folgenden Optionen verfügbar:  <br/> -Physische oder virtuelle Smartcard (AD FS)  <br/> -Azure Multi-Factor Authentication (Modul für AD FS)  <br/>  -Azure-mehrstufige Authentifizierung  <br/> |
   
Die Office 2013 Geräte-apps unterstützen MFA durch die Verwendung der [Active Directory-Authentifizierungsbibliothek (Adal)](https://go.microsoft.com/fwlink/p/?LinkId=526684). Azure Active Directory (Azure AD) hostet eine Webseite, auf der sich Benutzer anmelden können. Der Identitätsanbieter kann Azure AD oder ein Verbundidentitätsanbieter wie AD FS sein. Bei der Authentifizierung für Verbundbenutzer werden die folgenden Schritte ausgeführt:
  
1. Azure AD leitet den Benutzer auf die Anmeldewebseite um, die vom Identitätsanbieter des Datensatzes für die Organisation gehostet wird. Der Identitätsanbieter wird durch die im Anmeldenamen des Benutzers angegebene Domäne bestimmt.
    
2. Der Benutzer meldet sich über sein Gerät auf der Anmeldeseite an. 
    
3. Wenn der Benutzer erfolgreich angemeldet wurde, gibt der Identitätsanbieter ein Token an Azure AD zurück.
    
4. Azure AD gibt ein JSON-webtoken (JWT) an die Office-Geräte-app zurück, und die Geräte-APP wird mithilfe eines JWT mit Microsoft 365 authentifiziert. 
    
  
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

Führen Sie die folgenden Schritte aus, um MFA für Ihr Abonnement zu aktivieren:
  
1. Bei Bedarf: 

  - [Aktivieren Sie die moderne Authentifizierung für Office 2013 auf Windows-Geräten](enable-modern-authentication.md).
    
  - Einrichten der Azure-mehrstufigen Authentifizierung mit Verzeichnisdiensten von Drittanbietern.
    
    Informationen zu bestimmten Identitätsanbietern, die für dieses Programm akzeptiert werden, finden Sie unter [Erweiterte Szenarien mit mehrstufiger Azure-Authentifizierung und VPN-Lösungen von Drittanbietern](https://docs.microsoft.com/azure/active-directory/authentication/howto-mfaserver-nps-vpn) . 
    
2. [Einrichten von MFA für Microsoft 365](set-up-multi-factor-authentication.md).
    
3. Einzelnen Benutzern mitteilen, wie Sie sich über MFA anmelden. Weitere Informationen finden Sie unter [Anmelden bei Microsoft 365 mit MFA](https://support.office.com/en-us/article/sign-in-to-microsoft-365-with-2-step-verification-2b856342-170a-438e-9a4f-3c092394d3cb).

> [!IMPORTANT]
> Wenn Sie Ihre Benutzer für die Azure-mehrstufige Authentifizierung aktiviert haben und auf Geräten Office 2013, die nicht für die moderne Authentifizierung aktiviert sind, muss Wörtern auf diesen Geräten verwendet werden. Weitere Informationen zu Wörtern und wann/wo/wie Sie verwendet werden sollten, finden Sie hier: [App-Kennwörter mit mehrstufiger Azure-Authentifizierung](https://go.microsoft.com/fwlink/p/?LinkId=528178).
  
## <a name="faq"></a>Häufig gestellte Fragen

[Häufig gestellte Fragen zur modernen Authentifizierung (Wiki-Artikel)](https://go.microsoft.com/fwlink/p/?LinkId=530064)
  
## <a name="known-issues"></a>Bekannte Probleme

[Office 2013-und Microsoft 365-Apps für moderne Authentifizierung in Unternehmen: wichtige Informationen vor dem Onboarding](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Beheben von Problemen bei der Azure Multi-Factor Authentication:**
  
Weitere Informationen finden Sie unter [Problembehandlung bei Azure Multi-Factor Authentication](https://support.microsoft.com/help/2937344/troubleshooting-azure-multi-factor-authentication-issues).
  
[Behandlung von Anmeldeproblemen bei der modernen Authentifizierung in Office 2013 bei Verwendung von AD FS](https://support.microsoft.com/kb/3052203/)
  
 **Wenn alternative IDs nicht funktionieren:**
  
[Verwenden von PowerShell zum Korrigieren von doppelten Benutzerprinzipalnamen (User Principal Name, UPN)](https://go.microsoft.com/fwlink/p/?LinkId=396730)
  
[Skript zum Beheben von doppelten Benutzerprinzipalnamen (User Principal Name, UPN)](https://go.microsoft.com/fwlink/p/?LinkId=396725)
  
 **Clientzugriffsfilterung:**
  
[Office 2013 und Microsoft 365 apps for Enterprise modern Authentication and Client Access Filtering Policies: Wissenswerte Informationen vor dem Onboarding](https://social.technet.microsoft.com/wiki/contents/articles/30214.office-2013-and-office-365-proplus-modern-authentication-things-to-know-before-onboarding.aspx)
  
 **Welche Apps unterstützen MFA?**
  
|**Windows**|**Mac**|**iOS**|**Android-Smartphone**|**Android-Tablet**|
|:-----|:-----|:-----|:-----|:-----|
|Die moderne Authentifizierung für Word 2013, Word 2016, Excel 2013, Excel 2016, PowerPoint 2013, PowerPoint 2016, OneNote 2013, OneNote 2016, Project 2013, Project 2016, Visio 2013, Visio 2016, Lync 2013 und Skype for Business wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word 2016 für Mac, Excel 2016 für Mac und PowerPoint 2016 für Mac wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für iPad, Excel für iPad und PowerPoint für iPad wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für Android, Excel für Android und PowerPoint für Android wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Word für Android, Excel für Android und PowerPoint für Android wird in dieser Version unterstützt.  <br/> |
|Die moderne Authentifizierung für Outlook 2013 und Outlook 2016 wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Outlook 2016 für Mac wird in dieser Version unterstützt.  <br/> |Die moderne Authentifizierung für Outlook für iPad wird in dieser Version unterstützt.  <br/> |||
   

