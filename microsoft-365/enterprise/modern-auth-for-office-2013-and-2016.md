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
description: Erfahren Sie, wie Microsoft 365 features der modernen Authentifizierung für Office 2013- und 2016-Client-Apps unterschiedlich funktionieren.
ms.openlocfilehash: 60b1729d9830fd12141d162c4fe721267e52d437
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229839"
---
# <a name="how-modern-authentication-works-for-office-2013-office-2016-and-office-2019-client-apps"></a>Funktionsweise der modernen Authentifizierung für Office 2013-, Office 2016- und Office 2019-Client-Apps

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

In diesem Artikel erfahren Sie, wie Office 2013-, Office 2016- und Office 2019-Client-Apps moderne Authentifizierungsfunktionen basierend auf der Authentifizierungskonfiguration auf dem Microsoft 365 Mandanten für Exchange Online, SharePoint Online und Skype for Business Online verwenden.

> [!NOTE]
> Ältere Client-Apps wie Office 2010 und Office für Mac 2011 unterstützen keine moderne Authentifizierung und können nur mit standardauthentifizierung verwendet werden.

## <a name="availability-of-modern-authentication-for-microsoft-365-services"></a>Verfügbarkeit der modernen Authentifizierung für Microsoft 365-Dienste

Für die Microsoft 365-Dienste lautet der Standardstatus der modernen Authentifizierung:

