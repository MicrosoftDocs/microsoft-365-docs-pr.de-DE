---
title: Dienstplanausnahmen
description: Anfordern von Ausnahmen vom Standarddienstplan
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 59a2b8227eb7e410ecf8506ce288978213537edc
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245516"
---
# <a name="exceptions-to-the-service-plan"></a>Dienstplanausnahmen

Microsoft Managed Desktop bietet eine kuratierte [Geräteliste,](device-policies.md)Standardgeräteeinstellungen, Anwendungsanforderungen und bestimmte konfigurierbare [Einstellungen,](../working-with-managed-desktop/config-setting-overview.md)die alle für eine sichere, produktive und angenehme Benutzererfahrung konzipiert sind. Es ist am besten, den Dienst immer wie vorgesehen zu nutzen. Wir sind uns jedoch bewusst, dass einige Details des Diensts möglicherweise nicht genau zu den Anforderungen Ihrer Organisation passen. Wenn Sie der Meinung sind, dass Sie den Dienst in einer bestimmten Weise ändern müssen, ist es wichtig, dass Sie die folgenden Prozesse befolgen, um diese Änderungen an fordern.
 
## <a name="types-of-exceptions"></a>Arten von Ausnahmen

Eine Ausnahme ist jede Ergänzung oder Änderung der Microsoft Managed Desktop Basiskonfiguration. Beispiele reichen von der Konfiguration von USB-Ports bis zur Bereitstellung eines neuen Gerätetreibers. Wir gruppieren verschiedene Ausnahmen wie folgt:

|Typ  |Beschreibung  |
|---------|---------|
|Produktivitätssoftware     |  Von Benutzern benötigte Vordergrundsoftware, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)       |
|Sicherheitsagenten & VPNs     |  Software zum Sichern, Überwachen oder Ändern des Verhaltens des Geräts oder Netzwerks       |
|Überwachung der digitalen Benutzererfahrung     |  Software, die zum Nachverfolgen von Daten auf dem Gerät eines Benutzers zum Melden an die IT verwendet wird       |
|Hardware- oder Softwaretreiber     |   Gerätetreiber, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)      |
|Richtlinien     | Windows 10 oder Microsoft 365 Apps for Enterprise auf einem verwalteten Gerät        |
|Geräte     | Geräte, die nicht in der liste Microsoft Managed Desktop [sind](device-list.md)        |
|Andere     |  Alles, was nicht von den anderen Bereichen abgedeckt wird       |
 
## <a name="request-an-exception"></a>Anfordern einer Ausnahme

Übermitteln Sie Anforderungen über Microsoft Managed Desktop Administratorportal, indem Sie eine Änderungsanforderung erstellen. Stellen Sie sicher, dass Sie die folgenden Details enthalten:

- Ausnahmetyp: Welche Ausnahmekategorie ist dies? (siehe vorherige Tabelle)
- Anforderung: Was ist die spezifische Geschäftliche Anforderung für die Ausnahme?
- Vorschlag: Welche Lösung fordert Ihr Unternehmen an?
- Zeitachse: Wie lange soll diese Ausnahme dauern? 

## <a name="how-we-assess-an-exception-request"></a>Bewerten einer Ausnahmeanforderung

Wenn wir Ausnahmeanforderungen überprüfen, bewerten wir diese Faktoren in der folgenden Reihenfolge:
 
1. Einige Anwendungen und Richtlinien, die Microsoft Managed Desktop auf allen Geräten bereitgestellt werden, sind nicht verhandelbar, sodass Ihre Anforderung keine Auswirkungen auf diese haben darf. Weitere [Informationen finden Sie unter](device-policies.md) Gerätekonfiguration.
2. Eingeschränkte Produktivitätssoftware, die ein Benutzer für seine Aufgabe benötigt, wird wahrscheinlich genehmigt. 
3. Wenn wir Ihre Anforderung mithilfe der Microsoft-Technologie erfüllen können, genehmigen wir Wahrscheinlich Ihre Anforderung für einen Ausnahmemigrationszeitraum von drei bis 12 Monaten (abhängig vom Umfang des Projekts).
4. Wenn Wir Ihre Anforderung nicht mithilfe der Microsoft-Technologie erfüllen können, genehmigen wir Ihre Anforderung wahrscheinlich, es sei denn, sie verletzt eine der folgenden Bedingungen.  

