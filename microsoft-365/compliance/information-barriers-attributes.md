---
title: Attribute für Richtlinien für Informationsbarrieren
description: Dieser Artikel ist eine Referenz für Azure Active Directory Benutzerkontenattribute, die Sie zum Definieren von Informationsbarrieresegmenten verwenden können.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ee410bf455e770087da7999ad2019c17419a8e00
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919731"
---
# <a name="attributes-for-information-barrier-policies"></a>Attribute für Richtlinien für Informationsbarrieren

Bestimmte Attribute in Azure Active Directory können zum Segmentieren von Benutzern verwendet werden. Nachdem Segmente definiert wurden, können diese Segmente als Filter für Richtlinien für Informationsbarrieren verwendet werden. Sie können beispielsweise  Abteilung verwenden, um Benutzersegmente nach Abteilungen in Ihrer Organisation zu definieren (vorausgesetzt, dass kein einzelner Mitarbeiter gleichzeitig für zwei Abteilungen arbeitet).

In diesem Artikel wird die Verwendung von Attributen mit Informationsbarrieren beschrieben, und es wird eine Liste der Attribute angezeigt, die verwendet werden können. Weitere Informationen zu Informationsbarrieren finden Sie in den folgenden Ressourcen:

- [Informationsbarrieren](information-barriers.md)
- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Verwenden von Attributen in Richtlinien für Informationsbarrieren

Die in diesem Artikel aufgeführten Attribute können zum Definieren oder Bearbeiten von Benutzersegmenten verwendet werden. Ihre definierten Segmente dienen als Parameter (sogenannte *UserGroupFilter-Werte)* in [Informationsbarriererichtlinien.](information-barriers-policies.md)

1. Bestimmen Sie, welches Attribut Sie zum Definieren von Segmenten verwenden möchten. (Weitere Informationen finden Sie im [Abschnitt Referenz](#reference) in diesem Artikel.)

2. Stellen Sie sicher, dass für die Benutzerkonten werte ausgefüllt sind, die Sie in Schritt 1 ausgewählt haben. Zeigen Sie Die Details des Benutzerkontos an, und bearbeiten Sie bei Bedarf Benutzerkonten so, dass Attributwerte enthalten sind. 

    - Informationen zum Bearbeiten mehrerer Konten (oder zum Bearbeiten eines einzelnen Kontos mithilfe von PowerShell) finden Sie unter [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

    - Informationen zum Bearbeiten eines einzelnen Kontos finden Sie unter Hinzufügen oder Aktualisieren der Profilinformationen eines [Benutzers mithilfe Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

3. [Definieren von Segmenten mit PowerShell](information-barriers-policies.md#define-segments-using-powershell), ähnlich den folgenden Beispielen:

    |**Beispiel**|**Cmdlet**|
    |:----------|:---------|
    | Definieren eines Segments namens Segment1 mithilfe des Department-Attributs | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definieren Sie ein Segment namens SegmentA mit dem MemberOf-Attribut (angenommen, dieses Attribut enthält Gruppennamen, z. B. "BlueGroup"). | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definieren Eines Segments namens DayTraders mithilfe von ExtensionAttribute1 (angenommen, dieses Attribut enthält Auftragstitel, z. B. "DayTrader") | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Wenn Sie Segmente definieren, verwenden Sie dasselbe Attribut für alle Segmente. Wenn Sie beispielsweise einige Segmente mithilfe von *Department* definieren, definieren Sie alle Segmente mithilfe von *Department*. Definieren Sie einige Segmente nicht mithilfe von *Department* und andere mit *MemberOf*. Stellen Sie sicher, dass ihre Segmente nicht überlappen. Jedem Benutzer sollte genau ein Segment zugewiesen werden.

## <a name="reference"></a>Referenz

In der folgenden Tabelle sind die Attribute aufgeführt, die Sie mit Informationsbarrieren verwenden können.

|**Azure Active Directory <br/> -Eigenschaftsname (LDAP-Anzeigename)**|**Exchange-Eigenschaftsname**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Unternehmen | Unternehmen |
| Abteilung | Abteilung |
| ExtensionAttribute1 | CustomAttribute1 |
| ExtensionAttribute2 | CustomAttribute2 |
| ExtensionAttribute3 | CustomAttribute3 |
| ExtensionAttribute4 | CustomAttribute4 |
| ExtensionAttribute5 | CustomAttribute5 |
| ExtensionAttribute6 | CustomAttribute6 |
| ExtensionAttribute7 | CustomAttribute7 |
| ExtensionAttribute8 | CustomAttribute8 |
| ExtensionAttribute9 | CustomAttribute9 |
| ExtensionAttribute10 | CustomAttribute10 |
| ExtensionAttribute11 | CustomAttribute11 |
| ExtensionAttribute12 | CustomAttribute12 |
| ExtensionAttribute13 | CustomAttribute13 |
| ExtensionAttribute14 | CustomAttribute14 |
| ExtensionAttribute15 | CustomAttribute15 |
| MSExchExtensionCustomAttribute1 | ExtensionCustomAttribute1 |
| MSExchExtensionCustomAttribute2 | ExtensionCustomAttribute2 |
| MSExchExtensionCustomAttribute3 | ExtensionCustomAttribute3 |
| MSExchExtensionCustomAttribute4 | ExtensionCustomAttribute4 |
| MSExchExtensionCustomAttribute5 | ExtensionCustomAttribute5 |
| MailNickname | Alias |
| PhysicalDeliveryOfficeName | Office |
| PostalCode | PostalCode |
| ProxyAddresses | EmailAddresses |
| StreetAddress | StreetAddress |
| TargetAddress | ExternalEmailAddress |
| UsageLocation | UsageLocation |
| UserPrincipalName | UserPrincipalName |
| E-Mail | WindowsEmailAddress |
| Beschreibung | Beschreibung |
| MemberOf | MemberOfGroup |

## <a name="resources"></a>Ressourcen

- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md)
- [Informationsbarrieren](information-barriers.md)