---
title: Informationen zu Aufbewahrungsrichtlinien zum automatischen Beibehalten oder Löschen von Inhalten
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: Hier erfahren Sie, wie Sie mithilfe einer Aufbewahrungsrichtlinie Inhalte beibehalten oder löschen und wie Sie eine einzelne Richtlinie für die gesamte Organisation oder für bestimmte Speicherorte oder Benutzer anwenden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ffd7b644f33e7f432c62c182e2d69e07c8bce730
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818925"
---
# <a name="learn-about-retention-policies"></a>Informationen zu Aufbewahrungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

For most organizations, the volume and complexity of their data is increasing daily—email, documents, instant messages, and more. Effectively managing or governing this information is important because you need to:
  
- **branchenspezifische Vorschriften und interne Richtlinien einhalten müssen**, nach denen Inhalte für eine bestimmte Mindestdauer aufzubewahren sind – z. B. müssen Sie gemäß dem Sarbanes-Oxley Act möglicherweise bestimmte Arten von Inhalten sieben Jahre lang aufbewahren. 
    
- **das Risiko bei Rechtsstreitigkeiten oder einer Sicherheitsverletzung reduzieren müssen**, indem Sie alte Inhalte, die Sie nicht mehr aufbewahren müssen, endgültig löschen. 
    
- **Ihrer Organisation dabei helfen müssen, effektiven Wissensaustausch zu betreiben und agiler zu werden**, indem Sie sicherstellen, dass die Benutzer nur mit Inhalten arbeiten, die aktuell und für sie relevant sind. 
    
A retention policy can help you achieve all of these goals. Managing content commonly requires two actions:
  
- **Aufbewahrung** von Inhalten, sodass sie nicht vor dem Ende des Aufbewahrungszeitraums dauerhaft gelöscht werden 
    
- **Endgültiges Löschen** von Inhalten am Ende des Aufbewahrungszeitraums. 
    
Mit einer Aufbewahrungsrichtlinie können Sie:
  
- proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides, also aufbewahrt und dann gelöscht werden sollen.
    
- eine einzelne Richtlinie auf die gesamte Organisation oder auf bestimmte Speicherorte oder Benutzer anwenden.
    
- eine Richtlinie auf alle Inhalte oder auf bestimmte Kriterien erfüllende Inhalte anwenden, z. B. auf Inhalte, die bestimmte Schlüsselwörter oder [Arten von vertraulichen Informationen](what-the-sensitive-information-types-look-for.md) enthalten.
    
When content is subject to a retention policy, people can continue to edit and work with the content as if nothing's changed. The content is retained in place, in its original location. But if someone edits or deletes content that's subject to the retention policy, a copy of the original content is saved to a secure location where it's retained while the retention policy for that content is in effect. For more information, see the [How a retention policy works with content in place](#how-a-retention-policy-works-with-content-in-place) section on this page
  
