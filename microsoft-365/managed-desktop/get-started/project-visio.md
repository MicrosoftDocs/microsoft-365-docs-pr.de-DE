---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 203db332e1fcd7861f40c69b138ac8274544dceb
ms.sourcegitcommit: 6cabf0226de1c95bff6ddb1852dac5ecdb2d6b96
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/23/2019
ms.locfileid: "35830473"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten

Microsoft Project und Microsoft Visio erfordern bestimmte Schritte, die auf Microsoft Managed Desktop-Geräten installiert werden müssen. In diesem Thema werden die Voraussetzungen und der Installationsvorgang für diese Anwendungen dokumentiert.

## <a name="prerequisites"></a>Voraussetzungen

Administratoren sollten überprüfen, ob Sie diese Voraussetzungen erfüllen:
- **Lizenzmengen** – die richtige Menge an Microsoft Project-und Microsoft Visio Lizenzen müssen für Ihre Benutzer verfügbar sein. Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen. 
- **Lizenznamen** – die entsprechenden Lizenznamen für diese Anwendungen sind:
    - **Microsoft Project** -Project Online Professional oder Project Online Premium
    - **Microsoft Visio** -Visio Online-Plan 2
- **Unternehmensportal** : das Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können. Wenn das Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, finden Sie weitere Informationen unter [Unternehmensportal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Bereitstellen von Project und Visio für Microsoft Managed Desktop-Geräte
Nachdem Sie Ihre Supportanfrage gesendet haben, erstellt Microsoft Managed Desktop drei Azure Ad Gruppen und drei Anwendungsbereitstellungen über Microsoft InTune, um die apps für Ihren Mandanten bereitzustellen.  

**So stellen Sie Project und Visio bereit**
1. **Datei eine Supportanfrage** IT-Administratoren müssen eine Support-Anforderung einreichen, um diese Anwendungen Ihren Benutzern zur Verfügung zu stellen. Informationen zum Kontaktieren von Microsoft Managed Desktop finden Sie unter [Administrator Unterstützung für Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).
2. **Zuweisen von Benutzern zu neuen Azure Ad Gruppen** Microsoft Managed Desktop erstellt drei Azure Ad Gruppen in Ihrem Mandanten und 3 entsprechende Anwendungsbereitstellungen. IT-Administratoren müssen die Benutzer den entsprechenden Gruppen zuweisen.

>[!NOTE]
>Weisen Sie Benutzern nur eine dieser Azure Ad Gruppen zu. 

Azure AD Gruppenname | Welche Benutzer sollen zugewiesen werden?   
 --- | ---
Moderner Arbeitsplatz-Office-Project-install | Benutzer benötigen nur Projekt
Moderner Arbeitsplatz – Office – Visio – installieren | Benutzer, die nur Visio benötigen
Moderner Arbeitsplatz – Office-Project und Visio – installieren | Benutzer, die sowohl Project als auch Visio benötigen

Sobald diesen Gruppen zugewiesen ist, sind Anwendungen im Unternehmens Portal verfügbar. Es kann einige Minuten dauern, bis die Synchronisierung ausgeführt wird, aber dann können Ihre Benutzer die Apps aus dem Unternehmens Portal installieren. 

## <a name="communicate-changes"></a>Kommunizieren von Änderungen
Es ist wichtig, dass IT-Administratoren ihren Benutzern mitteilen können, wie Sie Project und Visio installieren. Dies umfasst Folgendes: 
- Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind. 
- Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmens Portal.

>[!NOTE]
>Benutzer müssen alle Office-Anwendungen schließen, bevor Sie Microsoft Project oder Microsoft Visio aus dem Unternehmens Portal installieren. 
