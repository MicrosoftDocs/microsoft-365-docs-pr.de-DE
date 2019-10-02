---
title: Übersicht über Dokumentlöschrichtlinien
ms.author: laurawi
author: laurawi
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
ms.assetid: 55e8d858-f278-482b-a198-2e62d6a2e6e5
description: Möglicherweise ist es erforderlich, dass Ihre Organisation Dokumente für einen bestimmten Zeitraum aufbewahrt, da Compliance, rechtliche oder andere geschäftliche Anforderungen erfüllt sind. Wenn Ihre Organisation Dokumente jedoch länger als erforderlich aufrecht erhält, erstellen Sie unnötiges rechtliches Risiko. Mit einer Richtlinie zum Löschen von Dokumenten können Sie das Risiko proaktiv verringern, indem Sie Dokumente in einer Website nach einem bestimmten Zeitraum löschen (beispielsweise können Sie fünf Jahre nach dem Erstellen der Dokumente die OneDrive für Unternehmen Websites von Benutzern löschen.
ms.openlocfilehash: 87d79f6b8f4381693bf043bc0e04fcfe4359fa90
ms.sourcegitcommit: 1eecd7b127462585c35b0c96a179d37db45f6013
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37342948"
---
# <a name="overview-of-document-deletion-policies"></a>Übersicht über Dokumentlöschrichtlinien

> [!IMPORTANT]
> Es wird empfohlen, dass Sie eine Aufbewahrungsrichtlinie oder Bezeichnungen verwenden, die im Microsoft 365 Compliance Center, im Microsoft 365 Security Center oder im Office 365 &amp; Security Compliance Center anstelle einer Dokument Löschrichtlinie erstellt wurden. Dokument Löschungsrichtlinien funktionieren weiterhin nebeneinander mit Aufbewahrungsrichtlinien, wenn Sie jedoch Inhalte an einer beliebigen Stelle in Office 365 beibehalten oder löschen müssen, wird empfohlen, eine Aufbewahrungsrichtlinie zu verwenden. Weitere Informationen finden Sie unter [Verwenden einer Aufbewahrungsrichtlinie anstelle dieser Features](retention-policies.md#use-a-retention-policy-instead-of-these-features).
  
Möglicherweise ist es erforderlich, dass Ihre Organisation Dokumente für einen bestimmten Zeitraum aufbewahrt, da Compliance, rechtliche oder andere geschäftliche Anforderungen erfüllt sind. Wenn Ihre Organisation Dokumente jedoch länger als erforderlich aufrecht erhält, erstellen Sie unnötiges rechtliches Risiko. Mit einer Richtlinie zum Löschen von Dokumenten können Sie das Risiko proaktiv verringern, indem Sie Dokumente in einer Website nach einem bestimmten Zeitraum löschen (beispielsweise können Sie fünf Jahre nach dem Erstellen der Dokumente die OneDrive für Unternehmen Websites von Benutzern löschen.
  
Dokument Löschungsrichtlinien sind leistungsfähig und dennoch flexibel – Sie können beispielsweise:
  
- Erlauben Sie Websitebesitzern, die von Ihnen erstellten und verwalteten Richtlinien auszuwählen. Sie können Websitebesitzern auch erlauben, eine Richtlinie abzuwählen, falls sie für ihre Inhalte nicht geeignet sein sollte.
    
- Erzwingen Sie eine einzelne obligatorische Richtlinie auf allen Websites in einer Websitesammlung, wie z. B. OneDrive for Business-Websites, oder erzwingen Sie eine Richtlinie auf allen Websitesammlungen, die aus einer bestimmten Vorlage für Websitesammlung, z. B. die Teamwebsitevorlage, erstellt wurde.
    
- Stellen Sie eine Standardrichtlinie mit einer Standardregel bereit, die automatisch angewendet wird, ohne dass die Websitebesitzer eine Aktion durchführen müssen.
    
- Erstellen Sie eine Richtlinie mit mehreren Löschregeln, aus denen ein Websitebesitzer wählen kann.
    
Sie erstellen und verwalten Dokument Löschungsrichtlinien mithilfe des Dokument Löschrichtlinien Centers. Alternativ können Sie das Richtlinien Center manuell erstellen, indem Sie [die Websitesammlung erstellen](https://go.microsoft.com/fwlink/p/?LinkID=404342) und auf der Registerkarte **Enterprise** die Option **Compliance Policy Center** auswählen. Jeder Mandant kann nur ein Dokument Löschrichtlinien Center haben. 
  
![Startseite des Dokument Löschrichtlinien Centers](media/IP-Document-Deletion-Policy-Center-home-page.png)
  
## <a name="when-to-use-document-deletion-policies"></a>Zeitpunkt für die Verwendung von Dokumentlöschrichtlinien

Zusätzlich zu Dokumentlöschrichtlinien enthält Office 365 die folgenden Aufbewahrungsrichtlinien für Websiteinhalte:
  
- [Datensatzverwaltung](https://go.microsoft.com/fwlink/p/?LinkID=404250)
    
- [Informationsverwaltungsrichtlinien für Inhaltstypen, Listen und Bibliotheken](https://go.microsoft.com/fwlink/p/?LinkID=404239)
    
- [Websiterichtlinien](https://go.microsoft.com/fwlink/p/?LinkID=404242)
    
Die einzelnen Richtlinientypen eignen sich am besten für einen bestimmten Website- oder Datentyp. Angenommen, Ihre Organisation hat eine hochgradig strukturierte Website, die Inhaltstypen verwendet, wie z. B. eine Finanzwebsite für Verträge oder eine Wissensdatenbank für Artikel. In diesem Fall können Sie Inhaltstyprichtlinien verwenden. Oder angenommen, Ihre Organisation muss rechtliche Dokumente aufbewahren. In diesem Fall könnten Sie Inhaltstypen und ein Datenarchiv verwenden, um einen Dateiplan zu implementieren.
  
Dokument Löschungsrichtlinien ersetzen keine Datensatzverwaltung oder Informationsverwaltungsrichtlinien, die am besten mit strukturierten Daten und Inhaltstypen funktionieren. Stattdessen empfiehlt sich, Dokumentlöschrichtlinien zu verwenden, wenn Sie allgemein das automatische Löschen von unstrukturierten Daten, wie z. B. OneDrive for Business-Websites und Teamwebsites, verwalten müssen.
  
![Diagramm mit Aufbewahrungsoptionen für Websiteinhalt](media/IP-Retention-policies-for-site-content.png)
  
Wenn Sie eine Dokumentlöschrichtlinie auf eine Website anwenden, die bereits Inhaltstyprichtlinien oder Informationsverwaltungsrichtlinien für eine Liste oder Bibliothek verwendet, werden diese Richtlinien ignoriert, solange die Dokumentlöschrichtlinie aktiv ist. Das heißt, für eine Website dürfen nur Richtlinien verwendet werden, die für strukturierten oder unstrukturierten Inhalt bestimmt sind, aber nicht beides. Weitere Informationen dazu, wie Dokumentlöschrichtlinien andere Richtlinien außer Kraft setzen, finden Sie unter [Apply or remove a document deletion policy for a site](apply-or-remove-a-document-deletion-policy-for-a-site.md).
  
Im Unterschied zu anderen Richtlinien eignen sich Dokumentlöschrichtlinien nur für Dokumentbibliotheken, nicht Listen.
  
## <a name="deletion-policies-and-rules"></a>Löschrichtlinien und -regeln

Eine Dokumentlöschrichtlinie enthält mindestens eine Löschregel, die Folgendes festlegt:
  
- Zeitraum bis zum Löschen.
    
- Legt fest, ob das Löschdatum ab dem Zeitpunkt der Erstellung oder der letzten Änderung des Dokuments berechnet werden soll.
    
- Legt fest, ob das Dokument permanent oder in den Papierkorb gelöscht werden soll.
    
Wenn eine Richtlinie mehr als eine Regel enthält, können Websitebesitzer die Regel auswählen, die sich am besten für ihren Inhalt eignet.
  
![Seite "neue Löschregel"](media/IP-New-deletion-rule.png)
  
## <a name="policies-and-assignments"></a>Richtlinien und Zuweisungen

Nachdem Sie eine Dokument Löschrichtlinie erstellt haben, können Sie Sie einer websitesammlungsvorlage zuweisen, beispielsweise können Sie der OneDrive für Unternehmen Vorlage eine Richtlinie zuweisen, sodass Sie die OneDrive-Website jedes Benutzers enthält. Wenn Sie eine Richtlinie einer websitesammlungsvorlage zuweisen, gilt dies für alle Websitesammlungen, die bereits aus dieser Vorlage erstellt wurden, sowie für zukünftige Websitesammlungen, die in Zukunft aus dieser Vorlage erstellt werden.
  
![Auswählen einer Vorlagenseite mit OneDrive-Option](media/IP-Choose-a-template.png)
  
Sie können außerdem einer bestimmten Websitesammlung eine Richtlinie zuweisen. Dadurch werden alle Richtlinien, die dieser Vorlage für Websitesammlung bereits zugewiesen wurden, außer Kraft gesetzt. Sie können zum Beispiel der Teamwebsitevorlage Richtlinien zuweisen, sie dann aber außer Kraft setzen, indem Sie einen anderen Satz von Richtlinien auf eine bestimmte Websitesammlung anwenden, die aus dieser Vorlage erstellt wurde.
  
### <a name="one-mandatory-policy-or-several-policies-to-choose-from"></a>Eine obligatorische Richtlinie oder mehrere Methoden zur Auswahl

Beim Zuweisen einer Richtlinie können Sie sie als obligatorisch festlegen, sodass nur diese Richtlinie zugewiesen werden kann und auf alle Websites in der Websitesammlung angewendet wird. Websitebesitzer können eine obligatorische Richtlinie nicht abwählen, d. h. Dokumente auf der Website sind auf jeden Fall von der Löschrichtlinie betroffen.
  
Statt eine einzelne Richtlinie als obligatorisch zu kennzeichnen, können Sie einer Websitesammlung auch mehrere Richtlinien zuweisen. Dadurch kann jeder Websitebesitzer die Richtlinie, die auf die Website angewendet werden soll, auswählen oder ganz abwählen. Sie können zum Beispiel eine Richtlinie für allgemeine Geschäftsdokumente und eine für finanzielle Dokumente erstellen, die einen anderen Aufbewahrungszeitplan haben. Ein Websitebesitzer weiß oft am besten, welchen Inhalt die Website enthält und welche Dokumentlöschrichtlinie angewendet werden soll. Auf jede Website kann immer nur eine Richtlinie angewendet werden.
  
### <a name="one-rule-or-several-rules-to-choose-from"></a>Eine Regel oder mehrere Regeln zur Auswahl

Jede Richtlinie kann wiederum viele Regeln enthalten (beispielsweise kann eine Löschrichtlinie für allgemeine Geschäftsdokumente zwei Regeln haben):
  
- Dokumente, die keine Aufbewahrung auf der Grundlage gesetzlicher Verpflichtungen oder laufender geschäftlicher Anforderungen benötigen, sollten nicht länger als ein Jahr nach der Erstellung aufbewahrt werden.
    
- Dokumente, die für aktive fortlaufende Geschäftsprozesse und länger als ein Jahr benötigt werden, sollten nicht länger als drei Jahre nach ihrer Erstellung aufbewahrt werden.
    
Ein Websitebesitzer kann festlegen, dass die Website allgemeine Geschäftsdokumente enthalten soll, und kann diese Löschrichtlinie und dann die entsprechende Regel aus der Richtlinie auswählen. Sie können nur eine Regel aus der Richtlinie auswählen, die derzeit auf die Website angewendet wird (nicht aus einer Richtlinie), und die Regel gilt für alle Dokumentbibliotheken auf der Website.
  
## <a name="the-relationship-of-site-collections-policies-and-rules"></a>Beziehung zwischen Websitesammlungen, Richtlinien und Regeln

Die grundlegende Beziehung ist:
  
Einer Websitesammlung oder einer websitesammlungsvorlage kann mindestens eine Richtlinie zugewiesen sein, und jede dieser Richtlinien kann eine oder mehrere Regeln haben. Es kann jedoch nur eine Richtlinie pro Standort aktiv sein, und es kann immer nur eine Löschregel für die Bibliotheken innerhalb der Website aktiv sein.
  
![Diagramm mit Beziehung zwischen Richtlinien](media/IP-Two-policies-four-rules.png)
  
## <a name="document-deletion-policies-are-inherited"></a>Dokumentlöschrichtlinien werden vererbt.

So wie Berechtigungen, Navigation und viele andere Websitefunktionen werden auch Dokumentlöschrichtlinien vererbt. Websitebesitzer können für ihre Website eine Richtlinie und Regel auswählen, und alle Unterwebsites erben die Richtlinie von der übergeordneten Website. Ein Besitzer einer Unterwebsite kann die Vererbung aufheben, indem er eine andere Richtlinien- und Regelkombination auswählt, und diese Richtlinie gilt dann für alle Unterwebsites, bis die Vererbung wieder aufgehoben wird.
  
## <a name="assigning-document-deletion-policies-for-the-first-time"></a>Erstmaliges Zuweisen von Dokumentlöschrichtlinien

Beachten Sie, dass es sich bei dem für eine Dokument Löschrichtlinie angegebenen Zeitraum um die Zeit seit dem Erstellen oder Ändern des Dokuments und nicht um die Zeit seit der Zuweisung der Richtlinie handelt. Sie können beispielsweise eine Dokument Löschrichtlinie erstellen, die Dokumente dauerhaft zwei Jahre nach ihrer Erstellung löscht, und diese Richtlinie dann einer websitesammlungsvorlage zuweisen, aus der mehrere Websitesammlungen vor vier oder fünf Jahren erstellt wurden. In diesem Fall ist es wahrscheinlich, dass die vorhandenen Websitesammlungen zahlreiche Dokumente enthalten, die bereits älter als die in der Löschrichtlinie angegebenen zwei Jahre sind, d. h., viele Inhalte werden bald nach dem Zuweisen der Dokument Löschrichtlinie für die erste gelöscht. Zeit.
  
Wenn Sie die Richtlinie zum ersten Mal zuweisen, werden alle Dokumente auf der Website ausgewertet und, falls sie die Kriterien erfüllen, gelöscht. Dies trifft auf alle vorhandenen Dokumente zu, nicht nur auf neue Dokumente, die seit der Zuweisung der Richtlinie erstellt wurden. Denken Sie auch daran, dass der Zeitraum das Alter eines Dokuments darstellt, nicht den Zeitraum ab der erstmaligen Zuweisung der Richtlinie.
  
Daher sollten Sie vor dem erstmaligen Zuweisen einer Richtlinie zu einer Website zunächst das Alter des vorhandenen Inhalts und die möglichen Auswirkungen der Richtlinie auf diesen vorhandenen Inhalt bedenken. Sie können außerdem vor dem Zuweisen die Websitebesitzer über die neue Richtlinie informieren, um ihnen Zeit zur Auswertung der möglichen Auswirkungen zu geben.
  
## <a name="time-lag-for-propagating-policies"></a>Zeitverzögerung für die Verbreitung von Richtlinien

Nachdem Sie einer Websitesammlung Richtlinien zugewiesen haben, können Websitebesitzer über den Link **Dokumentlöschrichtlinien** auf der Seite **Websiteeinstellungen** die für die Website verfügbaren Richtlinien anzeigen und anwenden. 
  
Der Link **Dokument Löschungsrichtlinien** wird nur angezeigt, wenn der Websitesammlung Richtlinien zugewiesen wurden. Außerdem wird der Link nicht unmittelbar nach dem Zuweisen von Richtlinien zur Website angezeigt – es kann bis zu 24 Stunden dauern, bis die Richtlinien zugewiesen sind, wenn der Link **Dokument Löschungsrichtlinien** angezeigt wird. 
  
## <a name="permissions"></a>Berechtigungen

Mitglieder Ihres Kompatibilitätsteams, die das Document Deletion Policy Center verwenden, benötigen Berechtigungen für das Policy Center und die Websitesammlungen, auf die die Richtlinien angewendet werden sollen. Wir empfehlen, dass Sie wie folgt vorgehen:
  
1. Erstellen Sie eine Sicherheitsgruppe, die alle Benutzer des Dokument Löschrichtlinien Centers enthält – wahrscheinlich Ihr Compliance-Richtlinien Verwaltungsteam. Weitere Informationen finden Sie unter [Verwalten von e-Mail-aktivierten Sicherheitsgruppen](https://go.microsoft.com/fwlink/p/?LinkID=404345) . 
    
2. Weisen Sie im Document Deletion Policy Center Websitesammlungs-Besitzerberechtigungen der Sicherheitsgruppe zu. Weitere Informationen finden Sie unter [Berechtigungen für Websitesammlungsadministratoren](https://go.microsoft.com/fwlink/p/?LinkID=404346) . 
    
3. Weisen Sie in jeder Websitesammlung, der Sie Dokumentlöschrichtlinien zuweisen müssen, Websitesammlungs-Besitzerberechtigungen zu der Sicherheitsgruppe zu.
    
## <a name="how-document-deletion-policies-work-with-hold-policies"></a>Funktionsweise von Dokumentlöschrichtlinien und Aufbewahrungsrichtlinien

Eine Aufbewahrungsrichtlinie stellt sicher, dass alle Inhalte für einen bestimmten Zeitraum archiviert werden, während eine Dokumentlöschrichtlinie sicherstellt, dass alle Inhalte nach einem bestimmten Zeitraum gelöscht werden.
  
Wenn Sie Dokumente für einen bestimmten Zeitraum aufbewahren müssen, verwenden Sie eine Aufbewahrungsrichtlinie gemeinsam mit einer Löschrichtlinie. Sie könnten zum Beispiel Dokumente nach ihrer letzten Änderung drei Jahre lang aufbewahren und dann eine Löschrichtlinie festlegen, um sie drei Jahre nach ihrer letzten Änderung zu löschen.
  
Beachten Sie, dass eine Löschrichtlinie eine Aufbewahrungsrichtlinie nicht außer Kraft setzen kann. Wenn eine Website archiviert und ein Dokument aufgrund einer Dokumentlöschrichtlinie gelöscht wird, dann wird das Dokument im permanenten Dokumentarchiv aufbewahrt, so als ob es manuell gelöscht worden sei.
  
## <a name="see-also"></a>Siehe auch

[Anwenden oder Entfernen einer Dokumentlöschrichtlinie für eine Website](apply-or-remove-a-document-deletion-policy-for-a-site.md)

[Erstellen einer Dokumentlöschrichtlinie](create-a-document-deletion-policy.md)


