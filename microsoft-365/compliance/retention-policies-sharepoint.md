---
title: Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive
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
description: Informationen zu Aufbewahrungsrichtlinien, die für SharePoint und OneDrive gelten
ms.openlocfilehash: e7a265d39b3cca2ffb9c403cf2c87f287a9325b2
ms.sourcegitcommit: 0650da0e54a2b484a3156b3aabe44397fbb38e00
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/01/2020
ms.locfileid: "45016246"
---
# <a name="learn-about-retention-policies-for-sharepoint-and-onedrive"></a>Informationen zu Aufbewahrungsrichtlinien für SharePoint und OneDrive

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Informationen in diesem Artikel ergänzen den Beitrag [Informationen zu Aufbewahrungsrichtlinien](retention-policies.md) um spezifische Angaben für SharePoint und OneDrive.

## <a name="how-a-retention-policy-works-with-sharepoint-and-onedrive"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit SharePoint und OneDrive

Eine Aufbewahrungsrichtlinie wird auf der Ebene einer Websitesammlung angewendet. Wenn Sie eine SharePoint-Websitesammlung oder ein OneDrive-Konto in eine Aufbewahrungsrichtlinie einschließen, wird ein permanentes Dokumentarchiv erstellt, sofern nicht bereits ein solches vorhanden ist. Sie können diese Bibliothek auf der Seite **Websiteinhalte** der Website auf oberster Ebene der Websitesammlung anzeigen. Die meisten Benutzer können das permanente Dokumentarchiv nicht anzeigen, da es nur für Websitesammlungsadministratoren sichtbar ist.
  
Wenn ein Benutzer versucht, den Inhalt einer Website, die einer Aufbewahrungsrichtlinie unterliegt, zu ändern oder zu löschen, überprüft die Aufbewahrungsrichtlinie zunächst, ob der Inhalt seit Anwendung der Richtlinie geändert wurde. Wenn dies die erste Änderung seit Anwendung der Richtlinie ist, kopiert die Aufbewahrungsrichtlinie den Inhalt in das permanente Dokumentarchiv und ermöglicht dem Benutzer anschließend das Ändern oder Löschen des ursprünglichen Inhalts. Alle Inhalte der Websitesammlung können auch dann in das permanente Dokumentarchiv kopiert werden, wenn der Inhalt der Abfrage, die von der Aufbewahrungsrichtlinie verwendet wird, nicht entspricht.
  
Ein Zeitgeberauftrag bereinigt in regelmäßigen Abständen das permanente Dokumentarchiv. Dieser vergleicht sämtliche Inhalte im permanenten Dokumentarchiv mit allen Abfragen, die von den Aufbewahrungsrichtlinien für die Website verwendet werden. Inhalte, die älter als die darin konfigurierte Aufbewahrungszeit sind, werden aus dem permanenten Dokumentarchiv sowie vom ursprünglichen Speicherort gelöscht, sofern sie dort noch vorhanden sind. Dieser Zeitgeberauftrag wird alle sieben Tage ausgeführt, was bedeutet, dass es bis zu sieben Tage dauern kann, bis Inhalte gelöscht werden.
  
