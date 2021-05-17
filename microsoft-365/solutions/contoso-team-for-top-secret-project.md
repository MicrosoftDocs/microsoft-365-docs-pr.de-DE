---
title: Isoliertes Team für ein geheimes Projekt der Contoso Corporation
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
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
ms.openlocfilehash: 751bf3972d148219a6cc341067c0bf34cd581447
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52029016"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isoliertes Team für ein geheimes Projekt der Contoso Corporation

Nach einer offsite der Geschäftsleitung hat der CEO von Contoso die Entwicklung einer neuen Suite von Produkten und Diensten bestellt, die den Gewinn von Contoso in den nächsten fünf Jahren verdoppeln könnte. Das geheime Projekt zur Entwicklung des Geschäfts-, Engineering- und Marktplans wurde **Project 2X** genannt, und wichtige Mitarbeiter im gesamten Unternehmen wurden eingestellt. 

Die Zeitachsen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.

Die resultierenden Ergebnisse für Project 2X waren Geschäftspläne, Produkt- und technische Spezifikationen sowie Marketingmaterialien und Zeitpläne in Form von Word-, Excel- und PowerPoint-Dateien. 

Aufgrund ihrer vertraulichen Art war der Zugriff auf diese Dateien wie die folgenden:

- Beschränkt auf Project 2X-Teammitglieder und leitende Führungskräfte.
- Verschlüsselt und mit Berechtigungen geschützt, um zugriff nur auf Project 2X-Teammitglieder und leitende Führungskräfte zu ermöglichen, auch wenn die Dateien außerhalb ihrer gesicherten Ordner verteilt wurden.

Contoso-IT-Mitarbeiter verwendeten ein Team mit [Sicherheitsisolation](secure-teams-security-isolation.md) für Project 2X und diese Schritte.

## <a name="step-1-created-a-private-team"></a>Schritt 1: Erstellen eines privaten Teams

Um zunächst den Zugriff auf die zugrunde liegende SharePoint für das Team zu schützen, haben Contoso-IT-Administratoren die empfohlenen [Zugriffsrichtlinien SharePoint konfiguriert.](../security/office-365-security/sharepoint-file-access-policies.md)

Als Nächstes hat ein Contoso-IT-Administrator ein neues privates Team mit dem Namen Project 2X erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt. Sie haben das Team auch so konfiguriert, dass nur Project 2X-Teambesitzer private Kanäle erstellen können.

Die Konfigurationsdetails finden Sie unter [Create a private team](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Schritt 2: Erstellen einer Vertraulichkeitsbezeichnung für das Project 2X-Team

Contoso-Administratoren haben eine neue Vertraulichkeitsbezeichnung namens **Project 2X erstellt,** die:

- Aktivierte Verschlüsselung.
- Zulässige Co-Author für die Project 2X-Microsoft 365 Gruppe.
- Zulässige Viewer-Berechtigungen für die Gruppe "Senior Leadership".
- Blockierter Zugriff auf nicht verwaltete Geräte.

Dateien im Abschnitt **Dokumente** der zugrunde liegenden Project 2X-SharePoint wurden durch:

- Die Websiteberechtigungen, die nur vollständige Berechtigungen für Mitglieder der gruppe Project 2X Microsoft 365 und Leseberechtigungen für die Gruppe "Senior Leadership" zulassen.
- Die Project 2X-Vertraulichkeitsbezeichnung mit Verschlüsselung und Berechtigungen, die mit der Datei reisen, wenn sie von der Website verschoben oder kopiert wird.

Die Konfigurationsdetails finden Sie unter [Create a sensitivity label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Schritt 3: Konfigurieren der zugrunde liegenden SharePoint Website

Um zunächst den Zugriff auf die zugrunde liegende SharePoint für das Team zu schützen, haben Contoso-IT-Administratoren die empfohlenen [Zugriffsrichtlinien SharePoint konfiguriert.](../security/office-365-security/sharepoint-file-access-policies.md)

Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website:

- Um zu Project, dass 2X-Gruppenmitglieder den Zugriff auf die Website freigeben. Die Konfigurationsdetails finden Sie [unter SharePoint einstellungen für ein Team mit Sicherheitsisolation](secure-teams-security-isolation.md#sharepoint-settings).
- For Read permissions for the Senior Leadership group.

Als Nächstes konfigurierten sie zusätzliche Berechtigungseinstellungen für die Website, um zu verhindern, dass Project 2X-Gruppenmitglieder den Zugriff auf die Website freigeben. 

Als private Kanäle für die Project 2X erstellt wurden, deaktivierte der Gruppenbesitzer die Gastfreigabe, und der Standardfreigabelink wurde auf den Wert **Spezifische Personen** festgelegt.

Hier sehen Sie die resultierende Konfiguration des Project 2X-Teams mit Sicherheitsisolation.

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Schritt 4: Geschulte Project 2X-Teammitglieder

Contoso-Sicherheitsmitarbeiter haben die Project 2X-Teammitglieder in einem obligatorischen Kurs geschult, der sie durch schritt:

- So greifen Sie auf das neue Project 2X-Team zu, verwenden Sie Besprechungen und Chats und wie Sie an Teamdateien zusammenarbeiten.
- Hier erfahren Sie, wie Sie neue Dateien im Team erstellen und neue lokal erstellte Dateien hochladen.
- So beschriften Sie Dateien mit Project 2X-Vertraulichkeitsbezeichnung.
- Eine Demonstration, wie Project 2X-Bezeichnung eine Datei schützt, auch wenn sie das Team verlässt.

Das Endergebnis war eine sichere Umgebung, in der Project 2X Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammenarbeiten.

Hier ist ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist, der die Project 2X-Vertraulichkeitsbezeichnung zugewiesen ist.

![Ein Beispiel für eine Datei, die auf der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project-example.png)

In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die durch die Project 2X-Bezeichnung geschützt sind, auf ein lokales Laufwerk für die Offlinearbeit. 

Nachdem sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, erkannten sie ihren Fehler und löschten sie.

Aufgrund der Umgebung für die Zusammenarbeit von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts geheim gehalten. Contoso hat seine Pläne angekündigt und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Unförmlich der Konkurrenten zu entwickeln.

## <a name="next-step"></a>Nächster Schritt

[Bereitstellen eines Teams mit Sicherheitsisolation](secure-teams-security-isolation.md) in Ihrer Organisation.

