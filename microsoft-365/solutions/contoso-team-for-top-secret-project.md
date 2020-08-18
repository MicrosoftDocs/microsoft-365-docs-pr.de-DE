---
title: Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation
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
description: 'Zusammenfassung: Hier erfahren Sie, wie Contoso ein Team mit Sicherheitsisolation für ein streng geheimes Projekt verwendet, um eine neue Produkt-und Dienst Suite zu entwickeln.'
ms.openlocfilehash: ba9a66d2419e81aeb1eac026b16c0475ac6d0614
ms.sourcegitcommit: 1780359234abdf081097c8064438d415da92fb85
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/17/2020
ms.locfileid: "46778586"
---
# <a name="isolated-team-for-a-top-secret-project-of-the-contoso-corporation"></a>Isoliertes Team für ein streng geheimes Projekt der Contoso Corporation

Nach einem externen Geschäftsführer ordnete der CEO von Contoso die Entwicklung einer neuen Produkt-und Dienst Suite an, die die Gewinne von Contoso in den nächsten fünf Jahren verdoppeln könnte. Das streng geheime Projekt zur Entwicklung des Geschäfts-, Ingenieur-und Marktplans wurde mit dem Namen **Project 2X** und den wichtigsten Mitarbeitern im gesamten Unternehmen rekrutiert. 

Die Zeitrahmen für Forschung und Entwicklung waren eng, was bedeutete, dass die Zusammenarbeit effizient sein und für sichere Besprechungen, laufende Unterhaltungen und Dateispeicherung sorgen musste.

Die daraus resultierenden Lieferumfänge für Project 2X Warengeschäfts Pläne, Produkt-und Engineering-Spezifikationen sowie Marketingmaterialien und-Zeitpläne in Form von Word-, Excel-und PowerPoint-Dateien. 

Der Zugriff auf diese Dateien erfolgte aufgrund Ihrer sensiblen Eigenschaften wie folgt:

- Beschränkt auf Project 2X-Teammitglieder und Führungskräfte.
- Verschlüsselt und mit Berechtigungen geschützt, um den Zugriff nur für Project 2X-Teammitglieder und Führungskräfte zu ermöglichen, auch wenn die Dateien außerhalb der gesicherten Ordner verteilt wurden.

Contoso-IT-Mitarbeiter haben ein [Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) für Project 2X und diese Schritte verwendet.

## <a name="step-1-created-a-private-team"></a>Schritt 1: Erstellen eines privaten Teams

Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../enterprise/sharepoint-file-access-policies.md)konfiguriert.

Als nächstes hat ein IT-Administrator von Contoso ein neues privates Team namens "Project 2X" erstellt und die Benutzerkonten von Project 2X-Mitarbeitern als Mitglieder hinzugefügt. Außerdem haben Sie das Team so konfiguriert, dass nur Projekt-2X-Teambesitzer private Kanäle erstellen können.