Einige Organisationen müssen darüber hinaus Vorschriften wie die Richtlinie 17a-4 der Securities and Exchange Commission (SEC, US-Börsenaufsichtsbehörde) einhalten. Diese Verordnung gibt vor, dass eine Aufbewahrungsrichtlinie nach deren Aktivierung nicht deaktiviert oder weniger restriktiv eingestellt werden kann. Um diese Anforderung zu erfüllen, können Sie die **Erhaltungssperre** verwenden. Nachdem eine Aufbewahrungsrichtlinie gesperrt wurde, kann niemand – auch nicht ein Administrator – die Richtlinie deaktivieren oder weniger restriktiv einstellen. Weitere Informationen hierzu finden Sie im Abschnitt [Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften](#use-preservation-lock-to-comply-with-regulatory-requirements) auf dieser Seite.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Inhalten

Wenn Sie einen Speicherort wie eine Website oder ein Postfach in eine Aufbewahrungsrichtlinie einschließen, verbleibt der Inhalt an seinem ursprünglichen Speicherort. Die Benutzer können weiterhin mit ihren Dokumenten oder E-Mails arbeiten, als ob sich nichts geändert hätte. Wenn aber Inhalte bearbeitet oder gelöscht werden, die in die Aufbewahrungsrichtlinie einbezogen sind, wird eine Kopie der Inhalte in der bei Aktivierung der Richtlinie vorhandenen Form aufbewahrt.
  
- Für SharePoint-und OneDrive-Websites: Die Kopie wird im **Permanenten Dokumentarchiv** aufbewahrt. Berücksichtigen Sie, dass das permanente Dokumentarchiv Speicherkontingent für die Website verbraucht.

- Für E-Mail-Nachrichten und öffentliche Ordner: Die Kopie wird im Ordner **Wiederherstellbare Elemente** aufbewahrt. 

- Für Microsoft Teams: Die Kopie wird im Exchange-Ordner **Wiederherstellbare Elemente** aufbewahrt.

- Für Microsoft 365-Gruppen ([vormals Office 365-Gruppen](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-365-groups-will-become-microsoft-365-groups/ba-p/1303601)): 
    - Das Gruppenpostfach wird im Exchange-Ordner **Wiederherstellbare Elemente** aufbewahrt.
    - Alle Websiteinhalte werden im **Permanenten Dokumentarchiv** aufbewahrt.

> [!NOTE]
> Das permanente Dokumentarchiv verbraucht Speicherplatz, der nicht vom Speicherkontingent für die Website ausgenommen ist. Möglicherweise müssen Sie den Speicherplatz erhöhen, wenn Sie Aufbewahrungsrichtlinien für SharePoint und Microsoft 365-Gruppen verwenden.
> 
Diese sicheren Speicherorte und die aufbewahrten Inhalte sind für die meisten Benutzer nicht sichtbar. Beim Einsatz einer Aufbewahrungsrichtlinie müssen die Benutzer gar nicht wissen, dass ihre Inhalte der Richtlinie unterliegen.

Ausführlichere Informationen zur Funktionsweise von Aufbewahrungsrichtlinien mit unterschiedlichen Workloads finden Sie in den folgenden Artikeln:

- [Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive](retention-policies-sharepoint.md)
- [Informationen zu Aufbewahrungsrichtlinien für Microsoft Teams.](retention-policies-teams.md)
- [EInformationen zu Aufbewahrungsrichtlinien für Exchange](retention-policies-exchange.md)

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Die Grundsätze der Aufbewahrung, oder was hat Vorrang?

Es ist möglich oder sogar wahrscheinlich, dass auf Inhalte mehrere Aufbewahrungsrichtlinien angewendet werden, die jeweils eine andere Aktion (Aufbewahren, Löschen oder beides, also zuerst Aufbewahren und dann Löschen) sowie einen anderen Aufbewahrungszeitraum vorgeben. Doch was hat Vorrang? Sie können generell darauf vertrauen, dass Inhalte, die aufgrund einer Aufbewahrungsrichtlinie aufbewahrt werden, nicht aufgrund einer anderen Aufbewahrungsrichtlinie dauerhaft gelöscht werden können.
  
![Diagramm der Grundsätze der Aufbewahrung](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Um zu verstehen, wie verschiedene Aufbewahrungsrichtlinien auf Inhalte angewendet werden, sollten Sie diese Grundsätze der Aufbewahrung beachten:
  
1. **Aufbewahrung hat Vorrang vor Löschen.** Nehmen wir einmal an, eine Aufbewahrungsrichtlinie ist so konfiguriert, dass Exchange-E-Mails nach drei Jahren gelöscht werden sollen, während eine andere Aufbewahrungsrichtlinie vorgibt, dass Exchange-E-Mails fünf Jahre aufbewahrt und dann gelöscht werden sollen. Alle Inhalte werden, sobald sie drei Jahre alt sind, gelöscht und für den Benutzer ausgeblendet, aber immer noch im Ordner "Wiederherstellbare Elemente" aufbewahrt, bis der Inhalt fünf Jahre alt ist, und dann dauerhaft gelöscht. 
    
2. **Der längste Aufbewahrungszeitraum hat Vorrang.** Inhalte, die mehreren Aufbewahrungsrichtlinien unterliegen, bleiben bis zum Ende des längsten Aufbewahrungszeitraums erhalten. 
    
3. **Explizite Einbindung hat Vorrang vor impliziter Einbindung.** Das bedeutet Folgendes: 
    
    1. Wenn eine Aufbewahrungsbezeichnung mit Einstellungen für die Aufbewahrung von einem Benutzer manuell einem Element, z. B. einer Exchange-E-Mail oder einem OneDrive-Dokument, zugewiesen wird, hat diese Aufbewahrungsbezeichnung sowohl Vorrang vor einer Aufbewahrungsrichtlinie, die auf Website- oder Postfachebene zugewiesen wurde, als auch vor einer Standard-Aufbewahrungsbezeichnung, die von der Dokumentbibliothek zugewiesen wurde. Wenn beispielsweise die explizite Aufbewahrungsbezeichnung eine Aufbewahrung von Inhalten über zehn Jahre vorgibt, die der Website zugewiesene Aufbewahrungsrichtlinie hingegen eine Aufbewahrung von Inhalten über nur fünf Jahre, hat die Aufbewahrungsbezeichnung Vorrang. Automatisch angewendete Bezeichnungen werden als implizit und nicht explizit angesehen, da sie von Microsoft 365 automatisch angewendet werden.
    
    2. Wenn eine Aufbewahrungsrichtlinie einen bestimmten Speicherort wie das Postfach oder OneDrive-Konto eines bestimmten Benutzers umfasst, hat diese Richtlinie Vorrang vor einer anderen Aufbewahrungsrichtlinie, die für alle Postfächer oder OneDrive-Konten von Benutzern gilt, aber nicht das Postfach dieses Benutzers speziell einschließt.
    
4. **Der kürzeste Zeitraum für Löschungen hat Vorrang.** Ebenso gilt, dass wenn Inhalte mehreren Aufbewahrungsrichtlinien zur Löschung (ohne Aufbewahrung) unterliegen, sie am Ende des kürzesten Aufbewahrungszeitraums gelöscht werden. 
    
Beachten Sie, dass die Grundsätze der Aufbewahrung nacheinander von oben nach unten zur Anwendung kommen: Wenn die Regeln, die von allen Aufbewahrungsrichtlinien oder -bezeichnungen angewendet werden, auf einer Ebene identisch sind, wird zur nächsten Ebene nach unten gewechselt, um die Rangfolge dafür zu ermitteln, welche Regel angewendet wird.
  
Inhalt, der für eDiscovery gesperrt ist, kann nicht dauerhaft aufgrund einer Aufbewahrungsrichtlinie oder -bezeichnung gelöscht werden. Wenn die Sperre aufgehoben wird, ist der Inhalt wieder für den oben beschriebenen Bereinigungsprozess verfügbar.

## <a name="use-preservation-lock-to-comply-with-regulatory-requirements"></a>Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften

Einige Organisationen müssen möglicherweise Regeln einhalten, die von Behörden definiert werden, wie zum Beispiel die Richtlinie 17a-4 der Securities And Exchange Commission (SEC), die vorgibt, dass eine Aufbewahrungsrichtlinie nach dem Aktivieren nicht deaktiviert oder weniger restriktiv eingestellt werden kann. 

Die Erhaltungssperre stellt sicher, dass Ihre Organisation solchen gesetzlichen Vorschriften gerecht werden kann, da hierdurch eine Aufbewahrungsrichtlinie gesperrt wird, sodass niemand – auch nicht der Administrator – die Richtlinie deaktivieren oder weniger restriktiv einstellen kann.
  
Das Sperren einer Aufbewahrungsrichtlinie bewirkt Folgendes:

- Niemand kann sie deaktivieren
- Speicherorte können hinzugefügt, aber nicht entfernt werden 
- Inhalte, die der Richtlinie unterliegen, können während des Aufbewahrungszeitraums weder geändert noch gelöscht werden.
- Sie können den Aufbewahrungszeitraum verlängern, ihn jedoch nicht verringern.

Zusammenfassend kann man sagen, dass eine gesperrte Richtlinie erweitert oder verlängert, jedoch nicht reduziert oder deaktiviert werden kann.
  
> [!IMPORTANT]
> Bevor Sie eine Aufbewahrungsrichtlinie sperren, ist es wichtig, dass Sie die Auswirkungen kennen und überlegen, ob dies zur Erfüllung der Compliance-Anforderungen durch Ihre Organisation erforderlich ist.

## <a name="releasing-a-retention-policy"></a>Aufheben einer Aufbewahrungsrichtlinie

Wenn eine Aufbewahrungsrichtlinie keiner Erhaltungssperre unterliegt, können Sie sie jederzeit deaktivieren oder löschen. 

In diesem Fall werden bis dahin im permanentes Dokumentarchiv aufbewahrte SharePoint- oder OneDrive-Inhalte nicht sofort und dauerhaft gelöscht. Um versehentlichem Datenverlust vorzubeugen, gibt es nun eine Nachfrist von 30 Tagen, während der der Inhaltsablauf für diese Richtlinie im permanenten Dokumentarchiv nicht eintritt, sodass Sie Inhalte ggf. wiederherstellen können. Darüber hinaus können Sie diese Inhalte während der Nachfrist nicht manuell löschen.

Sie können die Aufbewahrungsrichtlinie während der Nachfrist erneut aktivieren. In diesem Fall werden keine in Zusammenhang mit dieser Richtlinie stehenden Inhalte gelöscht.

Diese 30-tägige Nachfrist in SharePoint und OneDrive entspricht dem 30-tägigen Anhalten der Aufbewahrungszeit in Exchange. Weitere Informationen finden Sie unter [Verwalten von Postfächern mit angehaltener Aufbewahrungszeit](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="use-a-retention-policy-instead-of-older-features"></a>Verwenden einer Aufbewahrungsrichtlinie anstelle älterer Features

Eine einzelne Aufbewahrungsrichtlinie kann problemlos auf eine ganze Organisation und Speicherorte in Microsoft 365 angewendet werden. Dazu gehören Exchange Online, SharePoint Online, OneDrive und Microsoft 365-Gruppen. Wenn Sie Inhalte an beliebiger Stelle in Microsoft 365 aufbewahren oder löschen müssen, empfiehlt sich die Verwendung einer Aufbewahrungsrichtlinie und diese optional durch [Aufbewahrungsbezeichnungen](labels.md) zu ergänzen.
  
Wenn Sie zuvor andere Konfigurationen zum Aufbewahren oder Löschen von Inhalten in Microsoft 365 verwendet haben, werden diese weiterhin parallel zu Aufbewahrungsrichtlinien und -bezeichnungen angewendet. Es wird jedoch empfohlen, in Zukunft stattdessen Aufbewahrungsrichtlinien und -bezeichnungen zu verwenden. Sie bieten einen einzigen Mechanismus, um die Aufbewahrung und Löschung von Inhalten in Microsoft 365 zentral zu verwalten.

Nachfolgend die älteren Features, die Sie möglicherweise verwendet haben:
  
**Ältere Features von Exchange Online:**

- [In-Situ-Speicher und Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery-Sperre) 

- [Identifizieren des Haltebereichs für ein Exchange Online-Postfach](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/?linkid=846125), auch bekannt als [Messaging-Datensatzverwaltung](https://go.microsoft.com/fwlink/?linkid=846126) (Nur Löschen)
    
Siehe auch [Einstellung älterer eDiscovery-Tools](legacy-ediscovery-retirement.md).


**Ältere Features von SharePoint und OneDrive:**

- [Hinzufügen von Inhalten zu einem Fall und temporäres Sperren von Quellen im eDiscovery Center](https://docs.microsoft.com/SharePoint/governance/add-content-to-a-case-and-place-sources-on-hold-in-the-ediscovery-center) (eDiscovery-Sperre) 
    
- [Richtlinien zum Löschen von Dokumenten](https://support.office.com/article/Create-a-document-deletion-policy-in-SharePoint-Server-2016-4fe26e19-4849-4eb9-a044-840ab47458ff) (nur Löschvorgang)
    
- [Konfigurieren der direkten Datensatzverwaltung](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (nur Aufbewahrung) 
    
- [Verwenden von Richtlinien für das Schließen und Löschen von Websites](https://support.microsoft.com/de-DE/office/use-policies-for-site-closure-and-deletion-a8280d82-27fd-48c5-9adf-8a5431208ba5) (Nur Löschen) 
    
- [Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md) (Nur Löschen)
     
Wenn Sie bisher eines der eDiscovery-Archive zum Zwecke der Informationsgovernance verwendet haben, sollten Sie für proaktive Compliance stattdessen eine Aufbewahrungsrichtlinie verwenden. Verwenden Sie eDiscovery nur für Archive.
  
### <a name="retention-policies-and-sharepoint-content-type-policies-or-information-management-policies"></a>Aufbewahrungsrichtlinien und SharePoint-Inhaltstyprichtlinien oder Informationsverwaltungsrichtlinien

Wenn Sie SharePoint-Websites für Inhaltstyprichtlinien oder Informationsverwaltungsrichtlinien so konfiguriert haben, dass Inhalte für eine Liste oder Bibliothek aufbewahrt werden, werden diese Richtlinien ignoriert, während eine Aufbewahrungsrichtlinie in Kraft ist. 
  
### <a name="preservation-policies-are-converted-to-retention-policies"></a>Erhaltungsrichtlinien werden in Aufbewahrungsrichtlinien umgewandelt

Wenn Sie bisher eine Erhaltungsrichtlinie zum Aufbewahren von Daten in Postfächern, SharePoint oder OneDrive-Websites oder öffentlichen Ordnern verwendet haben: Diese Richtlinie wurde automatisch in eine Aufbewahrungsrichtlinie umgewandelt, bei der nur die Aufbewahrungsaktion verwendet wird – mit der Richtlinie werden keine Inhalte gelöscht. Es sind keine Änderungen erforderlich, um dasselbe Ergebnis wie Ihre zuvor konfigurierte Erhaltungsrichtlinie zu erzielen.

Sie finden alle konfigurierten Erhaltungsrichtlinien auf der Seite **Richtlinien** im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) oder auf der Seite **Aufbewahrung** unter **Informationsgovernance** im [Security&amp; Compliance Center](https://protection.office.com/). Sie können eine Erhaltungsrichtlinie bearbeiten, um den Aufbewahrungszeitraum zu ändern, jedoch keine anderen Änderungen vornehmen, z. B. keine Speicherorte hinzufügen oder entfernen. 


## <a name="related-information"></a>Verwandte Informationen

- [Informationen zu Aufbewahrungsbezeichnungen](labels.md)
- [SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limits und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
- [Einhaltung der SEC-Richtlinie 17a-4](use-exchange-online-to-comply-with-sec-rule-17a-4.md)

## <a name="next-steps"></a>Nächste Schritte

Wenn Sie bereit sind, Aufbewahrungsrichtlinien zu erstellen, lesen Sie [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md).

