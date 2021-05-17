---
title: Wählen Sie die Domäne aus, die beim Erstellen Microsoft 365 werden soll
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 7cf5655d-e523-4bc3-a93b-3ccebf44a01a
description: Erfahren Sie, wie Sie die Domäne auswählen, die beim Erstellen Microsoft 365 Gruppen verwendet werden soll, indem Sie E-Mail-Adressrichtlinien mithilfe von PowerShell konfigurieren.
ms.openlocfilehash: 4908d5bd58ca6d0fbb50151983ddb459f0732284
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904684"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Wählen Sie die Domäne aus, die beim Erstellen Microsoft 365 werden soll

Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren. Sie können angeben, welche Domäne verwendet werden soll, wenn Ihre Benutzer Microsoft 365 erstellen.
  
Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.

Bevor Sie die PowerShell-Cmdlets ausführen können, laden Sie ein Modul herunter, mit dem Sie mit Ihrer Organisation sprechen können. Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

## <a name="example-scenarios"></a>Beispielszenarien

Angenommen, die Hauptdomäne Ihres Unternehmens ist Contoso.com. Die standardmäßig akzeptierte Domäne Ihrer Organisation ist jedoch service.contoso.com. Dies bedeutet, dass Gruppen in service.contoso.com erstellt werden (z. B. jimsteam@service.contoso.com).
  
Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert. Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:
  
- students.contoso.com für Studierende
    
- faculty.contoso.com für Lehrkräfte
    
Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.

> [!NOTE]
> Wenn Sie über Mulitple-EAPs verfügen, werden sie in der Reihenfolge ihrer Priorität ausgewertet. Der Wert 1 bedeutet die höchste Priorität. Sobald ein EAP übereinstimmunget, wird keine weitere EAP ausgewertet, und Adressen, die für die Gruppe gestempelt werden, entsprechen dem übereinstimmenen EAP. > Wenn keine EAPs den angegebenen Kriterien entsprechen, wird die Gruppe in der standardmäßig akzeptierten Domäne der Organisation bereitgestellt. Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie [unter Manage accepted domains Exchange Online in](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) Exchange Online.
  
### <a name="scenario-1"></a>Szenario 1

Das folgende Beispiel zeigt, wie Sie alle Microsoft 365 in Ihrer Organisation in der groups.contoso.com bereitstellen.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Szenario 2

Angenommen, Sie möchten steuern, in welchen Unterdomänen Microsoft 365 Gruppen erstellt werden. Du willst:
  
- Von Kursteilnehmern erstellte Gruppen (Benutzer, für die **Abteilung** auf Kursteilnehmer **festgelegt** ist) in students.groups.contoso.com Domäne. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Von Lehrkräften erstellte Gruppen (Benutzer, deren **Abteilung** auf Fakultät oder E-Mail-Adresse festgelegt ist, enthält **faculty.contoso.com)** in der faculty.groups.contoso.com Domäne. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Gruppen, die von anderen Personen erstellt werden, werden in der groups.contoso.com erstellt. Verwenden Sie dazu diesen Befehl:
    
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

Wenn Ihre Organisation in einem Hybridszenario konfiguriert ist, lesen Sie [Configure Microsoft 365 groups with on-premises Exchange hybrid,](/exchange/hybrid-deployment/set-up-microsoft-365-groups) um sicherzustellen, dass Ihre Organisation die Anforderungen für das Erstellen von Microsoft 365 erfüllt. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Zusätzliche Informationen zur Verwendung von E-Mail-Adressrichtliniengruppen:

Es gibt ein paar weitere Punkte, die Sie wissen müssen:
  
- Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.
    
- Administratoren und Benutzer können domänen auch ändern, wenn sie Gruppen erstellen.
    
- Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt. Weitere Informationen [finden Sie unter Filterable properties for the -RecipientFilter parameter](/powershell/exchange/recipientfilter-properties) for supported filterable properties. 
    
- Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.
    
- Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.
    
- Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.
    
## <a name="related-articles"></a>Verwandte Artikel

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Erstellen einer Microsoft 365 im Admin Center](../admin/create-groups/create-groups.md)