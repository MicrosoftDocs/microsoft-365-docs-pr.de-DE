---
title: Integrieren von ServiceNow-Tickets in das Microsoft 365 Security Center und Compliance Center
description: Informationen zum Erstellen und Nachverfolgen von Tickets in ServiceNow im Microsoft 365 Security Center und Compliance Center.
keywords: Sicherheit, Microsoft 365, M365, Compliance, Compliance Center, Sicherheitscenter, ServiceNow, Tickets, Aufgaben, Schnee, Verbindung
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
ms.openlocfilehash: d258bf3ec4c04eafd22e850329ca925b4c974e94
ms.sourcegitcommit: 41bc923bb31598cea8f02923792c1cd786e39616
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45086667"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>Integrieren von ServiceNow-Tickets in das Microsoft 365 Security Center und Compliance Center

[!include[Prerelease information](../includes/prerelease.md)]

ServiceNow ist eine beliebte Cloud Computing-Plattform, mit der Unternehmen digitale Workflows für Unternehmensvorgänge verwalten können. Ihre now-Plattform umfasst IT-Workflows, Mitarbeiter Workflows und Kunden Workflows. [Erfahren Sie mehr über ServiceNow](https://www.servicenow.com/)

Microsoft hat eine Partnerschaft mit ServiceNow getroffen, um IT-Administratoren die Verwaltung Ihrer Tickets und Aufgaben auf beiden Plattformen zu erleichtern. Das [Microsoft 365 Security Center](overview-security-center.md) und das [Microsoft 365 Compliance Center](https://docs.microsoft.commicrosoft-365/compliance/microsoft-365-compliance-center) werden erweitert, sodass Tickets in ServiceNow nativ erstellt und nachverfolgt werden können.

- [**Verwalten von ServiceNow-Tickets im Sicherheitscenter**](tickets-security-center.md)
- **Verwalten von ServiceNow-Tickets im Compliance Center** (demnächst verfügbar)

## <a name="prerequisites"></a>Voraussetzungen

Zugriff auf das Microsoft 365 Security Center oder Compliance Center und eine ServiceNow-Instanz mit:  

* Version von Kingston oder höher
* Administrator-Hi-Anmeldeinformationen
* Verfügen über Administratorrechte für die Zielanbieter Instanz

ServiceNow empfiehlt Benutzern, die Standardeinstellungen in ihrer ServiceNow-Instanz beizubehalten. Anpassungen können beim Abschließen der Installationsprüfliste und der Integration mit dem Microsoft 365 Security Center zu Fehlern führen.

## <a name="data-exchange"></a>Datenaustausch

Wenn Sie das Microsoft 365 Security Center oder das Compliance Center mit ServiceNow verbinden, erhält Microsoft die folgenden zusätzlichen Daten:

* Name der ServiceNow-Instanz
* ServiceNow-Client-ID
* Geheimer ServiceNow-Client
* ServiceNow-Zugriffs & Aktualisierungstoken

Wenn Sie ein ServiceNow-Ticket im Microsoft 365 Security Center oder im Compliance Center erstellen, werden die folgenden Daten an ServiceNow gesendet:

* Benutzer-ID, die die Ticketerstellung initiiert
* Aufgabenname
* Aufgabenbeschreibung
* Priorität
* Fälligkeitsdatum
* Empfehlungsquelle (Benutzer Empfehlung oder Microsoft-Empfehlung)
* Empfehlungskategorie (Geräte, Daten, apps, Identität, Infrastruktur)

## <a name="connect-to-servicenow"></a>Herstellen einer Verbindung mit ServiceNow

Informationen zum Herstellen einer Verbindung mit ServiceNow finden Sie unter [Erstellen und Nachverfolgen von ServiceNow-Tickets im Microsoft 365 Security Center](tickets-security-center.md) . Eine Verbindung mit dem Microsoft 365 Compliance Center wird in Kürze verfügbar sein.

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

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>Überprüfen der OAuth-Entität, die für Microsoft 365 Security & Compliance Connector erstellt wurde

Wechseln Sie zur Tabelle Anwendungs Registrierungstabellen (**Menü > System OAuth > Anwendungsregistrierung**) in ServiceNow, und suchen Sie nach der von Ihnen erstellten OAuth-Entität mit dem Namen, den Sie Ihr zugewiesen haben.

### <a name="logging-in-as-the-integration-user"></a>Anmelden als Integrationsbenutzer

Bevor Sie die Verbindung zwischen dem Microsoft 365 Security Center und ServiceNow autorisieren, müssen Sie sicherstellen, dass Sie den Benutzernamen und das Kennwort für die Integration verwenden, die Sie in den Installationsschritten erstellt haben. Verwenden Sie Ihre persönlichen Anmeldeinformationen nicht.

1. Wechseln Sie zur Autorisierungs Seite in ServiceNow.
2. Wenn Sie mit Ihren persönlichen Anmeldeinformationen angemeldet sind, wählen Sie den Link **nicht** in der rechten oberen Ecke aus.
3. Melden Sie sich bei ServiceNow als der Integrationsbenutzer an, den Sie zuvor in der Installationsprüfliste erstellt haben.  
4. Wählen Sie auf der Seite ServiceNow die Option **zulassen** aus, die fragt, ob der Security + Compliance-Konnektor eine Verbindung mit Ihrem ServiceNow-Konto herstellen kann.
5. Fahren Sie mit den Setupschritten fort.

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>Überprüfen des Integrations Benutzers, der mit der Installationsprüfliste für Microsoft 365 Security & Compliance Connector erstellt wurde

Wechseln Sie zu Benutzertabelle **(Menü > Benutzerverwaltung > Benutzer**) in ServiceNow, und suchen Sie den von Ihnen erstellten Integrationsbenutzer mit dem Namen, den Sie ihm zugewiesen haben.

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

### <a name="ip-filtering"></a>IP-Filterung

Wenn Sie die IP-Filterung aktiviert haben, müssen Sie möglicherweise explizit IP-Adressen zulassen. Informationen zum Zulassen von IP-Bereichen in ServiceNow finden Sie unter [IP Address Access Control](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) . Eine Liste der zulässigen IP-Adressen finden Sie unter [Azure IP Ranges and Service Tags-Public Cloud](https://www.microsoft.com/en-us/download/details.aspx?id=56519) .

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>Die Installation ist abgeschlossen, es werden jedoch keine Tickets angezeigt und können nicht freigegeben werden

Wenn die Installations-und Setupschritte abgeschlossen wurden, die ServiceNow-Karten jedoch nicht auf der Startseite angezeigt werden und nicht von Microsoft Secure Score an ServiceNow freigegeben werden können, überprüfen Sie den Status der Seite Bereitstellung unter https://security.microsoft.com/ticketProvisioning . Wählen Sie **autorisieren** und zur Startseite zurückkehren. Die Karten sollten angezeigt werden.

## <a name="resources"></a>Ressourcen

- [Verwalten von ServiceNow-Tickets im Sicherheitscenter](tickets-security-center.md)