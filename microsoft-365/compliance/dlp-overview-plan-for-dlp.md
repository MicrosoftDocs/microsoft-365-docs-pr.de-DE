---
title: Planen der Verhinderung von Datenverlust
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Übersicht über den Planungsprozess für die Verhinderung von Datenverlust
ms.openlocfilehash: 6a72a8bab27db4d8b11d3e0b3d7a1dac7a1f0092
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52581594"
---
# <a name="plan-for-data-loss-prevention-dlp"></a>Planen der Verhinderung von Datenverlust (Data Loss Prevention, DLP)

Jede Organisation plant und implementiert die Verhinderung von Datenverlust (Data Loss Prevention, DLP) anders, da die Geschäftlichen Anforderungen, Ziele, Ressourcen und Situationen jeder Organisation für sie einzigartig sind. Es gibt jedoch Elemente, die allen erfolgreichen DLP-Implementierungen gemeinsam sind. In diesem Artikel werden die bewährten Methoden beschrieben, die von Organisationen bei der Planung von DLP verwendet werden.

## <a name="multiple-starting-points"></a>Mehrere Ausgangspunkte

Viele Organisationen entscheiden sich für die Implementierung von DLP, um verschiedene staatliche oder Branchenbestimmungen einzuhalten. Beispielsweise die Datenschutz-Grundverordnung (DSGVO) der Europäischen Union oder das Health Insurance Portability and Accountability Act (HIPAA) oder das California Consumer Privacy Act (CCPA). Sie implementieren auch die Verhinderung von Datenverlust, um ihr geistiges Eigentum zu schützen. Der Startort und das endgültige Ziel der DLP-Reise variieren jedoch. 

Organisationen können ihre DLP-Reise starten:

- von einem Plattformfokus aus, wie informationen in Chat- und Kanalnachrichten oder auf Teams oder auf Windows 10 schützen möchten
- Wissen, welche vertraulichen Informationen sie schützen möchten, wie Gesundheitsdatensätze, und direkt zur Definition von Richtlinien zum Schutz
- ohne zu wissen, was ihre vertraulichen Informationen sind, wo sie sich befindet und wer was damit macht, damit sie mit der Ermittlung und Kategorisierung beginnen und einen methodischen Ansatz wählen
- ohne zu wissen, was ihre vertraulichen Informationen sind oder wo sie sich befindet, oder wer was damit macht, aber sie werden direkt zur Definition von Richtlinien wechseln und diese Ergebnisse als Ausgangspunkt verwenden und dann ihre Richtlinien von dort aus verfeinern.
- Wissen, dass sie den vollständigen Informationsschutzstapel Microsoft 365 implementieren müssen und daher einen langfristigen, methodischen Ansatz verwenden möchten

Dies sind nur einige Beispiele dafür, wie Kunden mit DLP beginnen können, und es spielt keine Rolle, wo Sie beginnen, Microsoft 365 DLP ist flexibel genug, um verschiedene Arten von Informationsschutz-Reisen vom Anfang bis zu einer vollständig realisierten Strategie zur Verhinderung von Datenverlust zu unterstützen. 

## <a name="overview-of-planning-process"></a>Übersicht über den Planungsprozess

