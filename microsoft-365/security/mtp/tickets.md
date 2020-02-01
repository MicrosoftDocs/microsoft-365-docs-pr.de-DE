---
title: Erstellen und Nachverfolgen von Tickets über ServiceNow
description: Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Sicherheitsadministratoren können eine sichere Bewertungs Empfehlung direkt an ServiceNow senden und ein Ticket erstellen.
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
ms.openlocfilehash: 26e227b4b1e8047ca962ca9e65b139bacae55e03
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599992"
---
# <a name="manage-tickets-through-servicenow"></a>Verwalten von Tickets über ServiceNow

Das Microsoft 365-Sicherheitscenter wird erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können. Sicherheitsadministratoren können eine [Microsoft Secure Score](microsoft-secure-score.md) -Verbesserungs Aktion direkt an ServiceNow senden und ein Ticket erstellen. Es können sowohl Incident Management als auch Change Management-Tickets erstellt werden.

## <a name="prerequisites"></a>Voraussetzungen

Sie haben Zugriff auf das Microsoft 365 Security Center und eine ServiceNow-Instanz mit:  

* Version von Kingston oder höher
* Administrator-Hi-Anmeldeinformationen
* Verfügen über Administratorrechte für die Zielanbieter Instanz

ServiceNow empfiehlt Benutzern, die Standardeinstellungen in ihrer ServiceNow-Instanz beizubehalten. Anpassungen können beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center zu Fehlern führen.

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

Navigieren Sie zur Microsoft 365-Sicherheitscenter-Startseite, um die ServiceNow-Verbindungskarte anzuzeigen.

![Verwenden Sie ServiceNow](../images/do-you-use-servicenow-250.png)

Wählen Sie "mit ServiceNow verbinden" aus, um die ServiceNow-Setup Seite zu öffnen. Befolgen Sie die Anweisungen, um die Microsoft 365-Connector-APP zu autorisieren.

> [!NOTE]
> Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben. Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.

Nachdem Sie die Anweisungen befolgt und die Verbindung autorisiert haben, zeigen Sie den Verbindungsstatus sowohl auf der Microsoft 365 Security Center-Verbindungsseite als auch in der APP-Erfahrung von Microsoft 365 Ticketing Connector für den ServiceNow an. Jetzt können Sie mit dem Erstellen von Aufgaben beginnen.

## <a name="create-a-task-and-share-it-to-servicenow"></a>Erstellen einer Aufgabe und freigeben für ServiceNow

Nachdem die Integration eingerichtet wurde, erstellen Sie ServiceNow-Aufgaben basierend auf bestimmten Microsoft Secure Score-Verbesserungs Aktionen. Wechseln Sie zu einer Verbesserungs Aktion in Secure Score im Microsoft 365 Security Center-Portal, und wählen Sie das Symbol "freigeben" aus. Eine der Dropdownoptionen ist ServiceNow.

![ServiceNow-Freigabe in sicherer Punktzahl](../images/servicenow-share.png)

Es wird eine Aufgabe generiert, in der Sie die Priorität festlegen und den Namen, die Beschreibung oder das Fälligkeitsdatum bearbeiten können. Wenn alle erforderlichen Felder ausgefüllt sind, senden Sie die Aufgabe an ServiceNow.

Die Aufgabe ist in ServiceNow als Microsoft 365 Sicherheits-und Konfigurations Änderungsanforderung sichtbar.

## <a name="track-tickets"></a>Nachverfolgen von Tickets

Nachdem ServiceNow Change Management-und Incident Management-Tickets erstellt wurden, werden diese auf Karten auf der Startseite von Microsoft 365 Security Center angezeigt. Auf diesen Karten können Sie ein Ticket erstellen, alle Tickets anzeigen oder die ServiceNow-Konfiguration verwalten.

![ServiceNow Change Management-Tickets](../images/change-management-375.png)  ![ServiceNow Incident Management Tickets](../images/incident-management-375.png)

Um die ServiceNow-Integration in das Microsoft 365 Security Center erneut zu überwachen oder zu verwalten, wählen Sie auf beiden Karten die Option **Manage ServiceNow Configuration** aus. Entfernen Sie von dort die aktuelle ServiceNow-Verbindung, und passen Sie die Ticket Statusnamen an.

Wenn ServiceNow-Tickets im Microsoft 365 Security Center angezeigt werden, werden Ihre Aufgaben an einer Stelle gespeichert, an der Sie neben den anderen Sicherheits Dashboard-Elementen nachverfolgt und bearbeitet werden können.

