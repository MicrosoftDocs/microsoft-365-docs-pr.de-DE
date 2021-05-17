---
title: Anwendungen in Microsoft Managed Desktop
description: Erläutert, wie Apps behandelt werden, einschließlich des Packens, Bereitstellens und Unterstützens von Apps.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028944"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Anwendungen in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps im Allgemeinen

Microsoft enthält bestimmte wichtige Apps zusammen mit der Microsoft 365 E3- oder E5-Lizenz, die für die Teilnahme an Microsoft Managed Desktop erforderlich ist. Obwohl wir diese Apps bereitstellen, müssen Sie dennoch bestimmte Verantwortlichkeiten und Aktionen ausführen.

Sie können ihren Benutzern auch zusätzliche Nicht-Microsoft-Apps für self-service über das Unternehmensportal oder eine erforderliche Hintergrundinstallation bereitstellen, die alle die Bereitstellungspipeline von Microsoft Intune verwenden. 

## <a name="apps-provided-by-microsoft"></a>Von Microsoft bereitgestellte Apps

Ihre Microsoft Managed Desktop-Lizenz umfasst 64-Bit-Versionen der Apps in der Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business und OneNote).) Click-to-Run-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, Sie können jedoch anfordern, dass sie hinzugefügt werden. Weitere Informationen zu diesen Apps finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Was Microsoft zur Unterstützung der von uns zur Verfügung stellten Apps tut

Microsoft stellt full service für die Bereitstellung, das Update und den Support für die enthaltenen Microsoft 365 Apps for Enterprise-Apps zur Verfügung. Click-to-Run-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, aber Microsoft Managed Desktop stellt Bereitstellungsgruppen zur Verfügung, mit denen Ihr IT-Administrator Lizenzen verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitstellen kann. Microsoft unterstützt Benutzer dieser Anwendungen über die Microsoft Managed Desktop-Supportkanäle.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Was Sie tun müssen, um die von uns zur Verfügung stellten Apps zu unterstützen?

Es gibt noch bestimmte Dinge, die Sie mit diesen Apps tun müssen:

- **Zuweisen von** Lizenzen – Sie sind für das Abrufen und Zuweisen der entsprechenden Lizenzen an Benutzer für Microsoft 365 Apps for Enterprise verantwortlich.
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** – Wenn Sie Microsoft Project oder Visio verwenden, muss Ihr IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind auch für die Gewinnung von Lizenzen von diesen Benutzern verantwortlich, wenn sie das Unternehmen verlassen.
- Bereitstellen von **Microsoft 365-Add-Ons** – Wenn Sie Add-Ons für eine der Microsoft 365 Apps for Enterprise-Apps benötigen, stellen Sie sie zentral wie jede andere Windows 32-App zur Verfügung. 

## <a name="apps-you-provide"></a>Apps, die Sie bereitstellen

Wahrscheinlich verfügen Sie über andere Apps, die Sie für Ihre Geschäftsvorgänge benötigen. Diese Apps können nur mithilfe der Bereitstellungspipeline von Microsoft Intune auf Microsoft Managed Desktop-Geräten bereitgestellt werden. Weitere Informationen zur Anwendungsbereitstellung finden Sie unter Bereitstellen von [Apps auf Microsoft Managed Desktop-Geräten.](../get-started/deploy-apps.md)

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Vorbereiten Ihrer eigenen Apps für die Integration in Microsoft Managed Desktop
Überprüfen Sie Ihre Apps, und überprüfen Sie:

- Keine der Apps ist verboten oder hat ein eingeschränktes Verhalten, wie unter [Microsoft Managed Desktop App Requirements beschrieben.](../service-description/mmd-app-requirements.md)
- Apps müssen für die Verwaltung durch Microsoft Intune bereit sein. Weitere Informationen zu diesem Thema finden Sie unter [Windows 10-App-Bereitstellung mit Microsoft Intune](/intune/apps-windows-10-app-deploy) und Hinzufügen von Apps zu Microsoft [Intune](/intune/apps-add).
- Andere Pre-Packaging-Anforderungen, z. B. das Bereitstellen von Lizenzschlüsseln, die Vereinbarung mit Lizenzbedingungen und das Festlegen von Serververbindungen.

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfen [Sie Voraussetzungen für Microsoft Managed Desktop](prerequisites.md).
2. Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md) (Dieser Artikel)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
