---
title: Team für ein streng geheimes Projekt in der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/18/2019
audience: ITPro
ms.topic: overview
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Hier erfahren Sie, wie Contoso ein Team für streng geregelte Daten für ein streng geheimes Projekt verwendet, um eine neue Produkt-und Dienst Suite zu entwickeln.'
ms.openlocfilehash: 310ef33d4add7d71616aee8808515ca90536d8c1
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636498"
---
# <a name="team-for-a-top-secret-project-of-the-contoso-corporation"></a>Team für ein streng geheimes Projekt in der Contoso Corporation

Nach einem externen Geschäftsführer ordnete der CEO von Contoso die Entwicklung einer neuen Produkt-und Dienst Suite an, die die Gewinne von Contoso in den nächsten fünf Jahren verdoppeln könnte. Das streng geheime Projekt zur Entwicklung des Geschäfts-, Ingenieur-und Marktplans wurde mit dem Namen **Project 2X** und den wichtigsten Mitarbeitern im gesamten Unternehmen rekrutiert. 

Die Zeitrahmen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.

Die daraus resultierenden Lieferumfänge für Project 2X Warengeschäfts Pläne, Produkt-und Engineering-Spezifikationen sowie Marketingmaterialien und-Zeitpläne in Form von Word-, Excel-und PowerPoint-Dateien. 

Der Zugriff auf diese Dateien erfolgte aufgrund Ihrer sensiblen Eigenschaften wie folgt:

- Beschränkt auf Project 2X-Teammitglieder.
- Durch eine DLP-Richtlinie (Data Loss Prevention) geschützt, um zu verhindern, dass Project 2X-Teammitglieder Sie außerhalb des Teams freigeben.
- Verschlüsselt und mit Berechtigungen geschützt, um den Zugriff nur für Project 2X-Teammitglieder zu gewähren, auch wenn die Dateien außerhalb von Contoso verteilt wurden.

Contoso-IT-Mitarbeiter haben ein [Team für hochregulierte Daten](secure-teams-highly-regulated-data-scenario.md) für Project 2X und diese Schritte verwendet.

## <a name="step-1-created-a-private-team-and-locked-down-the-underlying-sharepoint-site"></a>Schritt 1: Erstellen eines privaten Teams und Sperren der zugrunde liegenden SharePoint-Website

Um den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben Contoso-IT-Administratoren die [empfohlenen SharePoint-Zugriffsrichtlinien](sharepoint-file-access-policies.md)konfiguriert.

Als nächstes hat ein IT-Administrator von Contoso ein neues privates Team namens "Project 2X" erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt.

Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Project 2X den Zugriff auf die Website freigibt und andere Benutzer den Zugriff auf die Website anfordern.

Informationen zu den Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein stark reguliertes Team](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-three-tiers#highly-confidential-teams).

## <a name="step-2-configured-a-dlp-policy-and-the-underlying-site-for-a-retention-label"></a>Schritt 2: Konfigurieren einer DLP-Richtlinie und des zugrunde liegenden Standorts für eine Aufbewahrungs Bezeichnung 

Zunächst wendeten Contoso-Administratoren die vorhandene **streng vertrauliche** Aufbewahrungs Bezeichnung auf den Abschnitt **Documents** der zugrunde liegenden SharePoint-Website des Project 2X-Teams an.

Als nächstes haben Sie eine neue DLP-Richtlinie mit dem Namen " **Project 2X** " erstellt, die:

- Verwendet die streng vertrauliche Aufbewahrungs Bezeichnung.
- Blockiert Benutzer, wenn Sie versuchen, eine Datei im Team des Projekts 2X außerhalb von Contoso freizugeben.

Informationen zu den Konfigurationsdetails finden Sie unter [Protect Files in Teams with Retention Labels and DLP](https://docs.microsoft.com/microsoft-365/security/office-365-security/deploy-teams-retention-dlp).

## <a name="step-3-created-a-sensitivity-label-for-the-project-2x-team"></a>Schritt 3: Erstellen einer Sensitivitäts Bezeichnung für das Team des Projekts 2x

Contoso-Administratoren haben eine neue Sensitivitäts Bezeichnung mit dem Namen " **Project 2X** " erstellt, die:

- Verschlüsselung erforderlich.
- Erlaubt gemeinsame Author-Berechtigungen für das Projekt 2X Microsoft 365 Group.

Hier ist die resultierende Konfiguration des Project 2X-Teams.

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-highly-confidential-assets/final-config.png)
 
Dateien im Abschnitt "Dokumente" der zugrunde liegenden Project 2X SharePoint-Website wurden durch Folgendes geschützt:

- Die Websiteberechtigungen, die nur den Zugriff auf Mitglieder der 2X Microsoft 365-Gruppe des Projekts ermöglichen.
- Die streng vertrauliche Aufbewahrungs Bezeichnung, die automatisch neuen Dateien zugewiesen wird.
- Eine DLP-Richtlinie, die die streng vertrauliche Aufbewahrungs Bezeichnung und Einstellungen verwendet, mit denen verhindert wird, dass die Datei für externe Benutzer freigegeben wird.
- Die Bezeichnung "Project 2X Sensitivity" mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der Website verschoben oder kopiert wird.

Im folgenden finden Sie ein Beispiel für eine Datei, die im zugrunde liegenden Projekt 2X-Standort mit der streng regulierten Aufbewahrungs Bezeichnung und der zugewiesenen 2-fachen Vertraulichkeits Bezeichnung gespeichert ist

![Ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-highly-confidential-assets/final-config-example-file.png)
 
## <a name="step-4-trained-project-2x-team-members"></a>Schritt 4: geschulte Project 2X-Teammitglieder

Contoso-Sicherheitsmitarbeiter haben die Teammitglieder des Projekts 2X in einem obligatorischen Kurs geschult, der Sie durchschritten hat:

- Wie Sie auf das neue Project 2X-Team zugreifen, Besprechungen und Chats verwenden und wie Sie an Team Dateien zusammenarbeiten können.
- Erstellen neuer Dateien im Team und Hochladen neuer Dateien, die lokal erstellt wurden.
- Ein Beispiel dafür, wie die DLP-Richtlinie verhindert, dass Dateien extern freigegeben werden.
- Vorgehensweise Beschriften von Dateien mit der Sensitivitäts Bezeichnung Project 2x.
- Eine Demonstration der Art und Weise, wie die Bezeichnung des Projekts 2X eine Datei schützt, auch wenn Sie das Team verlässt.

Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammengearbeitet haben.

In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die von der Bezeichnung "Project 2X" auf ein lokales Laufwerk für die Offlinearbeit geschützt wurden. Nachdem Sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, wurde der Fehler erkannt und gelöscht.

Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts vertraulich behandelt. Contoso kündigte seine Pläne an und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Leidwesen seiner Konkurrenten bereitzustellen.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen](deploy-microsoft-365-enterprise.md) Microsoft 365 Enterprise in Ihrer Organisation.

## <a name="see-also"></a>Siehe auch

[Microsoft 365-Produktivitätsbibliothek](https://aka.ms/productivitylibrary) (https://aka.ms/productivitylibrary)
