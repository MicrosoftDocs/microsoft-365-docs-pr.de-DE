---
title: Anpassen des Diensts
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: b2b74194c9b73e538fc1be937456b76deef75feb
ms.sourcegitcommit: eed48c21790d31a85292f7e39bf1e30c42f10d36
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/15/2019
ms.locfileid: "37523670"
---
# <a name="customize-the-service"></a>Anpassen des Diensts

Microsoft Managed Desktop stellt eine kuratierte Geräteliste, [Standardgeräte Einstellungen](device-policies.md), Anwendungsanforderungen und bestimmte [konfigurierbare Einstellungen](../working-with-managed-desktop/config-setting-overview.md)bereit, die für Endbenutzer eine sichere, produktive und angenehme Umgebung bieten. Es empfiehlt sich, immer bei der Bereitstellung des Diensts zu bleiben. Allerdings erkennen wir, dass einige Details des Diensts möglicherweise nicht genau den Anforderungen Ihrer Organisation entsprechen. Wenn Sie der Meinung sind, dass Sie den Dienst auf eine bestimmte Art und Weise ändern müssen, ist es wichtig, dass Sie die folgenden Prozesse befolgen, um diese Änderungen anzufordern.

 
## <a name="types-of-customizations"></a>Anpassungstypen
Eine Anpassung ist jede Ergänzung oder Änderung an der Microsoft Managed Desktop-Basiskonfiguration; Beispiele reichen von der Konfiguration von USB-Ports bis zur Bereitstellungeines neuen Sicherheits-Agents. Wir gruppieren verschiedene Anpassungen wie folgt:


|Typ  |Beschreibung  |
|---------|---------|
|Produktivitätssoftware     |  Von Endbenutzern benötigte Vordergrund-Software, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)       |
|Sicherheits-Agents #a0 VPNs     |  Software, die zum Sichern, überwachen oder Ändern des Verhaltens des Geräts oder Netzwerks verwendet wird       |
|Digitale Erlebnis Überwachung     |  Software zum Nachverfolgen von Daten auf dem Gerät eines Benutzers, um Sie zu melden.       |
|Hardware-oder Software Treiber     |   Gerätetreiber, eingeschränkt durch die [Anwendungsanforderungen](mmd-app-requirements.md)      |
|Richtlinien     | Windows 10-oder Office 365 ProPlus-Einstellungen auf einem verwalteten Gerät        |
|Geräte     | Geräte, die sich nicht in der Microsoft Managed Desktop- [Geräteliste](device-list.md) befinden        |
|Andere     |  Alles, was nicht von den anderen Bereichen abgedeckt wird       |



 
## <a name="request-a-customization"></a>Anfordern einer Anpassung

Übermitteln von Anforderungen über das Verwaltungsportal von Microsoft Managed Desktop durch Erstellen einer Änderungsanforderung. Achten Sie darauf, diese Details einzuschließen:
-   Anpassungstyp: welche Kategorie der Anpassung ist es? (siehe obige Tabelle)
-   Anforderung: Was ist die spezifische Geschäftsanforderung für die Anpassung?
-   Vorschlag: welche Lösung wird von Ihrem Unternehmen angefordert?
-   Zeitachsen: wie lange soll diese Anpassung dauern? 


## <a name="how-we-assess-a-customization-request"></a>So bewerten wir eine Anpassungs Anforderung

Bei der Überprüfung von Anpassungsanforderungen bewerten wir diese Faktoren in dieser Reihenfolge:
 
1.  Einige Anwendungen und Richtlinien, die von Microsoft Managed Desktop auf allen Geräten bereitgestellt werden, sind nicht verhandelbar, daher darf Ihre Anforderung keine Auswirkungen auf diese haben. Weitere Informationen finden Sie unter [Device Configuration](device-policies.md) .
2.  Eingeschränkte Produktivitätssoftware, die von einem Endbenutzer für seine Aufgabe benötigt wird, wird wahrscheinlich genehmigt. 
3.  Wenn Ihre Anforderung mithilfe der Microsoft-Technologie erfüllt werden kann, werden wir Ihre Anforderung für einen Migrationszeitraum von drei bis zwölf Monaten (je nach Projektumfang) genehmigen.
4.  Wenn Ihre Anforderung mithilfe der Microsoft-Technologie nicht erfüllt werden kann, werden wir Ihre Anfrage wahrscheinlich genehmigen, es sei denn, Sie verletzt eine der nachfolgenden Bedingungen.  

