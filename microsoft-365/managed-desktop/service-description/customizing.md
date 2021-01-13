---
title: Dienstplanausnahmen
description: So fordern Sie Ausnahmen für den Standarddienstplan an
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 97fe3fe1734908c46dcfff4acd76ce9ae5b8b1a5
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841267"
---
# <a name="exceptions-to-the-service-plan"></a>Dienstplanausnahmen

Microsoft Managed Desktop bietet eine [](device-policies.md)behandelte Geräteliste, Standardgeräteeinstellungen, Anwendungsanforderungen und bestimmte konfigurierbare [Einstellungen,](../working-with-managed-desktop/config-setting-overview.md)die alle eine sichere, produktive und angenehme Benutzererfahrung bieten. Es ist am besten, den Dienst immer wie bereitgestellt zu nutzen. Wir sind uns jedoch bewusst, dass einige Details des Diensts möglicherweise nicht genau den Anforderungen Ihrer Organisation entsprechen. Wenn Sie den Dienst in einer bestimmten Weise ändern müssen, ist es wichtig, dass Sie die folgenden Prozesse zum Anfordern dieser Änderungen befolgen.
 
## <a name="types-of-exceptions"></a>Arten von Ausnahmen

Eine Ausnahme ist jede Ergänzung oder Änderung der Microsoft Managed Desktop-Basiskonfiguration. Beispiele reichen von der Konfiguration von USB-Ports bis zur Bereitstellung eines neuen Gerätetreibers. Wir gruppieren verschiedene Ausnahmen wie folgt:

|Typ  |Beschreibung  |
|---------|---------|
|Produktivitätssoftware     |  Von Benutzern benötigte Vordergrundsoftware, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)       |
|Sicherheitsagenten & VPNs     |  Software zum Sichern, Überwachen oder Ändern des Verhaltens des Geräts oder Netzwerks       |
|Überwachung der digitalen Erfahrung     |  Software, die zum Nachverfolgen von Daten auf dem Gerät eines Benutzers verwendet wird, um Berichte an die IT zu senden       |
|Hardware- oder Softwaretreiber     |   Gerätetreiber, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)      |
|Richtlinien     | Windows 10- oder Microsoft 365 Apps for Enterprise-Einstellungen auf einem verwalteten Gerät        |
|Geräte     | Geräte, die nicht in der Microsoft Managed Desktop [-Geräteliste enthalten sind](device-list.md)        |
|Andere     |  Alles, was nicht von den anderen Bereichen abgedeckt wird       |
 
## <a name="request-an-exception"></a>Anfordern einer Ausnahme

Übermitteln Sie Anforderungen über das Microsoft Managed Desktop Admin-Portal, indem Sie eine Änderungsanforderung erstellen. Geben Sie unbedingt die folgenden Details an:

-   Ausnahmetyp: Welche Ausnahmekategorie ist dies? (siehe vorherige Tabelle)
-   Anforderung: Was ist die spezifische geschäftliche Anforderung für die Ausnahme?
-   Vorschlag: Welche Lösung fordert Ihr Unternehmen an?
-   Zeitachse: Wie lange soll diese Ausnahme dauern? 

## <a name="how-we-assess-an-exception-request"></a>Bewerten einer Ausnahmeanforderung

Bei der Überprüfung von Ausnahmeanforderungen werden diese Faktoren in der folgenden Reihenfolge bewertet:
 
1.  Einige Anwendungen und Richtlinien, die Microsoft Managed Desktop auf allen Geräten bereitgestellt, sind nicht verhandelbar, sodass Ihre Anforderung diese nicht betreffen darf. Weitere [Informationen finden Sie unter](device-policies.md) "Gerätekonfiguration".
2.  Eingeschränkte Produktivitätssoftware, die ein Benutzer für seine Arbeit benötigt, wird wahrscheinlich genehmigt. 
3.  Wenn wir Ihre Anforderungen mit der Technologie von Microsoft erfüllen können, genehmigen wir Wahrscheinlichkeit ihre Anforderung für einen Ausnahmemigrationszeitraum von drei bis 12 Monaten (je nach Umfang des Projekts).
4.  Wenn wir Ihre Anforderung mit der Technologie von Microsoft nicht erfüllen können, genehmigen wir Wahrscheinlichkeit nach Ihre Anforderung, es sei denn, sie verletzt eine der folgenden Bedingungen.  

