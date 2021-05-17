---
title: Microsoft 365 Mandantenisolation in microsoft Graph und Delve
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise Microsoft 365 Mandantenisolation in der Office Graph und in Delve.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: c029834c8a914b4e072de847fc4c3a3dde7790c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/02/2020
ms.locfileid: "47332388"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Mandantenisolation in microsoft Graph und Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Mandantenisolation im Microsoft Graph

Microsoft [Graph](https://developer.microsoft.com/graph) modelliert Aktivitäten in Microsoft 365-Diensten, einschließlich Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory und mehr sowie in externen Diensten, z. B. anderen Microsoft-Dienste- oder Drittanbieterdiensten. Microsoft Graph werden in allen Bereichen Microsoft 365. Die Microsoft-Graph stellt eine Sammlung von Inhalten und Aktivitäten sowie die Beziehungen zwischen ihnen dar, die in der gesamten Office werden. Es verwendet ausgeklügelte Maschinelles Lernen, um Personen mit den relevanten Inhalten, Unterhaltungen und Personen in ihrer Umgebung zu verbinden. Beispielsweise verfügt der Mandantenindex in SharePoint Online über einen Microsoft Graph-Index, der zum Verarbeiten von Delve-Abfragen verwendet wird, das Analyseverarbeitungsmodul in SharePoint Online wird zum Speichern von Signalen und zum Berechnen von Erkenntnissen verwendet, und Exchange Online berechnet den Empfängercache jedes Benutzers als Eingabe in die Mandantenanalyse.

Die Microsoft-Graph enthält Informationen zu Unternehmensobjekten, z. B. Personen und Dokumente, sowie die Beziehungen und Interaktionen zwischen diesen Objekten. Die Beziehungen und Interaktionen werden als Kanten *dargestellt.* Die Microsoft Graph nach Mandant segmentiert, so dass Kanten nur zwischen Knoten *in* demselben Mandanten vorhanden sein können. Ein *Knoten* ist eine Entität mit einem URI (Uniform Resource Identifier), einem Knotentyp, einer Zugriffssteuerungsliste und einer Reihe von Facets, die *Metadaten und* Kanten enthalten. Jeder Knoten verfügt über zugeordnete Metadaten und Kanten, die wie im Common Knowledge Model in *Facets* angeordnet sind. *Metadaten* sind benannte Eigenschaften, die auf einem Knoten gespeichert sind und für die Suche, Filterung oder Analyse innerhalb der Microsoft-Graph. Ein *Facet* ist eine logische Sammlung von Metadaten und Kanten auf einem Knoten. Jedes Facet beschreibt einen Aspekt eines Knotens. 

Die Microsoft-Graph führt nicht alle Daten in ein einzelnes Repository. stattdessen werden Metadaten und Beziehungen zu Daten gespeichert, die an anderer Stelle gespeichert werden. Das Microsoft Graph besteht aus mehreren Datenspeichern und Verarbeitungskomponenten:

- Die Mandanten-Graph Store bietet Massenspeicher, der für effiziente Analysen optimiert ist.
- Der Aktive Inhaltscache bietet schnellen zufälligen Zugriff auf aktive Knoten und Kanten, um die Benutzererfahrung zu ermöglichen.
- Der Eingaberouter benachrichtigt interne und externe Komponenten über Änderungen am Mandantendiagramm.

Analysen innerhalb jeder Arbeitsauslastung liefern Einblicke, die für die mandantenweiten Berechnungen relevant sind, und pushen sie an das Mandantendiagramm. Mandantenanalyse gründe für alle Aktivitäten in einem Mandanten, um Einblicke in Verhaltensmuster zu gewinnen. Beispielsweise berechnet Exchange Online den Empfängercache für jeden Benutzer mit Analysen, die effizient auf das Postfach der einzelnen Benutzer gründen. Diese Benutzeranalysen erzeugen eine Reihe von *RecipientCache Edges* für jede Person, die wiederum an das Mandantendiagramm weitergeleitet werden. Dadurch wird die Analyseverarbeitung so nah wie möglich an den Quelldaten gespeichert.

## <a name="tenant-isolation-in-delve"></a>Mandantenisolation in Delve

Wie bereits erwähnt, bietet die Microsoft Graph Erfahrungen, die Personen dabei unterstützen, aktuelle Aktivitäten in ihrem Unternehmen zu entdecken und gemeinsam zu bearbeiten, und bietet eine entitätszentrierte Plattform für Analysen, die über Inhalte und Aktivitäten in Arbeitsauslastungen und darüber hinaus Microsoft 365. Delve ist die erste derartige Erfahrung, die von microsoft Graph.
Delve ist eine Microsoft 365, die Inhalte von Microsoft 365 und Yammer Enterprise Microsoft 365 über die Microsoft-Graph. Die Weberfahrung zeigt Daten als unterschiedliche Boards mit jeweils einem bestimmten Thema an, z. B. *Trending around me* oder *Modified by me*. Jedes Board besteht aus mehreren Dokumentkarten, auf der der Zusammenfassungstext und ein Bild aus dem Dokument angezeigt werden. Mit der Karte können Benutzer beispielsweise das Dokument oder eine Yammer für das Dokument öffnen. Es gibt eine Seite für jede Person in einem Microsoft 365-Mandanten, auf der die relevantesten Dokumente für diese Person angezeigt werden, und Symbole, die Exchange Online oder Skype for Business für die Interaktion mit dieser Person aufrufen können. Da Delve auf der Microsoft Graph-API basiert, ist sie an die mandantenbasierte Isolation dieser API gebunden.