Dieses Verhalten gilt für Inhalte, die bei Anwendung der Aufbewahrungsrichtlinie vorhanden sind. Außerdem werden alle neuen Inhalte, die erstellt oder der Websitesammlung hinzugefügt werden, nachdem sie in die Richtlinie eingeschlossen wurden, auch nach dem Löschen aufbewahrt. Neue Inhalte werden jedoch nicht bei der ersten Bearbeitung in das permanente Dokumentarchiv kopiert, sondern nur, wenn sie gelöscht werden. Wenn Sie alle Versionen einer Datei aufbewahren möchten, müssen Sie die [Versionsverwaltung](#how-a-retention-policy-works-with-document-versions-in-a-site-collection) aktivieren.
  
Ein Benutzer erhält eine Fehlermeldung, wenn er versucht, Bibliotheken, Listen, Ordner oder Websites zu löschen, für die eine Aufbewahrungsrichtlinie gilt. Ein Benutzer kann einen Ordner löschen, wenn er zuerst Dateien im Ordner verschiebt oder löscht, die der Richtlinie unterliegen. Außerdem wird das permanente Dokumentarchiv in dieser Phase erstellt und nicht, wenn Sie die Aufbewahrungsrichtlinie erstellen. Zum Testen Ihrer Richtlinie müssen Sie daher zuerst ein Dokument in einer Website bearbeiten oder löschen, die der Aufbewahrungsrichtlinie unterliegt, und dann zum permanenten Dokumentarchiv wechseln, um die aufbewahrte Kopie anzuzeigen.
  
Nachdem einem OneDrive-Konto oder einer SharePoint-Site eine Aufbewahrungsrichtlinie zugewiesen wurde, sind die Inhaltspfade davon abhängig, ob die Aufbewahrungsrichtlinie der Aufbewahrung und dem Löschen, der reinen Aufbewahrung oder dem reinen Löschen dient.

Wenn Sie die Aufbewahrungsrichtlinie dem Aufbewahren und Löschen dient:

![Diagramm des Inhaltslebenszyklus in SharePoint und OneDrive](../media/Retention_Diagram_of_retention_flow_in_sites.png)
  
1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**, wird eine Kopie des ursprünglichen Inhalts in der beim Zuweisen der Richtlinie vorhandenen Form im permanenten Dokumentarchiv erstellt. Dort ermittelt der Zeitgeberauftrag Elemente, deren Aufbewahrungszeitraum abgelaufen ist. Diese Elemente werden in den endgültigen Papierkorb verschoben, von wo sie nach Ablauf von 93 Tagen endgültig gelöscht werden. Der endgültige Papierkorb wird den Endbenutzern nicht angezeigt (sie sehen nur den Standardpapierkorb), Websitesammlungsadministratoren können hingegen dessen Inhalte anzeigen und wiederherstellen.

    > [!NOTE]
    > Um versehentlichem Datenverlust vorzubeugen, werden Inhalte nicht mehr dauerhaft aus dem permanenten Dokumentarchiv gelöscht. Stattdessen werden Inhalte nur aus dem Papierkorb dauerhaft gelöscht, sodass nun sämtliche Inhalte aus dem permanenten Dokumentarchiv den endgültigen Papierkorb durchlaufen werden.
    
2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**, wird er vom Zeitgeberauftrag am Ende des Aufbewahrungszeitraums in den Standardpapierkorb verschoben. Wenn ein Benutzer den Inhalt dort löscht oder diesen Papierkorb leert (auch als Aufräumen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen.

Wenn die Aufbewahrungsrichtlinie dem reinen Aufbewahren oder dem reinen Löschen dient, stellen die Inhaltspfade Varianten von Aufbewahren und Löschen dar:

#### <a name="content-paths-for-retain-only-retention-policy"></a>Inhaltspfade für rein aufbewahrende Aufbewahrungsrichtlinien

1. **Wenn der Inhalt während des Aufbewahrungszeitraums geändert oder gelöscht wird**: Eine Kopie des ursprünglichen Dokuments wird im permanenten Dokumentarchiv erstellt und bis zum Ende des Aufbewahrungszeitraums aufbewahrt, wo dann die Kopie im permanenten Dokumentarchiv in den endgültigen Papierkorb verschoben und nach 93 Tagen endgültig gelöscht wird.

2. **Wenn der Inhalt während des Aufbewahrungszeitraums nicht geändert oder gelöscht wird**: Weder vor noch nach dem Aufbewahrungszeitraum passiert etwas. Das Dokument verbleibt an seinem Ursprungsort.

#### <a name="content-paths-for-delete-only-retention-policy"></a>Inhaltspfade für rein löschende Aufbewahrungsrichtlinien

1. **Wenn der Inhalt während des festgelegten Zeitraums gelöscht wird**: Das Dokument wird in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert, wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Wenn der Inhalt während des festgelegten Zeitraums geändert wird, folgt er nach Ablauf dieses Zeitraums demselben Löschpfad.

2. **Wenn der Inhalt während des festgelegten Zeitraums nicht gelöscht wird**: Das Dokument wird am Ende des in der Aufbewahrungsrichtlinie festgelegten Zeitraums in den Standardpapierkorb verschoben. Wenn ein Benutzer das Dokument dort löscht oder diesen Papierkorb leert (auch als Bereinigen bekannt), wird das Dokument in den endgültigen Papierkorb verschoben. Der Standard- und der endgültige Papierkorb umfassen zusammen einen Aufbewahrungszeitraum von 93 Tagen. Am Ende dieser 93 Tage wird das Dokument dauerhaft von seinem jeweiligen Aufbewahrungsort gelöscht, entweder im Standard- oder im endgültigen Papierkorb. Der Papierkorb ist nicht indiziert und daher für die Suche nicht verfügbar. Eine eDiscovery-Suche kann daher keinen Inhalt des Papierkorbs finden, um für diesen eine Aufbewahrungspflicht festzulegen.
    
## <a name="how-a-retention-policy-works-with-document-versions-in-a-site-collection"></a>Funktionsweise einer Aufbewahrungsrichtlinie mit Dokumentversionen in einer Websitesammlung

Die Versionsverwaltung ist ein Feature aller Dokumentbibliotheken in SharePoint und in OneDrive. Standardmäßig werden bei der Versionsverwaltung mindestens 500 Hauptversionen beibehalten, Sie können diese Beschränkung jedoch erhöhen. Weitere Informationen finden Sie unter [Aktivieren und Konfigurieren der Versionsverwaltung für eine Liste oder Bibliothek](https://support.office.com/article/1555d642-23ee-446a-990a-bcab618c7a37).
  
Eine Aufbewahrungsrichtlinie behält alle Versionen eines Dokuments in einer SharePoint-Websitesammlung oder einem OneDrive-Konto bei. Wenn ein Dokument, das einer Richtlinie für die reine Aufbewahrung untersteht, zum ersten Mal bearbeitet wird, wird eine Version des ursprünglichen Dokuments in das permanente Dokumentarchiv kopiert und dort aufbewahrt. Wenn ein Dokument, das einer Richtlinie für die reine Aufbewahrung untersteht, gelöscht wird, werden alle bestehenden Versionen in das permanente Dokumentarchiv kopiert. Vorrausetzung hierfür ist, dass die Versionsverwaltung aktiviert sein muss. Jede Version eines Dokuments im permanenten Dokumentarchiv bleibt in ihrem jeweiligen Aufbewahrungszeitraum als eigenständiges Element bestehen:
  
- If the retention policy is based on when the content was created, each version has the same expiration date as the original document. The original document and its versions all expire at the same time.
    
- If the retention policy is based on when the content was last modified, each version has its own expiration date based on when the original document was modified to create that version. The original documents and its versions expire independently of each other.

> [!NOTE]
> Aufbewahrte Versionen von SharePoint- und OneDrive-Dokumenten lassen sich nicht mithilfe von eDiscovery-Tools durchsuchen.

## <a name="when-a-user-leaves-the-organization"></a>Wenn ein Benutzer die Organisation verlässt 

**SharePoint**:

Wenn ein Benutzer Ihre Organisation verlässt, sind Inhalte, die von ihm erstellt wurden, nicht betroffen, weil SharePoint als eine Zusammenarbeitsumgebung betrachtet wird, im Gegensatz zu dem Postfach oder dem OneDrive-Konto des Benutzers.

**OneDrive**:

Wenn ein Benutzer Ihre Organisation verlässt, bleiben alle Dateien, für die eine Aufbewahrungsrichtlinie gilt oder die Aufbewahrungsbezeichnungen aufweisen, für die Dauer der Richtlinie oder Bezeichnung erhalten. Während dieses Zeitraums bleibt der gesamte Freigabezugriff aufrecht. Nach Ablauf des Aufbewahrungszeitraums wird der Inhalt in den Papierkorb der Websitesammlung verschoben, wo er nur für den Administrator zugänglich sein wird. Wenn ein Dokument durch eine Aufbewahrungsrichtlinie als Eintrag gekennzeichnet ist, wird es erst gelöscht, wenn der Aufbewahrungszeitraum abgelaufen ist. Danach wird der Inhalt endgültig gelöscht. 

## <a name="how-to-configure-a-retention-policy-for-sharepoint-and-onedrive"></a>Konfigurieren einer Aufbewahrungsrichtlinie für SharePoint und OneDrive

Folgen Sie den Anweisungen für [Erstellen und Konfigurieren von Aufbewahrungsrichtlinien](create-retention-policies.md), und wählen Sie für die Seite **Speicherorte wählen** des Assistenten eine der folgenden Optionen aus:

- **Richtlinie nur auf Inhalte in Exchange-E-Mails, öffentlichen Ordnern, Office 365-Gruppen, OneDrive und SharePoint-Dokumenten anwenden**

- **Bestimmte Speicherorte auswählen** > **SharePoint-Websites**, **OneDrive-Konten** und **Office 365-Gruppen**.

Wenn Sie den Speicherort Ihrer **SharePoint-Websites** auswählen, kann Ihre Aufbewahrungsrichtlinie Inhalte auf SharePoint-Kommunikationswebsites, auf Teamwebsites, die nicht über Office 365-Gruppen verbunden sind, und auf klassischen Websites beibehalten. Teamwebsites, die über Office 365-Gruppen verbunden sind, werden bei dieser Option nicht unterstützt. Verwenden Sie stattdessen die **Office 365-Gruppen**-Speicherorte, die sich auf das Postfach der Gruppe, deren Website und Dateien auswirken. 

Wenn Sie Ihre Speicherorte für SharePoint-Websites angeben, benötigen Sie keine Berechtigungen für den Zugriff auf die Website, und es erfolgt keine Validierung, wenn Sie die URL auf der Seite **Speicherorte bearbeiten** angeben. Die Websites müssen jedoch indiziert werden, und die von Ihnen angegebenen Websites werden vom Assistenten dahingehend überprüft, ob sie existieren. 

Wenn die Überprüfung fehlschlägt, wird eine Meldung angezeigt, die besagt, dass die Überprüfung für die eingegebene URL fehlgeschlagen ist. Der Assistent erstellt die Aufbewahrungsrichtlinie erst, wenn die Überprüfung erfolgreich war. Wenn diese Meldung angezeigt wird, wechseln Sie zurück in den Assistenten, um die URL zu ändern oder die Website zu entfernen.