- Standardmäßig für Exchange Online **aktiviert.** Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der modernen Authentifizierung in Exchange Online,](https://support.office.com/article/58018196-f918-49cd-8238-56f57f38d662) um sie zu deaktivieren oder zu aktivieren.

- Standardmäßig für SharePoint Online **aktiviert.**

- Standardmäßig für Skype for Business Online **aktiviert.** Informationen zum Deaktivieren oder Aktivieren der [modernen Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)finden Sie unter "Aktivieren Skype for Business Online".

> [!NOTE]
> Für Mandanten, die **vor** dem 1. August 2017 erstellt wurden, ist die moderne Authentifizierung für Exchange Online und Skype for Business Online standardmäßig **deaktiviert**.

## <a name="sign-in-behavior-of-office-client-apps"></a>Anmeldeverhalten von Office Client-Apps

Office 2013-Client-Apps unterstützen standardmäßig die Legacyauthentifizierung. Legacy bedeutet, dass sie entweder den Microsoft Online-Anmeldeassistenten oder die Standardauthentifizierung unterstützen. Damit diese Clients moderne Authentifizierungsfunktionen verwenden können, müssen für den Windows-Client Registrierungsschlüssel festgelegt sein. Anweisungen finden Sie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows Geräten.](https://support.office.com/article/7dc1c01a-090f-4971-9677-f1b192d6c910)

Um moderne Authentifizierung bei Geräten unter Windows (beispielsweise auf Laptops und Tablets) zu aktivieren, auf denen Microsoft Office 2013 installiert ist, müssen Sie die nachstehenden Registrierungsschlüssel festlegen. Die Schlüssel müssen auf jedem Gerät festgelegt werden, das Sie für moderne Authentifizierung aktivieren möchten:

|**Registrierungsschlüssel**|**Typ**|**Wert** |
|:-------|:------:|--------:|
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\EnableADAL  |REG_DWORD  |1   |
|HKCU\SOFTWARE\Microsoft\Office\15.0\Common\Identity\Version |REG_DWORD |1  |

Lesen Sie, wie Sie [moderne Authentifizierung (Modern Authentication, ADAL) mit Skype for Business verwenden,](./hybrid-modern-auth-overview.md) um mehr über die Funktionsweise mit Skype for Business zu erfahren.

Office 2016- und Office 2019-Clients unterstützen standardmäßig die moderne Authentifizierung, und es ist keine Aktion erforderlich, damit der Client diese neuen Flüsse verwenden kann. Für die Verwendung der Legacyauthentifizierung ist jedoch eine explizite Aktion erforderlich.

Klicken Sie auf die links unten, um zu sehen, wie Office 2013, Office 2016 und Office 2019-Clientauthentifizierung mit den Microsoft 365-Diensten funktioniert, je nachdem, ob die moderne Authentifizierung aktiviert ist.

- [Exchange Online](modern-auth-for-office-2013-and-2016.md#BK_EchangeOnline)

- [SharePoint Online](modern-auth-for-office-2013-and-2016.md#BK_SharePointOnline)

- [Skype for Business Online](modern-auth-for-office-2013-and-2016.md#BK_SFBO)

<a name="BK_EchangeOnline"> </a>
### <a name="exchange-online"></a>Exchange Online

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016- und Office 2019-Client-Apps beschrieben, wenn sie eine Verbindung mit Exchange Online mit oder ohne moderne Authentifizierung herstellen.

|Office Client-App-Version|Registrierungsschlüssel vorhanden??|Moderne Authentifizierung aktiviert?**|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten (Standard)"|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein <br> AlwaysUsemSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Erzwingt die moderne Authentifizierung auf Outlook 2013, 2016 oder 2019. <br/> [Weitere Informationen](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Erzwingt die moderne Authentifizierung im Outlook Client.<br/> |
|Office 2019  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL=0  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2016  <br/> |Nein <br> AlwaysUsemSOAuthForAutoDiscover = 1 <br/> |Ja  <br/> |Erzwingt die moderne Authentifizierung auf 2013, 2016 oder 2019. <br/> [Weitere Informationen](https://support.microsoft.com/help/3126599/outlook-prompts-for-password-when-modern-authentication-is-enabled)|Erzwingt die moderne Authentifizierung im Outlook Client.<br/> |
|Office 2016  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL=0  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Standardauthentifizierung  <br/> |Standardauthentifizierung  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird die Standardauthentifizierung verwendet. Der Server verweigert die moderne Authentifizierung, wenn der Mandant nicht aktiviert ist.  <br/> |

<a name="BK_SharePointOnline"> </a>
### <a name="sharepoint-online"></a>SharePoint Online

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016- und Office 2019-Client-Apps beschrieben, wenn sie mit oder ohne moderne Authentifizierung eine Verbindung mit SharePoint Online herstellen.

|Office Client-App-Version|Registrierungsschlüssel vorhanden??|Moderne Authentifizierung aktiviert?**|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten (Standard)"|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2016  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Nur moderne Authentifizierung.  <br/> |Fehler beim Herstellen einer Verbindung.  <br/> |

### <a name="skype-for-business-online"></a>Skype for Business Online
<a name="BK_SFBO"> </a>

In der folgenden Tabelle wird das Authentifizierungsverhalten für Office 2013-, Office 2016- und Office 2019-Client-Apps beschrieben, wenn sie mit oder ohne moderne Authentifizierung eine Verbindung mit Skype for Business Online herstellen.

|Office Client-App-Version|Registrierungsschlüssel vorhanden??|Moderne Authentifizierung aktiviert?**|Authentifizierungsverhalten bei aktivierter moderner Authentifizierung für den Mandanten|Authentifizierungsverhalten bei deaktivierter moderner Authentifizierung für den Mandanten (Standard)"|
|:-----|:-----|:-----|:-----|:-----|
|Office 2019  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |
|Office 2019  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2016  <br/> |Nein, oder EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |
|Office 2016  <br/> |Ja, EnableADAL = 0  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2013  <br/> |Nein  <br/> |Nein  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |
|Office 2013  <br/> |Ja, EnableADAL = 1  <br/> |Ja  <br/> |Die moderne Authentifizierung wird zuerst versucht. Wenn der Server eine moderne Authentifizierungsverbindung ablehnt, wird der Microsoft Online-Anmeldeassistent verwendet. Der Server verweigert die moderne Authentifizierung, wenn Skype for Business Onlinemandanten nicht aktiviert sind.  <br/> |Nur Microsoft Online-Anmeldeassistent.  <br/> |

## <a name="see-also"></a>Siehe auch

[Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](../admin/security-and-compliance/enable-modern-authentication.md)

[Mehrstufige Authentifizierung für Microsoft 365](../admin/security-and-compliance/multi-factor-authentication-microsoft-365.md)

[Anmelden bei Microsoft 365 mit mehrstufiger Authentifizierung](https://support.microsoft.com/office/sign-in-to-microsoft-365-with-multi-factor-authentication-2b856342-170a-438e-9a4f-3c092394d3cb)

[Übersicht zu Microsoft 365 Enterprise](microsoft-365-overview.md)