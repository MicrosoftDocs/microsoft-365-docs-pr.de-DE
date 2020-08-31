---
title: Minderjährige und Erwerb von Add-Ins aus dem Store
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
description: Erfahren Sie mehr über die allgemeinen Datenschutzverordnung (dsgvo)-Verordnungen, die die personenbezogenen Daten von Minderjährigen Regeln.
ms.openlocfilehash: a738e22a0ac0b995c8e44fcf4cc5a2eb47375be5
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306551"
---
# <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjährige und Erwerb von Add-Ins aus dem Store

Die allgemeine Datenschutzverordnung (dsgvo) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird. Es gibt Benutzern Rechte und Schutz Ihrer Daten. Einer der Aspekte des dsgvo ist, dass Minderjährige Ihre persönlichen Daten nicht an Parteien senden dürfen, die ihre Eltern oder Erziehungsberechtigten nicht genehmigt haben. Das spezifische Alter, das als Minderjährige definiert ist, hängt von der Region ab, in der sich die Person befindet.
  
Regionen mit gesetzlichen Bestimmungen zur elterlichen Zustimmung sind die Vereinigten Staaten, Südkorea, das Vereinigte Königreich und die Europäische Union. Für diese Regionen wird ein Minderjähriger (über Azure Active Directory) daran gehindert, neue Office-Add-Ins aus dem Store abzurufen und Add-Ins auszuführen, die zuvor erworben wurden. Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadbeschränkungen.
  
Ein Benutzer wird basierend auf den in Azure Active Directory angegebenen Daten als Minderjähriger festgelegt. Der Organisationsadministrator ist für die Deklaration der legalen Altersgruppe und der elterlichen Zustimmung für diesen Benutzer verantwortlich.
  
Wenn der übergeordnete/Erziehungsberechtigte einem Minderjährigen unter Verwendung eines bestimmten Add-ins zustimmt, kann der Organisationsadministrator die zentralisierte Bereitstellung verwenden, um das Add-in für alle Minderjährigen bereitzustellen, die Zustimmung haben.
  
Um dsgvo-konform für Minderjährige zu sein, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in ihrer Schule/Organisation bereitgestellt wird.
 
 **Für Word, Excel, PowerPoint und Project**: 

|**Plattform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Microsoft 365 apps for Enterprise (aktueller Kanal)  <br/> |9001,2138   <br/> |
|Microsoft 365-Apps für Unternehmen (halbjährlicher Enterprise-Kanal)  <br/> |8431,2159  <br/> |
|Office 2016 für Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 für Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 für Mac  <br/> |16.11.18020200  <br/> |
|Office für das Web  <br/> |Nicht zutreffend  <br/> |
   
 **Für Outlook**: 
  
|**Plattform** <br/> |**Buildnummer** <br/> |
|:-----|:-----|
|Outlook 2016 für Windows (MSI)  <br/> |Build kein feststellen  <br/> |
|Outlook 2016 für Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 für Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile für IOS  <br/> |2.75.0  <br/> |
|Outlook Mobile für Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Nicht zutreffend  <br/> |

 **Office 2013 Anforderungen**
  
Word-, Excel-und PowerPoint 2013 für Windows unterstützt die gleichen Minderjährigen überprüft, ob Active Directory Authentifizierungsbibliothek (Adal) aktiviert ist. Es gibt zwei Optionen für die Compliance, wie weiter erläutert.
  
- **Aktivieren Sie Adal**. In diesem Artikel wird erläutert, wie Sie Adal für Office 2013 aktivieren: [Verwenden der modernen Authentifizierung von Microsoft 365 mit Office-Clients](https://docs.microsoft.com/microsoft-365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Sie müssen auch die Registrierungsschlüssel festlegen, um Adal zu aktivieren, wie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](../security-and-compliance/enable-modern-authentication.md)erläutert.<br/>Darüber hinaus müssen Sie die folgenden April-Updates für Office 2013 installieren:
    
  - [Beschreibung des Sicherheitsupdates für Office 2013:10. April 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3. April 2018, Update für Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivieren Sie Adal nicht**. Wenn Sie Adal nicht in Office 2013 aktivieren können, empfehlen wir die Verwendung von Gruppenrichtlinien zum Deaktivieren des Speichers für die Office-Clients. Informationen zum Deaktivieren der Einstellungen für die APP für Office finden Sie [hier](https://technet.microsoft.com/library/cc178992.aspx).

## <a name="related-articles"></a>Verwandte Artikel

[Bereitstellen von Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

[Verwalten von Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center)
    
