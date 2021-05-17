---
title: Einrichten eines Connectors zum Archivieren von Facebook-Daten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Sie & connector im Microsoft 365 Compliance Center einrichten, um & Archivdaten von Facebook Business-Seiten in Microsoft 365.
ms.openlocfilehash: 616466a3af83c1558184526aa463f68c10ef9e70
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921735"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Einrichten eines Connectors zum Archivieren von Facebook-Daten (Vorschau)

Verwenden Sie einen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Daten von Facebook Business-Seiten Microsoft 365. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er (geplant) eine Verbindung mit der Facebook Business-Seite, konvertiert den Inhalt von Facebook-Elementen in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Facebook-Daten importiert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Rechtsstreitigkeiten, Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf die Facebook-Daten anwenden. Wenn z. B. ein Postfach in das Aufbewahrungsverfahren einbehalten oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden die Facebook-Daten beibehalten. Sie können Daten von Drittanbietern mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Facebook-Daten in einem bestimmten Fall Advanced eDiscovery werden. Die Verwendung eines Connectors zum Importieren und Archivieren von Facebook-Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Voraussetzungen für das Einrichten eines Connectors für Facebook Business-Seiten

Führen Sie die folgenden Voraussetzungen aus, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten von den Facebook Business-Seiten Ihrer Organisation zu importieren und zu archivieren. 

- Sie benötigen ein Facebook-Konto für die Geschäftsseiten Ihrer Organisation (Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten). Derzeit können Sie nur Daten von Facebook #A0 archivieren. Sie können keine Daten aus einzelnen Facebook-Profilen archivieren.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie über kein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren für ein kostenloses einjähriges Azure-Abonnement](https://azure.microsoft.com/free)

    - [Registrieren eines Pay-As-You-Go-Azure-Abonnements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [kostenlose Azure Active Directory,](use-your-free-azure-ad-subscription-in-office-365.md) das in Ihrem Microsoft 365-Abonnement enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Der Connector für Facebook Business-Seiten kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Facebook Business-Elemente an einem Tag enthalten sind, wird keines dieser Elemente in die Microsoft 365.

- Dem Benutzer, der den benutzerdefinierten Connector im Microsoft 365 Compliance Center (in Schritt 5) eingerichtet hat, muss die Rolle Postfachimportexport in der Exchange Online. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

Der erste Schritt besteht in der Registrierung einer neuen App in Azure Active Directory (AAD). Diese App entspricht der Web-App-Ressource, die Sie in Schritt 4 und Schritt 5 für den Facebook-Connector implementieren. 

Schrittweise Anweisungen finden Sie unter [Create an app in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Während des Abschlusses dieses Schritts (mithilfe der vorherigen schrittweisen Anweisungen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten im Bereitstellungsprozess verwendet.

- AAD-Anwendungs-ID

- Geheimer AAD-Anwendungsgeheimnis

- Mandanten-ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connectorwebdiensts GitHub Ihrem Azure-Konto

Der nächste Schritt besteht in der Bereitstellung des Quellcodes für die Facebook Business-Seiten-Connector-App, die die Facebook-API verwendet, um eine Verbindung mit Ihrem Facebook-Konto herzustellen und Daten zu extrahieren, damit Sie ihn in die App importieren Microsoft 365. Der für Ihre Organisation bereitgestellte Facebook-Connector laden die Elemente von Ihren Facebook Business-Seiten an den Azure Storage hoch, der in diesem Schritt erstellt wird. Nachdem Sie einen Connector für Facebook-Geschäftsseiten im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Importdienst die Daten der Facebook-Geschäftsseiten aus dem Azure Storage-Speicherort in ein Postfach in Ihrer Microsoft 365 Organisation. Wie bereits im Abschnitt Voraussetzungen erläutert, müssen Sie über ein [gültiges](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) Azure-Abonnement verfügen, um ein Azure Storage erstellen.

Schrittweise Anweisungen finden Sie unter [Deploy the connector web service from GitHub to your Azure account](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

In den schrittweisen Anweisungen zum Abschließen dieses Schritts stellen Sie die folgenden Informationen zur Verfügung:

- APISecretKey: Sie erstellen diesen Geheimschlüssel während des Abschlusses dieses Schritts. Es wird in Schritt 5 verwendet.

- TenantId: Die Mandanten-ID Ihrer Microsoft 365, die Sie nach dem Erstellen der Facebook-Connector-App in Azure Active Directory Schritt 1 kopiert haben.

Kopieren Sie nach Abschluss dieses Schritts unbedingt die Azure-App-Dienst-URL (z. B. https://fbconnector.azurewebsites.net) . Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abschließen zu können.

## <a name="step-3-register-the-web-app-on-facebook"></a>Schritt 3: Registrieren der Web-App auf Facebook

Der nächste Schritt besteht im Erstellen und Konfigurieren einer neuen App auf Facebook. Der in Schritt 5 erstellte Facebook-Geschäftsseitenconnector verwendet die Facebook-Web-App, um mit der Facebook-API zu interagieren, um Daten von den Facebook Business-Seiten Ihrer Organisation zu erhalten.

Schrittweise Anweisungen finden Sie unter [Registrieren der Facebook-App](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die Facebook-Connector-App in Schritt 4 zu konfigurieren.

- Facebook-Anwendungs-ID

- Geheimer Facebook-Anwendungsgeheimnis

- Facebook-Webhooks überprüfen Token

## <a name="step-4-configure-the-facebook-connector-app"></a>Schritt 4: Konfigurieren der Facebook-Connector-App

Im nächsten Schritt fügen Sie der Facebook-Connector-App Konfigurationseinstellungen hinzu, die Sie beim Erstellen der Azure Web App-Ressource in Schritt 1 hochgeladen haben. Dazu gehen Sie zur Startseite Ihrer Connector-App und konfigurieren sie.

Schrittweise Anweisungen finden Sie unter [Configure the Facebook connector app](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Facebook-Anwendungs-ID (in Schritt 3 erhalten)

- Geheimer Facebook-Anwendungsgeheimnis (in Schritt 3 erhalten)

- Facebook-Webhooks überprüfen Token (in Schritt 3 erhalten)

- Azure Active Directory Anwendungs-ID (die in Schritt 1 erhaltene AAD-Anwendungs-ID)

- Azure Active Directory -Anwendungsgeheimnis (der geheime AAD-Anwendungsgeheimnis in Schritt 1)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Facebook Business-Seitenconnector im Microsoft 365 Compliance Center

Der letzte Schritt besteht im Einrichten des Connectors im Microsoft 365 Compliance Center, das Daten von Ihren Facebook Business-Seiten in ein angegebenes Postfach in einem Microsoft 365. Nachdem Sie diesen Schritt abgeschlossen haben, beginnt Microsoft 365 Importdienst mit dem Importieren von Daten von Ihren Facebook Business-Seiten Microsoft 365.

Schrittweise Anweisungen finden Sie unter Schritt 5: Einrichten eines [Facebook-Connectors im Microsoft 365 Compliance Center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- AAD-Anwendungs-ID (in Schritt 1 erhalten)

- Azure-App-Dienst-URL (in Schritt 1 erhalten, z. B. https://fbconnector.azurewebsites.net)

- APISecretKey (erstellt in Schritt 2)