---
title: Verwalten des Gastzugriffs in Microsoft 365 Gruppen
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
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: Erfahren Sie, wie Sie einer Microsoft 365 Gruppe Gäste hinzufügen, Gastbenutzer anzeigen und PowerShell verwenden, um den Gastzugriff zu steuern.
ms.openlocfilehash: 41a42a0b4fc76b71892f758519db56f4c1adc897
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394063"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>Verwalten des Gastzugriffs in Microsoft 365 Gruppen

Standardmäßig ist der Gastzugriff für Microsoft 365 Gruppen für Ihre Organisation aktiviert. Administratoren können steuern, ob sie den Gastzugriff für die ganze Organisation oder für einzelne Gruppen zulassen möchten.

Wenn sie aktiviert ist, können Gruppenmitglieder Gastbenutzer über Outlook im Web zu einer Microsoft 365 Gruppe einladen. Einladungen werden zur Genehmigung an den Gruppenbesitzer gesendet.

Nach der Genehmigung wird der Gastbenutzer dem Verzeichnis und der Gruppe hinzugefügt.

> [!Note]
> Yammer Enterprise-Netzwerke, die sich im nativen Modus oder im [EU-Gebiet](/yammer/manage-security-and-compliance/manage-data-compliance) befinden, unterstützen keine Netzwerkgäste.
> Microsoft 365 Verbundene Yammer Gruppen unterstützen derzeit keinen Gastzugriff, sie können jedoch nicht verbundene externe Gruppen in Ihrem Yammer Netzwerk erstellen. Entsprechende Anleitungen finden Sie unter [Erstellen und Verwalten von externen Gruppen in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups).

Der Gastzugriff in Gruppen wird häufig als Teil eines breiter gefächerten Szenarios verwendet, das SharePoint oder Teams umfasst. Diese Dienste besitzen ihre eigenen Einstellungen für die Gastfreigabe. Umfassende Anweisungen zum Einrichten der gemeinsamen Nutzung über Gruppen, SharePoint und Teams hinweg finden Sie unter:

- [Zusammenarbeit mit Gästen in einer Website](../../solutions/collaborate-in-site.md)
- [Zusammenarbeit mit Gästen in einem Team](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>Verwalten des Gastzugriffs von Gruppen

Wenn Sie den Gastzugriff in Gruppen aktivieren oder deaktivieren möchten, können Sie dies im Microsoft 365 Admin Center tun.

1. Wechseln Sie im Admin Center zu **"Alle** \> **Organisationseinstellungen Einstellungen** \>  anzeigen", und wählen Sie auf der Registerkarte **"Dienste"** **Microsoft 365 Gruppen** aus.
  
2. Wählen Sie auf der Seite **Microsoft 365 Gruppen** aus, ob Personen außerhalb Ihrer Organisation auf Gruppenressourcen zugreifen oder Gruppenbesitzer Personen außerhalb Ihrer Organisation zu Gruppen hinzufügen möchten.

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>Hinzufügen von Gästen zu einer Microsoft 365-Gruppe aus dem Admin Center

Wenn der Gast bereits in Ihrem Verzeichnis vorhanden ist, können Sie ihn über das Microsoft 365 Admin Center zu Ihren Gruppen hinzufügen. (Gruppen mit dynamischer Mitgliedschaft müssen [in Azure Active Directory verwaltet](/azure/active-directory/enterprise-users/groups-create-rule)werden.)
  
1. Wechseln Sie im Admin Center zur Seite **Gruppen** > **Gruppen**.
  
2. Klicken Sie auf die Gruppe, der Sie den Gast hinzufügen möchten, und wählen Sie auf der Registerkarte **"Mitglieder"** die Option **"Alle anzeigen und Mitglieder verwalten"** aus. 
  
4. Wählen Sie **Mitglieder hinzufügen** und dann den Namen der Person, die Sie hinzufügen möchten.
    
5. Klicken Sie auf **Speichern**.

Wenn Sie einen Gast direkt zum Verzeichnis hinzufügen möchten, können Sie [Benutzer der Azure Active Directory-B2B-Zusammenarbeit im Azure-Portal hinzufügen](/azure/active-directory/b2b/add-users-administrator).

Wenn Sie die Informationen eines Gastes bearbeiten möchten, können Sie die [Profilinformationen eines Benutzers mithilfe von Azure Active Directory hinzufügen oder aktualisieren](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

## <a name="related-content"></a>Verwandte Inhalte

[Blockieren von Gastbenutzern aus einer bestimmten Gruppe](../../solutions/per-group-guest-access.md) (Artikel)\
[Verwalten der Gruppenmitgliedschaft im Microsoft 365 Admin Center](add-or-remove-members-from-groups.md) (Artikel)\
[Azure Active Directory Zugriffsüberprüfungen](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (Artikel)\
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (Artikel)