## <a name="troubleshooting"></a>Problembehandlung

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>Sie erhalten eine Fehlermeldung im ersten Schritt der Installationsprüfliste (OAuth-Erstellung)

**Fehlermeldung**: der Lesevorgang für "oauth_entity" aus dem Bereich "x_mioms_m365ticket" wurde aufgrund der bereichsübergreifenden Zugriffsrichtlinie der Tabelle verweigert.

Die APP geht davon aus, dass ein Administrator in der ServiceNow-Instanz OAuth-Entitäten erstellen und lesen kann. Dieser Fehler kann aufgrund einer Anpassung Ihrer Instanz von ServiceNow verursacht werden, wodurch die Benutzer eingeschränkt werden, die OAuth-Entitäten erstellen/lesen können.

**ServiceNow empfiehlt Benutzern, die Standardfunktionalität beizubehalten.**

Legen Sie die Tabellen Konfigurationen "Anwendungs Registrierungen" auf "Standard" fest:

* Label = Anwendungs Registrierungen
* Name = oauth_entity
* Zugänglich von = alle Anwendungsbereiche
* Can read = Kontrollkästchen aktiviert

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Überprüfen der OAuth-Entität, die für Microsoft 365 Security #a0 Compliance Connector erstellt wurde

Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (**Menü #a0 System OAuth #a1 Anwendungsregistrierung**) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität mit dem Namen, den Sie Ihr zugewiesen haben.

### <a name="logging-in-as-the-integration-user"></a>Anmelden als Integrationsbenutzer

Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben. Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.

1. Wechseln Sie zur Autorisierungs Seite in ServiceNow.
2. Wenn Sie mit Ihren persönlichen Anmeldeinformationen angemeldet sind, wählen Sie den Link **nicht** in der rechten oberen Ecke aus.
3. Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.  
4. Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.
5. Fahren Sie mit den Setupschritten fort.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Überprüfen des Integrations Benutzers, der mit der Installationsprüfliste für Microsoft 365 Security #a0 Compliance Connector erstellt wurde

Wechseln Sie zu Benutzertabelle **(Menü #a0 Benutzerverwaltung #a1 Benutzer**) in ServiceNow, und suchen Sie den von Ihnen erstellten Integrationsbenutzer mit dem Namen, den Sie ihm zugewiesen haben.

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>Ihr Unternehmen verfügt über ein einmaliges Anmelden, das verhindert, dass Sie sich über das Microsoft 365 Security Center mit ServiceNow verbinden.

Wenn Ihr Unternehmen einmaliges Anmelden aktiviert hat und Sie eine Fehlermeldung erhalten oder die Anmeldung nicht erfolgreich war, führen Sie eine der beiden Lösungen aus.

#### <a name="log-into-servicenow-as-the-integration-user"></a>Melden Sie sich als Integrationsbenutzer bei ServiceNow an.

1. Navigieren Sie zurück zur Autorisierungs Seite in ServiceNow.
2. Klicken Sie in der rechten oberen Ecke auf den Link **Not You** .
3. Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.  
4. Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.
5. Fahren Sie mit den Setupschritten fort.

#### <a name="create-a-security-admin-user"></a>Erstellen eines Sicherheitsadministrator Benutzers

1. Erstellen Sie einen Benutzer mit Sicherheitsadministrator rechten in Azure Active Directory. Der Benutzer benötigt denselben Namen und dieselbe e-Mail-Adresse wie der Integrationsbenutzer, den Sie aus der Installationsprüfliste erstellt haben. Sie können die Sicherheitsadministrator Rolle nach Abschluss der Anmeldung und der Verbindung entfernen.
2. Melden Sie sich beim Microsoft 365 Security Center als dieser Benutzer an, und befolgen Sie die Installationsschritte.

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Die Installation ist abgeschlossen, es werden jedoch keine Tickets angezeigt und können nicht freigegeben werden

Wenn die Installations-und Setupschritte abgeschlossen wurden, die ServiceNow-Karten jedoch nicht auf der Startseite angezeigt werden und nicht von Microsoft Secure Score an ServiceNow freigegeben werden können, überprüfen Sie den Status der https://security.microsoft.com/ticketProvisioningSeite Bereitstellung unter. Wählen Sie **autorisieren** und zur Startseite zurückkehren. Die Karten sollten angezeigt werden.

