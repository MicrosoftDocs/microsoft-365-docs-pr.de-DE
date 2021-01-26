---
title: Attribute für Richtlinien für Informationsbarrieren
description: Dieser Artikel ist eine Referenz für die Azure Active Directory-Benutzerkontoattribute, die Sie zum Definieren von Segmenten von Informationsbarrieren verwenden können.
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
ms.openlocfilehash: 5e7815dbcfc6129685322a250351276476f8a9e3
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980048"
---
# <a name="attributes-for-information-barrier-policies"></a>Attribute für Richtlinien für Informationsbarrieren

Bestimmte Attribute in Azure Active Directory können verwendet werden, um Benutzer zu segmentieren. Nachdem Segmente definiert wurden, können diese Segmente als Filter für Richtlinien für Informationsbarrieren verwendet werden. Sie können beispielsweise **"Abteilung"** verwenden, um Segmente von Benutzern nach Abteilung in Ihrer Organisation zu definieren (vorausgesetzt, dass kein einzelner Mitarbeiter gleichzeitig für zwei Abteilungen arbeitet).

Dieser Artikel beschreibt die Verwendung von Attributen mit Informationsbarrieren und enthält eine Liste der Attribute, die verwendet werden können. Weitere Informationen zu Informationsbarrieren finden Sie in den folgenden Ressourcen:

- [Informationsbarrieren](information-barriers.md)
- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Bearbeiten oder Entfernen von Richtlinien für Informationsbarrieren](information-barriers-edit-segments-policies.md)

## <a name="how-to-use-attributes-in-information-barrier-policies"></a>Verwenden von Attributen in Richtlinien für Informationsbarrieren

Die in diesem Artikel aufgeführten Attribute können zum Definieren oder Bearbeiten von Benutzersegmenten verwendet werden. Die definierten Segmente dienen als Parameter (so genannte *UserGroupFilter-Werte)* in [Richtlinien für Informationsbarrieren.](information-barriers-policies.md)

1. Bestimmen Sie, welches Attribut Sie zum Definieren von Segmenten verwenden möchten. (Weitere Informationen finden Sie im [Abschnitt "Referenz"](#reference) in diesem Artikel.)

2. Stellen Sie sicher, dass für die Benutzerkonten Werte für die Attribute angegeben sind, die Sie in Schritt 1 ausgewählt haben. Zeigen Sie Die Details des Benutzerkontos an, und bearbeiten Sie bei Bedarf Benutzerkonten so, dass Attributwerte enthalten sind. 

    - Informationen zum Bearbeiten mehrerer Konten (oder zum Bearbeiten eines einzelnen Kontos mithilfe von PowerShell) finden Sie unter Konfigurieren von Benutzerkontoeigenschaften mit [Office 365 PowerShell.](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

    - Informationen zum Bearbeiten eines einzelnen Kontos finden Sie unter Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers [mithilfe von Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

3. [Definieren Sie Segmente mit PowerShell,](information-barriers-policies.md#define-segments-using-powershell)ähnlich wie in den folgenden Beispielen:

    |**Beispiel**|**Cmdlet**|
    |:----------|:---------|
    | Definieren eines Segments namens "Segment1" mithilfe des Attributs "Department" | `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "Department -eq 'Department1'"` |
    | Definieren Sie ein Segment namens "SegmentA" mit dem Attribut "MemberOf" (angenommen, dieses Attribut enthält Gruppennamen, z. B. "BlueGroup"). | `New-OrganizationSegment -Name "SegmentA" -UserGroupFilter "MemberOf -eq 'BlueGroup'"` |
    | Definieren Sie ein Segment namens DayTraders mithilfe von ExtensionAttribute1 (angenommen, dieses Attribut enthält Auftragstitel, z. B. "DayTrader"). | `New-OrganizationSegment -Name "DayTraders" -UserGroupFilter "ExtensionAttribute1 -eq 'DayTrader'"` |

    > [!TIP]
    > Verwenden Sie beim Definieren von Segmenten dasselbe Attribut für alle Segmente. Wenn Sie beispielsweise einige Segmente mithilfe von *Abteilung* definieren, definieren Sie alle Segmente mithilfe von *Abteilung*. Definieren Sie einige Segmente nicht mithilfe von *Department* und andere nicht mit *MemberOf*. Stellen Sie sicher, dass sich Ihre Segmente nicht überschneiden. Jedem Benutzer sollte genau ein Segment zugewiesen werden.

## <a name="reference"></a>Referenz

In der folgenden Tabelle sind die Attribute aufgeführt, die Sie mit Informationsbarrieren verwenden können.

|**Azure Active Directory-Eigenschaftenname <br/> (LDAP-Anzeigename)**|**Name der Exchange-Eigenschaft**|
|:---------------------------------------------------------------|:-------------------------|
| Co | Co |
| Company | Company |
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