Im [Thema Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) werden die drei verschiedenen Aspekte des [DLP-Planungsprozesses präsentiert.](dlp-learn-about-dlp.md#plan-for-dlp) Wir gehen hier ausführlicher auf die Elemente ein, die allen DLP-Plänen gemeinsam sind.

### <a name="identify-stakeholders"></a>Bestimmen der Beteiligten

Bei der Implementierung können DLP-Richtlinien auf große Teile Ihrer Organisation angewendet werden. It can't develop a broad ranging plan on their own without negative consequences. Sie müssen die Beteiligten identifizieren, die:

- Beschreiben der Vorschriften, Gesetze und Branchenstandards, denen Ihre Organisation unterliegt
- die Kategorien vertraulicher Elemente, die geschützt werden sollen
- die Geschäftsprozesse, in der sie verwendet werden
- das riskante Verhalten, das eingeschränkt werden sollte
- Priorisieren, welche Daten zuerst geschützt werden sollten, basierend auf der Vertraulichkeit der Elemente und des risikobezogenen Risikos
- Gliederung des Prozesses zur Überprüfung und Behebung von DLP-Richtlinienbereinigungsereignis 
 
Im Allgemeinen sind diese Anforderungen in der Regel 85 % gesetzlicher Und Complianceschutz und 15 % Schutz geistigen Eigentums. Im Folgenden finden Sie einige Vorschläge zu Rollen, die Sie in Ihren Planungsprozess mit einplanen können:

- Aufsichts- und Compliance-Beauftragte
- Chief Risk Officer
- Rechtsbeauftragte
- Security and Compliance Officers
- Geschäftsbesitzer für die Datenelemente
- Geschäftsbenutzer
- IT

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a>Beschreiben der Zu schützende Kategorien vertraulicher Informationen

Die Beteiligten beschreiben dann die Kategorien vertraulicher Informationen, die geschützt werden sollen, und den Geschäftsprozess, in dem sie verwendet werden. Beispielsweise definiert Microsoft 365 DLP die folgenden Kategorien:

- Finanzwesen 
- Medizinische und Gesundheitsinformationen
- Datenschutz
- Benutzerdefiniert

Die Beteiligten identifizieren die vertraulichen Informationen möglicherweise als "Wir sind datenverarbeiter, daher müssen wir Datenschutzbestimmungen für betroffene Informationen und Finanzinformationen implementieren".

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a>Festlegen von Zielen und Strategie

Sobald Sie Ihre Beteiligten identifiziert haben und wissen, welche vertraulichen Informationen geschützt werden müssen und wo sie verwendet werden, können die Beteiligten ihre Schutzziele festlegen, und die IT kann einen Implementierungsplan entwickeln. 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a>Festlegen des Implementierungsplans

Ihr Implementierungsplan sollte Folgendes umfassen:

- Zuordnen des Anfangszustands und des gewünschten Endzustands sowie der Schritte, um von einem zum anderen zu kommen
- Wie Sie die Ermittlung vertraulicher Elemente adressen
- Richtlinienplanung und die Reihenfolge, in der sie implementiert werden
- Wie Sie alle Voraussetzungen erfüllen
- Planen, wie Richtlinien zuerst getestet werden, bevor sie zur Erzwingung über
- Wie Sie Ihre Endbenutzer schulen
- Testen und Optimieren Ihrer Richtlinien
- Wie Sie Ihre Strategie zur Verhinderung von Datenverlust basierend auf geänderten behördlichen, rechtlichen, Branchenstandards oder schutz vor geistigem Eigentum und geschäftsbezogenen Anforderungen überprüfen und aktualisieren

#### <a name="map-out-path-from-start-to-desired-end-state"></a>Pfad vom Anfang zum gewünschten Endzustand zuordnung

Dokumentieren, wie Ihre Organisation vom Startstatus in den gewünschten Endzustand kommt, ist für die Kommunikation mit Denkbeteiligten und das Festlegen des Projektumfangs unerlässlich. Im Folgenden finden Sie eine Reihe von Schritten, die häufig zum Bereitstellen von DLP verwendet werden. Sie möchten mehr Details als dies, aber Sie können dies verwenden, um Ihren DLP-Einführungspfad zu framen.

![Grafik mit der allgemeinen Reihenfolge für die Bereitstellung von DLP](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a>Ermittlung vertraulicher Elemente

Es gibt mehrere Möglichkeiten, um zu ermitteln, was einzelne vertrauliche Elemente sind und wo sie sich befinden. Möglicherweise haben Sie vertraulichkeitsbezeichnungen bereits bereitgestellt, oder Sie haben sich entschieden, eine sehr umfassende DLP-Richtlinie für alle Speicherorte zu implementieren, die nur Elemente ermitteln und überwacht. Weitere Informationen finden Sie unter [Know your data](information-protection.md#know-your-data).

#### <a name="policy-planning"></a>Richtlinienplanung

Wenn Sie mit der Einführung von DLP beginnen, können Sie diese Fragen verwenden, um Ihre Anstrengungen bei der Richtlinienentwurfs- und Implementierungsplanung zu konzentrieren.

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a>Welche Gesetze, Vorschriften und Branchenstandards muss Ihre Organisation einhalten?

Da viele Organisationen mit dem Ziel der Einhaltung gesetzlicher Vorschriften zu DLP kommen, ist die Beantwortung dieser Frage ein natürlicher Ausgangspunkt für die Planung Ihrer DLP-Implementierung. Als IT-Implementier sind Sie jedoch wahrscheinlich nicht positioniert, um darauf zu antworten. Sie muss von Ihrem Rechtsteam und ihren Führungskräften beantwortet werden. 
 
**Beispiel** Ihre Organisation unterliegt Großbritannien. Finanzbestimmungen.


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a>Über welche vertraulichen Elemente verfügt Ihre Organisation, die vor Lecks geschützt werden müssen?

Sobald Ihre Organisation weiß, wo sie hinsichtlich der Gesetzlichen Complianceanforderungen steht, haben Sie eine Vorstellung davon, welche vertraulichen Elemente vor Lecks geschützt werden müssen und wie Sie die Richtlinienimplementierung priorisieren möchten, um sie zu schützen. Dadurch können Sie die am besten geeigneten DLP-Richtlinienvorlagen auswählen. Microsoft 365 enthält vorkonfigurierte DLP-Vorlagen für Finanzen, Medizin und Gesundheit, Datenschutz, und Sie können ihre eigenen mit der benutzerdefinierten Vorlage erstellen. Wenn Sie Ihre tatsächlichen DLP-Richtlinien entwerfen und erstellen, hilft Ihnen das Wissen um die Antwort auf diese Frage auch bei der Auswahl des richtigen [vertraulichen Informationstyps.](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)

**Beispiel** Um schnell zu beginnen, wählen Sie die `U.K. Financial Data` Richtlinienvorlage aus, die die `Credit Card Number` Typen , und vertrauliche Informationen `EU Debit Card Number` `SWIFT Code` enthält. 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a>Wo sind die vertraulichen Elemente und an welchen Geschäftsprozessen beteiligt?

Die Elemente, die vertrauliche Informationen ihrer Organisation enthalten, werden im Laufe der Geschäftstätigkeit täglich verwendet. Sie müssen wissen, wo Instanzen dieser vertraulichen Informationen auftreten können und in welchen Geschäftsprozessen sie verwendet werden. Dies hilft Ihnen bei der Auswahl der richtigen Speicherorte, auf die Ihre DLP-Richtlinien angewendet werden sollen. Microsoft 365 DLP-Richtlinien werden auf Speicherorte angewendet:

- Exchange-E-Mail
- SharePoint-Websites
- OneDrive-Konten
- Teams-Chat- und Teams-Kanalnachrichten
- Windows 10 Geräte
- Microsoft Cloud App Security
- Lokale Repositorys

**Beispiel** Interne Auditoren Ihrer Organisation verfolgen eine Reihe von Kreditkartennummern. Sie bewahren eine Tabellenkalkulation von ihnen auf einer sicheren SharePoint auf. Mehrere Mitarbeiter erstellen Kopien und speichern sie auf ihrer OneDrive for Business, die mit ihrem Windows 10 synchronisiert wird. Einer von ihnen fügt eine Liste von 14 von ihnen in eine E-Mail ein und versucht, sie zur Überprüfung an die externe Auditoren zu senden. Sie möchten die Richtlinie auf den Sicheren SharePoint, alle internen Auditoren OneDrive for Business Konten, ihre Windows 10 Geräte und Exchange anwenden.

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a>Wie ist die Toleranz Ihrer Organisation für Leckagen?

Unterschiedliche Gruppen in Ihrer Organisation haben möglicherweise unterschiedliche Ansichten darüber, was ein akzeptables Maß an vertraulichen Elementlecks ist und was nicht. Das Erreichen der Vollkommenheit von Leckagen ohne Lecks kann zu hohen Kosten für das Unternehmen führen.

**Beispiel** Die Sicherheitsgruppe Ihrer Organisation und das Rechtsteam sind der Meinung, dass es keine Freigabe von Kreditkartennummern für personen außerhalb der Organisation gibt, und bestehen auf null Lecks. Im Rahmen der regelmäßigen Überprüfung der Aktivitäten mit Kreditkartennummern müssen die internen Prüfer jedoch einige Kreditkartennummern mit externen Prüfern teilen. Wenn Ihre DLP-Richtlinie die gesamte Freigabe von Kreditkartennummern außerhalb der Organisation verbietet, gibt es eine erhebliche Unterbrechung des Geschäftsprozesses und zusätzliche Kosten, um die Unterbrechung zu mindern, damit die internen Prüfer ihre Nachverfolgung abschließen können. Diese zusätzlichen Kosten sind für die Führungsspitze inakzeptabel. Um dies zu beheben, muss eine interne Unterhaltung geführt werden, um ein akzeptables Maß an Lecks zu bestimmen. Sobald dies entschieden ist, kann die Richtlinie Ausnahmen für bestimmte Personen bereitstellen, um die Informationen zu teilen, oder sie kann nur im Überwachungsmodus angewendet werden.

#### <a name="planning-for-prerequisites"></a>Planen von Voraussetzungen

Bevor Sie einige DLP-Speicherorte überwachen können, müssen die Voraussetzungen erfüllt sein. Weitere Informationen **finden Sie unter Before you begin** sections of:

- [Erste Schritte mit dem lokalen Scanner zur Verhinderung von Datenverlust (Vorschau)](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [Endpunkt-DLP – Erste Schritte](endpoint-dlp-getting-started.md#before-you-begin)
- [Erste Schritte mit der Microsoft Compliance-Erweiterung (Vorschau)](dlp-chrome-get-started.md#before-you-begin)
- [Verwenden von Richtlinien zur Verhinderung von Datenverlust für Nicht-Microsoft-Cloud-Apps (Vorschau)](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a>Richtlinienbereitstellung

Beim Erstellen von DLP-Richtlinien sollten Sie eine schrittweise Einführung in Erwägung ziehen, um ihre Auswirkungen zu bewerten und ihre Wirksamkeit zu testen, bevor Sie sie in umfassendem Maße erzwingen. Sie möchten beispielsweise nicht, dass eine neue DLP-Richtlinie versehentlich den Zugriff auf Tausende von Dokumenten blockiert oder einen vorhandenen Geschäftsprozess unterbricht.
  
Wenn Sie DLP-Richtlinien erstellen, die potenziell weitreichende Auswirkungen haben können, empfehlen wir, in der folgenden Reihenfolge vorzugehen:
  
1. **Beginnen Sie im Testmodus ohne Richtlinientipps**, und werten Sie die Auswirkungen dann anhand der DLP-Berichte aus. Sie können DLP-Berichte verwenden, um Anzahl, Ort, Typ und Schwere von Richtlinienübereinstimmungen anzuzeigen. Basierend auf den Ergebnissen können Sie die Richtlinien nach Bedarf optimieren. Im Testmodus haben DLP-Richtlinien keinen Einfluss auf die Produktivität der Mitarbeiter in Ihrer Organisation. Verwenden Sie diese Phase auch, um Ihren Workflow für die DLP-Ereignisüberprüfung zu testen und die Behebung zu problembehebungen aus.
    
2. Wechseln Sie in den Testmodus mit Benachrichtigungen und **Richtlinienrichtlinien Tipps** damit Sie beginnen können, Benutzern Informationen zu Ihren Compliancerichtlinien zu vermitteln und sie auf die Richtlinien vorzubereiten, die angewendet werden sollen. Es ist hilfreich, über einen Link zu einer Organisationsrichtlinienseite zu verfügen, die zusätzliche Details zur Richtlinie im Richtlinientipp enthält. In dieser Phase können Sie benutzer auch bitten, falsch positive Ergebnisse zu melden, damit Sie die Richtlinien weiter verfeinern können. Wechseln Sie zu dieser Phase, sobald Sie sicher sind, dass die Ergebnisse der Richtlinienanwendung mit dem übereinstimmen, was die Beteiligten im Sinn hatten. 
    
3. **Beginnen Sie mit der vollständigen Durchsetzung der Richtlinien**, sodass die Aktionen in den Regeln angewendet werden und der Inhalt geschützt ist. Überwachen Sie weiterhin die DLP-Berichte und alle Schadensberichte oder Benachrichtigungen, um sicherzustellen, dass die von Ihnen gewünschten Ergebnisse erzielt werden. 

    ![Optionen zum Verwenden des Testmodus und zum Aktivieren der Richtlinie](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    Sie können eine DLP-Richtlinie jederzeit deaktivieren. Dies wirkt sich auf alle Regeln in der Richtlinie aus. Jede Regel kann aber auch einzeln deaktiviert werden, indem ihr Status im Regel-Editor geändert wird.

    ![Optionen für das Deaktivieren einer Regel in einer Richtlinie](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    Sie können auch die Priorität mehrerer Regeln in einer Richtlinie ändern. Öffnen Sie dazu eine Richtlinie zur Bearbeitung. Klicken Sie in einer Zeile für eine Regel auf die drei Auslassungspunkte (**...**), und wählen Sie dann eine Option aus, z. B. **Nach unten** oder **Nach ganz unten**.

    ![Festlegen der Regelpriorität](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a>Endbenutzerschulungen

Wenn eine DLP-Richtlinie ausgelöst wird, können Sie Ihre Richtlinien so konfigurieren, dass E-Mail-Benachrichtigungen gesendet werden, und Administratoren und Endbenutzern Richtlinientipps für [DLP-Richtlinien](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) anzeigen. Während sich Ihre Richtlinien noch im Testmodus befinden und bevor sie zum Erzwingen einer Sperraktion festgelegt sind, sind Richtlinientipps hilfreiche Möglichkeiten, um das Risikoverhalten für vertrauliche Elemente zu sensibilisieren und Benutzer zu schulen, um diese Verhaltensweisen in Zukunft zu vermeiden.  

#### <a name="review-dlp-requirements-and-update-strategy"></a>Überprüfen von DLP-Anforderungen und Updatestrategie

Die Vorschriften, Gesetze und Branchenstandards, die Ihrer Organisation unterliegen, werden sich im Laufe der Zeit ändern, und Ihre Geschäftsziele für DLP werden sich ebenfalls ändern. Achten Sie darauf, alle diese Bereiche regelmäßig zu lesen, damit Ihre Organisation die Compliance einhält und Ihre DLP-Implementierung weiterhin Ihren Geschäftsanforderungen entspricht.

## <a name="approaches-to-deployment"></a>Bereitstellungsansätze

|Beschreibung der Geschäftsanforderungen des Kunden  | Ansatz  |
|---------|---------|
|**Die Contoso Bank** befindet sich in einer stark regulierten Branche und verfügt über viele verschiedene Typen vertraulicher Elemente an vielen verschiedenen Standorten. </br> - weiß, welche Arten vertraulicher Informationen oberste Priorität haben. </br> – muss Geschäftsunterbrechungen minimieren, wenn Richtlinien ausgeführt werden. </br> – verfügt über IT-Ressourcen und kann Experten für die Planung, das Entwerfen der Bereitstellung und die Bereitstellung beauftragen. </br> – hat einen erstklassigen Supportvertrag mit Microsoft| – Nehmen Sie sich die Zeit, um zu verstehen, welche Vorschriften sie einhalten müssen und wie sie diese einhalten werden. </br> -Nehmen Sie sich die Zeit, um den besseren gemeinsamen Wert des Microsoft 365 Information Protection-Stapels zu verstehen </br> – Entwickeln eines Vertraulichkeitskennzeichnungsschemas für priorisierte Elemente und Anwenden </br> – Beteiligung von Geschäftsprozessbesitzern </br>– Entwurfs-/Coderichtlinien, Bereitstellen im Testmodus, Schulen von Benutzern </br>- wiederholen|
|**TailSpin Toys** weiß nicht, was sie haben oder wo sie sich befindet, und hat wenig bis keine Ressourcentiefe. Sie verwenden Teams, ODB und Exchange umfassend.     |– Beginnen Sie mit einfachen Richtlinien für die priorisierten Speicherorte. </br>– Überwachen, was identifiziert wird </br>– Anwenden von Vertraulichkeitsbezeichnungen entsprechend </br>- Richtlinien verfeinern, Benutzer schulen       |
|**Fabrikam** ist ein kleines Start-up, das sein geistiges Eigentum schützen möchte und sich schnell bewegen muss. Sie sind bereit, einige Ressourcen zu verwenden, können es sich aber nicht leisten, externe Experten zu einstellen. </br>– Vertrauliche Elemente befinden sich alle in Microsoft 365 OneDdrive for Business/SharePoint </br>– Die Einführung von OneDrive for Business und SharePoint ist langsam, Mitarbeiter/Schatten-IT verwenden DropBox und Google Drive, um Elemente zu teilen/zu speichern </br>- Mitarbeiter schätzen Arbeitsgeschwindigkeit gegenüber Datenschutz-Disziplin </br>– Kunden haben alle 18 Mitarbeiter mit neuen Geräten Windows 10 gekauft     |– Nutzen Sie die standardmäßige DLP-Richtlinie in Teams </br>- Standardeinstellung für eingeschränkte Elemente SharePoint </br>– Bereitstellen von Richtlinien, die die externe Freigabe verhindern </br>– Bereitstellen von Richtlinien an priorisierten Speicherorten </br>– Bereitstellen von Richtlinien auf Windows 10 Geräten </br>– Blockieren von Uploads in nicht OneDrive for Business Cloudspeicher      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a>Siehe auch
- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
