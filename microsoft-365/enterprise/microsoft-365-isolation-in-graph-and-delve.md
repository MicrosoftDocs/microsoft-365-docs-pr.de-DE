---
title: Microsoft 365-Mandanten Isolierung in Microsoft Graph und Tauchen
ms.author: josephd
author: JoeDavies-MSFT
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
description: In diesem Artikel finden Sie eine Erläuterung der Funktionsweise der Microsoft 365-Mandanten Isolierung in Office Graph und in "vertiefen".
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab9b216656e076cc3ba02a4ef6c75b25b94547fe
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690617"
---
# <a name="microsoft-365-tenant-isolation-in-the-microsoft-graph-and-delve"></a>Microsoft 365-Mandanten Isolierung in Microsoft Graph und Tauchen

## <a name="tenant-isolation-in-the-microsoft-graph"></a>Mandanten Isolierung in Microsoft Graph

[Microsoft Graph](https://developer.microsoft.com/graph) modelliert Aktivitäten in Microsoft 365-Diensten, einschließlich Exchange Online, SharePoint Online, jammern, Skype for Business, Azure Active Directory und mehr sowie in externen Diensten wie anderen Microsoft-Diensten oder Drittanbieterdiensten. Microsoft Graph-Komponenten werden in Microsoft 365 verwendet. Microsoft Graph stellt eine Sammlung von Inhalten und Aktivitäten sowie die Beziehungen zwischen Ihnen dar, die in der gesamten Office-Suite stattfinden. Es verwendet ausgefeilte maschinelle Lerntechniken, um Personen mit den relevanten Inhalten, Unterhaltungen und Personen um Sie zu verbinden. Beispielsweise verfügt der Mandanten Index in SharePoint Online über einen Microsoft Graph-Index, der zur Bereitstellung von vertieften Abfragen verwendet wird, das Analyse Verarbeitungsmodul in SharePoint Online dient zum Speichern von Signalen und zum Berechnen von Einblicken, und Exchange Online berechnet den Empfängercache des Benutzers als Eingabe in die Mandanten Analyse.

Das Microsoft Graph-Objekt enthält Informationen zu Enterprise-Objekten wie Personen und Dokumenten sowie zu den Beziehungen und Interaktionen zwischen diesen Objekten. Die Beziehungen und Interaktionen werden als *Kanten*dargestellt. Microsoft Graph wird nach Mandanten segmentiert, sodass Kanten nur zwischen *Knoten* im gleichen Mandanten vorhanden sein können. Ein *Knoten* ist eine Entität mit einem Uniform Resource Identifier (URI), Knotentyp, Zugriffssteuerungsliste und einer Reihe von Facetten, die *Metadaten* und Ränder enthalten. Jedem Knoten sind Metadaten und Kanten zugeordnet, die in *Facets* wie im allgemeinen Wissens Modell angeordnet sind. *Metadaten* sind benannte Eigenschaften, die auf einem Knoten gespeichert sind, der zum Suchen, Filtern oder analysieren in Microsoft Graph verwendet werden kann. Ein *Facet* ist eine logische Auflistung von Metadaten und Rändern auf einem Knoten. Jedes facet beschreibt einen Aspekt eines Knotens. 

Microsoft Graph bringt nicht alle Daten in ein einzelnes Repository; Vielmehr werden Metadaten und Beziehungen zu Daten gespeichert, die an anderer Stelle Leben. Microsoft Graph besteht aus mehreren Daten speichern und Verarbeitungskomponenten:

- Der Mandanten Graph-Speicher bietet einen optimierten Massenspeicher für effiziente Analysen.
- Der aktive Inhalts Cache bietet schnellen Zufallszugriff auf aktive Knoten und Kanten, um Benutzeroberflächen zu steuern.
- Der Eingabe Router benachrichtigt die internen und externen Komponenten von Änderungen am Mandanten Graph.

Analysen innerhalb jeder Arbeitsauslastung leiten Einblicke in die Mandanten weiten Berechnungen ab und drücken Sie auf das Mandanten Diagramm. Mandanten Analyse Gründe für alle Aktivitäten in einem Mandanten, um Einblicke in Verhaltensmuster zu erzeugen. Exchange Online berechnet beispielsweise den Empfängercache für jeden Benutzer mit Analysen, die das Postfach jedes Benutzers effizient begründen. Diese benutzerspezifische Analyse erzeugt eine Reihe von *RecipientCache-Rändern* für jede Person, die wiederum in das Mandanten Diagramm verschoben werden. Dadurch bleibt die Analyse Verarbeitung so weit wie möglich an den Quelldaten.

## <a name="tenant-isolation-in-delve"></a>Mandanten Isolierung in "vertiefen"

Wie bereits erwähnt, macht Microsoft Graph Erfahrungen, die es Benutzern ermöglichen, aktuelle Aktivitäten in Ihrem Unternehmen zu entdecken und zusammenzuarbeiten, und stellt eine Entitäts zentrierte Plattform für Analysen zur Verfügung, um Inhalte und Aktivitäten über Arbeitslasten hinweg und über Microsoft 365 hinaus zu überdenken. Vertiefen ist die erste solche Erfahrung, die von Microsoft Graph angetrieben wird.
Vertiefen ist eine Microsoft 365-Weberfahrung, die Inhalte von Microsoft 365 und jammern von Enterprise auf Microsoft 365-Benutzer über das Microsoft Graph-Oberfläche. Das Weberlebnis zeigt Daten als unterschiedliche Karten an, die jeweils ein bestimmtes Thema aufweisen, beispielsweise *um mich herum* oder *von mir modifiziert*. Jedes Board besteht aus mehreren Dokumentkarten, die einen Zusammenfassungstext und ein Bild aus dem Dokument anzeigen. Die Karte ermöglicht Benutzern das Öffnen des Dokuments oder eine Jammer Seite für das Dokument. Es gibt eine Seite für jede Person in einem Microsoft 365-Mandanten, in der die relevantesten Dokumente für diese Person angezeigt werden, sowie Symbole, mit denen Exchange Online oder Skype for Business für die Interaktion mit dieser Person aufgerufen werden können. Da Sie auf der Microsoft Graph-API basieren, ist Sie an die Mandanten basierte Isolierung dieser API gebunden.