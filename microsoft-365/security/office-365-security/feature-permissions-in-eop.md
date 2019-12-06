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
ms.openlocfilehash: dcf56a5295f7964b2271331deb2e7f8c1ba1635e
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871851"
---
# <a name="feature-permissions-in-eop"></a>Featureberechtigungen in EOP

Die erforderlichen Berechtigungen zum Ausführen von Aufgaben zum Verwalten von Exchange Online Schutz (EoP) hängen von dem Feature ab, das Sie verwalten.

Zum Einrichten von EOP müssen Sie globaler Office 365-Administrator oder Exchange-Unternehmensadministrator (Rollengruppe „Organisationsverwaltung") sein.

## <a name="exchange-online-protection-permissions"></a>Exchange Online Protection-Berechtigungen

In der folgenden Tabelle sind die Berechtigungen aufgeführt, die für die Verwaltung der EOP-Funktionen erforderlich sind. Wenn für eine Funktion mehr als eine Rollengruppe aufgelistet wird, muss Ihnen lediglich eine der Rollengruppen zugewiesen sein, um diese Funktion nutzen zu können.

|**Funktion**|**Erforderliche Berechtigungen**|
|:-----|:-----|
|Antischadsoftware|Organisationsverwaltung <br/><br/> Nachrichtenschutz|
|Antispam|Organisationsverwaltung <br/><br/> Nachrichtenschutz|
|Nachrichtenflussregeln|Organisationsverwaltung <br/><br/> Datensatzverwaltung|
|Domänen|Organisationsverwaltung <br/><br/> Organisationsverwaltung – nur Leserechte|
|Advanced Threat Protection (ATP)|Organisationsverwaltung <br/><br/> Nachrichtenschutz|
|Office 365-Connectors|Organisationsverwaltung|
|Nachrichtenablaufverfolgung|Organisationsverwaltung <br/><br/> Organisationsverwaltung – nur Leserechte|
|Organisationskonfiguration|Organisationsverwaltung|
|Quarantine|Organisationsverwaltung <br/><br/> Organisationsverwaltung – nur Leserechte <br/><br/> Nachrichtenschutz|
|Benutzer, Kontakte und Rollengruppen|Organisationsverwaltung <br/><br/> Organisationsverwaltung – nur Leserechte <br/><br/> Nachrichtenschutz|
|Verteilergruppen und Sicherheitsgruppen|Organisationsverwaltung <br/><br/> Organisationsverwaltung – nur Leserechte <br/><br/> Nachrichtenschutz|
|Berichte anzeigen|Organisationsverwaltung: Zugriff auf e-Mail-Schutz Berichte. <br/><br/> View-Only Recipients: Zugriff auf e-Mail-Schutz Berichte.  <br/><br/> Compliance-Verwaltung: Zugriff auf e-Mail-Schutz Berichte und DLP-Berichte (Data Loss Prevention) (wenn Ihr Abonnement über DLP-Funktionen verfügt).|
