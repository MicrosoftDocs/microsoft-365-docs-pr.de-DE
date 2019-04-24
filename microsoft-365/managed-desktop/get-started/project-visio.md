---
title: Installieren von Microsoft Project oder Microsoft Visio auf verwalteten Desktop Geräten von Microsoft
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 5c820e36b7b397fe770216ee229e38a1da5b034d
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32288996"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installieren von Microsoft Project oder Microsoft Visio auf verwalteten Desktop Geräten von Microsoft

Microsoft Project und Microsoft Visio erfordern bestimmte Schritte für die Installation auf Microsoft-Desktop Geräten. In diesem Thema werden die Voraussetzungen und der Installationsvorgang für diese Anwendungen dokumentiert.

## <a name="prerequisites"></a>Voraussetzungen

Administratoren sollten überprüfen, ob Sie diese Voraussetzungen erfüllen:
- **Lizenzmengen** – die richtige Menge an Microsoft Project-und Microsoft Visio-Lizenzen muss für Ihre Benutzer verfügbar sein. Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen. 
- **Lizenznamen** – die entsprechenden Lizenznamen für diese Anwendungen sind:
    - **Microsoft Project** -Project Online Professional oder Project Online Premium
    - **Microsoft Visio** -Visio Online-Plan 2
- **Unternehmensportal** – das Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können. Wenn das Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, finden Sie weitere Informationen unter [Unternehmensportal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Bereitstellen von Project und Visio für Microsoft Managed Desktop-Geräte
Nachdem Sie Ihre Supportanfrage übermittelt haben, erstellt Microsoft Managed Desktop drei Azure AD-Gruppen und drei Anwendungsbereitstellungen über Microsoft InTune, um die apps für Ihren Mandanten bereitzustellen.  

**So stellen Sie Project und Visio bereit**
1. **Datei eine Supportanfrage** IT-Administratoren müssen eine Supportanfrage einreichen, damit diese Anwendungen Ihren Benutzern zur Verfügung stehen. Informationen zur Kontaktaufnahme mit Microsoft Managed Desktop finden Sie unter [Admin Support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
2. **Zuweisen von Benutzern zu neuen Azure Ad-Gruppen** Microsoft Managed Desktop erstellt 3 Azure AD-Gruppen in Ihrem Mandanten und 3 entsprechende Anwendungsbereitstellungen. IT-Administratoren müssen die Benutzer den entsprechenden Gruppen zuweisen.

>[!NOTE]
>Weisen Sie Benutzer nur einer dieser Azure AD-Gruppen zu. 

Name der Azure AD-Gruppe | Welche Benutzer sollen zugewiesen werden?   
 --- | ---
Microsoft-Office-Project-install | Benutzer, die nur Project benötigen
Microsoft-Office-Visio-install | Benutzer, die nur Visio benötigen
Microsoft-Office-Project und Visio-install | Benutzer, die sowohl Project als auch Visio benötigen

Nach der Zuweisung zu diesen Gruppen stehen Anwendungen im Unternehmens Portal zur Verfügung. Es kann einige Minuten dauern, bis die Synchronisierung stattfindet, aber dann können Ihre Benutzer die apps über das Unternehmens Portal installieren. 

## <a name="communicate-changes"></a>Kommunizieren von Änderungen
Es ist wichtig, dass IT-Administratoren ihre Benutzer über die Installation von Project und Visio informieren können. Dies umfasst Folgendes: 
- Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind. 
- Anweisungen zur Installation dieser Anwendungen über das Unternehmens Portal.

>[!NOTE]
>Benutzer müssen alle Office-Anwendungen schließen, bevor Sie Microsoft Project oder Microsoft Visio aus dem Unternehmens Portal installieren. 
