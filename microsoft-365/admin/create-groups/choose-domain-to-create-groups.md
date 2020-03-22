---
title: Auswählen der beim Erstellen von Office 365-Gruppen zu verwendenden Domäne
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
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
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: 'Hier erfahren Sie, wie Sie beim Erstellen von Office 365 Gruppen die Domäne auswählen können, indem Sie e-Mail-Adress Richtlinien mithilfe von PowerShell konfigurieren. '
ms.openlocfilehash: 8bca0e3c33d5cb523fc075d1d2d5b04b6506b256
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42894645"
---
# <a name="choose-the-domain-to-use-when-creating-office-365-groups"></a>Auswählen der beim Erstellen von Office 365-Gruppen zu verwendenden Domäne

 Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren. Sie können angeben, welche Domäne verwendet werden soll, wenn Ihre Benutzer Office 365-Gruppen erstellen.
  
Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.
  
Bevor Sie die PowerShell-Cmdlets ausführen können, müssen Sie ein Modul herunterladen und installieren, das Ihnen die Kommunikation mit Ihrer Office 365-Organisation ermöglicht. Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).
  
## <a name="example-scenarios"></a>Beispielszenarien

Angenommen, die Hauptdomäne Ihres Unternehmens lautet contoso.com. Die akzeptierte Standarddomäne Ihrer Organisation ist jedoch Service.contoso.com. Dies bedeutet, dass Gruppen in Service.contoso.com erstellt werden (beispielsweise jimsteam@Service.contoso.com).
  
Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert. Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:
  
- students.contoso.com für Studierende
    
- faculty.contoso.com für Lehrkräfte
    
Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.
  
> [!NOTE]
> Wenn Sie mehreren Stand eaps haben, werden Sie in der Reihenfolge der Priorität ausgewertet. Der Wert 1 bedeutet die höchste Priorität. Wenn ein EAP übereinstimmt, wird kein weiterer EAP ausgewertet, und Adressen, die auf die Gruppe gestempelt werden, entsprechen dem entsprechenden EAP. > Wenn kein eaps mit den angegebenen Kriterien übereinstimmt, wird die Gruppe in der standardmäßigen akzeptierten Domäne der Organisation festgelegt. Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie [unter Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) . 
  
### <a name="scenario-1"></a>Szenario 1

Im folgenden Beispiel wird gezeigt, wie Sie alle Office 365-Gruppen in Ihrer Organisation in der Domäne "groups.contoso.com" bereitstellen.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Szenario 2

Angenommen, Sie möchten steuern, in welchen Unterdomänen Office 365 Gruppen erstellt werden. Du willst:
  
- Gruppen, die von Teilnehmern (Benutzer mit **Abteilungs** Einstellungen für **Schüler**) in der students.Groups.contoso.com-Domäne erstellt wurden. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Von Fakultätsmitgliedern erstellte Gruppen (Benutzer, die eine **Abteilung** für die **Fakultät oder die e-Mail-Adresse enthalten Faculty.contoso.com)**) in der Faculty.Groups.contoso.com-Domäne. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Alle anderen Benutzer sollen in der Domäne "groups.contoso.com" erstellt werden. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name OtherGroups -IncludeUnifiedGroupRecipients -EnabledPrimarySMTPAddressTemplate "SMTP:@groups.contoso.com" -Priority 3
  ```

## <a name="change-email-address-policies"></a>Ändern von E-Mail-Adressrichtlinien

Zum Ändern der Priorität oder von E-Mail-Adressvorlagen für eine vorhandene EAP verwenden Sie das Cmdlet "Set-EmailAddressPolicy".
  
```
Set-EmailAddressPolicy -Name StudentsGroups -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com", "smtp:@students.contoso.com" ManagedByFilter {Department -eq 'Students'} -Priority 2

```

Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.
  
## <a name="delete-email-address-policies"></a>Löschen von E-Mail-Adressrichtlinien

Zum Löschen einer EAP verwenden Sie das Cmdlet "Remove-EmailAddressPolicy".
  
```
Remove-EmailAddressPolicy -Identity StudentsGroups
```

Die Änderung einer EAP hat keine Auswirkungen auf die bereits bereitgestellten Gruppen.
  
## <a name="hybrid-requirements"></a>Anforderungen für Hybridbereitstellungen

Wenn Ihre Organisation in einem Hybridszenario konfiguriert ist, lesen Sie [Konfigurieren von Office 365-Gruppen für lokale Exchange-Hybridbereitstellungen](https://go.microsoft.com/fwlink/p/?LinkId=785430), um sicherzustellen, dass Ihre Organisation die Anforderungen für das Erstellen von Office 365-Gruppen erfüllt. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Weitere Informationen zur Verwendung von Gruppen mit e-Mail-Adress Richtlinien:

Es gibt ein paar weitere Punkte, die Sie wissen müssen:
  
- Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.
    
- Administratoren und Benutzer können Domänen beim Erstellen von Gruppen auch ändern.
    
- Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt. Überprüfen Sie [die filterbaren Eigenschaften für den Parameter "-RecipientFilter"](https://go.microsoft.com/fwlink/p/?LinkId=785918) für unterstützte Filterbare Eigenschaften. 
    
- Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.
    
- Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.
    
- Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.
    
## <a name="related-articles"></a>Verwandte Artikel

[Erstellen einer Office 365-Gruppe im Admin Center](create-groups.md)
