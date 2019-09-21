---
title: Arbeiten mit Kommunikationen in Advanced eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Mit Advanced eDiscovery können Sie den Workflow für rechtliche Aufbewahrungs Benachrichtigungen einfach verwalten, um Benachrichtigungsverwalter in rechtlichen Ermittlungen zu benachrichtigen.
ms.openlocfilehash: 67cd9266fe8e7bc3c476eac39497a3a2a0fe0c9e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081577"
---
# <a name="work-with-communications-in-advanced-ediscovery"></a>Arbeiten mit Kommunikationen in Advanced eDiscovery

Advanced eDiscovery ermöglicht juristischen Abteilungen, Ihre Prozesse bei der Verfolgung und Verteilung von Benachrichtigungen über rechtliche Aufbewahrungsfristen zu vereinfachen. Das Tool "Depotbank-Kommunikation" ermöglicht es juristischen Abteilungen, den gesamten rechtlichen Aufbewahrungs Prozess, von erst Benachrichtigungen über Erinnerungen bis hin zu Eskalationen, an einem einzigen Ort zu verwalten und zu automatisieren.

## <a name="what-is-a-legal-hold-notification"></a>Was ist eine rechtliche Aufbewahrungs Benachrichtigung?

Eine rechtliche Aufbewahrungspflicht (auch als *Beweissicherungsverfahren*bezeichnet) ist eine Benachrichtigung, die von der Rechtsabteilung einer Organisation an Mitarbeiter, Kontingente Mitarbeiter oder Verwalter von Daten gesendet wird, die möglicherweise für eine rechtliche Untersuchung relevant sind. Diese Benachrichtigungen weisen Verwalter an, elektronisch gespeicherte Informationen sowie alle Inhalte beizubehalten, die für eine aktive oder bevorstehende Rechtsfrage relevant sein können. Juristische Teams müssen wissen, dass jede Depotbank die angegebenen Anweisungen erhalten, gelesen, verstanden und vereinbart hat.

## <a name="the-legal-hold-notification-process"></a>Benachrichtigungsprozess für Legal Hold

Eine Organisation hat die Pflicht, relevante Informationen beizubehalten, wenn Sie von einer bevorstehenden Rechtsstreitigkeiten oder behördlichen Untersuchung erfahren. Um die Aufbewahrungsanforderungen einer Untersuchung einzuhalten, sollte die Organisation potenzielle Verwalter unverzüglich über ihre Pflicht zur Wahrung relevanter Informationen informieren.

Mit Advanced eDiscovery können Legal Teams ihren rechtlichen Aufbewahrungs Benachrichtigungs Workflow erstellen und anpassen. Das Tool "Depotbank-Kommunikation" ermöglicht es juristischen Teams, die folgenden Hinweise und Workflows zu konfigurieren:

1. **Veröffentlichungshinweis**: eine rechtliche Aufbewahrungsfrist wird durch eine Mitteilung der Rechtsabteilung an Verwalter ausgestellt (oder eingeleitet), die möglicherweise relevante Informationen zum Fall haben. In diesem Hinweis werden die Verwalter angehalten, alle Informationen beizubehalten, die für die Ermittlung möglicherweise erforderlich sind.
   
2.  **Hinweis zur erneuten Veröffentlichung**: in einem Fall müssen Verwalter möglicherweise zusätzliche Inhalte (oder weniger Inhalte) aufbewahren, als zuvor angefordert wurden. In diesem Szenario können Sie den vorhandenen Aufbewahrungs Hinweis aktualisieren und ihn erneut an Verwalter ausgeben.

3.  **Veröffentlichungshinweis**: Sobald ein Problem gelöst ist und die Depotbank nicht mehr einer Aufbewahrungspflicht unterliegt, kann die Depotbank aus dem Fall entlassen werden. Darüber hinaus können Sie die Depotbank darüber informieren, dass Sie nicht mehr für die Aufbewahrung von Inhalten benötigt werden, und Anweisungen zum Fortsetzen ihrer normalen Arbeitsaktivität im Hinblick auf Ihre Daten geben.

4. **Erinnerungen und Eskalationen**: in einigen Fällen genügt ein Hinweis nur, um gesetzliche Ermittlungsanforderungen zu erfüllen. Mit jeder Benachrichtigung können Legal Teams einen Mahn-und Eskalations Workflow für die automatische Nachverfolgung mit nicht reagierenden Depotstellen planen.

    - **Erinnerungen**: Nachdem ein rechtlicher Aufbewahrungs Vermerk für eine Gruppe von Verwaltern ausgestellt oder erneut ausgestellt wurde, kann eine Organisation Erinnerungen einrichten, um nicht reagierende depotverwalter zu warnen.

    - **Eskalationen**: Wenn eine Depotbank auch nach einer Reihe von Erinnerungen über einen bestimmten Zeitraum nicht mehr reagiert, kann das juristische Team einen Eskalations Workflow einrichten, um nicht reagierende Verwalter und deren Vorgesetzten zu benachrichtigen.

## <a name="role-groups-and-permissions"></a>Rollengruppen und Berechtigungen 

Zugelassene Teams können Ihre Fall Aktivitäten mithilfe von eDiscovery-bezogenen Rollengruppen und Berechtigungen im Security #a0 Compliance Center Steuern und trennen. 

Zum Erstellen und Verwalten von Benachrichtigungen über rechtliche Aufbewahrungsfristen muss ein Benutzer Teil der folgenden Rollengruppen sein:

- **eDiscovery Manager** – Mitglieder dieser Rollengruppe können eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Aufbewahrungen und inhaltsspeicherorte in der Warteschleife platzieren, Benachrichtigungen für legale Aufbewahrungen verwalten, Inhalts Suchvorgänge erstellen und bearbeiten, die einem Fall zugeordnet sind, die Ergebnisse einer Inhaltssuche exportieren und Suchergebnisse für die Analyse in Advanced vorbereiten. eDiscovery. In dieser Rollengruppe gibt es zwei Untergruppen. Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

  - **eDiscovery-Manager** -kann die eDiscovery-Fälle anzeigen und verwalten, in denen Sie erstellt werden oder Mitglied von sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falles hinzufügt, kann der zweite eDiscovery-Manager den Fall nicht auf der eDiscovery-Seite im Security #a0 Compliance Center anzeigen oder öffnen. eDiscovery-Manager können auch auf ihre Fälle in Advanced eDiscovery zugreifen, um Analyseaufgaben durchzuführen.

  - **eDiscovery-Administrator** -kann alle Fall Verwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen:
    
    - Anzeigen aller Fälle, die auf der Seite eDiscovery-Fälle aufgeführt sind.
    - Verwalten Sie alle Fälle in der Organisation, nachdem Sie sich selbst als Mitglied der Anfrage hinzugefügt haben.
    - Zugriffs Fall Daten in Advanced eDiscovery für jeden Fall in der Organisation.

Weitere Informationen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen im Security #a0 Compliance Center](assign-ediscovery-permissions.md).