Diese Prinzipien stellen sicher, dass Microsoft Managed Desktop ihre Anforderungen immer erfüllen kann, während Abweichungen von unserer Standardvorlage nachverfolgung werden. 

## <a name="key-conditions"></a>Wichtige Bedingungen

Wir überprüfen Ausnahmen, um sicherzustellen, dass sie keine dieser Bedingungen verletzen:

-   Eine Ausnahme darf sich nicht negativ auf die Systemsicherheit auswirken. 
-   Die Verwaltung der Ausnahme darf weder für Microsoft Managed Desktop noch für support erhebliche Kosten entstehen.
-   Eine Ausnahme darf sich nicht auf die Systemstabilität auswirken, z. B. durch Das Verursachen von Abstürzen oder Hängen des Kernelmodus.
-   Die Änderung darf uns nicht davon abschränken, den Dienst zu verwenden, oder mit der Microsoft Managed Desktop-Kerntechnologie in Konflikt stehen.

Diese Bedingungen können sich in Zukunft ändern. Wenn wir solche Änderungen vornehmen, werden wir 30 Tage vor dem In-Kraft-Treten dieser Bedingungen eine Benachrichtigung bereitstellen.  Wenn Microsoft Managed Desktop eine alternative Möglichkeit bietet, eine genehmigte Ausnahme zu erfüllen, benachrichtigt Microsoft Managed Desktop den Kunden, wenn Microsoft Managed Desktop die Art und Weise der Unterstützung der Ausnahme ändert. 

## <a name="revoking-approval-for-an-exception"></a>Die Genehmigung für eine Ausnahme wird wieder erteilt.

Nachdem eine angeforderte Ausnahme genehmigt und bereitgestellt wurde, kann es sein, dass probleme auftreten, die die wichtigsten Bedingungen verletzen, die bei der Genehmigung der Änderung nicht offensichtlich waren. In diesem Fall müssen wir möglicherweise die Genehmigung für die Ausnahme widerrufen.
 
In diesem Fall benachrichtigen wir Sie über das Microsoft Managed Desktop-Verwaltungsportal. Ab der ersten Benachrichtigung haben Sie 90 Tage Zeit, um die Ausnahme zu entfernen, bevor die Geräte mit der Ausnahme nicht mehr an Die Vereinbarungen zum Servicelevel von Microsoft Managed Desktop gebunden sind. Wir senden Ihnen mehrere Benachrichtigungen gemäß einer strikten Zeitachse. Bei einem schwerwiegenden Vorfall oder einer Bedrohung müssen wir jedoch möglicherweise die Zeitachse oder unsere Entscheidungen zu einer Ausnahme ändern. Wir entfernen keine *Ausnahme* ohne Ihre Zustimmung, aber jedes Gerät mit einer widerrufenen Ausnahme ist nicht mehr an unsere Vereinbarung zum Servicelevel gebunden. Hier ist die Zeitachse der Benachrichtigungen, die wir Ihnen senden:

- **Erster Hinweis:** Wir stellen den ersten Hinweis auf unsere Entscheidung zum Widerrufen der Genehmigung zur Verfügung, einschließlich Informationen dazu, warum wir sie widerrufen, die Von Ihnen zu ergreifenden Maßnahmen, den Stichtag für diese Aktionen und die zu befolgenden Schritte, wenn Sie gegen die Entscheidung vorgehen möchten. Dieser Hinweis tritt 90 Tage im Voraus auf, bevor die Ausnahme von allen Geräten entfernt werden muss. 
- **Zweiter Hinweis (30 Tage später):** Wir stellen einen zweiten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis enthalten sind. 
- **Dritter Hinweis (60 Tage nach dem ersten Hinweis):** Wir stellen einen dritten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis enthalten sind. 
- **Letzter Hinweis (eine Woche vor Ablauf der Frist von 90 Tage):** Wir stellen einen vierten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis enthalten sind.
- **90 Tage nach dem ersten Hinweis:** Vereinbarungen zum Servicelevel von Microsoft Managed Desktop gelten nicht mehr für Geräte mit der widerrufenen Ausnahme. Sie können die Entscheidung jederzeit in Frage stellen und zusätzliche Informationen zur Prüfung bereitstellen, z. B. Upgrade, Konfigurationsänderungen oder Softwareänderungen. 


