---
title: Wählen Sie die Domäne aus, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll.
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
description: Hier erfahren Sie, wie Sie die zu verwendende Domäne beim Erstellen von Microsoft 365-Gruppen auswählen, indem Sie e-Mail-Adress Richtlinien mithilfe von PowerShell konfigurieren
ms.openlocfilehash: 1e56268c3994b1ac822869d154be826326039bfc
ms.sourcegitcommit: a0cddd1f888edb940717e434cda2dbe62e5e9475
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/09/2020
ms.locfileid: "49612940"
---
# <a name="choose-the-domain-to-use-when-creating-microsoft-365-groups"></a>Wählen Sie die Domäne aus, die beim Erstellen von Microsoft 365-Gruppen verwendet werden soll.

Einige Organisationen verwenden separate E-Mail-Domänen, um unterschiedliche Unternehmensbereiche zu segmentieren. Sie können angeben, welche Domäne verwendet werden soll, wenn Ihre Benutzer Microsoft 365-Gruppen erstellen.
  
Wenn Benutzer in Ihrer Organisation ihre Gruppen in anderen Domänen als der akzeptierten Standarddomäne Ihres Unternehmens erstellen müssen, können Sie dies erlauben, indem Sie E-Mail-Adressrichtlinien (Email Address Policies, EAPs) mithilfe von PowerShell konfigurieren.

Bevor Sie die PowerShell-Cmdlets ausführen können, müssen Sie ein Modul herunterladen und installieren, mit dem Sie mit Ihrer Organisation in Gespräch treten können. Lesen Sie [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=785881).

## <a name="example-scenarios"></a>Beispielszenarien

Angenommen, die Hauptdomäne Ihres Unternehmens lautet contoso.com. Die akzeptierte Standarddomäne Ihrer Organisation ist jedoch Service.contoso.com. Dies bedeutet, dass Gruppen in Service.contoso.com erstellt werden (beispielsweise jimsteam@Service.contoso.com).
  
Weiterhin angenommen, Sie haben in Ihrer Organisation auch Unterdomänen konfiguriert. Sie möchten auch, dass Gruppen in diesen Domänen erstellt werden:
  
- students.contoso.com für Studierende
    
- faculty.contoso.com für Lehrkräfte
    
Anhand der beiden folgenden Szenarien wird erläutert, wie Sie dies erreichen können.

> [!NOTE]
> Wenn Sie mehreren Stand eaps haben, werden Sie in der Reihenfolge der Priorität ausgewertet. Der Wert 1 bedeutet die höchste Priorität. Wenn ein EAP übereinstimmt, wird kein weiterer EAP ausgewertet, und Adressen, die auf die Gruppe gestempelt werden, entsprechen dem entsprechenden EAP. > Wenn kein eaps mit den angegebenen Kriterien übereinstimmt, wird die Gruppe in der standardmäßigen akzeptierten Domäne der Organisation festgelegt. Weitere Informationen zum Hinzufügen einer akzeptierten Domäne finden Sie [unter Manage accepted domains in Exchange Online](https://go.microsoft.com/fwlink/p/?LinkId=785428) .
  
### <a name="scenario-1"></a>Szenario 1

Das folgende Beispiel zeigt, wie Sie alle Microsoft 365-Gruppen in Ihrer Organisation in der Groups.contoso.com-Domäne anbieten.
  
```
New-EmailAddressPolicy -Name Groups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@groups.contoso.com" -Priority 1
```

### <a name="scenario-2"></a>Szenario 2

Angenommen, Sie möchten steuern, in welchen Unterdomänen Microsoft 365-Gruppen erstellt werden. Du willst:
  
- Gruppen, die von Teilnehmern (Benutzer mit **Abteilungs** Einstellungen für **Schüler**) in der students.Groups.contoso.com-Domäne erstellt wurden. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name StudentsGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@students.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Students'} -Priority 1
  ```

- Von Fakultätsmitgliedern erstellte Gruppen (Benutzer, die eine **Abteilung** für die **Fakultät oder die e-Mail-Adresse enthalten Faculty.contoso.com)**) in der Faculty.Groups.contoso.com-Domäne. Verwenden Sie dazu diesen Befehl:
    
  ```
  New-EmailAddressPolicy -Name FacultyGroups -IncludeUnifiedGroupRecipients -EnabledEmailAddressTemplates "SMTP:@faculty.groups.contoso.com","smtp:@groups.contoso.com" -ManagedByFilter {Department -eq 'Faculty' -or EmailAddresses -like "*faculty.contoso.com*"} -Priority 2
  ```

- Gruppen, die von anderen Benutzern erstellt wurden, werden in der Groups.contoso.com-Domäne erstellt. Verwenden Sie dazu diesen Befehl:
    
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

Wenn Ihre Organisation in einem Hybrid Szenario konfiguriert ist, lesen Sie [configure Microsoft 365 groups with on-premises Exchange Hybrid](https://docs.microsoft.com/exchange/hybrid-deployment/set-up-microsoft-365-groups) , um sicherzustellen, dass Ihre Organisation die Anforderungen zum Erstellen von Microsoft 365-Gruppen erfüllt. 
  
## <a name="additional-info-about-using-email-address-policies-groups"></a>Weitere Informationen zur Verwendung von Gruppen mit e-Mail-Adress Richtlinien:

Es gibt ein paar weitere Punkte, die Sie wissen müssen:
  
- Wie schnell Gruppen erstellt werden, ist von der Anzahl der in Ihrer Organisation konfigurierten EAPs abhängig.
    
- Administratoren und Benutzer können Domänen beim Erstellen von Gruppen auch ändern.
    
- Die Gruppe der Benutzer wird mithilfe der bereits verfügbaren Standardabfragen (Benutzereigenschaften) bestimmt. Überprüfen Sie [die filterbaren Eigenschaften für den Parameter "-RecipientFilter"](https://docs.microsoft.com/powershell/exchange/recipientfilter-properties) für unterstützte Filterbare Eigenschaften. 
    
- Wenn Sie keine EAPs für Gruppen konfigurieren, wird die akzeptierte Standarddomäne für die Gruppenerstellung ausgewählt.
    
- Wenn Sie eine akzeptierte Domäne entfernen möchten, müssen Sie zuerst die EAPs aktualisieren, andernfalls hat dies Auswirkungen auf die Gruppenbereitstellung.
    
- Für eine Organisation können maximal 100 E-Mail-Adressrichtlinien konfiguriert werden.
    
## <a name="related-articles"></a>Verwandte Artikel

[Planung der Collaboration-Steuerung Schritt für Schritt](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Steuerungsplans für die Zusammenarbeit](collaboration-governance-first.md)

[Erstellen einer Microsoft 365-Gruppe im Admin Center](https://docs.microsoft.com/microsoft-365/admin/create-groups/create-groups)