Informationen zu den Konfigurationsdetails finden Sie unter [Erstellen eines privaten Teams](secure-teams-security-isolation.md#create-a-private-team).

## <a name="step-2-created-a-sensitivity-label-for-the-project-2x-team"></a>Schritt 2: Erstellen einer Sensitivitäts Bezeichnung für das Team des Projekts 2x

Contoso-Administratoren haben eine neue Sensitivitäts Bezeichnung mit dem Namen " **Project 2X** " erstellt, die:

- Aktivierte Verschlüsselung.
- Erlaubte gemeinsame Author-Berechtigungen für das Projekt 2X Microsoft 365 Group.
- Zulässige Viewer-Berechtigungen für die Führungskräfte Gruppe.
- Blockierter Zugriff auf nicht verwaltete Geräte.

Dateien im Abschnitt " **Dokumente** " der zugrunde liegenden Project 2X SharePoint-Website wurden durch Folgendes geschützt:

- Die Websiteberechtigungen, die nur vollständige Berechtigungen für Mitglieder des Projekts 2X Microsoft 365 Group und Leseberechtigungen für die Führungskräfte Gruppe gewähren.
- Die Bezeichnung "Project 2X Sensitivity" mit Verschlüsselung und Berechtigungen, die mit der Datei transportiert werden, wenn Sie von der Website verschoben oder kopiert wird.

Informationen zu den Konfigurationsdetails finden Sie unter [Create a Sensitivity Label](secure-teams-security-isolation.md#create-a-sensitivity-label).

## <a name="step-3-configured-the-underlying-sharepoint-site"></a>Schritt 3: Konfigurieren der zugrunde liegenden SharePoint-Website

Um zunächst den Zugriff auf die zugrunde liegende SharePoint-Website für das Team zu schützen, haben die IT-Administratoren von Contoso die [empfohlenen SharePoint-Zugriffsrichtlinien](../enterprise/sharepoint-file-access-policies.md)konfiguriert.

Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert:

- So verhindern Sie, dass Mitglieder von Project 2X-Gruppen Zugriff auf die Website freigeben. Informationen zu den Konfigurationsdetails finden Sie unter [SharePoint-Einstellungen für ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md#sharepoint-settings).
- Für Leseberechtigungen für die Führungskräfte Gruppe.

Als nächstes haben Sie zusätzliche Berechtigungseinstellungen für die Website konfiguriert, um zu verhindern, dass Mitglieder von Project 2X-Gruppen Zugriff auf die Website freigeben. 

Wenn private Kanäle für das Projekt 2X erstellt wurden, hat der Gruppenbesitzer die Option "Gast Freigabe" deaktiviert und den standardmäßigen Freigabe Link auf den Wert " **bestimmte Personen** " festgelegt.

Hier ist die resultierende Konfiguration des Project 2X-Teams mit Sicherheitsisolierung.

![Die resultierende Konfiguration des Project 2X-Teams](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project.png)

 ## <a name="step-4-trained-project-2x-team-members"></a>Schritt 4: geschulte Project 2X-Teammitglieder

Contoso-Sicherheitsmitarbeiter haben die Teammitglieder des Projekts 2X in einem obligatorischen Kurs geschult, der Sie durchschritten hat:

- Wie Sie auf das neue Project 2X-Team zugreifen, Besprechungen und Chats verwenden und wie Sie an Team Dateien zusammenarbeiten können.
- Erstellen neuer Dateien im Team und Hochladen neuer Dateien, die lokal erstellt wurden.
- Vorgehensweise Beschriften von Dateien mit der Sensitivitäts Bezeichnung Project 2x.
- Eine Demonstration der Art und Weise, wie die Bezeichnung des Projekts 2X eine Datei schützt, auch wenn Sie das Team verlässt.

Das Endergebnis war eine sichere Umgebung, in der Project 2X-Teammitglieder in einer sicheren Umgebung für Chats, Besprechungen und Dateien zusammengearbeitet haben.

Im folgenden finden Sie ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist, wobei die Sensitivitäts Bezeichnung Project 2X zugeordnet ist

![Ein Beispiel für eine Datei, die in der zugrunde liegenden Project 2X-Website gespeichert ist](../media/contoso-team-for-top-secret-project/contoso-team-for-top-secret-project-example.png)

In einigen Fällen haben Project 2X-Teammitglieder Dateien heruntergeladen, die von der Bezeichnung "Project 2X" auf ein lokales Laufwerk für die Offlinearbeit geschützt wurden. 

Nachdem Sie jedoch beim Öffnen zur Eingabe von Anmeldeinformationen aufgefordert wurden, wurde der Fehler erkannt und gelöscht.

Aufgrund der Zusammenarbeitsumgebung von Teams und der Sicherheitsfeatures von Microsoft 365 wurden die Details von Project 2X für die Dauer des Projekts vertraulich behandelt. Contoso kündigte seine Pläne an und ist dabei, die neuen Produkte und Dienstleistungen zur Freude seiner Kunden und Investoren und zum Leidwesen seiner Konkurrenten bereitzustellen.

## <a name="next-step"></a>Nächster Schritt

[Stellen Sie ein Team mit Sicherheitsisolierung](secure-teams-security-isolation.md) in Ihrer Organisation bereit.

