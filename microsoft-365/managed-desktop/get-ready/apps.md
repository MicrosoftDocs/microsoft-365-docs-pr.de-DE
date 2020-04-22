---
title: Apps in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: a24212cf69df50d00a32f17e8daf1939657dd602
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632851"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Apps in Microsoft Managed Desktop

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>Apps allgemein

Microsoft enthält bestimmte wichtige Apps zusammen mit der Microsoft 365 E3-oder E5-Lizenz, die für die Teilnahme an Microsoft Managed Desktop benötigt wird. Obwohl wir diese apps bereitstellen, haben Sie jedoch immer noch bestimmte Zuständigkeiten und Aktionen.

Sie können auch zusätzliche nicht-Microsoft-Apps für Ihre Endbenutzer zur Self-Service-Bereitstellung über das Unternehmens Portal oder eine erforderliche Hintergrundinstallation mit der Bereitstellungs Pipeline von Microsoft InTune bereitstellen. Wenn Sie über das Fachwissen verfügen, können Sie diese apps, die Sie selbst benötigen, migrieren. Alternativ können Microsoft Consulting Services (MCS) oder nicht-Microsoft-Anbieter Ihnen gerne bei einem Paket-und Migrationsprojekt behilflich sein. Weitere Informationen zum Arbeiten mit MCS finden Sie unter [Working with Microsoft Consulting Services](apps-MCS.md).


## <a name="apps-provided-by-microsoft"></a>Von Microsoft bereitgestellte apps

In Ihrer Microsoft Managed Desktop-Lizenz sind 64-Bit-Versionen der apps in der Microsoft 365-Apps für Enterprise-Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business und OneNote) enthalten. Klick-und-Los-Versionen von Microsoft Project und Visio sind standardmäßig *nicht* enthalten, Sie können jedoch anfordern, dass Sie hinzugefügt werden. Weitere Informationen zu diesen apps finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten](../get-started/project-visio.md).

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Was Microsoft zur Unterstützung der von uns bereitgestellten apps tut

Microsoft stellt den vollständigen Dienst für die Bereitstellung, Aktualisierung und Unterstützung für die enthaltenen Microsoft 365-Apps für Enterprise-apps bereit. Klick-und-Los-Versionen von Microsoft Project und Visio sind *nicht* standardmäßig enthalten, aber Microsoft Managed Desktop stellt Bereitstellungsgruppen zur Verfügung, mit denen Ihr IT-Administrator Lizenzen verwalten und diese Anwendungen entsprechend für Ihre Organisation bereitstellen kann. Microsoft unterstützt Endbenutzer dieser Anwendungen über die Microsoft Managed Desktop-Supportkanäle.

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>Was Sie zur Unterstützung der von uns bereitgestellten apps tun müssen

Es gibt immer noch bestimmte Dinge, die Sie mit diesen apps tun müssen:

- **Zuweisen von Lizenzen** – Sie sind für das Abrufen und Zuweisen der entsprechenden Lizenzen an Endbenutzer für Microsoft 365 apps for Enterprise verantwortlich.
- **Hinzufügen von Benutzern zu Sicherheitsgruppen** – Wenn Sie Microsoft Project oder Visio verwenden, muss Ihr IT-Administrator diese Benutzer den entsprechenden Bereitstellungsgruppen hinzufügen. IT-Administratoren sind außerdem dafür verantwortlich, Lizenzen von diesen Benutzern zurückzufordern, wenn Sie das Unternehmen verlassen.
- **Bereitstellen von Microsoft 365-Add-ons** – Wenn Sie Add-ons für alle Microsoft 365-Apps für Enterprise-apps benötigen, stellen Sie Sie wie jede andere Windows 32-App zentral bereit. 

## <a name="apps-you-provide"></a>Von Ihnen bereitgestellten apps

Natürlich haben Sie wahrscheinlich eine Reihe anderer apps, die Sie für Ihre Geschäftsvorgänge benötigen. Diese können nur auf von Microsoft verwalteten Desktop Geräten mithilfe der Bereitstellungs Pipeline von Microsoft InTune bereitgestellt werden. Wenn die APP dies benötigt, können Sie Sie von einem Anbieter verpacken lassen (Dies kann ein Anbieter von Drittanbietern oder Microsoft Consulting Services (MCS) sein), oder wenn Sie über die Mittel verfügen, können Sie diese selbst verpacken. Anschließend fügen Sie diese Pakete dem Microsoft Managed Desktop Portal hinzu und weisen Sie Azure Active Directory Gruppen zu, um die Bereitstellung auszulösen. 

Wenn Sie Ihre apps derzeit mithilfe von Microsoft Endpoint Configuration Manager bereitstellen, kann Microsoft Managed Desktop Sie mit einer Abfrage zum Bewerten Ihrer Apps und zum ermitteln, welche für die Migration zu Microsoft InTune bereit sind und welche möglicherweise eine gewisse Anpassung erfordern, bereitstellen.


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>Vorbereiten Ihrer eigenen Apps für die Integration in Microsoft Managed Desktop
Überprüfen Sie Ihre apps, und überprüfen Sie Folgendes:

- Keine der apps ist untersagt oder hat ein eingeschränktes Verhalten, wie in den [Microsoft Managed Desktop-App-Anforderungen](https://aka.ms/app-req)beschrieben.
- Apps müssen für die Verwaltung durch Microsoft InTune verfügbar sein. Weitere Informationen hierzu finden Sie unter [Windows 10-App-Bereitstellung mithilfe von Microsoft InTune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) und [Hinzufügen von apps zu Microsoft InTune](https://docs.microsoft.com/intune/apps-add).
- Andere Anforderungen vor dem Verpacken, beispielsweise das Bereitstellen von Lizenzschlüsseln, eine Vereinbarung mit Lizenzbedingungen und die Voreinstellung von Serververbindungen.

### <a name="decide-how-to-package-apps"></a>Entscheiden, wie apps gepackt werden

Einige unabhängige Softwarehersteller erfordern möglicherweise, dass Ihre apps verpackt sind, bevor Sie zentral bereitgestellt werden. "Verpacken" bedeutet, dass das Installationsprogramm der APP mit Einstellungen wie Lizenzschlüsseln, Remoteserver Standorten oder Desktopverknüpfungen konfiguriert ist, damit die APP im Hintergrund installiert werden kann.

Es gibt drei Optionen zum Verpacken Ihrer Apps: 


- Sie können Apps selbst verpacken
- Sie können mit einem anderen Anbieter als Microsoft zusammenarbeiten.
- Sie können sich mit MCS beschäftigen, um Ihre apps zu verpacken. Arbeiten Sie mit Ihrem Microsoft-Konto Vertreter zusammen. Weitere Informationen finden Sie unter [Working with Microsoft Consulting Services](apps-MCS.md).







## <a name="deploying-apps"></a>Bereitstellen von apps

Unabhängig davon, welche Methode Sie zum Verpacken von Apps verwenden, sobald diese abgeschlossen ist, sind Sie bereit, die Schritte unter [Deploy Apps to Microsoft Managed Desktop Devices](../get-started/deploy-apps.md)zu befolgen.


