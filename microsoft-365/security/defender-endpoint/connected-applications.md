---
title: Verbundene Anwendungen in Microsoft Defender for Endpoint
ms.reviewer: ''
description: Anzeigen von Anwendungen mit verbundenen Partnern, die das Standard-OAuth 2.0-Protokoll verwenden, um sich zu authentifizieren und Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs zur Verfügung zu stellen.
keywords: partner, applications, third-party, connections, sentinelone, lookout, bitdefender, corrata, morphisec, paloalto, ziften, better mobile
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 26c531c0544f92d664bfa0f1a21e4f33a0765d24
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893497"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Verbundene Anwendungen in Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Verbundene Anwendungen werden mithilfe von APIs in die Defender for Endpoint-Plattform integriert. 

Anwendungen verwenden das Standard-OAuth 2.0-Protokoll, um sich zu authentifizieren und Token für die Verwendung mit Microsoft Defender for Endpoint-APIs zur Verfügung zu stellen.  Darüber hinaus können Mandantenadministratoren mit Azure Active Directory (Azure AD)-Anwendungen explizit steuern, auf welche APIs über die entsprechende App zugegriffen werden kann.
 
Sie müssen diese Schritte [ausführen,](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/apis-intro) um die APIs mit der verbundenen Anwendung zu verwenden.
 
## <a name="access-the-connected-application-page"></a>Zugreifen auf die Seite der verbundenen Anwendung
Wählen Sie im linken Navigationsmenü **Partner & APIs**  >  **Connected AAD applications aus.**

 
## <a name="view-connected-application-details"></a>Anzeigen verbundener Anwendungsdetails
Die Seite Verbundene Anwendungen enthält Informationen zu den Azure AD-Anwendungen, die mit Microsoft Defender for Endpoint in Ihrer Organisation verbunden sind. Sie können die Verwendung der verbundenen Anwendungen überprüfen: zuletzt gesehen, Anzahl der Anforderungen in den letzten 24 Stunden und Anforderungstrends in den letzten 30 Tagen.

![Abbildung von verbundenen Apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Bearbeiten, Neukonfiguration oder Löschen einer verbundenen Anwendung
Der **Link Anwendungseinstellungen öffnen** öffnet die entsprechende Azure AD-Anwendungsverwaltungsseite im Azure-Portal. Über das Azure-Portal können Sie Berechtigungen verwalten, die verbundenen Anwendungen neu konfigurieren oder löschen.
