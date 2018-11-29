---
title: SharePoint Online-Website für streng vertraulich digitale Objekte der Contoso Corporation
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Wie für eine SharePoint Online-Website von Contoso stark implementiert teams regulierte Daten für einfachere Zusammenarbeit zwischen den Research.'
ms.openlocfilehash: 697ddb27b56fd529e9c73b89d9f07b8731ad76c3
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868150"
---
# <a name="sharepoint-online-site-for-highly-confidential-digital-assets-of-the-contoso-corporation"></a>SharePoint Online-Website für streng vertraulich digitale Objekte der Contoso Corporation

 **Zusammenfassung:** Contoso hat wie eine SharePoint Online-Website für stark regulierten Daten für einfachere Zusammenarbeit zwischen den Teams Research implementiert.
  
Wichtigsten Ressourcen von Contoso sind dessen Rechte an geistigem Eigentum in Form von Geschäftsgeheimnissen wie proprietäre Fertigung Techniken, und Entwerfen Spezifikationen von Produkten, die bei der Entwicklung sind. Diese Objekte sind in digitaler Form, die ursprünglich als Dateien auf einer SharePoint Server 2016-Website gespeichert. Bei Contoso Microsoft 365 Enterprise bereitgestellt haben, sollte damit ihre lokale digitaler Objekte in die Cloud für leichteren Zugriff und anfälliger für die Zusammenarbeit über Research Teams in Paris, Moskau, New York, Peking und Bangalore umzustellen. 
  
Aufgrund der sensiblen Daten, muss jedoch Zugriff auf diese Dateien werden:

- Klicken Sie auf die Gruppe von Personen, die berechtigt sind, anzeigen oder ändern, mit dem laufenden Berechtigungen für die Website nur von SharePoint-Administratoren verwaltet beschränkt. 
- Geschützte mit Data Loss Prevention (DLP) verhindert, dass Benutzer außerhalb der Website verteilt werden.
- Verschlüsselte und geschützt mit Access Zugriffssteuerungslisten zu verhindern, dass der nicht autorisierte Benutzer den Zugriff auf ihre Inhalte, auch wenn sie außerhalb des Standorts verteilt werden.

Sicherheit und SharePoint-Administratoren in Contoso des IT-Abteilung entschieden, eine [SharePoint Online-Website für stark regulierter Daten](teams-sharepoint-online-sites-highly-regulated-data.md)zu verwenden.
  
Contoso verwendet diese Schritte zum Erstellen und Sichern eine SharePoint Online Teamwebsites für ihre Research-Teams.

## <a name="step-1-reviewed-and-verified-the-members-of-research-team-groups"></a>Schritt 1: Überprüft und die Mitglieder einer Gruppe von Research Team überprüft

Contoso-IT-Administratoren einen Überblick über den Satz von Sicherheitsgruppen für ihre Teams Research ausgeführt. Diese entfernt Personen war keine Interviewer oder nicht benötigen Zugriff auf Research-Objekte. 

Sie auch und diese neue Sicherheitsgruppen erstellt:

- **Research-Admins**  Der Satz von SharePoint-Administratoren, die vollständige Kontrolle über die Website, einschließlich der Möglichkeit zum Ändern der Berechtigungen verfügen.
- **Research-Member**  Der Satz von Sicherheitsgruppen für die Research Teams auf der ganzen Welt.
- **Research-Viewer**  Der Satz von Management-Benutzer, wie die Führungskräfte in der Organisation Research, die die Anlagen auf der Website anzeigen können.

## <a name="step-2-created-an-isolated-sharepoint-online-team-site"></a>Schritt 2: Erstellt eine isolierte SharePoint Online-Teamwebsite 

**Namens Contoso SharePoint-Administratoren, die zuerst erstellt eine neue Teamwebsite.** Diese dann konfiguriert:

- Die Berechtigungsstufe Vollzugriff auf die Research Besitzer SharePoint-Gruppe verwenden, die die Sicherheitsgruppe **"Research-Admins"** als Mitglied aufweist
- Die Berechtigungsstufe bearbeiten die Research Mitglieder SharePoint-Gruppe verwenden, die die Sicherheitsgruppe **Research Mitglieder** als Mitglied aufweist
- Die Berechtigungsstufe lesen, um die Research Besucher von SharePoint-Gruppe verwenden, die als Mitglied die **Research-Viewer** -Sicherheitsgruppe verfügt

