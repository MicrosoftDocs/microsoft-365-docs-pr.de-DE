---
title: Aktivieren von SharePoint Multi-Geo am Satellitenstandort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
localization_priority: Normal
description: Dieser Artikel enthält Informationen für globale oder SharePoint Administratoren zum Aktivieren SharePoint Multi-Geo in geografischen Satellitenstandorten.
ms.openlocfilehash: 78f0e925a333dd48a6016bc749459b13e1ac21c0
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690856"
---
# <a name="enabling-sharepoint-multi-geo-in-your-satellite-geo-location"></a>Aktivieren von SharePoint Multi-Geo am Satellitenstandort

Dieser Artikel richtet sich an globale oder SharePoint-Administratoren, die einen Multi-Geo-Satellitenstandort erstellt haben, **bevor** SharePoint Multi-Geo-Funktionen am 27. März 2019 allgemein zur Verfügung gestellt wurden, und SharePoint Multi-Geo nicht an ihrem Satellitenstandort aktiviert haben. 

>[!Note]
>Wenn Sie einen neuen geografischen Standort **nach dem 27. März** hinzugefügt haben, müssen Sie die folgenden Anweisungen nicht befolgen, da Ihr neuer geografischer Standort bereits für OneDrive und SharePoint Multi-Geo aktiviert ist.

Anhand dieser Anweisungen können Sie SharePoint an Ihrem Satellitenstandort aktivieren, sodass Multi-Geo-Satellitenbenutzer sowohl von OneDrive als auch von SharePoint Multi-Geo-Funktionen in Office 365 profitieren können. 

>[!IMPORTANT]
>Beachten Sie, dass dies eine unidirektionale Aktivierung ist. Sobald der SPO-Modus festgelegt wurde, können Sie nicht mehr zum OneDrive Multi-Geo-Modus ohne eine Eskalation an den Support wechseln. 

## <a name="to-set-a-geo-location-into-spo-mode"></a>So legen Sie den SPO-Modus für einen geografischen Standort fest

Um den SPO-Modus für einen geografischen Standort festzulegen, stellen Sie eine Verbindung zu dem geografischen Standort fest, für den der SPO-Modus festgelegt werden soll:

1.    Öffnen Sie die SharePoint Online-Verwaltungsshell. 
2.    Connect-SPOService -URL "https://$tenantGeo-admin.sharepoint.com" -Credential $credential
3.    Set-SPOMultiGeoExperience</br></br>
![Set-SPOMultiGeoExperience](../media/Set-SPO-MultiGeo.jpg)
4.    Dieser Vorgang nimmt in der Regel etwa eine Stunde in Anspruch. Es werden verschiedene Veröffentlichungen im Dienst zurückgenommen, und der Mandant erhält einen neuen Stempel. Warten Sie mindestens eine Stunde, und führen Sie dann Get-SPOMultiGeoExperience aus.  Mit diesem Befehl wird angezeigt, ob dieser geografische Standort den SPO-Modus aufweist.</br></br>
![Set-SPOMultiGeoExperience](../media/Get-SPO-MultiGeo.jpg)

 
 
 
>[!Note]
>Bestimmte Caches im Dienst werden alle 24 Stunden aktualisiert. Es kann also sein, dass sich Ihr Satellitenstandort bis zu 24 Stunden zeitweise so verhält, als wäre immer noch der ODB-Modus für diesen festgelegt. Dies verursacht keine technischen Probleme. 
 
Weitere Informationen zu SharePoint Multi-Geo finden Sie unter [aka.ms/sharepointmultigeo](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md).


