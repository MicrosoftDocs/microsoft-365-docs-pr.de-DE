---
title: Informationen zur Aufbewahrung für SharePoint und OneDrive
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
description: Informationen, wie die Aufbewahrung für SharePoint und OneDrive funktioniert.
ms.openlocfilehash: 448f3e8e2ab827527b02263fea2b07de4b345dc1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919771"
---
# <a name="learn-about-retention-for-sharepoint-and-onedrive"></a>Informationen zur Aufbewahrung für SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zur Aufbewahrung](retention.md) um spezifische Angaben für SharePoint und OneDrive.

Informationen zu anderen Arbeitsbereichen finden Sie unter:

- [Informationen zur Aufbewahrung für Microsoft Teams](retention-policies-teams.md)
- [Informationen zur Aufbewahrung für Yammer](retention-policies-yammer.md)
- [Informationen zur Aufbewahrung für Exchange](retention-policies-exchange.md)

## <a name="whats-included-for-retention-and-deletion"></a>Lieferumfang für Aufbewahrung und Löschung

Alle Dateien, die auf SharePoint oder OneDrive-Websites gespeichert sind, können aufbewahrt werden, indem eine Aufbewahrungsrichtlinie oder Aufbewahrungsbezeichnung angewendet wird. 

Die folgenden Dateien können gelöscht werden:

- Wenn Sie eine Aufbewahrungsrichtlinie verwenden: Alle Dateien in Dokumentbibliotheken, inklusive automatisch erstellte SharePoint-Dokumentbibliotheken wie z. B. **Website-Objekte**.
    
- Wenn Sie Aufbewahrungsbezeichnungen verwenden: Alle Dateien in allen Dokumentbibliotheken und alle Dateien im Stammverzeichnis, die sich nicht in einem Ordner befinden.
    
