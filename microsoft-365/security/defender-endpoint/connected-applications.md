---
title: Verbundene Anwendungen in Microsoft Defender für Endpunkt
ms.reviewer: ''
description: Zeigen Sie verbundene Partneranwendungen an, die das standardmäßige OAuth 2.0-Protokoll zum Authentifizieren und Bereitstellen von Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs verwenden.
keywords: Partner, Anwendungen, Drittanbieter, Verbindungen, Sentinelone, Spur, Bitdefender, Corrata, Morphisec, paloalto, ziften, besser mobil
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
ms.openlocfilehash: 4b212acdf4bdf8fa53ef00763463190e204fc1ed
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339166"
---
# <a name="connected-applications-in-microsoft-defender-for-endpoint"></a>Verbundene Anwendungen in Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

Verbundene Anwendungen können mithilfe von APIs in die Defender für Endpunkt-Plattform integriert werden. 

Anwendungen verwenden das OAuth 2.0-Standardprotokoll zum Authentifizieren und Bereitstellen von Token für die Verwendung mit Microsoft Defender für Endpunkt-APIs.  Darüber hinaus können Mandantenadministratoren Azure Active Directory (Azure AD)-Anwendungen explizit steuern, auf welche APIs mithilfe der entsprechenden App zugegriffen werden kann.
 
Sie müssen diese [Schritte](/microsoft-365/security/defender-endpoint/apis-intro) ausführen, um die APIs mit der verbundenen Anwendung zu verwenden.
 
## <a name="access-the-connected-application-page"></a>Zugreifen auf die verbundene Anwendungsseite
Wählen Sie im linken **Navigationsmenü**  >  **Endpunktpartner und**  >  **APIs Verbundene Anwendungen** aus.

 
## <a name="view-connected-application-details"></a>Anzeigen von Details zu verbundenen Anwendungen
Die Seite "Verbundene Anwendungen" enthält Informationen zu den Azure AD-Anwendungen, die mit Microsoft Defender für Endpunkt in Ihrer Organisation verbunden sind. Sie können die Verwendung der verbundenen Anwendungen überprüfen: zuletzt gesehen, anzahl der Anforderungen in den letzten 24 Stunden und Anforderungstrends in den letzten 30 Tagen.

![Abbildung der verbundenen Apps](images/connected-apps.png)
 
## <a name="edit-reconfigure-or-delete-a-connected-application"></a>Bearbeiten, Neukonfigurieren oder Löschen einer verbundenen Anwendung
Über den Link **"Anwendungseinstellungen öffnen"** wird die entsprechende Azure AD-Anwendungsverwaltungsseite im Azure-Portal geöffnet. Über das Azure-Portal können Sie Berechtigungen verwalten, neu konfigurieren oder die verbundenen Anwendungen löschen.