Hier sind die resultierenden SharePoint-Berechtigungsstufen, SharePoint-Gruppen und deren Member.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/spo-permissions.png)

Im nächsten Schritt konfiguriert sie zusätzliche Einschränkungen für die Website.

Die Konfigurationsdetails finden Sie unter [Bereitstellen einer isolierten SharePoint Online-Teamwebsite](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site).

## <a name="step-3-configured-the-site-for-a-restrictive-office-365-label-dlp-policy"></a>Schritt 3: Konfiguriert die Website für eine eingeschränkte Office 365 Bezeichnung DLP-Richtlinie

"Contoso Admins" wird zuerst die Bezeichnung des **Streng vertraulich** Office 365 zu der Website **Research** angewendet.

Erstellt im nächsten Schritt eine neue Office 365 DLP-Richtlinie mit dem Namen **Research** , die:

- Verwendet die **Streng vertraulich** Office 365-Beschriftung. 
- Wird auf der Website **Research** angewendet.
- Verhindert, dass Benutzer Dokumente freigeben.

Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Office 365 Etiketten und DLP](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp).

## <a name="step-4-created-an-azure-information-protection-sub-label-for-the-site"></a>Schritt 4: Erstellt eine untergeordnete Azure Information Protection Beschriftung für die Website

"Contoso Admins" erstellt eine neue Azure Information Protection untergeordnete Beschriftung mit dem Namen **Research** der standardmäßigen **Streng vertraulich** Beschriftung in einer bereichsbezogenen Richtlinie, die:

- Verschlüsselung ist erforderlich.
- Ermöglicht den Vollzugriff durch ein Mitglied der Sicherheitsgruppe **Research Mitglieder** .
- Ermöglicht den Lesezugriff durch ein Mitglied der Sicherheitsgruppe **Research Leser von Berichten** .

Im nächsten Schritt bereitgestellt sie Azure Information Protection-Client für die Geräte der Teammitglieder Research.

Die Konfigurationsdetails finden Sie unter [Schützen von SharePoint Online-Dateien mit Azure Information Protection](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection). 

Hier ist die resultierende Konfiguration der Website **Research** für streng vertraulich Objekte.

![](./media/contoso-sharepoint-online-site-for-highly-confidential-assets/final-config.png)

## <a name="step-5-migrated-the-on-premises-sharepoint-research-data"></a>Schritt 5: Migriert Research lokale SharePoint-Daten

"Contoso Admins" verschoben, dass alle von der lokalen Dateien in der lokalen SharePoint Server 2016 Website in Ordnern in die neue **Research** SharePoint Online-Website Recherchieren.

## <a name="step-6-trained-their-users"></a>Schritt 6: Geschulte ihre Benutzer 

Contoso Sicherheit Mitarbeiter geschult die Research Teams ein obligatorisch Kurs, der über diese schrittweise durchlaufen:

- Wie Sie auf die neue **Research** SharePoint Online-Website und die vorhandenen Dateien zugreifen.
- Erklären Sie, wie neue Dateien auf der Website erstellt und neue, lokal gespeicherte Dateien hochgeladen werden.
- Veranschaulicht die Erstellung blockiert die DLP-Richtlinie Dateien extern freigegeben.
- Wie Sie mit der Azure Information Protection Client Research-Dateien mit der untergeordneten **Research** Bezeichnung bezeichnen.
- Veranschaulicht die Erstellung schützt **Research** untergeordnete Beschriftung eine Datei, auch wenn es von der Website offengelegt werden.

Das Ergebnis ist eine sichere Umgebung, in der die Forscher in der gesamten Organisation in einer sicheren Umgebung zusammenarbeiten können. 

Wenn ein Research-Dokument mit der untergeordneten **Research** Bezeichnung aus der Website **Research** offengelegt werden, ist es verschlüsselte und können nur Mitglieder der Sicherheitsgruppen **Research Elemente** und **Research Leser von Berichten** mit gültigen Anmeldeinformationen zugreifen.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen](deploy-microsoft-365-enterprise.md) von Microsoft 365 Enterprise in Ihrer Organisation.

