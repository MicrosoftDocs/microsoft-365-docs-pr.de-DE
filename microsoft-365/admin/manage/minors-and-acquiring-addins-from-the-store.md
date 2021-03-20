---
title: Minderjährige und Erwerben von Add-Ins aus dem Store
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: c49ea719bc85166cc8082200eb833273b0ab5835
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915254"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjährige und Erwerben von Add-Ins aus dem Store

Die Datenschutz-Grundverordnung (DSGVO) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird. Es gibt Benutzern Rechte an und Schutz ihrer Daten. Einer der Aspekte der DSGVO ist, dass Minderjährige ihre personenbezogenen Daten nicht an Parteien übermitteln lassen können, die von ihren Eltern oder Erziehungsberechtigten nicht genehmigt wurden. Das spezifische Alter, das als Nebenperson definiert ist, hängt von der Region ab, in der sich die Person befindet.
  
Zu den Regionen mit gesetzlichen Bestimmungen über die Zustimmung der Eltern gehören die USA, Südkorea, Großbritannien und die Europäische Union. Für diese Regionen wird ein Minderjähriger (über Azure Active Directory) daran blockiert, neue Office-Add-Ins aus dem Store zu erhalten und zuvor erworbene Add-Ins ausführen. Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadeinschränkungen.
  
Ein Benutzer wird basierend auf den in Azure Active Directory angegebenen Daten als Nebenbenutzer bestimmt. Der Organisationsadministrator ist für die Deklarieren der gesetzlichen Altersgruppe und der elterlichen Zustimmung für den Benutzer verantwortlich.
  
Wenn das Übergeordnete/Erziehungsberechtigte einer Minderjährigen mithilfe eines bestimmten Add-Ins zuwilligt, kann der Organisationsadministrator die zentrale Bereitstellung verwenden, um dieses Add-In für alle Minderjährigen mit Zustimmung zu bereitstellen.
  
Damit die DSGVO für Minderjährige kompatibel ist, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in Ihrer Schule/Organisation bereitgestellt wird.
 
 **Für Word, Excel, PowerPoint und Project**: 

|**Plattform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Microsoft 365 Apps for Enterprise (Aktueller Kanal)  <br/> |9001.2138   <br/> |
|Microsoft 365 Apps for enterprise (Semi-Annual Enterprise Channel)  <br/> |8431.2159  <br/> |
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
|Outlook mobile für iOS  <br/> |2.75.0  <br/> |
|Outlook mobile für Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Nicht zutreffend  <br/> |

 **Office 2013-Anforderungen**
  
Word, Excel und PowerPoint 2013 für Windows unterstützen dieselben Nebenprüfungen, ob die Active Directory Authentication Library (ADAL) aktiviert ist. Es gibt zwei Optionen für die Compliance, wie im nächsten Schritt erläutert.
  
- **Aktivieren Sie ADAL**. In diesem Artikel wird erläutert, wie Sie ADAL für Office 2013 aktivieren: Verwenden der [modernen Microsoft 365-Authentifizierung mit Office-Clients.](../../enterprise/modern-auth-for-office-2013-and-2016.md)<br/>Sie müssen auch die Registrierungsschlüssel festlegen, um ADAL zu aktivieren, wie unter [Enable Modern Authentication for Office 2013 on Windows devices erläutert.](../security-and-compliance/enable-modern-authentication.md)<br/>Darüber hinaus müssen Sie die folgenden Aprilupdates für Office 2013 installieren:
    
  - [Beschreibung des Sicherheitsupdates für Office 2013: 10. April 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [Update vom 3. April 2018 für Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivieren Sie ADAL nicht.** Wenn Sie ADAL in Office 2013 nicht aktivieren können, empfehlen wir, den Store für die Office-Clients mithilfe von Gruppenrichtlinien zu deaktivieren. Informationen zum Deaktivieren der App für Office-Einstellungen finden Sie [hier.](/previous-versions/office/office-2013-resource-kit/cc178992(v=office.15))

## <a name="related-articles"></a>Verwandte Artikel

[Bereitstellen von Add-Ins im Admin Center](./manage-deployment-of-add-ins.md)

[Verwalten von Add-Ins im Admin Center](./manage-addins-in-the-admin-center.md)
