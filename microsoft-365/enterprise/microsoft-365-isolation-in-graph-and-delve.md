---
title: Microsoft 365 Mandantenisolation im Microsoft Graph und Delve
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
description: In diesem Artikel finden Sie eine Erläuterung dazu, wie Microsoft 365 Mandantenisolation im Office Graph und in Delve funktioniert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 966f02726a2cce18e30e4d5bc7ab0beb5db51a29
ms.sourcegitcommit: 27addd4dac07926528b788215d2dcd0e46301eb1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53464089"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365 Mandantenisolation im Microsoft Graph und Delve

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Mandantenisolation im Microsoft Graph

Microsoft [Graph](https://developer.microsoft.com/graph) modelliert Aktivitäten in Microsoft 365 Diensten, einschließlich Exchange Online, SharePoint Online, Yammer, Skype for Business, Azure Active Directory und mehr, und in externen Diensten, z. B. anderen Microsoft-Dienste oder Diensten von Drittanbietern. Microsoft Graph-Komponenten werden in Microsoft 365 verwendet. Die Microsoft Graph stellt eine Sammlung von Inhalten und Aktivitäten sowie die Beziehungen zwischen diesen dar, die in der gesamten Office Suite stattfinden. Es verwendet anspruchsvolle Machine Learning-Techniken, um Personen mit den relevanten Inhalten, Unterhaltungen und Personen in ihrer Nähe zu verbinden. For example, the tenant index in SharePoint Online has an Microsoft Graph index that is used to serve Delve queries, the Analytics Processing Engine in SharePoint Online is used to store signals and calculate insights, and Exchange Online calculates each user's recipient cache as input into tenant analytics.

Die Microsoft Graph enthält Informationen zu Unternehmensobjekten, z. B. Personen und Dokumenten, sowie die Beziehungen und Interaktionen zwischen diesen Objekten. Die Beziehungen und Interaktionen werden als *Ränder* dargestellt. Die Microsoft Graph wird nach Mandant segmentiert, sodass Ränder nur zwischen *Knoten* im gleichen Mandanten vorhanden sein können. Ein *Knoten* ist eine Entität mit einem Uniform Resource Identifier (URI), einem Knotentyp, einer Zugriffssteuerungsliste und einer Reihe von Facets, die *Metadaten* und Ränder enthalten. Jedem Knoten sind Metadaten und Ränder zugeordnet, die in *Facets* wie im allgemeinen Wissensmodell angeordnet sind. *Metadaten* sind benannte Eigenschaften, die auf einem Knoten gespeichert sind und zum Suchen, Filtern oder Analysieren innerhalb der Microsoft Graph verwendet werden können. Ein *Facet* ist eine logische Sammlung von Metadaten und Rändern auf einem Knoten. Jedes Facet beschreibt einen Aspekt eines Knotens. 

Die Microsoft Graph bringt nicht alle Daten in ein einziges Repository; Stattdessen werden Metadaten und Beziehungen zu Daten gespeichert, die sich an einem anderen Ort befinden. Die Microsoft Graph besteht aus mehreren Datenspeichern und Verarbeitungskomponenten:

- Die Mandanten-Graph Store bietet Massenspeicher, der für effiziente Analysen optimiert ist.
- Der Aktive Inhaltscache bietet schnellen zufälligen Zugriff auf aktive Knoten und Ränder, um die Benutzererfahrung zu fördern.
- Der Eingaberouter benachrichtigt Komponenten intern und extern über Änderungen am Mandantendiagramm.

Analysen innerhalb der einzelnen Workloads leiten Einblicke ab, die für die mandantenweiten Berechnungen relevant sind, und übertragen sie in das Mandantendiagramm. Mandantenanalysegrundlagen über alle Aktivitäten in einem Mandanten, um Einblicke in Verhaltensmuster zu gewinnen. Beispielsweise berechnet Exchange Online den Empfängercache für jeden Benutzer mit Analysen, die effizient über das Postfach jedes Benutzers führen. Diese Analysen pro Benutzer erzeugen eine Reihe von *RecipientCache-Edges* für jede Person, die wiederum an das Mandantendiagramm übertragen werden. Dadurch bleibt der Großteil der Analyseverarbeitung so nah wie möglich an den Quelldaten.

## <a name="tenant-isolation-in-delve"></a>Mandantenisolation in Delve

Wie bereits erwähnt, unterstützt microsoft Graph Oberflächen, die Personen dabei helfen, aktuelle Aktivitäten in ihrem Unternehmen zu entdecken und daran zusammenzuarbeiten, und bietet eine entitätsorientierte Plattform für Analysen, die über Inhalte und Aktivitäten über Workloads und über Microsoft 365 hinausgeht. Delve ist die erste benutzererfahrung, die von Microsoft Graph unterstützt wird.
Delve ist eine Microsoft 365 Weboberfläche, die Inhalte aus Microsoft 365 anzeigt und Yammer Enterprise, um Benutzer über die Microsoft Graph zu Microsoft 365. Die Weboberfläche zeigt Daten als verschiedene Boards mit jeweils einem bestimmten Thema an, *z. B. "Trending around me"* oder *"Modified by me".* Jedes Board besteht aus mehreren Dokumentkarten, die Zusammenfassungstext und ein Bild aus dem Dokument anzeigen. Auf der Karte können Benutzer z. B. das Dokument oder eine Yammer Seite für das Dokument öffnen. Es gibt eine Seite für jede Person in einem Microsoft 365 Mandanten, die die relevantesten Dokumente für diese Person anzeigt, sowie Symbole, die Exchange Online oder Skype for Business für die Interaktion mit dieser Person aufrufen können. Da Delve auf der Microsoft Graph-API basiert, ist sie an die mandantenbasierte Isolation dieser API gebunden.