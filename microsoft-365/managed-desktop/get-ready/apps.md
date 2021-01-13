---
title: Anwendungen in Microsoft Managed Desktop
description: Erläutert, wie Apps behandelt werden, einschließlich der Art und Weise, wie Sie sie packen, bereitstellen und unterstützen.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 20d68ec007ccda82816ad2288428016019f6d4b2
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840693"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Anwendungen in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps im Allgemeinen

Microsoft umfasst bestimmte wichtige Apps zusammen mit der Microsoft 365 E3- oder E5-Lizenz, die für die Teilnahme an Microsoft Managed Desktop erforderlich ist. Obwohl wir diese Apps bereitstellen, müssen Sie dennoch bestimmte Aufgaben und Aktionen ausführen.

Sie können ihren Benutzern auch zusätzliche Nicht-Microsoft-Apps zur Self-Service-Bereitstellung über das Unternehmensportal oder eine erforderliche Hintergrundinstallation bereitstellen, und dies alles über die Bereitstellungspipeline von Microsoft Intune. Wenn Sie über das Fachwissen verfügen, können Sie die benötigten Apps selbst migrieren. Alternativ können Microsoft Consulting Services (MCS) oder Nicht-Microsoft-Anbieter Ihnen bei einem Paket- und Migrationsprojekt helfen. Weitere Informationen zum Arbeiten mit MCS finden Sie unter [Arbeiten mit Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Von Microsoft bereitgestellte Apps

In Ihrer Microsoft Managed Desktop-Lizenz sind 64-Bit-Versionen der Apps in der Microsoft 365 Apps for Enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business und OneNote) enthalten. Klick-und-Klick-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, Sie können jedoch anfordern, dass sie hinzugefügt werden. Weitere Informationen zu diesen Apps finden Sie unter "Installieren von [Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten".](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>What Microsoft does to support the apps we provide

Microsoft stellt den vollständigen Dienst für die Bereitstellung, das Update und den Support für die enthaltenen Microsoft 365 Apps for Enterprise-Apps zur Verfügung. Klick-und-Klick-Versionen von Microsoft  Project und Visio sind standardmäßig nicht enthalten, aber Microsoft Managed Desktop stellt Bereitstellungsgruppen zur Verfügung, mit denen Ihr IT-Administrator Lizenzen verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitstellen kann. Microsoft unterstützt Benutzer dieser Anwendungen über die Microsoft Managed Desktop-Supportkanäle.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Was Sie tun müssen, um die von uns zur Verfügung stellten Apps zu unterstützen?

Es gibt noch bestimmte Dinge, die Sie mit diesen Apps tun müssen:

- **Zuweisen von** Lizenzen – Sie sind für das Abrufen und Zuweisen der entsprechenden Lizenzen an Benutzer für Microsoft 365 Apps for Enterprise verantwortlich.
- **Hinzufügen von Benutzern zu Sicherheitsgruppen:** Wenn Sie Microsoft Project oder Visio verwenden, muss Ihr IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen. It administrators are also responsible for reclaiming licenses from those users if they leave the company.
- Bereitstellen von **Microsoft 365-Add-Ons** : Wenn Sie Für eine der Microsoft 365 Apps for Enterprise-Apps Add-Ons benötigen, stellen Sie diese zentral wie jede andere Windows 32-App zur Verfügung. 

## <a name="apps-you-provide"></a>Von Ihnen zur Verfügung stellende Apps

Wahrscheinlich verfügen Sie über andere Apps, die Sie für Ihre Geschäftsvorgänge benötigen. Diese Apps können nur mithilfe der Bereitstellungspipeline von Microsoft Intune auf Microsoft Managed Desktop-Geräten bereitgestellt werden. Wenn die App sie benötigt, können Sie sie von einem Anbieter (bei dem es sich um einen Nicht-Microsoft-Anbieter oder Microsoft Consulting Services (MCS) oder über die Mittel verfügen, packen Lassen Sie sie selbst packen. Anschließend fügen Sie diese Pakete dem Microsoft Managed Desktop-Portal hinzu und weisen sie Azure Active Directory-Gruppen zu, um die Bereitstellung auszulösen. 

Wenn Sie Ihre Apps derzeit mithilfe von Microsoft Endpoint Configuration Manager bereitstellen, kann Ihnen Microsoft Managed Desktop eine Abfrage bereitstellen, um Ihre Apps zu bewerten und zu ermitteln, welche Apps für die Migration zu Microsoft Intune bereit sind und welche anpassungen erforderlich sein können.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Vorbereiten Ihrer eigenen Apps für die Integration in Microsoft Managed Desktop
Überprüfen Sie Ihre Apps, und überprüfen Sie dabei:

- Keine der Apps ist verboten oder hat ein eingeschränktes Verhalten, wie in [den Microsoft Managed Desktop-App-Anforderungen beschrieben.](https://aka.ms/app-req)
- Apps müssen für die Verwaltung durch Microsoft Intune bereit sein. Weitere Informationen zu diesem Thema finden Sie unter [Windows 10-App-Bereitstellung mit Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) und Hinzufügen von Apps zu Microsoft [Intune.](https://docs.microsoft.com/intune/apps-add)
- Weitere Pre-Packaging-Anforderungen, z. B. das Bereitstellen von Lizenzschlüsseln, die Vereinbarung mit Lizenzbedingungen und das Voreinstellungen von Serververbindungen.

### <a name="decide-how-to-package-apps"></a>Entscheiden, wie Apps gepackt werden

Einige unabhängige Softwareherausgeber erfordern möglicherweise, dass Ihre Apps verpackt werden, bevor sie zentral bereitgestellt werden. "Verpacken" bedeutet, dass das Installationsprogramm der App mit Einstellungen wie Lizenzschlüsseln, Remoteserverstandorten oder Desktopverknüpfungen konfiguriert ist, sodass die App im Hintergrund installiert werden kann.

Es gibt drei Optionen zum Packen Ihrer Apps: 


- Sie können Apps selbst packen
- Sie können mit einem Nicht-Microsoft-Anbieter zusammenarbeiten.
- Sie können mit MCS interagieren, um Ihre Apps zu packen. Arbeiten Sie mit Ihrem Microsoft-Konto-Vertreter zusammen. Weitere Informationen finden Sie unter [Arbeiten mit Microsoft Consulting Services](apps-MCS.md).



## <a name="deploying-apps"></a>Bereitstellen von Apps

Unabhängig davon, welche Methode Sie zum Packen von Apps verwenden, können Sie nach Abschluss des Vorgangs die Schritte in "Bereitstellen von Apps auf [Microsoft Managed Desktop-Geräten" ausführen.](../get-started/deploy-apps.md)


