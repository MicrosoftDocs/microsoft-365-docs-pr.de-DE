---
title: DNS-Einträge für Office 365 DoD
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 'Zusammenfassung: DNS-Einträge für Office 365 DoD'
hideEdit: true
ms.openlocfilehash: 656fb5aff3365dfb5f975f7d3ad1c222b36e1e56
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690499"
---
# <a name="dns-records-for-office-365-dod"></a>DNS-Einträge für Office 365 DoD

*Dieser Artikel bezieht sich auf Office 365 DoD und Microsoft 365 DoD*

Im Rahmen des onboardings für Office 365 DoD müssen Sie Ihre SMTP-und SIP-Domänen zu Ihrem Online Dienste-Mandanten hinzufügen.  Verwenden Sie dazu das Cmdlet New-MsolDomain in Azure AD PowerShell, oder verwenden Sie das [Azure Government-Portal](https://portal.azure.us) , um den Prozess des Hinzufügens der Domäne und des Besitzes zu unter Beweis zu starten.

Nachdem Sie Ihre Domänen Ihrem Mandanten hinzugefügt und überprüft haben, können Sie die entsprechenden DNS-Einträge für die unten aufgeführten Dienste mit dem folgenden Leitfaden hinzufügen.  Möglicherweise müssen Sie die folgende Tabelle ändern, um die Anforderungen Ihrer Organisation in Bezug auf den eingehenden MX-Eintrag (n) und alle vorhandenen Exchange-Auto Ermittlungs Einträge anzupassen, die Sie in der richtigen Position haben.  Es wird dringend empfohlen, diese DNS-Einträge mit Ihrem Messaging-Team zu koordinieren, um Ausfälle oder falsche Zustellung von e-Mails zu vermeiden.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Hostname | Verweist auf Adresse oder Wert | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *Mandanten*. Mail.Protection.office365.US (Weitere Informationen finden Sie weiter unten) | 1 Hour |
| TXT | - | @ | v = spf1 include:SPF. Protection. office365. US-all | 1 Hour |
| CNAME | - | autodiscover | autodiscover-dod.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange-Auto Ermittlungs Eintrag

Wenn Sie Exchange Server lokal haben, sollten Sie den vorhandenen Datensatz bei der Migration zu Exchange Online beibehalten und diesen Eintrag aktualisieren, nachdem Sie die Migration abgeschlossen haben.

### <a name="exchange-online-mx-record"></a>Exchange Online MX-Eintrag

Der Wert des MX-Eintrags für Ihre akzeptierten Domänen folgt einem Standardformat, wie oben erwähnt: *Tenant*. Mail.Protection.office365.US, das den *Mandanten* durch den ersten Teil des Standardmandanten namens ersetzt.

Wenn Ihr Mandantenname beispielsweise contoso.onmicrosoft.US lautet, verwenden Sie **contoso.Mail.Protection.office365.US** als Wert für den MX-Eintrag.

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>CNAME-Einträge

| Typ | Hostname | Verweist auf Adresse oder Wert | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.dod.skypeforbusiness.us | 1 Hour |
| CNAME | lyncdiscover | webdir.online.dod.skypeforbusiness.us | 1 Hour | 

### <a name="srv-records"></a>SRV-Einträge

| Typ | Dienst | Protokoll | Port | Schriftbreite | Priorität | Name | Ziel | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_TLS | 443 | 1 | 100 | @ | sipdir.online.dod.skypeforbusiness.us | 1 Hour |
| SRV | \_sipfederationtls | \_TCP | 5061 | 1 | 100 | @ | sipfed.online.dod.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Zusätzliche DNS-Einträge

> [!IMPORTANT]
> Wenn Sie einen vorhandenen *msoID* -CNAME-Eintrag in Ihrer DNS-Zone haben, müssen Sie den Datensatz zu diesem Zeitpunkt aus DNS **Entfernen** .  Der msoID-Eintrag ist nicht mit Microsoft 365 Enterprise-apps *(ehemals Office 365 ProPlus)* kompatibel und verhindert, dass die Aktivierung erfolgreich ausgeführt wird.
