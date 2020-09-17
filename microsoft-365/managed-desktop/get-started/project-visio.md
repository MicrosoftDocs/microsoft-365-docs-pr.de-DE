---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: c04bcdf846bafaa7838ef5932c8de595f5035992
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950532"
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
Microsoft Managed Desktop wird Microsoft Project und Microsoft Visio als zwei Win32-Anwendungen in Microsoft InTune hinzufügen. Außerdem werden zwei Gruppen in Azure Active Directory erstellt, die der entsprechenden Anwendung mit der "available"-Absicht zugewiesen werden. 

**So stellen Sie Project und Visio bereit** Fügen Sie den Benutzer der entsprechenden Gruppe hinzu, und die Anwendung wird im Unternehmens Portal verfügbar sein. Es kann einige Minuten dauern, bis die Synchronisierung ausgeführt wird, aber dann können Ihre Benutzer die Apps aus dem Unternehmens Portal installieren. 

Azure AD Gruppenname | Welche Benutzer sollen zugewiesen werden?   
 --- | ---
Moderner Arbeitsplatz-Office-Project_Install | Benutzer, die Project benötigen
Moderner Arbeitsplatz-Office-Visio_Install | Benutzer, die Visio benötigen

## <a name="communicate-changes"></a>Kommunizieren von Änderungen
Es ist wichtig, dass IT-Administratoren ihren Benutzern mitteilen können, wie Sie Project und Visio installieren. Dies umfasst Folgendes: 
- Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind. 
- Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmens Portal.
