---
title: Minderjährige und Erwerben von Add-Ins Store
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie mehr über die Datenschutz-Grundverordnung (DSGVO), die die personenbezogenen Daten von Minderjährigen regeln.
ms.openlocfilehash: e7f53a5a6b64f29f5029f0080fef44439c926edb
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580918"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjährige und Erwerben von Add-Ins Store

Die Datenschutz-Grundverordnung (DSGVO) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird. Es gibt Benutzern Rechte an und Schutz ihrer Daten. Einer der Aspekte der DSGVO ist, dass Minderjährige ihre personenbezogenen Daten nicht an Parteien übermitteln lassen können, die von ihren Eltern oder Erziehungsberechtigten nicht genehmigt wurden. Das spezifische Alter, das als Nebenperson definiert ist, hängt von der Region ab, in der sich die Person befindet.
  
Zu den Regionen mit gesetzlichen Bestimmungen über die Zustimmung der Eltern gehören die USA, Südkorea, Großbritannien und die Europäische Union. Für diese Regionen wird verhindert, dass ein Minderjähriger (über Azure Active Directory) neue Office-Add-Ins aus dem Store abrufen und zuvor erworbene Add-Ins ausführen kann. Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadeinschränkungen.
  
Ein Benutzer wird basierend auf den in der Datei angegebenen Daten als nebens Azure Active Directory. Der Organisationsadministrator ist für die Deklarieren der gesetzlichen Altersgruppe und der elterlichen Zustimmung für den Benutzer verantwortlich.
  
Wenn das Übergeordnete/Erziehungsberechtigte einer Minderjährigen mithilfe eines bestimmten Add-Ins zuwilligt, kann der Organisationsadministrator die zentrale Bereitstellung verwenden, um dieses Add-In für alle Minderjährigen mit Zustimmung zu bereitstellen.
  
Damit die DSGVO für Minderjährige kompatibel ist, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in Ihrer Schule/Organisation bereitgestellt wird.
 
 **Für Word, Excel, PowerPoint und Project**: 

|**Plattform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for Enterprise (Aktueller Kanal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for Enterprise (Semi-Annual Enterprise Channel)  <br/> |8431.2159  <br/> |
|Office 2016 für Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 für Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 für Mac  <br/> |16.11.18020200  <br/> |
|Office für das Web  <br/> |Nicht zutreffend  <br/> |
   
 **Für Outlook**: 
  
|**Plattform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Outlook 2016 für Windows (MSI)  <br/> |Build No TBD  <br/> |
|Outlook 2016 für Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 für Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook für iOS  <br/> |2.75.0  <br/> |
|Outlook für Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Nicht zutreffend  <br/> |

 **Office 2013-Anforderungen**
  
Word, Excel und PowerPoint 2013 für Windows unterstützen dieselben Nebenprüfungen, wenn die Active Directory-Authentifizierungsbibliothek (Active Directory Authentication Library, ADAL) aktiviert ist. Es gibt zwei Optionen für die Compliance, wie im nächsten Schritt erläutert.
  
- **Aktivieren Sie ADAL**. In diesem Artikel wird erläutert, wie Sie ADAL für Office 2013 aktivieren: Verwenden Microsoft 365 [modernen Authentifizierung](../../enterprise/modern-auth-for-office-2013-and-2016.md)mit Office Clients .<br/>Sie müssen außerdem die Registrierungsschlüssel festlegen, um ADAL zu aktivieren, wie unter [Enable Modern Authentication for Office 2013 on Windows erläutert.](../security-and-compliance/enable-modern-authentication.md)<br/>Darüber hinaus müssen Sie die folgenden Aprilupdates für Office 2013 installieren:
    
  - [Beschreibung des Sicherheitsupdates für Office 2013: 10. April 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [Update vom 3. April 2018 für Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivieren Sie ADAL nicht.** Wenn Sie ADAL in Office 2013 nicht aktivieren können, empfehlen wir die Verwendung von Gruppenrichtlinien, um die Store für die Office zu deaktivieren. Informationen zum Deaktivieren der App für Office finden Sie [hier](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15)).

## <a name="related-articles"></a>Verwandte Artikel

[Bereitstellen von Add-Ins im Admin Center](./manage-deployment-of-add-ins.md)

[Verwalten von Add-Ins im Admin Center](./manage-addins-in-the-admin-center.md)