Durch diese Grundsätze wird sichergestellt, dass Microsoft Managed Desktop Ihren Anforderungen immer gerecht wird, während Abweichungen von unserer Standardvorlage nachverfolgt werden. 

## <a name="key-conditions"></a>Wichtige Bedingungen

Wir überprüfen Anpassungen, um sicherzustellen, dass Sie keine dieser Bedingungen verletzen:

-   Eine Anpassung darf sich nicht negativ auf die Systemsicherheit auswirken. 
-   Das aufrecht erhalten der Anpassung darf weder für Microsoft Managed Desktop-Vorgänge noch für den Support erhebliche Kosten verursachen.
-   Eine Anpassung darf sich nicht auf die Systemstabilität auswirken, beispielsweise dadurch, dass Kernelmodus abstürzt oder hängt.
-   Die Änderung darf uns nicht daran hindern, den Dienst zu betreiben oder mit der Kerntechnologie von Microsoft Managed Desktop in Konflikt zu stehen.

Diese Bedingungen können sich in Zukunft ändern. Wenn wir solche Änderungen vornehmen, werden wir eine Frist von 30 Tagen vorlegen, bevor diese Bedingungen in Kraft treten.

## <a name="revoking-approval-for-a-customization"></a>Aufheben der Genehmigung für eine Anpassung

Nachdem eine angeforderte Anpassung genehmigt und bereitgestellt wurde, ist es möglich, dass Probleme auftreten, die die wichtigsten Bedingungen verletzen, die nicht offensichtlich waren, als wir die Änderung in erster Linie genehmigt haben. In diesem Fall müssen wir möglicherweise die Genehmigung für die Anpassung widerrufen.
 
In diesem Fall werden Sie über das Verwaltungsportal von Microsoft Managed Desktop benachrichtigt. Ab dem ersten Mal, wenn Sie benachrichtigt werden, haben Sie 90 Tage Zeit, um die Anpassung zu entfernen, bevor die Geräte mit der Anpassung nicht mehr an Vereinbarungen zum Service Level für Microsoft Managed Desktop gebunden sind. Wir senden Ihnen mehrere Benachrichtigungen entsprechend einer strengen Zeitachse--es kann jedoch sein, dass ein schwerer Vorfall oder eine Bedrohung die Zeitachse oder unsere Entscheidungen zu einer Anpassung ändern muss. Eine Anpassung wird nicht ohne Ihre Zustimmung *entfernt* , aber jedes Gerät mit einer gesperrten Anpassung wird nicht mehr an unsere Vereinbarung zum Service Level gebunden. Hier ist die Zeitachse der Benachrichtigungen, die wir Ihnen senden werden:

- **Erste Nachricht:** Wir bieten den ersten Hinweis auf unsere Entscheidung, die Genehmigung zu widerrufen, einschließlich Informationen dazu, warum wir Sie widerrufen, die Aktionen, die wir Ihnen empfehlen, die Frist für diese Aktionen und die folgenden Schritte, wenn Sie die Entscheidung anfechten möchten. Dies ist 90 Tage im voraus, bevor die Anpassung von allen Geräten entfernt werden muss. 
- **Zweite Benachrichtigung (30 Tage später):** Wir bieten eine zweite Benachrichtigung an, einschließlich der in der ersten Benachrichtigung bereitgestellten Informationen. 
- **Dritte Benachrichtigung (60 Tage nach der ersten Benachrichtigung):** Wir bieten eine dritte Benachrichtigung an, einschließlich der in der ersten Benachrichtigung bereitgestellten Informationen. 
- **Letzte Benachrichtigung (1 Woche vor der 90-tägigen Frist):** Wir bieten eine vierte Benachrichtigung an, einschließlich der in der ersten Benachrichtigung angegebenen Informationen.
- **90 Tage nach der ersten Benachrichtigung:** Vereinbarungen zum Service Level von Microsoft Managed Desktop gelten nicht mehr für Geräte, die die Anpassung gesperrt haben. Sie können die Entscheidung jederzeit herausfordern und zusätzliche Informationen zur Überlegung bereitstellen, einschließlich Upgrades, Konfigurationsänderungen oder Softwareänderungen. 

