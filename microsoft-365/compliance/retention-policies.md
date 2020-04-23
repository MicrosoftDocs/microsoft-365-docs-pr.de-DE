---
title: Übersicht über Aufbewahrungsrichtlinien
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
description: Mit einer Aufbewahrungsrichtlinie können Sie proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides, also aufbewahrt und dann gelöscht werden sollen, eine einzelne Richtlinie auf die gesamte Organisation oder auf bestimmte Speicherorte oder Benutzer anwenden sowie eine Richtlinie auf alle Inhalte oder auf bestimmte Bedingungen erfüllende Inhalte anwenden.
ms.openlocfilehash: 7075e043a2d45358447137fbf76bcbf88a65e9f4
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43632436"
---
# <a name="overview-of-retention-policies"></a>Übersicht über Aufbewahrungsrichtlinien

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit & Compliance](https://aka.ms/ComplianceSD).*

In den meisten Organisationen nimmt die Menge und Komplexität der Daten täglich zu – E-Mails, Dokumente, Chatnachrichten usw. Eine effektive Verwaltung bzw. Governance dieser Informationen ist wichtig, da Sie:
  
- **branchenspezifische Vorschriften und interne Richtlinien einhalten müssen**, nach denen Inhalte für eine bestimmte Mindestdauer aufzubewahren sind – z. B. müssen Sie gemäß dem Sarbanes-Oxley Act möglicherweise bestimmte Arten von Inhalten über sieben Jahre lang aufbewahren. 
    
- **das Risiko bei Rechtsstreitigkeiten oder einer Sicherheitsverletzung reduzieren müssen**, indem Sie alte Inhalte, die Sie nicht mehr aufbewahren müssen, endgültig löschen. 
    
- **Ihrer Organisation dabei helfen müssen, effektiven Wissensaustausch zu betreiben und agiler zu werden**, indem Sie sicherstellen, dass die Benutzer nur mit Inhalten arbeiten, die aktuell und für sie relevant sind. 
    
Eine Aufbewahrungsrichtlinie kann Ihnen dabei helfen, alle diese Ziele zu erreichen. Das Verwalten von Inhalten macht häufig zwei Aktionen erforderlich:
  
- **Aufbewahrung** von Inhalten, sodass sie nicht vor dem Ende des Aufbewahrungszeitraums dauerhaft gelöscht werden 
    
- **Endgültiges Löschen** von Inhalten am Ende des Aufbewahrungszeitraums. 
    
Mit einer Aufbewahrungsrichtlinie können Sie:
  
- proaktiv entscheiden, ob Inhalte aufbewahrt, gelöscht oder beides, also aufbewahrt und dann gelöscht werden sollen.
    
- eine einzelne Richtlinie auf die gesamte Organisation oder auf bestimmte Speicherorte oder Benutzer anwenden.
    
- eine Richtlinie auf alle Inhalte oder auf bestimmte Kriterien erfüllende Inhalte anwenden, z. B. auf Inhalte, die bestimmte Schlüsselwörter oder [bestimmte Arten von vertraulichen Informationen](what-the-sensitive-information-types-look-for.md) enthalten.
    
Wenn Inhalte einer permanenten Richtlinie unterliegen, können Benutzer den Inhalt weiterhin bearbeiten und verwenden, als hatte sich nichts geändert, da der Inhalt an seinem ursprünglichen Speicherort beibehalten wird. Falls Inhalte, die der Richtlinie unterliegen, jedoch bearbeitet oder gelöscht werden, wird eine Kopie an einem sicheren Standort gespeichert, an dem sie beibehalten wird, solange die Richtlinie gilt.
  
Schließlich müssen einige Organisationen Vorschriften einhalten, wie zum Beispiel die Rule 17a-4 der Securities and Exchange Commission (SEC), nach der eine Aufbewahrungsrichtlinie nach dem Aktivieren nicht deaktiviert oder weniger restriktiv eingestellt werden darf. Um diese Anforderung zu erfüllen, können Sie die Erhaltungssperre verwenden. Nachdem eine Richtlinie gesperrt wurde, kann niemand (auch nicht ein Administrator) die Richtlinie deaktivieren oder weniger restriktiv einstellen.
  
Sie erstellen und verwalten Aufbewahrungsrichtlinien über das [Microsoft 365 Compliance Center](https://compliance.microsoft.com/): **Richtlinien** > **Daten** > **Aufbewahrung**

Alternativ können Sie zur selben Stelle im Microsoft 365 Compliance Center navigieren, indem Sie die Registerkarten **Lösungen** > **Information Governance** > **Aufbewahrung** verwenden. 

**Wenn Sie die Möglichkeit haben möchten, Inhalte zu überprüfen, bevor sie endgültig gelöscht werden, **sollten Sie die Verwendung von [Aufbewahrungsbezeichnungen](labels.md) anstelle einer Aufbewahrungsrichtlinie in Betracht ziehen. Wenn Sie eine Aufbewahrungsbezeichnung erstellen, können Sie eine [Löschungsprüfung](disposition-reviews.md) einrichten, um den Inhalt am Ende der Aufbewahrungsfrist zu überprüfen.

## <a name="how-a-retention-policy-works-with-content-in-place"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Inhalten

Wenn Sie einen Speicherort, z. B. eine Website oder ein Postfach in eine Aufbewahrungsrichtlinie einschließen, verbleibt der Inhalt an seinem ursprünglichen Speicherort. Benutzer können weiter mit ihren Dokumenten oder E-Mails arbeiten, als ob sich nichts geändert hätte. Wenn sie jedoch Inhalte bearbeiten oder löschen, die von der Richtlinie abgedeckt sind, wird eine Kopie des Inhalts in seinem Zustand zum Zeitpunkt der Anwendung der Richtlinie beibehalten.
  
Für SharePoint-Websitesammlungen wird eine Kopie des ursprünglichen Inhalts im permanenten Dokumentarchiv beibehalten, wenn Benutzer diesen bearbeiten oder löschen. Bei E-Mails und öffentlichen Ordnern wird die Kopie im Ordner „Wiederherstellbare Elemente“ aufbewahrt. Diese sicheren Speicherorte und die aufbewahrten Inhalte werden den meisten Benutzern nicht angezeigt. Mit einer Aufbewahrungsrichtlinie müssen Benutzer nicht einmal wissen, dass ihre Inhalte der Richtlinie unterliegen.
  
Hinweise:
  
- Teams (Chat)-Inhalte werden in Exchange gespeichert und die Richtlinie basierend auf dem Nachrichtentyp (E-Mail oder Unterhaltung) angewendet.
    
- Eine auf eine Office 365-Gruppe angewendete Aufbewahrungsrichtlinie umfasst sowohl das Gruppenpostfach als auch die Website.

- Das permanente Dokumentarchiv verbraucht Speicherkontingent für die Website.
    
### <a name="content-in-onedrive-accounts-and-sharepoint-sites"></a>Inhalte in OneDrive-Konten und SharePoint-Websites

Eine Aufbewahrungsrichtlinie wird auf der Ebene einer Websitesammlung angewendet. Wenn Sie eine SharePoint-Websitesammlung oder ein OneDrive-Konto in eine Aufbewahrungsrichtlinie einschließen, wird ein permanentes Dokumentarchiv verwendet, um Dokumente aufzubewahren. Diese Bibliothek wird automatisch erstellt, wenn sie nicht bereits vorhanden ist. Sie können diese Bibliothek auf der Seite **Websiteinhalte** der Website auf oberster Ebene der Websitesammlung anzeigen. Die meisten Benutzer können das permanente Dokumentarchiv nicht anzeigen, da es nur für Websitesammlungsadministratoren sichtbar ist.
  
Wenn ein Benutzer versucht, den Inhalt einer Website, die einer Aufbewahrungs- und Löschungs- oder einer reinen Aufbewahrungsrichtlinie unterliegt, zu ändern oder zu löschen, überprüft die Aufbewahrungsrichtlinie zunächst, ob der Inhalt seit Anwendung der Richtlinie geändert wurde. Wenn dies die erste Änderung seit Anwendung der Richtlinie ist, kopiert die Aufbewahrungsrichtlinie den Inhalt in das permanente Dokumentarchiv und ermöglicht dem Benutzer anschließend das Ändern oder Löschen des ursprünglichen Inhalts. Alle Inhalte der Websitesammlung können auch dann in das permanente Dokumentarchiv kopiert werden, wenn der Inhalt der Abfrage, die von der Aufbewahrungsrichtlinie verwendet wird, nicht entspricht.

Das Kopieren von Inhalten in das permanente Dokumentarchiv gilt auch für Inhalte, die bei Anwendung der Aufbewahrungsrichtlinie vorhanden sind. Außerdem werden alle neuen Inhalte, die erstellt oder der Websitesammlung hinzugefügt werden, nachdem sie in die Richtlinie eingeschlossen wurden, auch nach dem Löschen aufbewahrt. Neue Inhalte werden jedoch nicht bei der ersten Bearbeitung in das permanente Dokumentarchiv kopiert, sondern nur, wenn sie gelöscht werden. Wenn Sie alle Versionen einer Datei aufbewahren möchten, aktivieren Sie die Versionsverwaltung, wie im folgenden [Abschnitt](#how-a-retention-policy-works-with-document-versions-in-a-site-collection) erläutert.
  
Beachten Sie, dass ein Benutzer eine Fehlermeldung erhält, wenn er versucht, Bibliotheken, Listen, Ordner oder Websites zu löschen, für die eine Aufbewahrungsrichtlinie gilt. Ein Benutzer kann einen Ordner löschen, wenn er zuerst Dateien im Ordner verschiebt oder löscht, die der Richtlinie unterliegen. Außerdem wird das permanente Dokumentarchiv nur erstellt, sobald das erste Element in das Archiv kopiert werden muss, und nicht, wenn Sie die Aufbewahrungsrichtlinie erstellen. Zum Testen Ihrer Richtlinie müssen Sie daher zuerst ein Dokument in einer Website bearbeiten oder löschen, die der Richtlinie unterliegt, und dann zum permanenten Dokumentarchiv wechseln, um die aufbewahrte Kopie anzuzeigen.
  
Nachdem einem OneDrive-Konto oder einer SharePoint-Site eine Aufbewahrungsrichtlinie zugewiesen wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie der Aufbewahrung und dem Löschen, der reinen Aufbewahrung oder dem reinen Löschen dient.

Wenn Sie die Aufbewahrungsrichtlinie dem Aufbewahren und Löschen dient:

![Diagramm des Inhaltslebenszyklus in SharePoint und OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Inhalts wird in der beim Zuweisen der Richtlinie vorhandenen Form im permanenten Dokumentarchiv erstellt. Dort wird regelmäßig ein Zeitgeberauftrag ausgeführt, der Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden in den endgültigen Papierkorb verschoben, von wo sie nach Ablauf von 93 Tagen endgültig gelöscht werden. Der endgültige Papierkorb wird den Endbenutzern nicht angezeigt (sie sehen nur den Standardpapierkorb), Websitesammlungsadministratoren können hingegen dessen Inhalte anzeigen und wiederherstellen.

    > [!NOTE]
    > Um versehentlichen Datenverlust zu vermeiden, werden Inhalte nie automatisch aus dem permanenten Dokumentarchiv gelöscht, sondern in den endgültigen Papierkorb verschoben. Dort können Administratoren dank der Kulanzperiode von 93 Tagen diese Inhalte ggf. wiederherstellen.
    
2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Das Dokument wird am Ende des Aufbewahrungszeitraums in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert (auch als Bereinigen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen. 

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar:

#### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Dokuments wird im permanenten Dokumentarchiv erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im permanenten Dokumentarchiv in den endgültigen Papierkorb verschoben und nach 93 Tagen endgültig gelöscht wird.

2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Dokument verbleibt an seinem Ursprungsort.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für rein löschende Aufbewahrungsrichtlinien

1. **Wenn der Inhalt während des Aufbewahrungszeitraums gelöscht wird**: Das Dokument wird in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert, wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Wenn der Inhalt während des Aufbewahrungszeitraums geändert wird, folgt er nach Ablauf des Inhalts demselben Löschpfad.

2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht gelöscht wird**: Das Dokument wird am Ende des Aufbewahrungszeitraums in den Standardpapierkorb verschoben. Wenn der Inhalt während des Aufbewahrungszeitraums gelöscht wird, wird das Dokument sofort in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert (auch als Bereinigen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen.

### <a name="content-in-mailboxes-and-public-folders"></a>Inhalte in Postfächern und öffentlichen Ordnern

Für die E-Mails, den Kalender und andere Elemente eines Benutzers wird eine Aufbewahrungsrichtlinie auf Postfachebene angewendet. Für einen öffentlichen Ordner wird eine Aufbewahrungsrichtlinie auf Ordnerebene angewendet, nicht auf Postfachebene. Ein Postfach und ein öffentlicher Ordner verwenden beide den Order „Wiederherstellbare Elemente“, um Elemente beizubehalten. Nur Personen, denen eDiscovery-Berechtigungen zugewiesen wurden, können den Ordner „Wiederherstellbare Elemente“ eines anderen Benutzers anzeigen.
  
Standardmäßig wird eine Nachricht, die von einem Benutzer aus einem anderen Ordner als dem Ordner "Gelöschte Elemente" gelöscht wird, in den Ordner "Gelöschte Elemente" verschoben. Wenn ein Benutzer ein Element aus dem Ordner "Gelöschte Elemente" löscht, wird die Nachricht in den Ordner "Wiederherstellbare Elemente" verschoben. Außerdem kann ein Benutzer ein Element in einem Ordner mit UMSCHALT+ENTF löschen. Auf diese Weise wird der Ordner "Gelöschte Elemente" umgangen und das Element direkt in den Ordner "Wiederherstellbare Elemente" verschoben.
  
Ein Prozess bewertet die Elemente im Ordner "Wiederherstellbare Elemente" in regelmäßigen Abständen. Wenn ein Element den Regeln mindestens einer Aufbewahrungsrichtlinie nicht entspricht, wird das Element endgültig aus dem Ordner "Wiederherstellbare Elemente" gelöscht (wird auch als endgültiges Löschen bezeichnet).
  
Wenn ein Benutzer versucht, bestimmte Eigenschaften eines Postfachelements zu ändern – zum Beispiel Betreff, Text, Anhänge, Sender und Empfänger oder Sende- bzw. Empfangsdatum einer Nachricht – wird eine Kopie des ursprünglichen Elements im Ordner "Wiederherstellbare Elemente" gespeichert, bevor die Änderung übernommen wird. Diese Aktion findet für alle nachfolgenden Änderungen statt. Am Ende des Aufbewahrungszeitraums werden Kopien im Ordner "Wiederherstellbare Elemente" endgültig gelöscht.
  
Wenn Sie die Aufbewahrungsrichtlinie dem Aufbewahren und Löschen dient:

![Diagramm des Aufbewahrungsflusses in E-Mail- und öffentlichen Ordnern](../media/88f174cc-bbf4-4305-93d7-0515f496c8f9.png)

1. **Wenn das Element während des Aufbewahrungszeitraums vom Benutzer geändert oder dauerhaft gelöscht wird** (entweder per UMSCHALT + ENTF oder aus gelöschte Elemente gelöscht), wird das Element in den Ordner "Wiederherstellbare Elemente" verschoben (oder, im Fall der Bearbeitung, kopiert). Dort wird in regelmäßigen Abständen ein Vorgang ausgeführt, der Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist, und diese Elemente werden innerhalb von 14 Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass die Standardeinstellung 14 Tage beträgt, aber es können auch 30 Tage eingestellt werden.
    
2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**, wird derselbe Prozess in regelmäßigen Abständen für alle Ordner im Postfach ausgeführt, und es werden Elemente identifiziert, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden innerhalb von 14 Tagen nach Ende des Aufbewahrungszeitraums dauerhaft gelöscht. Beachten Sie, dass 14 Tage die Standardeinstellung ist, die aber auf bis zu 30 Tage festgelegt werden kann. Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar:

#### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn das Element während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Elements wird im Ordner „Wiederherstellbare Elemente“ erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im Ordner „Wiederherstellbare Elemente“ innerhalb von 14 Tagen nach Ablauf des Elements endgültig gelöscht wird. 

2. **Wenn das Element während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Element verbleibt an seinem Ursprungsort.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für rein löschende Aufbewahrungsrichtlinien

1. **Wenn das Element während des Aufbewahrungszeitraums nicht gelöscht wird**: Das Element wird am Ende des Aufbewahrungszeitraums in den Ordner „Wiederherstellbare Elemente“ verschoben. 

2. **Wenn das Element während des Zeitraums gelöscht wird**, wird das Element sofort in den Ordner „Wiederherstellbare Elemente“ verschoben. Wenn ein Benutzer das Element dort löscht oder den Ordner „Wiederherstellbare Elemente“ leert, wird das Element endgültig gelöscht. Andernfalls wird das Element endgültig gelöscht, nachdem es 14 Tage im Ordner „Wiederherstellbare Elemente“ aufbewahrt wurde. 

### <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt

**Exchange** 

Wenn ein Benutzer Ihre Organisation verlässt und sein Postfach in einer Aufbewahrungsrichtlinie enthalten ist, wird das Postfach zu einem inaktiven Postfach, wenn das Office 365-Konto des Benutzers gelöscht wird. Die Inhalte eines inaktiven Postfachs unterliegen weiterhin jeglicher Aufbewahrungsrichtlinie, die dem Postfach zugewiesen wurde, bevor es inaktiv wurde, und die Inhalte sind für eDiscovery-Suchen verfügbar. Weitere Informationen finden Sie unter [Inaktive Postfächer in Exchange Online](inactive-mailboxes-in-office-365.md).

**OneDrive**

Wenn ein Benutzer Ihre Organisation verlässt, bleiben alle Dateien, für die eine Aufbewahrungsrichtlinie gilt oder die Aufbewahrungsbezeichnungen enthalten, für die Dauer der Richtlinie oder Bezeichnung erhalten. Während dieses Zeitraums bleibt der gesamte Freigabezugriff aufrecht. Nach Ablauf des Aufbewahrungszeitraums wird der Inhalt in den Papierkorb der Websitesammlung verschoben, wo er nur für den Administrator zugänglich sein wird. Wenn ein Dokument durch eine Aufbewahrungsrichtlinie als Eintrag gekennzeichnet ist, wird es erst gelöscht, wenn der Aufbewahrungszeitraum abgelaufen ist. Danach wird der Inhalt endgültig gelöscht.

**SharePoint**

Wenn ein Benutzer Ihre Organisation verlässt, sind Inhalte, die von ihm erstellt wurden, nicht betroffen, weil SharePoint als eine Zusammenarbeitsumgebung betrachtet wird, im Gegensatz zu dem Postfach oder dem OneDrive-Konto des Benutzers.

## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Dokumentversion in einer Websitesammlung

Die Versionsverwaltung ist ein Feature aller Dokumentbibliotheken in SharePoint Online und in OneDrive for Business. Standardmäßig werden bei der Versionsverwaltung mindestens 500 Hauptversionen beibehalten, Sie können diese Beschränkung jedoch erhöhen. Weitere Informationen finden Sie unter [Aktivieren und Konfigurieren der Versionsverwaltung für eine Liste oder Bibliothek](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Eine Aufbewahrungsregelung (Aufbewahrungsrichtlinie, im Rahmen derer Inhalte nicht einfach nur gelöscht sondern auch aufbewahrt werden können) umfasst alle Versionen eines Dokuments in einer SharePoint-Websitesammlung oder einem OneDrive-Konto. Wenn ein Dokument, das einer Aufbewahrungsrichtlinie untersteht, zum ersten Mal bearbeitet wird, wird eine Version des ursprünglichen Dokuments in das permanente Dokumentarchiv kopiert und dort aufbewahrt. Wenn ein Dokument, das einer Aufbewahrungsregelung untersteht, gelöscht wird, werden alle bestehenden Versionen in das permanente Dokumentarchiv kopiert. Vorrausetzung hierfür ist, dass die Versionsverwaltung aktiviert sein muss. Jede Version eines Dokuments im permanenten Dokumentarchiv bleibt in ihrem jeweiligen Aufbewahrungszeitraum als eigenständiges Element bestehen:
  
- Wenn die Aufbewahrungsrichtlinie darauf basiert, wann der Inhalt erstellt wurde, verfügt jede Version über das gleiche Ablaufdatum wie das ursprüngliche Dokument. Das ursprüngliche Dokument und dessen Versionen laufen gleichzeitig ab.
    
- Wenn die Aufbewahrungsrichtlinie darauf basiert, wann der Inhalt zuletzt geändert wurde, verfügt jede Version über ein eigenes Ablaufdatum basierend auf dem Zeitpunkt der Änderung des ursprünglichen Dokuments, aus der diese Version hervorgegangen ist. Die Originaldokumente und deren Versionen laufen unabhängig voneinander ab.

> [!NOTE]
> Aufbewahrte Versionen von SharePoint- und OneDrive-Dokumenten lassen sich nicht mithilfe von eDiscovery-Tools durchsuchen.

## <a name="retaining-content-for-a-specific-period-of-time"></a>Aufbewahren von Inhalten für einen bestimmten Zeitraum

Mit einer Aufbewahrungsrichtlinie können Sie Inhalte zeitlich unbegrenzt oder für eine bestimmte Anzahl von Tagen, Monaten oder Jahren aufbewahren. Die Dauer der Aufbewahrung von Inhalten wird anhand des Alters der Inhalte und nicht anhand des Anwendungsdatums der Aufbewahrungsrichtlinie berechnet. Sie können auswählen, ob das Alter auf dem Erstellungsdatum des Inhalts oder (bei OneDrive und SharePoint) auf dem Datum der letzten Änderung basiert.
  
Wenn Sie Inhalte einer Websitesammlung beispielsweise nach ihrer letzten Änderung sieben Jahre lang aufbewahren möchten und ein Dokument in dieser Websitesammlung sechs Jahre lang nicht geändert wurde, wird das Dokument nur noch ein weiteres Jahr aufbewahrt, falls es nicht geändert wird. Falls das Dokument wieder geändert wird, wird das Alter des Dokuments anhand des neuen Datums der letzten Änderung berechnet und weitere sieben Jahre lang aufbewahrt.
  
Ebenso wird, wenn Sie Inhalte in einem Postfach für sieben Jahre aufbewahren möchten, und eine Nachricht wurde vor sechs Jahren gesendet, die Nachricht nur noch ein Jahr lang aufbewahrt. Bei Exchange-Inhalten basiert das Alter immer auf dem Empfangs- oder Sendedatum (diese sind identisch). Das Aufbewahren von Inhalten basierend auf ihrer letzten Änderung gilt nur für Websiteinhalte in OneDrive und SharePoint.
  
Sie können wählen, ob der Inhalt am Ende des Aufbewahrungszeitraums dauerhaft gelöscht werden soll. Mithilfe einer Aufbewahrungsrichtlinie können auch alte Inhalte gelöscht werden, ohne sie aufzubewahren. Informationen dazu finden Sie im nächsten Abschnitt.
  
![Ordneraufbewahrungseinstellungen](../media/b05f84e5-fc71-4717-8f7b-d06a29dc4f29.png)
  
## <a name="deleting-content-thats-older-than-a-specific-age"></a>Löschen von Inhalten, die ein bestimmtes Alter überschritten haben

Eine Aufbewahrungsrichtlinie kann Inhalte sowohl aufbewahren und dann löschen, oder alte Inhalte löschen, ohne sie aufzubewahren.
  
Wenn Ihre Aufbewahrungsrichtlinie Inhalte löscht, ist es wichtig, zu wissen, dass der für eine Aufbewahrungsrichtlinie festgelegte Zeitraum jedes Mal berechnet wird, wenn der betreffende Inhalt erstellt oder geändert wird.
  
![Löscheinstellungen](../media/042f9571-96f4-458f-8f38-fad3ed68ed31.png)
  
Nehmen wir zum Beispiel an, dass Sie eine Aufbewahrungsrichtlinie erstellen, nach der Inhalte nach drei Jahren gelöscht werden, und diese Aufbewahrungsrichtlinie dann allen OneDrive-Konten zuweisen, die viele Inhalte enthalten, die vor vier oder fünf Jahren erstellt wurden. In einem solchen Fall werden viele der Inhalte schon bald nach der ersten Zuweisung der Aufbewahrungsrichtlinie gelöscht. Daher kann **eine Aufbewahrungsrichtlinie, nach der Inhalte gelöscht werden, wesentliche Auswirkungen auf Ihre Inhalte haben**. 
  
Daher sollten Sie vor dem erstmaligen Zuweisen einer Richtlinie zu einer Websitesammlung zunächst das Alter des vorhandenen Inhalts und die möglichen Auswirkungen der Richtlinie auf diesen Inhalt bedenken. Sie können außerdem vor dem Zuweisen die Benutzer über die neue Richtlinie informieren, um ihnen Zeit zur Auswertung der möglichen Auswirkungen zu geben. Beachten Sie, dass folgende Warnung erscheint, wenn Sie die Einstellungen für Ihre Aufbewahrungsrichtlinie prüfen, bevor Sie sie erstellen.
  
![Warnung zum Löschen von Inhalten](../media/59c26b19-3628-4cc1-9a73-a05127a8e81b.png)
  
## <a name="advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions"></a>Erweiterte Einstellungen, nach denen eine Richtlinie nur auf Inhalte angewendet wird, die bestimmte Bedingungen erfüllen.

Eine Aufbewahrungsrichtlinie kann für alle Inhalte an den von ihr abgedeckten Speicherorten gelten, oder Sie können auswählen, eine Aufbewahrungsrichtlinie nur auf Inhalte anzuwenden, die bestimmte Stichwörter oder [bestimmte Arten von vertraulichen Informationen](what-the-sensitive-information-types-look-for.md) enthalten.
  
![Erweiterte Aufbewahrungsoptionen](../media/e8d9dd42-c062-4e8b-a2ca-bffe3ea298e0.png)
  
### <a name="retain-content-that-contains-specific-keywords"></a>Aufbewahren von Inhalten, die bestimmte Stichwörter enthalten

Sie können eine Aufbewahrungsrichtlinie ausschließlich auf Inhalte anwenden, die bestimmte Kriterien erfüllen, und dann Aufbewahrungsaktionen nur für diese Inhalte ausführen. Die verfügbaren Bedingungen unterstützen jetzt das Anwenden einer Aufbewahrungsrichtlinie auf Inhalte, die bestimmte Wörter oder Ausdrücke enthalten. Sie können Ihre Abfrage mithilfe von Suchoperatoren wie UND, ODER und NICHT verfeinern. Weitere Informationen zu diesen Operatoren finden Sie unter [Stichwortabfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
  
Unterstützung für das Hinzufügen durchsuchbarer Eigenschaften (z. B. **Betreff:**) wird in Kürze verfügbar sein.
  
Die abfragebasierte Aufbewahrung verwendet den Suchindex, um Inhalte zu identifizieren.
  
![Abfrage-Editor](../media/2c31b412-922e-4a88-89e4-5175c23d9b5f.png)
  
### <a name="retain-content-that-contains-sensitive-information"></a>Aufbewahren von Inhalten, die vertrauliche Informationen enthalten

Sie können eine Aufbewahrungsrichtlinie auch nur auf Inhalte anwenden, die [bestimmte Arten von vertraulichen Informationen](what-the-sensitive-information-types-look-for.md) enthalten. Sie können z. B. eindeutige Aufbewahrungsanforderungen nur auf Inhalte, die personenbezogene Informationen (PII) wie Steuernummern, Sozialversicherungsnummern oder Reisepassnummern enthalten, anwenden.
  
![Seite „Typen vertraulicher Informationen“](../media/8b104819-d185-4d58-b6b3-d06e82686a05.png)
  
Hinweise:
  
- Die erweiterte Aufbewahrung für vertrauliche Informationen gilt nicht für öffentliche Exchange-Ordner oder Skype for Business, da diese Speicherorte keine vertraulichen Informationstypen unterstützen.
    
- Sie sollten wissen, dass in Exchange Online E-Mail-Flussregeln (auch als Transportregeln bezeichnet) zum Identifizieren vertraulicher Informationen verwendet werden, sodass dies nur bei Nachrichten während der Übertragung funktioniert, jedoch nicht für alle Elemente, die bereits in einem Postfach gespeichert sind. Für Exchange Online bedeutet dies, dass mit einer Aufbewahrungsrichtlinie nur für Nachrichten, die **nach** der Richtlinienaktivierung für das Postfach empfangen werden, vertrauliche Informationen identifiziert und Aufbewahrungsaktionen ausgeführt werden können.(Beachten Sie, dass die im vorherigen Abschnitt beschriebene abfragebasierte Aufbewahrung diese Einschränkung nicht aufweist, da zum Identifizieren von Inhalten der Suchindex verwendet wird.) 
    
## <a name="applying-a-retention-policy-to-an-entire-organization-or-specific-locations"></a>Anwenden einer Aufbewahrungsrichtlinie auf eine gesamte Organisation oder bestimmte Speicherorte

Sie können eine Aufbewahrungsrichtlinie ganz einfach auf eine gesamte Organisation, ganze Speicherorte oder nur auf bestimmte Speicherorte oder Benutzer anwenden.
  
### <a name="org-wide-policy"></a>Organisationsweite Richtlinie

Eines der leistungsstärksten Features einer Aufbewahrungsrichtlinie ist, dass sie für Speicherorte in ganz Office 365 angewendet werden kann, einschließlich:
  
- Exchange-E-Mail
    
- SharePoint-Websitesammlungen
    
- OneDrive-Konten
    
- Office 365-Gruppen (gilt für Inhalte in Postfach und zugehöriger Website der Gruppe)
    
- Öffentliche Exchange-Ordner
    

![Option „Alle Speicherorte“](../media/retention-policies-all-locations.png)

Weitere wichtige Features einer organisationsweiten Aufbewahrungsrichtlinie sind:
  
- Es gibt keine Beschränkung für die Anzahl der Postfächer oder Websites, die in der Richtlinie enthalten sein können.
    
- Bei Exchange erben alle neuen Postfächer, die nach der Anwendung der Richtlinie erstellt werden, die Richtlinie automatisch.
  
### <a name="a-policy-that-applies-to-entire-locations"></a>Eine Richtlinie, die für ganze Speicherorte gilt

Beim Auswählen von Speicherorten können Sie einen ganzen Speicherort (z. B. Exchange-E-Mail- oder OneDrive-Konten) problemlos ein- oder ausschließen. Hierzu müssen Sie den **Status** des entsprechenden Speicherorts aktivieren oder deaktivieren. 
  
Wie auch bei organisationsweiten Richtlinien gilt, dass wenn eine Richtlinie für eine beliebige Kombination aus ganzen Speicherorten gilt, es keine Beschränkung für die Anzahl der Postfächer oder Websites gibt, die in der Richtlinie enthalten sein können. Wenn eine Richtlinie z. B. alle Exchange-E-Mail-Konten und alle SharePoint-Websites umfasst, werden alle Websites und Postfächer einbezogen, ganz gleich, wie viele es sind. Und bei Exchange erben alle neuen Postfächer, die erstellt werden, nachdem die Richtlinie angewendet wurde, die Richtlinie automatisch.

### <a name="a-policy-with-specific-inclusions-or-exclusions"></a>Eine Richtlinie mit bestimmten eingeschlossenen oder ausgeschlossenen Elementen

Sie können eine Aufbewahrungsrichtlinie auch auf bestimmte Benutzer, Office 365-Gruppen, oder Websites anwenden. Schalten Sie zu diesem Zweck den **Status** des entsprechenden Speicherorts an und verwenden Sie dann die Links, um bestimmte Benutzer, Office 365-Gruppen oder Websites ein- oder auszuschließen. 
  
Beachten Sie jedoch, dass die folgenden Grenzwerte für die Konfiguration von Aufbewahrungsrichtlinien gelten, die mehr als 1.000 bestimmte Speicherorte ein- oder ausschließen:
  
- Maximale Anzahl für die Aufbewahrungsrichtlinie:
    - 1.000 Postfächer
    - 1.000 Office 365-Gruppen
    - 1.000 Benutzer für private Teams-Chats
    - 100 Websites (OneDrive oder SharePoint)

- Ein Mandant darf nicht mehr als 10.000 Aufbewahrungsrichtlinien umfassen.
    
Obwohl diese Grenzwerte gelten, können Sie diese umgehen, indem Sie entweder eine organisationsübergreifende Richtlinie oder eine Richtlinie, die für ganze Speicherorte gilt, anwenden.
  
### <a name="skype-locations"></a>Skype-Speicherorte

Im Gegensatz zu Exchange-E-Mails kann der Status des Skype-Speicherorts nicht einfach aktiviert werden, um alle Benutzer einzuschließen. Wenn Sie diesen Speicherort jedoch aktivieren, können Sie anschließend manuell die Benutzer auswählen, deren Unterhaltungen Sie aufbewahren möchten:

![Auswählen des Skype-Speicherorts für Aufbewahrungsrichtlinien](../media/skype-location-retention-policies.png)
  
Bei Auswahl von **Benutzer auswählen** können Sie schnell alle Benutzer hinzufügen, indem Sie in der Spaltenüberschrift das Feld **Name** auswählen. Es ist jedoch wichtig zu wissen, dass jeder Benutzer als ein bestimmtes eingeschlossenes Element in der Richtlinie zählt. Wenn Sie also mehr als 1.000 Benutzer einschließen, gelten die im vorherigen Abschnitt angegebenen Grenzwerte. Wenn hier alle Skype-Benutzer ausgewählt werden, entspricht dies nicht dem standardmäßigen Einschließen aller Skype-Benutzer mithilfe einer organisationsübergreifenden Richtlinie. 
  
![Seite „Skype-Benutzer auswählen“](../media/f1742493-741a-4142-a564-d7d41ab0236a.png)
  
Beachten Sie, dass **Aufgezeichnete Unterhaltungen**, ein Ordner in Outlook, ein Feature ist, das nichts mit Skype-Archivierung zu tun hat. **Aufgezeichnete Unterhaltungen** kann vom Endbenutzer deaktiviert werden, Archivierung für Skype erfolgt jedoch durch das Speichern einer Kopie von Skype-Verbindungen in einem ausgeblendeten Ordner, auf den der Benutzer nicht zugreifen kann, der aber für eDiscovery verfügbar ist.

### <a name="sharepoint-locations"></a>SharePoint-Speicherorte

Ihre Aufbewahrungsrichtlinie kann Inhalte auf SharePoint-Kommunikationswebsites, auf Teamwebsites, die nicht über Office 365-Gruppen verbunden sind, und auf klassischen Websites beibehalten. Teamwebsites, die über Office 365-Gruppen verbunden sind, werden bei dieser Option nicht unterstützt. Verwenden Sie stattdessen die **Office 365-Gruppen**-Speicherorte.

Wenn Sie Websites angeben, die nicht unterstützt werden, werden diese von der Aufbewahrungsrichtlinie ignoriert.

Wenn Sie Ihre Speicherorte für SharePoint-Websites angeben, benötigen Sie keine Berechtigungen für den Zugriff auf die Website, und es erfolgt keine Validierung, wenn Sie die URL auf der Seite **Speicherorte bearbeiten** angeben. Die Websites müssen jedoch indiziert werden, und die von Ihnen angegebenen Websites werden vom Assistenten dahingehend überprüft, ob sie existieren.

Wenn die Überprüfung fehlschlägt, wird eine Meldung angezeigt, die besagt, dass die Überprüfung für die eingegebene URL fehlgeschlagen ist. Der Assistent erstellt die Aufbewahrungsrichtlinie erst, wenn die Überprüfung erfolgreich war. Wenn diese Meldung angezeigt wird, wechseln Sie zurück in den Assistenten, um die URL zu ändern oder die Website zu entfernen.

### <a name="teams-locations"></a>Team-Speicherorte

> [!NOTE]
> Die Konfiguration zur Aufbewahrung von Nachrichten auf privaten Kanälen wird noch nicht unterstützt. Die Aufbewahrung von Dateien, die in privaten Kanälen freigegeben sind, wird unterstützt.

Sie können eine Aufbewahrungsrichtlinie nutzen, um Chats und Kanalnachrichten in Teams aufzubewahren. Teams-Chats sind in einem ausgeblendeten Ordner im Postfach jedes Benutzers im Chat enthalten, und Teams-Kanalnachrichten werden in einem ähnlichen ausgeblendeten Ordner im Gruppenpostfach des Teams gespeichert. Es ist jedoch wichtig zu wissen, dass Teams einen von Azure unterstützten Chat-Dienst nutzt, der diese Daten ebenfalls speichert, und dieser Dienst speichert die Daten standardmäßig auf unbestimmte Zeit. Aus diesem Grund wird dringend empfohlen, dass Sie den Teams-Speicherort nutzen, um Teams-Daten aufzubewahren und zu löschen. Durch die Nutzung des Teams-Speicherorts werden Daten aus den Exchange-Postfächern und dem zugrunde liegenden von Azure unterstützten Chat-Dienst endgültig gelöscht. Weitere Informationen finden Sie unter [Übersicht über Sicherheit und Compliance in Microsoft Teams](https://go.microsoft.com/fwlink/?linkid=871258).
  
Aufbewahrungsrichtlinien, die auf Benutzer- oder Gruppenpostfächer in den Speicherorten von Exchange oder Office 365-Gruppen angewendet wurden, wirken sich nicht auf Microsoft Teams-Chats und -Kanalnachrichten aus. Auch wenn Microsoft Teams-Chats und -Kanalnachrichten in Exchange gespeichert werden, sind sie nur von Aufbewahrungsrichtlinien betroffen, die auf den Teams-Speicherort angewendet werden.

> [!NOTE]
> Wenn eine aktive Aufbewahrungsrichtlinie, durch die Teams-Daten aufbewahrt werden, Benutzer einbezieht, und Sie ein Postfach eines in diese Richtlinie einbezogenen Benutzers löschen, wird das Postfach in ein [inaktives Postfach](inactive-mailboxes-in-office-365.md) konvertiert, damit die Daten aufbewahrt werden. Wenn die Daten für den Benutzer nicht aufbewahrt werden müssen, schließen Sie den Benutzer aus der Aufbewahrungsrichtlinie aus, bevor Sie sein Postfach löschen.
  
Nachdem einem Team eine Aufbewahrungsrichtlinie zugewiesen wurde, können Chat- und Kanalnachrichten einem von zwei Pfaden folgen:

![Diagramm des Aufbewahrungsflusses für Microsoft Teams-Chat- und Kanalnachrichten](../media/TeamsRetentionLifecycle.png)

1. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums vom Benutzer geändert oder gelöscht wird**, wird die Nachricht in den Ordner "SubstrateHolds" (ein ausgeblendeter Ordner in jedem Benutzer- oder Gruppenpostfach) verschoben bzw. bei Änderungen kopiert und bis zum Ablauf des Aufbewahrungszeitraums dort gespeichert. Nachrichten werden am Tag des Ablaufs des Aufbewahrungszeitraums dauerhaft gelöscht.

2. **Wenn eine Chat- oder Kanalnachricht während des Aufbewahrungszeitraums nicht gelöscht wird**, wird die Nachricht innerhalb eines Tages nach Ablauf des Aufbewahrungszeitraums in den Ordner "SubstrateHolds" verschoben (dies erfolgt innerhalb 0 bis 24 Stunden). Die Nachricht wird einen Tag, nachdem sie in den Ordner "SubstrateHolds" verschoben wurde, dauerhaft gelöscht. 

> [!NOTE]
> Nachrichten im Ordner "SubstrateHolds" können mit eDiscovery-Tools durchsucht werden. Nachdem eine Nachricht dauerhaft gelöscht wurde, wird sie nicht mehr in eDiscovery-Suchen zurückgegeben.

Wir arbeiten kontinuierlich an der Optimierung der Aufbewahrungsfunktionen in Microsoft Teams und planen, in den kommenden Monaten neue Features bereitzustellen. In der Zwischenzeit gibt es einige Beschränkungen, die Sie beachten müssen:
  
- **Microsoft Teams erfordern eine separate Aufbewahrungsrichtlinie**. Wenn Sie eine Aufbewahrungsrichtlinie erstellen und den Teams-Speicherort aktivieren, werden alle anderen Speicherorte deaktiviert. Eine Aufbewahrungsrichtlinie, die Microsoft Teams umfasst, darf nur Teams und keine anderen Speicherorte betreffen. 
    
- **Microsoft Teams ist nicht in einer organisationsweiten Richtlinie eingeschlossen**. Wenn Sie eine organisationsweite Richtlinie erstellen, ist Microsoft Teams nicht eingeschlossen, da es eine separate Aufbewahrungsrichtlinie erfordert. 
    
- **Microsoft Teams unterstützt nicht die erweiterte Archivierung**. Wenn Sie eine Aufbewahrungsrichtlinie erstellen und die [Erweiterten Einstellungen auswählen, nach denen eine Richtlinie nur auf Inhalte angewendet wird, die bestimmten Kriterien entsprechen](#advanced-settings-that-apply-a-policy-only-to-content-that-meets-certain-conditions), ist der Teams-Speicherort nicht verfügbar. Derzeit betrifft die Aufbewahrung in Microsoft Teams alle Chat- und Kanalnachrichteninhalte. 

- **Microsoft Teams-Inhalte in privaten Kanälen werden nicht unterstützt**. Zu diesem Zeitpunkt gelten für Microsoft Teams erstellte Aufbewahrungsrichtlinien nicht für Nachrichten in privaten Kanälen. Nur Nachrichten in Standardkanälen unterliegen einer für Microsoft Teams erstellten Aufbewahrungsrichtlinie. Die Unterstützung von Aufbewahrungsrichtlinien für private Kanäle wird in Kürze verfügbar sein. 
    
- **Es kann bis zu drei Tage dauern, bis abgelaufene Nachrichten in Microsoft Teams gelöscht sind**. Eine auf Microsoft Teams angewendete Aufbewahrungsrichtlinie löscht Chat- und Kanalnachrichten, wenn der entsprechende Aufbewahrungszeitraum abgelaufen ist. Es kann jedoch bis zu drei Tage dauern, bis diese Nachrichten bereinigt und dauerhaft gelöscht sind. Außerdem können Chat- und Kanalnachrichten mit eDiscovery-Tools nach Ablauf des Aufbewahrungszeitraums und nach deren dauerhafter Löschung durchsucht werden.

   > [!NOTE]
   > Es stimmte zwar, dass eine Aufbewahrungsrichtlinie keine Microsoft Teams-Inhalte löschen konnte, die weniger als 30 Tage alt waren, wir haben diese Einschränkung jedoch aufgehoben. Jetzt kann der Aufbewahrungszeitraum für Microsoft Teams-Inhalte eine beliebige Anzahl von Tagen umfassen, auch nur einen einzigen Tag. Bei einem Aufbewahrungszeitraum von nur einem Tag dauert es bis zu drei Tage nach Ablauf dieses Zeitraums, bevor Nachrichten endgültig gelöscht werden.
    
In Teams werden in einem Chat freigegebene Dateien im OneDrive-Konto des Benutzers gespeichert, der sie freigegeben hat. In Kanäle hochgeladene Dateien werden auf der SharePoint-Website für das Team gespeichert. Wenn Sie also Dateien in Teams aufbewahren oder löschen möchten, müssen Sie eine Aufbewahrungsrichtlinie erstellen, die auf die OneDrive- und Microsoft 365-Gruppenspeicherorte angewendet wird. Wenn Sie eine Richtlinie in Teams nur auf die freigegebenen Dateien eines bestimmten Benutzers oder Teams anwenden möchten, können Sie die OneDrive- oder Microsoft 365-Gruppenspeicherorte auswählen und den gewünschten Benutzer oder das gewünschte Team einbeziehen.
  
Eine Aufbewahrungsrichtlinie, die für Teams gilt, kann die [Erhaltungssperre](#locking-a-retention-policy) nutzen.
  
![Teams-Speicherorte für Chat- und Kanalnachrichten](../media/127345da-e802-4b3a-afc7-6e354dc3f409.png)
  
> [!NOTE]
> Wenn Sie Aufbewahrungsrichtlinien für Skype- oder Microsoft Teams-Speicherorte in Ihrer Organisation erstellen, wird eine dieser Richtlinien als Standard-Ordnerrichtlinie angezeigt, wenn ein Benutzer die Eigenschaften eines Postfachordners im Outlook Desktop-Client einsieht. Hierbei handelt es sich um ein Anzeigeproblem in Outlook und [ein bekanntes Problem](https://support.microsoft.com/help/4491013/outlook-client-displays-teams-or-skype-for-business-retention-policies). Als Standard-Ordnerrichtlinie sollte die Aufbewahrungsrichtlinie für Postfächer, die für den Ordner gilt, angezeigt werden. Die Aufbewahrungsrichtlinie für Skype oder Microsoft Teams wird nicht auf das Postfach des Benutzers angewendet.  

### <a name="microsoft-365-groups-locations"></a>Microsoft 365-Gruppenspeicherorte

Wenn Sie Inhalte für eine Microsoft 365-Gruppe aufbewahren möchten, müssen Sie den Microsoft 365-Gruppenspeicherort verwenden. Obwohl eine Microsoft 365-Gruppe über ein Exchange-Postfach verfügt, bezieht eine Aufbewahrungsrichtlinie, die den gesamten Exchange-Speicherort umfasst, keine Inhalte in Microsoft 365-Gruppenpostfächern mit ein. Eine auf eine Microsoft 365-Gruppe angewendete Aufbewahrungsrichtlinie umfasst sowohl das Gruppenpostfach als auch die Website. Eine auf eine Microsoft 365-Gruppe angewendete Aufbewahrungsrichtlinie schützt die Ressourcen, die von einer Microsoft 365-Gruppe erstellt wurden. Dazu gehört ggf. auch Microsoft Teams.

Außerdem ist es nicht möglich, den Exchange-Speicherort für den Ein- oder Ausschluss eines bestimmten Gruppenpostfachs zu verwenden. Obwohl der Exchange-Speicherort zunächst die Auswahl eines Gruppenpostfachs zulässt, erhalten Sie beim Versuch, die Aufbewahrungsrichtlinie zu speichern, die Fehlermeldung, dass "RemoteGroupMailbox" keine gültige Auswahl für den Exchange-Speicherort ist. 

## <a name="excluding-specific-types-of-exchange-items-from-a-retention-policy"></a>Ausschließen von bestimmten Typen von Exchange-Elementen aus einer Aufbewahrungsrichtlinie
Indem Sie PowerShell verwenden, können Sie bestimmte Typen von Exchange-Elementen aus einer Aufbewahrungsrichtlinie ausschließen. Sie können z. B. Sprachnachrichten, Chatnachrichten und andere Skype for Business Online-Inhalte in Postfächern ausschließen. Sie können auch Kalender-, Notiz- und Aufgabenelemente ausschließen. Diese Funktion ist nur mit PowerShell verfügbar. Es ist nicht auf der Benutzeroberfläche verfügbar, wenn Sie eine Aufbewahrungsrichtlinie erstellen.
  
Verwenden Sie dazu den Parameter `ExcludedItemClasses` der Cmdlets `New-RetentionComplianceRule` und `Set-RetentionComplianceRule`.

## <a name="locking-a-retention-policy"></a>Sperren einer Aufbewahrungsrichtlinie
Einige Organisationen müssen Regeln einhalten, die von Behörden definiert werden, wie zum Beispiel die Rule 17a-4 der Securities And Exchange Commission (SEC), die erfordert, dass eine Aufbewahrungsrichtlinie nach dem Aktivieren nicht deaktiviert oder weniger restriktiv eingestellt werden kann. Mit der Aufbewahrungssperre können Sie die Richtlinie sperren, sodass niemand – auch nicht der Administrator – die Richtlinie deaktivieren oder weniger restriktiv einstellen kann.
  
Nach dem Sperren einer Richtlinie kann sie von niemandem deaktiviert werden. Außerdem können keine Speicherorte aus der Richtlinie entfernt werden. Darüber hinaus ist es nicht möglich, Inhalte zu ändern oder zu löschen, die während des Aufbewahrungszeitraums der Richtlinie unterliegen. Nach dem Sperren der Richtlinie können Sie die Richtlinie nur ändern, indem Sie Inhalte hinzufügen oder die Dauer verlängern. Eine gesperrte Richtlinie kann vergrößert oder verlängert werden kann, kann jedoch nicht verkleinert oder deaktiviert werden.
  
Aus diesem Grund müssen Sie sich vor der Sperrung einer Aufbewahrungsrichtlinie **unbedingt** einen genauen Überblick über die Compliance-Anforderungen Ihrer Organisation verschaffen. Sie **dürfen eine Richtlinie auf keinen Fall sperren**, bevor Sie sich absolut sicher sind, dass dies notwendig ist.

### <a name="lock-a-retention-policy-by-using-powershell"></a>Sperren einer Aufbewahrungsrichtlinie mit PowerShell
  
Sie können eine Aufbewahrungsrichtlinie nur mithilfe von PowerShell sperren.

Stellen Sie [zunächst eine Verbindung mit Office 365 Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

Führen Sie dann zum Anzeigen einer Liste von Aufbewahrungsrichtlinien und Suchen nach dem Namen der Richtlinie, die Sie sperren möchten, den Befehl `Get-RetentionCompliancePolicy` aus.

![Liste der Aufbewahrungsrichtlinien in PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

Um eine Aufbewahrungssperre zu einer Aufbewahrungsrichtlinie hinzuzufügen, führen Sie den Befehl `Set-RetentionCompliancePolicy` aus, und legen Sie dabei den `RestrictiveRetention`-Parameter auf „true“ fest. Zum Beispiel:

`Set-RetentionCompliancePolicy -Identity "<Name of Policy>" – RestrictiveRetention $true`

![RestrictiveRetention-Parameter in PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)

Nachdem Sie das Cmdlet ausgeführt haben, werden Sie zur Bestätigung aufgefordert. Wählen Sie **Ja für alle** aus.

![Aufforderung zur Bestätigung der Sperre einer Aufbewahrungsrichtlinie in PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

Eine Aufbewahrungssperre wird jetzt zur Aufbewahrungsrichtlinie hinzugefügt. Wenn Sie `Get-RetentionCompliancePolicy`ausführen, legen Sie den Parameter `RestrictiveRetention`auf "true" fest. Zum Beispiel:

`Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl`

![Gesperrte Richtlinie mit allen Parametern in PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)
  
## <a name="releasing-a-retention-policy"></a>Aufheben einer Aufbewahrungsrichtlinie

Sie können eine Aufbewahrungsrichtlinie jederzeit deaktivieren oder löschen. In diesem Fall werden bis dahin im permanentes Dokumentarchiv aufbewahrte SharePoint- oder OneDrive-Inhalte nicht sofort und dauerhaft gelöscht. Um versehentlichem Datenverlust vorzubeugen, gibt es nun eine Nachfrist von 30 Tagen, während der der Inhaltsablauf für diese Richtlinie im permanenten Dokumentarchiv nicht eintritt, sodass Sie Inhalte ggf. wiederherstellen können. Sie können die Aufbewahrungsrichtlinie auch während der Nachfrist erneut aktivieren. In diesem Fall werden keine in Zusammenhang mit dieser Richtlinie stehenden Inhalte gelöscht.

Diese 30-tägige Nachfrist in SharePoint und OneDrive entspricht dem 30-tägigen Anhalten der Aufbewahrungszeit in Exchange. Weitere Informationen finden Sie unter [Verwalten von Postfächern mit angehaltener Aufbewahrungszeit](identify-a-hold-on-an-exchange-online-mailbox.md#managing-mailboxes-on-delay-hold).

## <a name="the-principles-of-retention-or-what-takes-precedence"></a>Die Grundsätze der Aufbewahrung, oder was hat Vorrang?

Es ist möglich oder sogar wahrscheinlich, dass auf Inhalte mehrere Aufbewahrungsrichtlinien angewendet werden, die jeweils mit einer anderen Aktion (aufbewahren, löschen oder beides) und einem anderen Aufbewahrungszeitraum verbunden sind. Was hat Vorrang? Ganz allgemein sei gesagt, dass Sie sich sicher sein können, dass Inhalte, die aufgrund einer Richtlinie aufbewahrt werden müssen, nicht von einer anderen Richtlinie dauerhaft gelöscht werden können.
  
![Diagramm der Grundsätze der Aufbewahrung](../media/1693d6ec-b340-4805-9da3-89aa41bc6afb.png)
  
Um zu verstehen, wie verschiedene Aufbewahrungsrichtlinien auf Inhalte angewendet werden, sollten Sie diese Grundsätze der Aufbewahrung beachten:
  
1. **Aufbewahrung hat Vorrang vor Löschen.** Nehmen wir einmal an, eine Aufbewahrungsrichtlinie gibt an, dass Exchange-E-Mails nach drei Jahren gelöscht werden sollen, und eine andere Aufbewahrungsrichtlinie gibt an, dass Exchange-E-Mails fünf Jahre aufbewahrt und dann gelöscht werden sollen. Alle Inhalte werden, sobald sie drei Jahre alt sind, gelöscht und für den Benutzer ausgeblendet, aber immer noch im Ordner "Wiederherstellbare Elemente" aufbewahrt, bis der Inhalt fünf Jahre alt ist, und dann dauerhaft gelöscht. 
    
2. **Der längste Aufbewahrungszeitraum hat Vorrang.** Wenn Inhalte mehreren Aufbewahrungsrichtlinien unterliegen, bleiben diese bis zum Ende des längsten Aufbewahrungszeitraums erhalten. 
    
3. **Explizite Einbindung hat Vorrang vor impliziter Einbindung.** Das bedeutet Folgendes: 
    
    1. Wenn eine Bezeichnung mit Einstellungen für die Aufbewahrung von einem Benutzer manuell einem Element, z. B. einer Exchange-E-Mail oder einem OneDrive-Dokument, zugewiesen wird, hat diese Bezeichnung sowohl Vorrang vor einer Richtlinie, die auf Website- oder Postfachebene zugewiesen wurde, als auch vor einer Standardbezeichnung, die von der Dokumentbibliothek zugewiesen wurde. Wenn beispielsweise die explizite Bezeichnung eine Aufbewahrung über zehn Jahre angibt, die der Website zugewiesene Richtlinie jedoch eine Aufbewahrung über nur fünf Jahre angibt, hat die Bezeichnung Vorrang. Automatisch zugewiesene Bezeichnungen werden als implizit (und nicht explizit) angesehen, weil sie von Microsoft 365 automatisch angewendet werden.
    
    2. Wenn eine Aufbewahrungsrichtlinie einen bestimmten Speicherort wie das Postfach oder OneDrive for Business-Konto eines bestimmten Benutzers umfasst, hat diese Richtlinie Vorrang vor einer anderen Aufbewahrungsrichtlinie, die für alle Postfächer oder OneDrive for Business-Konten von Benutzern gilt, aber nicht das Postfach dieses Benutzers speziell einschließt.
    
4. **Der kürzeste Löschzeitraum hat Vorrang. ** Ebenso gilt, dass wenn Inhalte mehreren Aufbewahrungsrichtlinien zur Löschung (ohne Aufbewahrung) unterliegen, sie am Ende des kürzesten Aufbewahrungszeitraums gelöscht werden. 
    
Beachten Sie: Wenn die Regeln, die von allen Richtlinien oder Kennzeichnungen angewendet werden, auf einer Ebene identisch sind, bewegt sich der Fluss nach unten zur nächsten Ebene, wo entschieden wird, welche Regel Vorrang hat.
  
Schließlich kann keine Aufbewahrungsrichtlinie oder Kennzeichnung einen Inhalt dauerhaft löschen, der für eDiscovery gesperrt ist. Wenn die Sperre aufgehoben wird, kommt der Inhalt wieder für den oben beschriebenen Bereinigungsprozess infrage.
  
## <a name="use-a-retention-policy-instead-of-these-features"></a>Verwenden einer Aufbewahrungsrichtlinie anstelle dieser Features

Eine einzelne Aufbewahrungsrichtlinie kann problemlos auf eine ganze Organisation und Speicherorte in Microsoft 365 angewendet werden. Dazu gehören Exchange Online, SharePoint Online, OneDrive for Business und Microsoft 365-Gruppen. Wenn Sie Inhalte an einer beliebigen Stelle in Microsoft 365 aufbewahren oder löschen müssen, empfiehlt sich die Verwendung einer Aufbewahrungsrichtlinie. (Sie können auch Bezeichnungen mit Aufbewahrungseinstellungen verwenden. Weitere Informationen finden Sie unter [Übersicht über Bezeichnungen](labels.md).)
  
Es gibt mehrere andere Features, die zuvor zum Aufbewahren oder Löschen von Inhalten in Microsoft 365 verwendet wurden. Diese sind nachfolgend aufgeführt. Diese Features funktionieren weiterhin Seite an Seite mit Aufbewahrungsrichtlinien und -bezeichnungen. Auf lange Sicht wird im Hinblick auf Informationsgovernance jedoch empfohlen, eine Aufbewahrungsrichtlinie oder Bezeichnungen anstelle dieser Features zu verwenden. Eine Aufbewahrungsrichtlinie ist das einzige Feature, mit dem Inhalte in Microsoft 365 übergreifend sowohl aufbewahrt als auch gelöscht werden können.
  
### <a name="exchange-online"></a>Exchange Online

- [Verwalten von eDiscovery-Fällen im Security &amp; Compliance Center](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery-Sperre) 
    
- [In-Situ-Speicher und Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=846124) (eDiscovery-Sperre) 

- [Identifizieren des Haltebereichs für ein Exchange Online-Postfach](identify-a-hold-on-an-exchange-online-mailbox.md)
    
- [Aufbewahrungstags und Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/?linkid=846125), auch bekannt als [Messaging-Datensatzverwaltung](https://go.microsoft.com/fwlink/?linkid=846126) (Nur Löschen) 
    
### <a name="sharepoint-online-and-onedrive-for-business"></a>SharePoint Online und OneDrive for Business

- [Verwalten von eDiscovery-Fällen im Security &amp; Compliance Center](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) (eDiscovery-Sperre) 
    
- [Hinzufügen von Inhalten zu einem Fall und temporäres Sperren von Quellen im eDiscovery Center](https://support.office.com/article/54d70de9-1ec2-4325-84f3-aeb588554479) (eDiscovery-Sperre) 
    
- [Übersicht über Dokumentlöschrichtlinien](https://support.office.com/article/55e8d858-f278-482b-a198-2e62d6a2e6e5) (Nur Löschen) 
    
- [Konfiguration von Datensatzverwaltung in situ](https://support.office.com/article/7707a878-780c-4be6-9cb0-9718ecde050a) (Aufbewahrung) 
    
- [Verwenden von Richtlinien für das Schließen und Löschen von Websites](https://support.office.com/article/a8280d82-27fd-48c5-9adf-8a5431208ba5) (Nur Löschen) 
    
- [Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md) (Nur Löschen) 
    
Wenn Sie bisher eines der eDiscovery-Archive zum Zwecke der Informationsgovernance verwendet haben, sollten Sie stattdessen eine Aufbewahrungsrichtlinie für proaktive Compliance verwenden. Verwenden Sie einen Haltebereich nur für eDiscovery.
  
### <a name="retention-policies-override-information-management-policies"></a>Aufbewahrungsrichtlinien setzen Informationsverwaltungsrichtlinien außer Kraft

In SharePoint-Websites verwenden Sie für die Aufbewahrung von Inhalten möglicherweise [Informationsverwaltungsrichtlinien](intro-to-info-mgmt-policies.md). Wenn Sie eine Aufbewahrungsrichtlinie auf eine Website anwenden, die für eine Liste oder Bibliothek bereits Inhaltstyp- oder Informationsverwaltungsrichtlinien verwendet, werden diese Richtlinien ignoriert, während die Aufbewahrungsrichtlinie angewendet wird. 
  
## <a name="what-happened-to-preservation-policies"></a>Was ist aus den Erhaltungsrichtlinien geworden?

Wenn Sie bisher eine Erhaltungsrichtlinie verwendet haben, wurde diese Richtlinie automatisch in eine Aufbewahrungsrichtlinie umgewandelt, bei der nur die Aufbewahrungsaktion verwendet wird – mit der Richtlinie werden keine Inhalte gelöscht. Die Erhaltungsrichtlinie funktioniert weiterhin und erhält Ihre Inhalte, ohne dass Sie Änderungen vornehmen müssen. Sie finden diese Richtlinien auf der Seite **Richtlinien** im [Microsoft 365 Compliance Center](https://compliance.microsoft.com/) oder auf der Seite **Aufbewahrung** unter **Informationsgovernance** im [Security&amp; Compliance Center](https://protection.office.com/). Sie können eine Erhaltungsrichtlinie bearbeiten, um den Aufbewahrungszeitraum zu ändern, jedoch keine anderen Änderungen vornehmen, z. B. keine Speicherorte hinzufügen oder entfernen. 

## <a name="find-the-powershell-cmdlets-for-retention-policies"></a>Die PowerShell-Cmdlets für Aufbewahrungsrichtlinien finden

So verwenden Sie die Cmdlets für Aufbewahrungsrichtlinien
  
1. [Stellen Sie eine Verbindung mit der Security & Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).
    
2. Verwenden Sie die folgenden Security & Compliance Center-Cmdlets:
    
    - [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancepolicy)
    
    - [New-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancepolicy)
    
    - [Remove-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancepolicy)
    
    - [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancepolicy)
    
    - [Get-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/get-retentioncompliancerule)
    
    - [New-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/new-retentioncompliancerule)
    
    - [Remove-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/remove-retentioncompliancerule)
    
    - [Set-RetentionComplianceRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-retention/set-retentioncompliancerule)

## <a name="permissions"></a>Berechtigungen

Die Mitglieder Ihres Complianceteams, die Aufbewahrungsrichtlinien erstellen sollen, benötigen Berechtigungen für das [Security&amp; Compliance Center](https://protection.office.com/). Standardmäßig hat Ihr Mandantenadministrator Zugriff auf diesen Speicherort und kann anderen Personen den Zugriff auf das [Security &amp; Compliance Center](https://protection.office.com/) gewähren, ohne ihnen alle Berechtigungen eines Mandantenadministrators zu geben. Zu diesem Zweck wird empfohlen, dass Sie zur Seite **Berechtigungen** des [Security &amp; Compliance Centers](https://protection.office.com/) gehen, die Rollengruppe **Compliance-Administrator** bearbeiten und dieser Rollengruppe Mitglieder hinzufügen. 
  
Weitere Informationen finden Sie unter [Gewähren des Zugriffs auf das Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center). 

Diese Berechtigungen sind nur erforderlich, um eine Aufbewahrungsrichtlinie zu erstellen und anzuwenden. Für die Richtlinienerzwingung ist kein Zugriff auf den Inhalt erforderlich.

## <a name="more-information"></a>Weitere Informationen

- [Aufbewahrungsrichtlinien in Microsoft Teams](/microsoftteams/retention-policies#using-powershell )
- [Übersicht über Bezeichnungen](labels.md)
- [SharePoint Online-Beschränkungen](https://docs.microsoft.com/office365/servicedescriptions/sharepoint-online-service-description/sharepoint-online-limits)
- [Limits und Spezifikationen für Microsoft Teams](https://docs.microsoft.com/microsoftteams/limits-specifications-teams) 
    