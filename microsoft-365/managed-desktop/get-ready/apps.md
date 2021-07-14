---
title: Anwendungen in Microsoft Managed Desktop
description: Erläutert, wie Apps behandelt werden, z. B. wie sie verpackt, bereitgestellt und unterstützt werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430768"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Anwendungen in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps im Allgemeinen

Microsoft enthält bestimmte wichtige Apps zusammen mit der Microsoft 365 E3- oder E5-Lizenz, die für die Teilnahme an Microsoft Managed Desktop erforderlich ist. Obwohl wir diese Apps bereitstellen, müssen Sie dennoch bestimmte Verantwortlichkeiten und Aktionen ausführen.

Sie können ihren Benutzern auch zusätzliche Nicht-Microsoft-Apps für self-service über die Unternehmensportal oder eine erforderliche Hintergrundinstallation bereitstellen, die alle die Bereitstellungspipeline Microsoft Intune verwenden. 

## <a name="apps-provided-by-microsoft"></a>Von Microsoft bereitgestellte Apps

In Ihrer Microsoft Managed Desktop-Lizenz sind 64-Bit-Versionen der Apps in der Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams und OneNote) enthalten. Klick-und-Los-Versionen von Microsoft Project und Visio sind standardmäßig *nicht* enthalten, Sie können jedoch anfordern, dass sie hinzugefügt werden. Weitere Informationen zu diesen Apps finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop Geräten.](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Was Microsoft tut, um die von uns bereitgestellten Apps zu unterstützen

Microsoft bietet Volldienst für die Bereitstellung, das Update und den Support für die enthaltenen Microsoft 365 Apps for Enterprise-Apps. Klick-und-Los-Versionen von Microsoft Project und Visio sind *standardmäßig nicht* enthalten, aber Microsoft Managed Desktop stellt Bereitstellungsgruppen bereit, mit denen Ihr IT-Administrator Lizenzen verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitstellen kann. Microsoft unterstützt Benutzer dieser Anwendungen über die Microsoft Managed Desktop Supportkanäle.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Was Sie tun müssen, um die von uns bereitgestellten Apps zu unterstützen

Es gibt noch bestimmte Dinge, die Sie mit diesen Apps tun müssen:

- **Zuweisen von Lizenzen** – Sie sind für das Abrufen und Zuweisen der entsprechenden Lizenzen für Benutzer für Microsoft 365 Apps for Enterprise verantwortlich.
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** – Wenn Sie Microsoft Project oder Visio verwenden, muss Ihr IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind auch dafür verantwortlich, Lizenzen von diesen Benutzern freizugeben, wenn sie das Unternehmen verlassen.
- **Bereitstellen von Microsoft 365-Add-Ons–** Wenn Sie Add-Ons für eine der Microsoft 365 Apps for Enterprise-Apps benötigen, stellen Sie sie zentral wie jede andere Windows 32-App bereit. 

## <a name="apps-you-provide"></a>Von Ihnen bereitgestellte Apps

Wahrscheinlich verfügen Sie über andere Apps, die Sie für Ihre Geschäftsvorgänge benötigen. Diese Apps können nur mithilfe der Bereitstellungspipeline von Microsoft Intune auf Microsoft Managed Desktop Geräten bereitgestellt werden. Weitere Informationen zur Anwendungsbereitstellung finden Sie unter [Bereitstellen von Apps auf Microsoft Managed Desktop Geräten.](../get-started/deploy-apps.md)

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Vorbereiten Ihrer eigenen Apps für die Aufnahme in Microsoft Managed Desktop
Überprüfen Sie Ihre Apps, und überprüfen Sie:

- Keine der Apps ist verboten oder hat eingeschränktes Verhalten, wie in [Microsoft Managed Desktop App-Anforderungen](../service-description/mmd-app-requirements.md)beschrieben.
- Apps müssen für die Verwaltung durch Microsoft Intune bereit sein. Weitere Informationen zu diesem Thema finden Sie unter [Windows 10 App-Bereitstellung mit Microsoft Intune](/intune/apps-windows-10-app-deploy) und Hinzufügen von Apps zu [Microsoft Intune.](/intune/apps-add)
- Andere Anforderungen vor dem Verpacken, z. B. Bereitstellen von Lizenzschlüsseln, Vereinbarung mit Lizenzbedingungen und Vorabeinstellung von Serververbindungen.

## <a name="steps-to-get-ready"></a>Schritte zum Vorbereiten

1. Überprüfen Sie [die Voraussetzungen für Microsoft Managed Desktop.](prerequisites.md)
2. Verwenden Sie [Bereitschaftsbewertungstools.](readiness-assessment-tool.md)
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps in Microsoft Managed Desktop](apps.md) (dieser Artikel)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
