---
title: Isoliertes Team für ein geheimes Projekt der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/14/2020
audience: ITPro
ms.topic: overview
ms.prod: microsoft-365-enterprise
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: Ent_Architecture
description: 'Zusammenfassung: Wie Contoso ein Team mit Sicherheitsisolation für ein geheimes Projekt verwendet hat, um eine neue Suite von Produkten und Diensten zu entwickeln.'
ms.openlocfilehash: d5ab2808251ff6a53f8975ea868431691d3301e2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051006"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isoliertes Team für ein geheimes Projekt der Contoso Corporation

Nach einer offsite der Geschäftsleitung hat der CEO von Contoso die Entwicklung einer neuen Suite von Produkten und Diensten bestellt, die den Gewinn von Contoso in den nächsten fünf Jahren verdoppeln könnte. Das geheime Projekt zur Entwicklung des Geschäfts-, Engineering- und Marktplans hieß **Project 2X,** und wichtige Mitarbeiter im gesamten Unternehmen wurden eingestellt. 

Die Zeitachsen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.

Die resultierenden Ergebnisse für Project 2X waren Geschäftspläne, Produkt- und Technische Spezifikationen sowie Marketingmaterialien und Zeitpläne in Form von Word-, Excel- und PowerPoint-Dateien. 

Aufgrund ihrer vertraulichen Art war der Zugriff auf diese Dateien wie die folgenden:

- Beschränkt auf Project 2X-Teammitglieder und leitende Führungskräfte.
- Verschlüsselt und mit Berechtigungen geschützt, um nur Den Zugriff auf Project 2X-Teammitglieder und leitende Führungskräfte zu ermöglichen, auch wenn die Dateien außerhalb ihrer gesicherten Ordner verteilt wurden.

Contoso-IT-Mitarbeiter haben [ein Team mit Sicherheitsisolation](secure-teams-security-isolation.md) für Project 2X und diese Schritte verwendet.

## <a name="step-1-created-a-private-team"></a>Schritt 1: Erstellen eines privaten Teams

Zunächst haben Contoso-IT-Administratoren die empfohlenen SharePoint-Zugriffsrichtlinien konfiguriert, um den Zugriff auf die zugrunde liegende [SharePoint-Website](../security/defender-365-security/sharepoint-file-access-policies.md)für das Team zu schützen.

Als Nächstes hat ein Contoso-IT-Administrator ein neues privates Team namens Project 2X erstellt und die Benutzerkonten der Project 2X-Mitarbeiter als Mitglieder hinzugefügt. Sie haben das Team auch so konfiguriert, dass nur Project 2X-Teambesitzer private Kanäle erstellen können.

Die Konfigurationsdetails finden Sie unter [Create a private team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Schritt 2: Erstellen einer Vertraulichkeitsbezeichnung für das Project 2X-Team

Contoso-Administratoren haben eine neue Vertraulichkeitsbezeichnung namens **Project 2X erstellt,** die:

- Aktivierte Verschlüsselung.
- Zulässige Co-Author für die Project 2X Microsoft 365-Gruppe.
- Zulässige Viewer-Berechtigungen für die Gruppe "Senior Leadership".
- Blockierter Zugriff auf nicht verwaltete Geräte.

Dateien im Abschnitt **Dokumente** der zugrunde liegenden Project 2X -SharePoint-Website wurden durch:

- Die Websiteberechtigungen, die nur vollständige Berechtigungen für Mitglieder der Project 2X Microsoft 365-Gruppe zulassen und Berechtigungen für die Gruppe "Senior Leadership" lesen.
- Die Project 2X-Vertraulichkeitsbezeichnung mit Verschlüsselung und Berechtigungen, die mit der Datei reisen, wenn sie verschoben oder von der Website kopiert wird.

Die Konfigurationsdetails finden Sie unter [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website

Zunächst haben Contoso-IT-Administratoren die empfohlenen SharePoint-Zugriffsrichtlinien konfiguriert, um den Zugriff auf die zugrunde liegende [SharePoint-Website](../security/defender-365-security/sharepoint-file-access-policies.md)für das Team zu schützen.

Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website:

- So verhindern Sie, dass Project 2X-Gruppenmitglieder den Zugriff auf die Website freigeben. Die Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein Team mit Sicherheitsisolation](secure-teams-security-isolation.md#sharepoint-settings).
- For Read permissions for the Senior Leadership group.

Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website, um zu verhindern, dass Project 2X-Gruppenmitglieder den Zugriff auf die Website freigeben. 

Als private Kanäle für project 2X erstellt wurden, hat der Gruppenbesitzer die Gastfreigabe deaktiviert und den Standardfreigabelink auf den **Wert Spezifische Personen** festgelegt.

Hier sehen Sie die resultierende Konfiguration des Project 2X-Teams mit Sicherheitsisolation.

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Schritt 4: Geschulte Project 2X-Teammitglieder

Die Contoso-Sicherheitsmitarbeiter haben die Project 2X-Teammitglieder in einem obligatorischen Kurs geschult, der sie durch schritt:

- So greifen Sie auf das neue Project 2X-Team zu, verwenden Sie Besprechungen und Chats und wie Sie an Teamdateien zusammenarbeiten.
- Hier erfahren Sie, wie Sie neue Dateien im Team erstellen und neue lokal erstellte Dateien hochladen.
- So beschriften Sie Dateien mit der Project 2X-Vertraulichkeitsbezeichnung.
- Eine Demonstration, wie die Project 2X-Bezeichnung eine Datei schützt, auch wenn sie das Team verlässt.

Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammenarbeiten.

Im Folgenden finden Sie ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist, der die Project 2X-Vertraulichkeitsbezeichnung zugewiesen ist.

![Ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project-example.png)

In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die durch die Project 2X-Bezeichnung geschützt sind, auf ein lokales Laufwerk für Offlinearbeit. 

Nachdem sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, erkannten sie ihren Fehler und löschten sie.

Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts geheim gehalten. Contoso hat seine Pläne angekündigt und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Unförmlich der Konkurrenten zu entwickeln.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen eines Teams mit Sicherheitsisolation](secure-teams-security-isolation.md) in Ihrer Organisation.

