---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9fd46410877012d92e847ba7ff8b60cd5acceb1e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925539"
---
# <a name="install-microsoft-project-or-microsoft-visio-on-microsoft-managed-desktop-devices"></a>Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop Geräten

für Microsoft Project und Microsoft Visio müssen bestimmte Schritte auf Microsoft Managed Desktop Geräten installiert werden. In diesem Thema werden die Voraussetzungen und der Installationsprozess für diese Anwendungen dokumentiert.

## <a name="prerequisites"></a>Voraussetzungen

Administratoren sollten überprüfen, ob sie die folgenden Voraussetzungen erfüllen:
- **Lizenzmengen** – Die richtige Menge an Microsoft Project und Microsoft Visio Lizenzen müssen für Ihre Benutzer verfügbar sein. Microsoft Managed Desktop unterstützt derzeit nur 64-Bit-Versionen dieser Anwendungen. 
- **Lizenznamen:** Die entsprechenden Lizenznamen für diese Anwendungen sind:
    - **Microsoft Project** – Project Online Professional oder Project Online Premium
    - **Microsoft Visio** – Visio Onlineplan 2
- **Unternehmensportal:** Die Unternehmensportal muss in Ihrem Mandanten verfügbar sein, damit Ihre Benutzer diese Anwendungen installieren können. Wenn die Unternehmensportal nicht in Ihrem Mandanten bereitgestellt wird, lesen Sie [Unternehmensportal](company-portal.md).

## <a name="deploy-project-and-visio-for-microsoft-managed-desktop-devices"></a>Bereitstellen von Project und Visio für Microsoft Managed Desktop Geräte
Microsoft Managed Desktop fügt Microsoft Project und Microsoft Visio als zwei Win32-Anwendungen in Microsoft Intune hinzu. Außerdem erstellen wir zwei Gruppen in Azure Active Directory, die der entsprechenden Anwendung mit der Absicht "Verfügbar" zugewiesen werden. 

**So stellen Sie Project und Visio bereit** Fügen Sie den Benutzer zur entsprechenden Gruppe hinzu, und die Anwendung wird im Unternehmensportal verfügbar. Die Synchronisierung kann einige Minuten dauern, aber dann können Ihre Benutzer die Apps über Unternehmensportal installieren. 

Name der Azure AD-Gruppe | Welche Benutzer müssen zugewiesen werden?   
 --- | ---
Moderne Workplace-Office-Project_Install | Benutzer, die Project benötigen
Moderne Workplace-Office-Visio_Install | Benutzer, die Visio benötigen

## <a name="communicate-changes"></a>Kommunizieren von Änderungen
IT-Administratoren müssen ihren Benutzern mitteilen, wie Project und Visio installiert werden. Dies umfasst Folgendes: 
- Benutzer benachrichtigen, wenn diese Anwendungen für sie verfügbar sind. 
- Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmensportal.
