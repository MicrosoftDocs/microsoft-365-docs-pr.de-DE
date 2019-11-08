---
title: Featureberechtigungen in EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Die erforderlichen Berechtigungen zum Ausführung von Verwaltungsaufgaben für Microsoft Exchange Online Protection (EOP) variieren abhängig davon, welche Funktion verwaltet werden soll.
ms.openlocfilehash: e3b41ea2b58397a9af2a1cb8ba979b5f816b416b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031910"
---
# <a name="feature-permissions-in-eop"></a>Featureberechtigungen in EOP

Die erforderlichen Berechtigungen zum Ausführen von Aufgaben zum Verwalten von Exchange Online Schutz (EoP) hängen von dem Feature ab, das Sie verwalten.

Zum Einrichten von EOP müssen Sie globaler Office 365-Administrator oder Exchange-Unternehmensadministrator (Rollengruppe „Organisationsverwaltung") sein.

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection-Berechtigungen

In der folgenden Tabelle sind die Berechtigungen aufgeführt, die für die Verwaltung der EOP-Funktionen erforderlich sind. Wenn für eine Funktion mehr als eine Rollengruppe aufgelistet wird, muss Ihnen lediglich eine der Rollengruppen zugewiesen sein, um diese Funktion nutzen zu können.

|**Funktion**|**Erforderliche Berechtigungen**|
|:-----|:-----|
|Antischadsoftware|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Verwaltung von Nachrichtenschutz](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Antispam|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Verwaltung von Nachrichtenschutz](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Nachrichtenflussregeln|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](https://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx)|
|Domänen|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Advanced Threat Protection (ATP)|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Verwaltung von Nachrichtenschutz](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Office 365-Connectors|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Nachrichtenablaufverfolgung|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Organisationskonfiguration|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Quarantäne|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Benutzer, Kontakte und Rollengruppen|[Organisationsverwaltung](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Verteilergruppen und Sicherheitsgruppen|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Berichte anzeigen|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) - Benutzer haben Zugriff auf E-Mail-Schutzberichte.  <br/> [View-Only Recipients](https://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx) - Benutzer haben Zugriff auf E-Mail-Schutzberichte.  <br/> [Compliance Management](https://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx) - Benutzer haben Zugriff auf E-Mail-Schutzberichte und DLP-Berichte (Data Loss Prevention, Schutz vor Datenverlust), sofern ihr Abonnement über DLP-Funktionen verfügt.|
