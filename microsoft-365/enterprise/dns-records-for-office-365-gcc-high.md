---
title: DNS-Einträge für Office 365 GCC High
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
description: 'Zusammenfassung: DNS-Einträge für Office 365 GCC High'
hideEdit: true
ms.openlocfilehash: 9edcda4616d50d05331db0e2d6c4d89967b02fdc
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690488"
---
# <a name="dns-records-for-office-365-gcc-high"></a>DNS-Einträge für Office 365 GCC High

*Dieser Artikel gilt für Office 365 GCC High und Microsoft 365 GCC High*

Im Rahmen des Onboardings Office 365 GCC High müssen Sie Ihre SMTP- und SIP-Domänen zu Ihrem Online Services-Mandanten hinzufügen.  Dazu verwenden Sie das cmdlet New-MsolDomain in Azure AD PowerShell oder verwenden das [Azure Government Portal,](https://portal.azure.us) um mit dem Hinzufügen der Domäne und dem Nachweis des Besitzes zu beginnen.

Nachdem Sie Ihre Domänen zu Ihrem Mandanten hinzugefügt und überprüft haben, verwenden Sie die folgenden Anleitungen, um die entsprechenden DNS-Einträge für die folgenden Dienste hinzuzufügen.  Möglicherweise müssen Sie die folgende Tabelle an die Anforderungen Ihrer Organisation im Hinblick auf die eingehenden MX-Einträge und alle vorhandenen Exchange AutoErmittlungsdatensatz(n) anpassen.  Es wird dringend empfohlen, diese DNS-Einträge mit Ihrem Messagingteam zu koordinieren, um Ausfälle oder fehlgeleitete E-Mails zu vermeiden.

## <a name="exchange-online"></a>Exchange Online

| Type | Priority | Hostname | Verweist auf Adresse oder Wert | TTL |
| --- | --- | --- | --- | --- |
| MX | 0 | @ | *Mandant*.mail.protection.office365.us (weitere Details finden Sie unten) | 1 Hour |
| TXT | - | @ | v=spf1 include:spf.protection.office365.us -all | 1 Hour |
| CNAME | - | autodiscover | autodiscover.office365.us | 1 Hour |

### <a name="exchange-autodiscover-record"></a>Exchange AutoErmittlungsdatensatz

Wenn Sie über Exchange Server verfügen, wird empfohlen, den vorhandenen Datensatz während der Migration zu Exchange Online zu erhalten, und diesen Datensatz zu aktualisieren, sobald Sie die Migration abgeschlossen haben. 

### <a name="exchange-online-mx-record"></a>Exchange Online MX-Eintrag

Der WERT des MX-Eintrags für Ihre akzeptierten Domänen folgt einem  Standardformat wie oben *erwähnt:* Mandant .mail.protection.office365.us, das den Mandanten durch den ersten Teil Des Standard mandantennamens ersetzt.

Wenn Ihr Mandantenname z. B. contoso.onmicrosoft.us ist, verwenden Sie **contoso.mail.protection.office365.us** als Wert für Ihren MX-Eintrag.

## <a name="skype-for-business-online"></a>Skype for Business Online

### <a name="cname-records"></a>#A0

| Typ | Hostname | Verweist auf Adresse oder Wert | TTL |
| --- | --- | --- | --- |
| CNAME | sip | sipdir.online.gov.skypeforbusiness.us | 1 Hour |
| CNAME | lyncdiscover | webdir.online.gov.skypeforbusiness.us | 1 Hour |

### <a name="srv-records"></a>SRV-Einträge

| Typ | Dienst | Protokoll | Port | Schriftbreite | Priorität | Name | Ziel | TTL |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| SRV | \_sip | \_tls | 443 | 1 | 100 | @ | sipdir.online.gov.skypeforbusiness.us | 1 Hour |
| SRV | \_sipfederationtls | \_tcp | 5061 | 1 | 100 | @ | sipfed.online.gov.skypeforbusiness.us | 1 Hour |

## <a name="additional-dns-records"></a>Zusätzliche DNS-Einträge

> [!IMPORTANT]
> Wenn Sie über einen *vorhandenen msoid-CNAME-Eintrag* in Ihrer #A0 verfügen, müssen Sie den Eintrag zu diesem Zeitpunkt aus DNS entfernen.   Der msoid-Datensatz ist mit Microsoft 365 Enterprise Apps *(früher Office 365 ProPlus)* nicht kompatibel und verhindert, dass die Aktivierung erfolgreich ist.
