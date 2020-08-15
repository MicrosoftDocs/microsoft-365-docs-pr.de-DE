---
title: Funktionsweise der modernen Authentifizierung in Office 2013- und Office 2016-Client-Apps
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/1/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- MED150
- GMA150
- GPA150
- GEA150
- BCS160
ms.assetid: e4c45989-4b1a-462e-a81b-2a13191cf517
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie die modernen Authentifizierungsfunktionen von Microsoft 365 für Office 2013-und 2016-Client-apps anders funktionieren.
ms.openlocfilehash: 62aa04e295c2734d705f22bd2f62c6bc5e622426
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690842"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Funktionsweise der modernen Authentifizierung für Office 2013-, Office 2016-und Office 2019-Client-apps

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Lesen Sie diesen Artikel, um zu erfahren, wie Office 2013-, Office 2016-und Office 2019-Client-apps moderne Authentifizierungsfunktionen basierend auf der Authentifizierungskonfiguration des Microsoft 365-Mandanten für Exchange Online, SharePoint Online und Skype for Business Online verwenden.

> [!NOTE]
> Ältere Client-apps wie Office 2010 und Office für Mac 2011 unterstützen keine moderne Authentifizierung und können nur mit der Standardauthentifizierung verwendet werden.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Verfügbarkeit moderner Authentifizierung für Microsoft 365-Dienste

Für die Microsoft 365-Dienste lautet der Standardstatus der modernen Authentifizierung wie folgt:
  
- Standardmäßig **aktiviert für Exchange Online** . Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der modernen Authentifizierung in Exchange Online](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) , um Sie zu deaktivieren. 
    
- Standardmäßig **aktiviert für SharePoint Online** . 
    
- Standardmäßig **aktiviert für Skype for Business Online** . Weitere Informationen finden Sie unter [Aktivieren von Skype for Business Online für die moderne Authentifizierung ](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx), um Sie zu deaktivieren.

> [!NOTE]
> Für Mandanten, die **vor** dem 1. August 2017 erstellt wurden, ist die moderne Authentifizierung für Exchange Online und Skype for Business Online standardmäßig **deaktiviert**.
    
## <a name="sign-in-behavior-of-office-client-apps"></a>Anmeldeverhalten von Office-Client-apps

Office 2013-Client-apps unterstützen standardmäßig die Legacy Authentifizierung. Legacy bedeutet, dass Sie entweder den Microsoft Online-Anmelde Assistenten oder die Standardauthentifizierung unterstützen. Damit diese Clients moderne Authentifizierungsfeatures verwenden können, muss der Windows-Client Registrierungsschlüssel festgelegt haben. Anweisungen finden Sie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910).

Um moderne Authentifizierung bei Geräten unter Windows (beispielsweise auf Laptops und Tablets) zu aktivieren, auf denen Microsoft Office 2013 installiert ist, müssen Sie die nachstehenden Registrierungsschlüssel festlegen. Die Schlüssel müssen auf jedem Gerät festgelegt werden, das Sie für moderne Authentifizierung aktivieren möchten:
  
|**Registrierungsschlüssel**|**Type**|**Wert** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1  |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1 |
  
Erfahren Sie, wie Sie die [moderne Authentifizierung (Adal) mit Skype for Business verwenden](https://go.microsoft.com/fwlink/p/?LinkId=785431) , um sich mit der Funktionsweise von Skype for Business vertraut zu machen. 
  
Office 2016-und Office 2019-Clients unterstützen standardmäßig die moderne Authentifizierung, und es ist keine Aktion erforderlich, damit der Client diese neuen Flows verwendet. Für die Verwendung der Legacy Authentifizierung ist jedoch eine explizite Aktion erforderlich.
  
Klicken Sie auf die Links unten, um zu sehen, wie Office 2013-, Office 2016-und Office 2019-Clientauthentifizierung mit den Microsoft 365-Diensten funktioniert, je nachdem, ob die moderne Authentifizierung aktiviert ist oder nicht.
  
- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)
    
- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)
    
- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)
    
<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016-und Office 2019-Client-apps beschrieben, wenn Sie eine Verbindung mit Exchange Online mit oder ohne moderne Authentifizierung herstellen.
  
|Version des Office-Client-App * * * *|Registrierungsschlüssel vorhanden? * * * *|Moderne Authentifizierung auf? * * * *|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten (Standard) * * * *|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Erzwingt moderne Authentifizierung für Outlook 2013, 2016 oder 2019. <br/> [Weitere Informationen](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Erzwingt moderne Authentifizierung innerhalb des Outlook-Clients.<br/> |
|Office 2019  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2016  <br/> |Nein <br> AlwaysUseMSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Erzwingt moderne Authentifizierung auf 2013, 2016 oder 2019. <br/> [Weitere Informationen](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Erzwingt moderne Authentifizierung innerhalb des Outlook-Clients.<br/> |
|Office 2016  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird die Standardauthentifizierung verwendet. Server lehnt moderne Authentifizierung ab, wenn der Mandant nicht aktiviert ist.  <br/> |
   
<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016-und Office 2019-Client-apps beschrieben, wenn Sie eine Verbindung mit SharePoint Online mit oder ohne moderne Authentifizierung herstellen.
  
|Version des Office-Client-App * * * *|Registrierungsschlüssel vorhanden? * * * *|Moderne Authentifizierung auf? * * * *|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten (Standard) * * * *|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2016  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
   
### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016-und Office 2019-Client-apps beschrieben, wenn Sie eine Verbindung mit Skype for Business Online mit oder ohne moderne Authentifizierung herstellen.
  
|Version des Office-Client-App * * * *|Registrierungsschlüssel vorhanden? * * * *|Moderne Authentifizierung auf? * * * *|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten * * * *|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten (Standardeinstellung) * * * *|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2016  <br/> |Nein oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungs Verbindung ablehnt, wird der Microsoft Online-Anmelde-Assistent verwendet. Server lehnt moderne Authentifizierung ab, wenn Skype for Business Online Mandanten nicht aktiviert sind.  <br/> |Nur Microsoft Online-Anmelde-Assistent.  <br/> |
   
## <a name="see-also"></a>Siehe auch

[Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/enable-modern-authentication)

[Mehrstufige Authentifizierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/multi-factor-authentication-microsoft-365)

[Anmelden bei Microsoft 365 mit mehrstufiger Authentifizierung](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)
