---
title: Risikominderungen bei der Verwaltung der Geschäftskontinuität in Microsoft 365 Enterprise
author: chrfox
ms.author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: Einige Beispiele für Risikominderungen für Microsoft 365-Dienstvorfallszenarien.
ms.openlocfilehash: 830d8c3ac9993185bbb60ff15c08903e298b9b78
ms.sourcegitcommit: 7690c8bfdea6e6d245cfa7c5b09b913b092cde0a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2019
ms.locfileid: "37122265"
---
# <a name="service-incident-mitigation-strategies"></a>Strategien zur Schadensbegrenzung bei Dienstvorfällen

Nachfolgend finden Sie einige Strategien und Szenarien, die veranschaulichen, wie Sie die Auswirkungen eines Microsoft 365-Dienstvorfalls auf Ihre Geschäftsprozesse verringern können.

## <a name="service-incident-scenarios-and-potential-mitigations"></a>Dienstvorfallszenarien und mögliche Risikominderungen

|Microsoft 365-Abhängigkeit|Mögliche Risikominderungen|
|---------|---------|
|Das Incident Management-System basiert auf Exchange Online und bindet Bereitschaftstechniker und Vorfalls-Manager ein.|Stellen Sie sicher, dass Ihr Incident Management-System eine Kommunikation über mehrere Kanäle, z. B. E-Mails, Telefonanrufe und SMS-Benachrichtigungen, sowie Anrufstrukturhierarchien unterstützt, falls der primäre Bereitschaftstechniker nicht verfügbar ist, sodass der Backup kontaktiert wird. Außerdem können Sie in jede Benachrichtigung Kontaktmethoden für den Backup einfügen, sodass die Kommunikationsmethoden eingebettet werden, damit sie leicht zu finden sind. Alternative Kommunikationsmethoden, z. B. Yammer, können für die Zusammenarbeit im Notfall verwendet werden, wenn der Vorfallverwaltungsdienst nicht verfügbar ist.|
|Microsoft Teams dient zum Speichern von Dateien, auf die über den Client zugegriffen wird.|Teams speichert Dateien, die in einer SharePoint Online-Dokumentbibliothek auf den Client hochgeladen wurden. Auf die Dateien kann weiterhin über SharePoint Online zugegriffen werden. Schulen Sie Benutzer im Hinblick auf Dateispeicherorte in SharePoint Online.|
|Für die allgemeine Kommunikation und die Einstufung der Vorfallsverwaltung werden Microsoft Teams-Telefonkonferenzen verwendet.|Richten Sie eine Backup-Konferenzlösung bei einem Drittanbieter ein.|
|VoIP-Telefone werden als sekundäre Kommunikationsmethode verwendet.|Implementieren Sie Nicht-VoIP-Telefone für Festnetztelefonate, insbesondere für Netzwerk- und Service-Rechenzentren während Vorfällen. Fügen Sie die Mobiltelefonnummer der Mitarbeiter zum Unternehmensverzeichnis hinzu, damit wichtige Mitarbeiter über das Mobilfunknetz kontaktiert werden können.|
|OneDrive for Business wird für Dateispeicherung und Benutzerproduktivität verwendet. [Dateien bei Bedarf](https://techcommunity.microsoft.com/t5/Microsoft-OneDrive-Blog/OneDrive-Files-On-Demand-For-The-Enterprise/ba-p/117234) wird so konfiguriert, dass Speicherplatz auf lokalen Benutzer Laufwerken freigegeben wird.|Die OneDrive-Synchronisierung stellt Gruppenrichtlinien bereit, mit denen Administratoren festlegen können, dass bestimmte Inhalte lokal synchronisiert werden müssen oder bei Bedarf Speicherplatz freigegeben wird. Um das Risiko zu minimieren, dass auf ein Dokument nicht zugegriffen werden kann, konfigurieren Sie diese Richtlinie so, dass wichtige Dokumente lokal synchronisiert werden. Schulen Sie die Benutzer dahingehend, dass die Einstellung „Immer behalten auf diesem Gerät“ für wichtige Dokumente angewendet wird.|
|Die Kommunikation von Geschäftsunterbrechungen an Kunden und Lieferanten erfolgt über Exchange Online.|Öffentliche soziale Netzwerke von Drittanbietern können als alternative Massenkommunikationsmethode verwendet werden.

## <a name="leveraging-mobile-app-access"></a>Nutzen des Zugriffs per mobiler App

Da die Nutzung mobiler Geräte weiter stark gewachsen ist, gibt es neue Möglichkeiten, um in Verbindung zu bleiben. Mobile Microsoft 365-Anwendungen können ein wichtiger Bestandteil Ihrer Strategie für die Ausfallsicherheit sein. Da diese Anwendungen über das Mobilfunknetz eine Verbindung mit Clouddiensten herstellen, sind sie nicht von der Netzwerkinfrastruktur Ihrer Organisation abhängig.

Verwenden wir beispielsweise Outlook. Benutzer können je nach verwendeter E-Mail-App eine Verbindung mit ihren Exchange Online-Postfächern über unterschiedliche Netzwerkprotokolle (HTTPS oder MAPI) herstellen. Wenn es einen Dienstvorfall im Zusammenhang mit einem dieser Protokolle gibt, z. B. MAPI, das vom Desktopclient verwendet wird, können ihre Benutzer nach wie vor über die mobile Outlook-App oder Outlook im Web auf ihre Postfächer zugreifen.
  
Wenn Sie sich entscheiden, Benutzern das Herstellen einer Verbindung mit Microsoft 365-Diensten über ihre mobilen Geräte zu erlauben, können Sie Microsoft Intune verwenden, um diese Geräte sicher zu konfigurieren und zu verwalten. Nachdem die Benutzerkonten und -geräte in Ihrer mobilen Verwaltungslösung registriert wurden, müssen Sie sicherstellen, dass die Apps heruntergeladen und konfiguriert wurden.