> [!TIP]
> Wenn Sie eine [Abfrage mit einer Richtlinie für die automatische Anwendung einer Aufbewahrungsbezeichnung](apply-retention-labels-automatically.md#auto-apply-labels-to-content-with-keywords-or-searchable-properties) verwenden, können Sie Dokumentbibliotheken mithilfe des folgenden Eintrags ausschließen: `NOT(DocumentLink:"<URL to document library>")`

Listenelemente werden von Aufbewahrungsbezeichnungen, nicht aber von Aufbewahrungsrichtlinien unterstützt, mit Ausnahme von Elementen in Systemlisten. Dies sind von SharePoint verwendete ausgeblendete Listen zum Verwalten des Systems und zum Einschließen des Gestaltungsvorlagenkatalogs, des Lösungskatalogs und der Datenquellen. Wenn Sie eine Aufbewahrungsbezeichnung auf ein unterstütztes Listenelement mit einem Dokumentanhang anwenden:
- Für eine Standard-Aufbewahrungsbezeichnung (deklariert das Element nicht als Datensatz):
    - Der Dokumentanhang erbt nicht automatisch die Aufbewahrungseinstellungen der Bezeichnung, sondern kann unabhängig davon bezeichnet werden.
- Für eine Aufbewahrungsbezeichnung, die das Element als Datensatz deklariert: 
    - Der Dokumentanhang erbt automatisch die Aufbewahrungseinstellungen der Bezeichnung, sondern das Dokument nicht bereits bezeichnet ist.

Aufbewahrungseinstellungen aus Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen gelten nicht für Organisationsstrukturen, die Bibliotheken, Listen und Ordner umfassen.

Aufbewahrungsrichtlinien und Bezeichnungsrichtlinien für die automatische Anwendung: SharePoint-Websites müssen indiziert sein, damit die Aufbewahrungseinstellungen angewendet werden können. Wenn Elemente in SharePoint-Dokumentbibliotheken jedoch so konfiguriert sind, dass sie nicht in den Suchergebnissen angezeigt werden, schließt diese Konfiguration keine Dateien aus den Aufbewahrungseinstellungen aus.

## <a name="how-retention-works-for-sharepoint-and-onedrive"></a>Wie die Aufbewahrung für SharePoint und OneDrive funktioniert

Um Inhalte zu speichern, die aufbewahrt werden müssen, erstellen SharePoint und OneDrive ein permanentes Dokumentarchiv, falls noch nicht vorhanden. Sie können diese Bibliothek auf der Seite **Websiteinhalte** der Website auf oberster Ebene der Websitesammlung anzeigen. Die meisten Benutzer können das permanente Dokumentarchiv nicht anzeigen, da es nur für Websitesammlungsadministratoren sichtbar ist.

Elemente in SharePoint, die eine Standard-Aufbewahrungsbezeichnung haben (die das Element nicht als Datensatz deklariert), benötigen das permanente Dokumentarchiv nicht, da diese Elemente an ihrem ursprünglichen Speicherort verbleiben. SharePoint verhindert, dass Benutzer Elemente löschen, wenn die angewandte Aufbewahrungsbezeichnung so konfiguriert ist, dass der Inhalt beibehalten wird. Die SharePoint-Versionierung bewahrt ältere Versionen, wenn Elemente bearbeitet werden. Für andere Szenarien wird jedoch das permanente Dokumentarchiv verwendet, wenn Elemente aufbewahrt werden müssen:
- Elemente in OneDrive mit standardmäßigen Aufbewahrungsbezeichnungen
- Elemente in SharePoint oder OneDrive, die Aufbewahrungbezeichnungen haben, die sie zu einem Datensatz erklären, und das Element ist für die Bearbeitung freigeschaltet
- Elemente, für die Aufbewahrungsrichtlinien gelten

Um diesen Inhalt zu bewahren, wenn ein Benutzer versucht, ihn zu ändern oder zu löschen, wird überprüft, ob der Inhalt geändert wurde, seit die Aufbewahrungseinstellungen angewendet wurden. Wenn dies die erste Änderung seit Anwendung der Aufbewahrungseinstellungen ist, wird der Inhalt in das permanente Dokumentarchiv kopiert. Dies ermöglicht dem Benutzer das Ändern oder Löschen des ursprünglichen Inhalts. Jeder Inhalt in einer Websitesammlung kann unabhängig von den Aufbewahrungseinstellungen in das permanente Dokumentenarchiv kopiert werden.
  
Ein Zeitgeberauftrag bereinigt in regelmäßigen Abständen das permanente Dokumentarchiv. Inhalte, die sich seit mehr als 30 Tagen im permanenten Dokumentarchiv befinden, werden mit allen von den Aufbewahrungseinstellungen für diese Inhalte verwendeten Abfragen verglichen. Inhalte, die älter als die darin konfigurierte Aufbewahrungszeit sind, werden dann aus dem permanenten Dokumentarchiv sowie vom ursprünglichen Speicherort gelöscht, sofern sie dort noch vorhanden sind. Dieser Zeitgeberauftrag wird alle sieben Tage ausgeführt, was bedeutet, dass es zusammen mit den mindestens 30 Tagen bis zu 37 Tage dauern kann, bis Inhalte aus dem permanenten Dokumentarchiv gelöscht werden.

Während Dateien im permanenten Dokumentarchiv gespeichert werden, können Administratoren die SharePoint-Site oder das OneDrive-Konto des Inhalts nicht löschen.

Dieses Verhalten beim Kopieren von Dateien in das permanente Dokumentenarchiv gilt für Inhalte, die zum Zeitpunkt der Anwendung der Aufbewahrungseinstellungen vorhanden waren. Darüber hinaus werden für Aufbewahrungsrichtlinien alle neuen Inhalte, die nach dem Einfügen in die Richtlinie erstellt oder zur Site hinzugefügt wurden, in dem permanenten Dokumentenarchiv beibehalten. Neue Inhalte werden jedoch nicht bei der ersten Bearbeitung in das permanente Dokumentarchiv kopiert, sondern nur, wenn sie gelöscht werden. Wenn Sie alle Versionen einer Datei aufbewahren möchten, müssen Sie die [Versionsverwaltung](#how-retention-works-with-document-versions) aktivieren.
  
Benutzer sehen eine Fehlermeldung, wenn sie versuchen, eine Bibliothek, eine Liste, einen Ordner oder eine Website zu löschen, die der Aufbewahrungspflicht unterliegen. Sie können einen Ordner löschen, wenn sie zuerst alle aufbewahrungspflichtigen Dateien im Ordner verschieben oder löschen.

> [!NOTE]
> Da das permanente Dokumentarchiv nur erstellt wird, wenn es benötigt wird, und nicht, wenn Sie eine Aufbewahrungsrichtlinie oder eine Aufbewahrungsbezeichnung anwenden, müssen Sie zunächst ein Element, das der Aufbewahrungspflicht unterliegt, bearbeiten oder löschen, damit dies funktioniert. Wechseln Sie dann zum permanenten Dokumentarchiv, um die aufbewahrte Kopie anzuzeigen.
  
Nachdem auf Inhalte in einem OneDrive-Konto oder einer SharePoint-Site Aufbewahrungseinstellungen angewendet wurden, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungseinstellungen der Aufbewahrung und dem Löschen, der reinen Aufbewahrung oder dem reinen Löschen dienen.

Wenn die Aufbewahrungseinstellungen das Aufbewahren und Löschen vorgeben:

![Diagramm des Inhaltslebenszyklus in SharePoint und OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**, wird eine Kopie des ursprünglichen Inhalts in der beim Zuweisen der Aufbewahrungseinstellungen vorhandenen Form im permanenten Dokumentarchiv erstellt. Dort ermittelt der Zeitgeberauftrag Elemente, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden in den endgültigen Papierkorb verschoben, von wo sie nach Ablauf von 93 Tagen endgültig gelöscht werden. Der endgültige Papierkorb wird den Endbenutzern nicht angezeigt (sie sehen nur den Standardpapierkorb), Websitesammlungsadministratoren können hingegen dessen Inhalte anzeigen und wiederherstellen.

    > [!NOTE]
    > Um versehentlichem Datenverlust vorzubeugen, werden Inhalte nicht mehr dauerhaft aus dem permanenten Dokumentarchiv gelöscht. Stattdessen werden Inhalte nur aus dem Papierkorb dauerhaft gelöscht, sodass nun sämtliche Inhalte aus dem permanenten Dokumentarchiv den endgültigen Papierkorb durchlaufen werden.
    
2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**, wird er vom Zeitgeberauftrag am Ende des Aufbewahrungszeitraums in den Standardpapierkorb verschoben. Wenn ein Benutzer den Inhalt dort löscht oder diesen Papierkorb leert (auch als Aufräumen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen.

Wenn die Aufbewahrungseinstellungen das reine Aufbewahren oder das reine Löschen vorgeben, stellen die Inhaltspfade Varianten von "Aufbewahren und Löschen" dar:

### <a name="content-paths-for-retain-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reine Aufbewahrung

1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Dokuments wird im permanenten Dokumentarchiv erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im permanenten Dokumentarchiv in den endgültigen Papierkorb verschoben und nach 93 Tagen endgültig gelöscht wird.

2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Dokument verbleibt an seinem Ursprungsort.

### <a name="content-paths-for-delete-only-retention-settings"></a>Inhaltspfade für Aufbewahrungseinstellungen für reines Löschen

1. **Wenn der Inhalt während des festgelegten Zeitraums gelöscht wird**: Das Dokument wird in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert, wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Wenn der Inhalt während des festgelegten Zeitraums geändert wird, folgt er nach Ablauf dieses Zeitraums demselben Löschpfad.

2. **Wenn der Inhalt während des festgelegten Zeitraums nicht gelöscht wird**: Das Dokument wird am Ende des in der Aufbewahrungsrichtlinie festgelegten Zeitraums in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert (auch als Bereinigen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen.

## <a name="how-retention-works-for-onenote-content"></a>Funktionsweise einer Aufbewahrungsrichtlinie für OneNote-Inhalte

Wenn Sie eine Aufbewahrungsrichtlinie auf einen Speicherort anwenden, der OneNote-Inhalte beinhaltet, dann sind die unterschiedlichen OneNote-Abschnitte tatsächlich einzelne Dateien. Dies bedeutet, dass jeder Abschnitt entsprechend den von Ihnen festgelegten Aufbewahrungseinstellungen einzeln aufbewahrt oder gelöscht wird.

## <a name="how-retention-works-with-document-versions"></a>Funktionsweise der Aufbewahrung mit Dokumentversionen

Die Versionsverwaltung ist ein Feature aller Dokumentlisten und -bibliotheken in SharePoint und in OneDrive. Standardmäßig werden bei der Versionsverwaltung mindestens 500 Hauptversionen beibehalten, Sie können diese Beschränkung jedoch erhöhen. Weitere Informationen finden Sie unter [Aktivieren und Konfigurieren der Versionsverwaltung für eine Liste oder Bibliothek](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37) und [So funktioniert die Versionsverwaltung in Listen und Bibliotheken](https://support.microsoft.com/office/how-versioning-works-in-lists-and-libraries-0f6cd105-974f-44a4-aadb-43ac5bdfd247).
  
Wenn ein Dokument mit Versionen Aufbewahrungseinstellungen unterliegt, um den Inhalt beizubehalten, existieren Versionen, die in das permanente Dokumentarchiv kopiert werden, als separate Elemente. Wenn die Aufbewahrungseinstellungen so konfiguriert sind, dass sie am Ende des Aufbewahrungszeitraums gelöscht werden:

- Wenn der Aufbewahrungszeitraum darauf basiert, wann der Inhalt erstellt wurde, verfügt jede Version über das gleiche Ablaufdatum wie das ursprüngliche Dokument. Das ursprüngliche Dokument und dessen Versionen werden alle gleichzeitig ablaufen.

- Wenn der Aufbewahrungszeitraum darauf basiert, wann der Inhalt zuletzt geändert wurde, verfügt jede Version über ein eigenes Ablaufdatum basierend auf dem Zeitpunkt der Änderung des ursprünglichen Dokuments, aus der diese Version hervorgegangen ist. Das ursprüngliche Dokument und seine Versionen laufen unabhängig voneinander ab.

> [!NOTE]
> Die aufbewahrten Versionen dieser SharePoint- und OneDrive-Dokumente lassen sich nicht mithilfe von eDiscovery-Tools durchsuchen.

Wenn die Aufbewahrungsaktion das Dokument löschen soll, werden alle Versionen, die sich nicht im permanenten Dokumentarchiv befinden, gleichzeitig mit der aktuellen Version gelöscht.

Bei Elementen, die einer Aufbewahrungsrichtlinie (oder einer eDiscovery-Sperre) unterliegen, werden die Einschränkungen der Versionsverwaltung für die Dokumentbibliothek ignoriert, bis der Aufbewahrungszeitraum des Dokuments beendet ist (oder die eDiscovery-Sperre aufgehoben wird). In diesem Szenario werden alte Versionen nicht automatisch gelöscht und Benutzer können Versionen nicht löschen.

Das gilt nicht für Aufbewahrungsbezeichnungen, wenn der Inhalt keiner Aufbewahrungsrichtlinie (oder eDiscovery-Sperre) unterliegt. Stattdessen werden die Einschränkungen der Versionsverwaltung berücksichtigt, sodass ältere Versionen automatisch gelöscht und durch neuere Versionen ersetzt werden. Benutzer werden jedoch immer noch daran gehindert, Versionen zu löschen.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt

**SharePoint**:

Wenn ein Benutzer Ihre Organisation verlässt, sind Inhalte, die von ihm erstellt wurden, nicht betroffen, weil SharePoint als eine Zusammenarbeitsumgebung betrachtet wird, im Gegensatz zu dem Postfach oder dem OneDrive-Konto des Benutzers.

**OneDrive**:

Wenn ein Benutzer Ihre Organisation verlässt, bleiben alle Dateien, für die eine Aufbewahrungsrichtlinie gilt oder die Aufbewahrungsbezeichnungen aufweisen, für die Dauer der Richtlinie oder Bezeichnung erhalten. Während dieses Zeitraums bleibt der gesamte Freigabezugriff aufrecht. Nach Ablauf des Aufbewahrungszeitraums wird der Inhalt in den Papierkorb der Websitesammlung verschoben, wo er nur für den Administrator zugänglich sein wird. Wenn ein Dokument durch eine Aufbewahrungsbezeichnung als Eintrag gekennzeichnet ist, wird das Dokument erst gelöscht, wenn der Aufbewahrungszeitraum abgelaufen ist. Danach wird der Inhalt endgültig gelöscht.

## <a name="configuration-guidance"></a>Konfigurationsleitfaden

Wenn Sie die Konfiguration der Datenaufbewahrung in Microsoft 365 zum ersten Mal durchführen möchten, lesen Sie [Erste Schritte mit Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](get-started-with-retention.md).

Wenn Sie eine Aufbewahrungsrichtlinie oder Aufbewahrungsbezeichnung für Exchange konfigurieren möchten, lesen Sie die folgenden Anweisungen:
- [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md)
- [Erstellen von Aufbewahrungsbezeichnungen und Anwenden in Apps](create-apply-retention-labels.md)
- [Automatisches Anwenden einer Aufbewahrungsbezeichnung auf Inhalte](apply-retention-labels-automatically.md)