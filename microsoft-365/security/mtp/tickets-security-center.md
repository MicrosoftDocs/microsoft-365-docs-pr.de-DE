---
title: Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center
description: Informationen zum Erstellen und Nachverfolgen von Tickets in ServiceNow im Microsoft 365 Security Center.
keywords: Sicherheit, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, ServiceNow, Tickets, Aufgaben
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: bd5bf8533d38337c063acdf0dda073e4961e416a
ms.sourcegitcommit: 787b198765565d54ee73972f664bdbd5023d666b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/24/2020
ms.locfileid: "46867245"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center

Das [Microsoft 365-Sicherheitscenter](overview-security-center.md) wurde erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. [Erfahren Sie mehr über ServiceNow](https://www.servicenow.com/)

Im Sicherheitscenter können Sicherheitsadministratoren eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen. Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden. Verfolgen Sie Tickets auf der Startseite des Sicherheitscenters und ServiceNow.

- [**Informationen zu Voraussetzungen, Datenaustausch und Problembehandlung**](tickets.md)
- **Verwalten von ServiceNow-Tickets im Compliance Center** (demnächst verfügbar)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Verbinden von Microsoft 365 Security Center mit ServiceNow

Navigieren Sie zur Microsoft 365-Sicherheitscenter-Startseite, um die ServiceNow-Verbindungskarte anzuzeigen.

![Verwenden Sie ServiceNow](../../media/do-you-use-servicenow-250.png)

Wählen Sie "mit ServiceNow verbinden" aus, um die ServiceNow-Setup Seite zu öffnen. Befolgen Sie die Anweisungen, um die Microsoft 365-Connector-APP zu autorisieren.

> [!NOTE]
> Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben. Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.

Nachdem Sie die Anweisungen befolgt und die Verbindung autorisiert haben, zeigen Sie den Verbindungsstatus auf der Seite Microsoft 365 Security Center Connection und in der ServiceNow Microsoft 365 Ticketing Connector App Experience an. Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.

### <a name="troubleshooting"></a>Problembehandlung

Erfahren Sie häufig auftretende Fehler im Verbindungsprozess und wie Sie sie entschärfen können, im [Abschnitt Problembehandlung](tickets.md#troubleshooting).

## <a name="create-a-task-and-share-it-to-servicenow"></a>Erstellen einer Aufgabe und freigeben für ServiceNow

Nachdem die Integration eingerichtet wurde, erstellen Sie ServiceNow-Aufgaben basierend auf bestimmten [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktionen. Wechseln Sie zur Aktion sichere Ergebnisverbesserung im Microsoft 365 Security Center, und wählen Sie dann **Freigeben**aus. Eine der Dropdownoptionen ist ServiceNow.

Es wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können. Wenn alle erforderlichen Felder ausgefüllt sind, senden Sie die Aufgabe an ServiceNow.

Die Aufgabe ist in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung sichtbar.

## <a name="track-tickets"></a>Nachverfolgen von Tickets

Nachdem ServiceNow Change Management-und Incident Management-Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt. Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.

![ServiceNow Change Management-Tickets](../../media/change-management-375.png)  ![ServiceNow Incident Management Tickets](../../media/incident-management-375.png)

Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus. Entfernen Sie von dort die aktuelle ServiceNow-Verbindung, und passen Sie die Ticket Statusnamen an.

Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.

## <a name="resources"></a>Ressourcen

- [Informationen zu Voraussetzungen, Datenaustausch und Problembehandlung](tickets.md)
- [Microsoft-Sicherheitsbewertung](microsoft-secure-score.md)