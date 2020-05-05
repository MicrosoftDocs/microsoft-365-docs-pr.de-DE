---
title: Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
description: Informationen zum Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten
keywords: Microsoft Managed Desktop, Microsoft 365, Microsoft Project, Microsoft Visio
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 03/07/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 450dbcb08cd0636dae575ecd2d5e9abadc5ceb25
ms.sourcegitcommit: 44e685a0b193e89de5befb1e1a3740eb31931799
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44022096"
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
Moderner Arbeitsplatz-Office-Project_Install | Benutzer, die Project benötigen
Moderner Arbeitsplatz-Office-Visio_Install | Benutzer, die Visio benötigen

Sobald diesen Gruppen zugewiesen ist, sind Anwendungen im Unternehmens Portal verfügbar. Es kann einige Minuten dauern, bis die Synchronisierung ausgeführt wird, aber dann können Ihre Benutzer die Apps aus dem Unternehmens Portal installieren. 

## <a name="communicate-changes"></a>Kommunizieren von Änderungen
Es ist wichtig, dass IT-Administratoren ihren Benutzern mitteilen können, wie Sie Project und Visio installieren. Dies umfasst Folgendes: 
- Benachrichtigen von Benutzern, wenn diese Anwendungen für Sie verfügbar sind. 
- Anweisungen zum Installieren dieser Anwendungen aus dem Unternehmens Portal.

>[!NOTE]
>Benutzer müssen alle Office-Anwendungen schließen, bevor Sie Microsoft Project oder Microsoft Visio aus dem Unternehmens Portal installieren. 
