---
title: Attribute für Richtlinien für Informationsbarrieren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Verwenden Sie diesen Artikel als Referenz für verschiedene Attribute, die Sie in Richtlinien für Informationsbarrieren verwenden können.
ms.openlocfilehash: ff7b6e22370c086f6b685fce4de8b61396017bf9
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600622"
---
# <a name="attributes-for-information-barrier-policies"></a>Attribute für Richtlinien für Informationsbarrieren

Bestimmte Attribute in Azure Active Directory können verwendet werden, um Benutzer zu segmentieren. Nachdem Segmente definiert wurden, können diese Segmente als Filter für Richtlinien für Informationsbarrieren verwendet werden. Beispielsweise können Sie mithilfe von **Department** Segmente von Benutzern nach Abteilung in Ihrer Organisation definieren (sofern kein einzelner Mitarbeiter gleichzeitig für zwei Abteilungen arbeitet). 

In diesem Artikel wird beschrieben, wie Sie Attribute mit Informationsbarrieren verwenden, und es wird eine Liste der Attribute bereitgestellt, die verwendet werden können. Wenn Sie mehr über Informationsbarrieren erfahren möchten, lesen Sie die folgenden Ressourcen:
- [Informationsbarrieren](information-barriers.md)
- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Verwenden von Attributen in Richtlinien für Informationsbarrieren

Die in diesem Artikel aufgeführten Attribute können verwendet werden, um Segmente von Benutzern zu definieren oder zu bearbeiten. Ihre definierten Segmente dienen als Parameter (als *UserGroupFilter* -Werte bezeichnet) in [Richtlinien für Informationsbarrieren](information-barriers-policies.md).

1. Bestimmen Sie, welches Attribut zum Definieren von Segmenten verwendet werden soll. (Weitere Informationen finden Sie im Abschnitt " [Reference](#reference) " in diesem Artikel.)

2. Stellen Sie sicher, dass die Benutzerkonten Werte für die in Schritt 1 ausgewählten Attribute eingegeben haben. Zeigen Sie die Benutzerkontodetails an, und bearbeiten Sie Benutzerkonten bei Bedarf, um Attributwerte einzubeziehen. 

    - Informationen zum Bearbeiten mehrerer Konten (oder zum Bearbeiten eines einzelnen Kontos mithilfe von PowerShell) finden Sie unter [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

    - Informationen zum Bearbeiten eines einzelnen Kontos finden Sie unter [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definieren Sie Segmente mithilfe von PowerShell](information-barriers-policies.md#define-segments-using-powershell), ähnlich wie in den folgenden Beispielen:

    |Beispiel  |Cmdlet  |
    |---------|---------|
    |Definieren eines Segments namens Segment1 mit dem Department-Attribut     | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"`        |
    |Definieren Sie ein Segment, das als segmenta bezeichnet wird, indem Sie das Attribut "Attributs" verwenden (angenommen, dieses Attribut enthält Gruppennamen, beispielsweise "bluegroup").     | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"`        |
    |Definieren Sie ein Segment namens Daytrader mit ExtensionAttribute1 (angenommen, dieses Attribut enthält Auftragstitel wie "Daytrader").|`New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Wenn Sie Segmente definieren, verwenden Sie für alle Segmente dasselbe Attribut. Wenn Sie beispielsweise einige Segmente mithilfe von *Department*definieren, definieren Sie alle Segmente mithilfe von *Department*. Definieren Sie einige Segmente nicht mithilfe von *Department* und anderen mithilfe von "Redefine *".* Stellen Sie sicher, dass sich Ihre Segmente nicht überschneiden. Jeder Benutzer sollte genau einem Segment zugeordnet werden. 

## <a name="reference"></a>Referenz

In der folgenden Tabelle sind die Attribute aufgeführt, die Sie mit Informationsbarrieren verwenden können.

|Name der Azure Active Directory-Eigenschaft<br/>(LDAP-Anzeigename)  |Exchange-Eigenschaftsname  |
|---------|---------|
|Gemeinsame Dokument       | Gemeinsame Dokument        |
|Unternehmen     |Unternehmen         |
|Department     |Department         |
|ExtensionAttribute1 |CustomAttribute1  |
|ExtensionAttribute2 |CustomAttribute2  |
|ExtensionAttribute3 |CustomAttribute3  |
|ExtensionAttribute4 |Parameter CustomAttribute4  |
|ExtensionAttribute5 |Eigenschaft CustomAttribute5  |
|ExtensionAttribute6 |CustomAttribute6  |
|ExtensionAttribute7 |CustomAttribute7  |
|ExtensionAttribute8 |CustomAttribute8  |
|ExtensionAttribute9 |CustomAttribute9  |
|ExtensionAttribute10 |CustomAttribute10  |
|ExtensionAttribute11 |CustomAttribute11  |
|ExtensionAttribute12 |CustomAttribute12  |
|ExtensionAttribute13 |CustomAttribute13  |
|ExtensionAttribute14 |CustomAttribute14  |
|ExtensionAttribute15 |CustomAttribute15  |
|MSExchExtensionCustomAttribute1 |ExtensionCustomAttribute1 |
|MSExchExtensionCustomAttribute2 |ExtensionCustomAttribute2 |
|MSExchExtensionCustomAttribute3 |ExtensionCustomAttribute3 |
|MSExchExtensionCustomAttribute4 |ExtensionCustomAttribute4 |
|MSExchExtensionCustomAttribute5 |ExtensionCustomAttribute5 |
|MailNickname |Alias |
|PhysicalDeliveryOfficeName |Office |
|PostalCode |PostalCode |
|ProxyAddresses |EmailAddresses |
|StreetAddress |StreetAddress |
|TargetAddress |ExternalEmailAddress |
|UsageLocation |UsageLocation |
|UserPrincipalName  |UserPrincipalName  |
|E-Mail   |WindowsEmailAddress    |
|Beschreibung    |Beschreibung    |
|MemberOf   |MemberOfGroup  |

## <a name="related-topics"></a>Verwandte Themen

[Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)

[Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md)

[Informationsbarrieren](information-barriers.md)



