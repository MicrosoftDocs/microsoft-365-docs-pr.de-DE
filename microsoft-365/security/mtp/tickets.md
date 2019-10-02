---
title: Erstellen und Nachverfolgen von Tickets über ServiceNow
description: Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Auf diese Weise können Sicherheitsadministratoren eine sichere Bewertungs Empfehlung direkt an ServiceNow senden und ein Ticket erstellen.
keywords: Sicherheit, Microsoft 365, M365, sicheres Ergebnis, Sicherheitscenter, ServiceNow, Tickets, Aufgaben
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
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
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350330"
---
# <a name="manage-tickets-through-servicenow"></a>Verwalten von Tickets über ServiceNow

Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Auf diese Weise können Sicherheitsadministratoren eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen. Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.

## <a name="prerequisites"></a>Voraussetzungen

Sie haben Zugriff auf das Microsoft 365 Security Center und eine ServiceNow-Instanz mit:  

* Version von Kingston oder höher
* Administrator-Hi-Anmeldeinformationen
* Verfügen über Administratorrechte für die Zielanbieter Instanz

ServiceNow empfiehlt Benutzern, die Einstellungen (Standardeinstellung) in ihrer ServiceNow-Instanz aus dem Feld zu halten.  Das Ausführen von Anpassungen kann zu Fehlern beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center führen.

## <a name="data-exchange"></a>Datenaustausch

Wenn Sie das Microsoft 365 Security Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:

* Name der ServiceNow-Instanz
* ServiceNow-Client-ID
* Geheimer ServiceNow-Client
* ServiceNow-Zugriffs #a0 Aktualisierungstoken

Wenn Sie ein ServiceNow-Ticket aus dem Microsoft 365 Security Center erstellen, werden die folgenden Daten an ServiceNow gesendet:

* Benutzer-ID, die die Ticketerstellung initiiert
* Aufgabenname
* Aufgabenbeschreibung
* Priorität
* Fälligkeitsdatum
* Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)
* Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>Verbinden von Microsoft 365 Security Center mit ServiceNow

Navigieren Sie zur Microsoft 365 Security Center-Startseite, auf der Sie eine Karte sehen, in der Sie gefragt werden, ob Sie ServiceNow verwenden.

![Verwenden Sie ServiceNow](../images/do-you-use-servicenow-250.png)

Von dort aus werden Sie an die ServiceNow-Setup Seite gesendet, auf der Sie die Anweisungen zum Autorisieren der Microsoft 365 Connector-App befolgen.

Stellen Sie beim Autorisieren der Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow sicher, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten und nicht in Ihren persönlichen Anmeldeinformationen erstellt haben.

Nachdem Sie den Anweisungen folgen und die Verbindung autorisiert haben, können Sie den Verbindungsstatus sowohl auf der Microsoft 365 Security Center-Verbindungsseite als auch in der APP-Erfahrung von ServiceNow Microsoft 365 Ticketing Connector anzeigen. Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.

## <a name="create-a-task-and-share-it-to-servicenow"></a>Erstellen einer Aufgabe und freigeben für ServiceNow

Nachdem die Integration eingerichtet wurde, können Sie ServiceNow-Aufgaben basierend auf bestimmten Microsoft Secure Score-Verbesserungs Aktionen erstellen. Wechseln Sie zu einer Verbesserungs Aktion in Secure Score im Microsoft 365 Security Center-Portal, und wählen Sie das Symbol "freigeben" aus. Eine der Dropdownoptionen ist ServiceNow.

![ServiceNow-Freigabe in sicherer Punktzahl](../images/servicenow-share.png)

Anschließend wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können. Sobald alle erforderlichen Felder ausgefüllt sind, können Sie die Aufgabe an ServiceNow senden.

Die Aufgabe wird in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung angezeigt.

## <a name="track-tickets"></a>Nachverfolgen von Tickets

Nachdem ServiceNow Change Management und Incident Management Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt. Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.

![ServiceNow Change Management-Tickets](../images/change-management-375.png)  ![ServiceNow Incident Management Tickets](../images/incident-management-375.png)

Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus. Von dort aus können Sie die aktuelle ServiceNow-Verbindung entfernen und Ticket Statusnamen anpassen.

Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Ich erhalte einen Fehler im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)

**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle verweigert.

Unsere App geht davon aus, dass Administratoren in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen können. Dieser Fehler kann aufgrund einer Anpassung Ihrer Instanz von ServiceNow verursacht werden, wodurch die Benutzer eingeschränkt werden, die OAuth-Entitäten erstellen/lesen können. ServiceNow empfiehlt Benutzern, die Funktionalität außerhalb der Box zu halten (Standardeinstellung).

Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:

* Label = Anwendungs Registrierungen
* Name = oauth_entity
* Zugänglich von = alle Anwendungsbereiche
* Can read = Kontrollkästchen aktiviert

**ServiceNow empfiehlt Benutzern, die Funktionalität außerhalb der Box zu halten (Standardeinstellung).**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Wie kann ich die OAuth-Entität überprüfen, die für Microsoft 365 Security #a0 Compliance Connector erstellt wurde?

Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (Menü #a0 System OAuth #a1 Anwendungsregistrierung) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität (Name, den Sie Ihr zugewiesen haben).

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Wie kann ich den Integrationsbenutzer überprüfen, der in Schritt 2 der Installationsprüfliste für Microsoft 365 Security #a0 Compliance Connector erstellt wurde?

Wechseln Sie zu Benutzertabelle (Menü #a0 Benutzerverwaltung #a1 Benutzer) in ServiceNow, und suchen Sie nach dem von Ihnen erstellten Integrationsbenutzer (Name, den Sie ihm zugewiesen haben).

Stellen Sie beim Autorisieren der Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow sicher, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten und nicht in Ihren persönlichen Anmeldeinformationen erstellt haben.

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>Ich habe die Installation abgeschlossen und Schritte eingerichtet, aber ich kann die ServiceNow-Karten nicht auf der Startseite anzeigen und das Symbol "freigeben" in Microsoft Secure Score nicht sehen.

Überprüfen Sie den Status der Seite "Übersicht", indem https://security.microsoft.com/ticketProvisioningSie zu wechseln. Wählen Sie **Speichern** und zur Startseite zurückkehren aus. Die Karten sollten angezeigt werden.