Diese Prinzipien stellen sicher, Microsoft Managed Desktop ihre Anforderungen immer erfüllen können, während Abweichungen von unserer Standardvorlage nachverfolgungen werden. 

## <a name="key-conditions"></a>Wichtige Bedingungen

Wir überprüfen Ausnahmen, um sicherzustellen, dass sie keine dieser Bedingungen verletzen:

- Eine Ausnahme darf sich nicht negativ auf die Systemsicherheit auswirken. 
- Die Aufrechterhaltung der Ausnahme darf keine erheblichen Kosten für Microsoft Managed Desktop oder Support mit sich selbst haben.
- Eine Ausnahme darf sich nicht auf die Systemstabilität auswirken, z. B. indem der Kernelmodus abstürzt oder hängt.
- Die Änderung darf uns nicht davon abschränken, den Dienst zu nutzen, oder es darf nicht zu Konflikten mit Microsoft Managed Desktop werden.

Diese Bedingungen könnten sich in Zukunft ändern. Wenn wir solche Änderungen vornehmen, stellen wir 30 Tage vor dem In-Kraft-Treten dieser Bedingungen eine Benachrichtigung zur Verfügung.  Wenn Microsoft Managed Desktop eine alternative Möglichkeit bietet, eine genehmigte Ausnahme zu erfüllen, benachrichtigt Microsoft Managed Desktop den Kunden, Microsoft Managed Desktop die Unterstützung der Ausnahme zu ändern. 

## <a name="revoking-approval-for-an-exception"></a>Genehmigung für eine Ausnahme erneut endieren

Nachdem eine angeforderte Ausnahme genehmigt und bereitgestellt wurde, kann es sein, dass probleme auftreten, die die wichtigsten Bedingungen verletzen, die bei der Genehmigung der Änderung nicht offensichtlich waren. In diesem Fall müssen wir möglicherweise die Genehmigung für die Ausnahme widerrufen.
 
In diesem Fall benachrichtigen wir Sie über das Microsoft Managed Desktop Administratorportal. Ab dem ersten Benachrichtigen haben Sie 90 Tage Zeit, um die Ausnahme zu entfernen, bevor die Geräte mit der Ausnahme nicht mehr an Microsoft Managed Desktop gebunden sind. Wir senden Ihnen mehrere Benachrichtigungen gemäß einer strikten Zeitachse. Bei einem schwerwiegenden Vorfall oder einer schwerwiegenden Bedrohung müssen wir jedoch möglicherweise die Zeitachse oder unsere Entscheidungen zu einer Ausnahme ändern. Wir entfernen  keine Ausnahme ohne Ihre Zustimmung, aber jedes Gerät mit einer widerrufenen Ausnahme ist nicht mehr an unseren Servicelevelvertrag gebunden. Hier ist die Zeitachse der Benachrichtigungen, die wir Ihnen senden werden:

- **Erster Hinweis:** Wir stellen die erste Benachrichtigung über unsere Entscheidung zum Widerrufen der Genehmigung zur Verfügung, einschließlich Informationen dazu, warum wir sie widerrufen, die Von Ihnen zu ergreifenden Maßnahmen, den Stichtag für diese Aktionen und die Schritte, die sie ausführen müssen, wenn Sie gegen die Entscheidung Einspruch einlegen möchten. Dieser Hinweis tritt 90 Tage im Voraus auf, bevor die Ausnahme von allen Geräten entfernt werden muss. 
- **Zweiter Hinweis (30 Tage später):** Wir stellen einen zweiten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis angegeben sind. 
- **Dritter Hinweis (60 Tage nach dem ersten Hinweis):** Wir stellen einen dritten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis enthalten sind. 
- **Letzte Benachrichtigung (eine Woche vor Ablauf der 90-Tage-Frist):** Wir stellen einen vierten Hinweis bereit, einschließlich der gleichen Informationen, die im ersten Hinweis enthalten sind.
- **90 Tage nach** dem ersten Hinweis: Microsoft Managed Desktop service level agreements gelten nicht mehr für Geräte mit der widerrufenen Ausnahme. Sie können die Entscheidung jederzeit anfingen und zusätzliche Informationen zur Prüfung bereitstellen, z. B. Upgrade, Konfigurationsänderungen oder Softwareänderungen. 


