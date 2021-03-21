---
title: Einrichten eines Connectors zum Archivieren von Twitter-Daten
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
description: Erfahren Sie, wie Administratoren einen systemeigenen Connector einrichten und verwenden können, um Twitter-Daten in Microsoft 365 zu importieren.
ms.openlocfilehash: 277af8ea7367936c4c9528a8ca50ccd678745bf6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922257"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Einrichten eines Connectors zum Archivieren von Twitter-Daten (Vorschau)

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten von Twitter zu Microsoft 365 zu importieren und zu archivieren. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er (geplant) eine Verbindung mit dem Twitter-Konto Ihrer Organisation, konvertiert den Inhalt eines Elements in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Twitter-Daten importiert wurden, können Sie Microsoft 365-Compliancefeatures wie Das Archivieren von Rechtsstreitigkeiten, die Inhaltssuche, In-Place Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf die Twitter-Daten anwenden. Wenn z. B. ein Postfach in das Aufbewahrungsverfahren einbehalten oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden die Twitter-Daten beibehalten. Sie können Daten von Drittanbietern mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Twitter-Daten in einem Advanced eDiscovery-Fall einem Verwahrer gespeichert werden. Die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

Nach dem Importieren von Twitter-Daten können Sie Microsoft 365-Compliancefeatures wie z. B. Das Rechtsstreitigkeitensverfahren, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf die im Postfach gespeicherten Daten anwenden. Sie können z. B. Twitter-Daten mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Daten in einem Advanced eDiscovery-Fall einem Verwahrer gespeichert werden. Die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Erfüllen Sie die folgenden Voraussetzungen, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten aus dem Twitter-Konto Ihrer Organisation zu importieren und zu archivieren.

- Sie benötigen ein #A0 für Ihre Organisation. Sie müssen sich bei diesem Konto beim Einrichten des Connectors anmelden.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie über kein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren für ein kostenloses einjähriges Azure-Abonnement](https://azure.microsoft.com/free) 

    - [Registrieren eines Pay-As-You-Go-Azure-Abonnements](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [kostenlose Azure Active Directory-Abonnement,](use-your-free-azure-ad-subscription-in-office-365.md) das in Ihrem Microsoft 365-Abonnement enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Der Twitter-Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Twitter-Elemente an einem Tag verfügbar sind, wird keines dieser Elemente nach Microsoft 365 importiert.

- Dem Benutzer, der den Twitter-Connector im Microsoft 365 Compliance Center (in Schritt 5) eingerichtet hat, muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von  [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

Der erste Schritt besteht in der Registrierung einer neuen App in Azure Active Directory (AAD). Diese App entspricht der Web-App-Ressource, die Sie in Schritt 2 für den Twitter-Connector implementieren.

Schrittweise Anweisungen finden Sie unter [Create an app in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten des Bereitstellungsprozesses verwendet.

- AAD-Anwendungs-ID

- Geheimer AAD-Anwendungsgeheimnis

- Mandanten-ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connectorwebdiensts aus dem GitHub-Repository in Ihrem Azure-Konto

Der nächste Schritt besteht in der Bereitstellung des Quellcodes für die Twitter-Connector-App, die die Twitter-API verwendet, um eine Verbindung mit Ihrem Twitter-Konto herzustellen und Daten zu extrahieren, sodass Sie ihn in Microsoft 365 importieren können. Der twitter-Connector, den Sie für Ihre Organisation bereitstellen, laden die Elemente aus dem Twitter-Konto Ihrer Organisation an den Azure Storage-Speicherort hoch, der in diesem Schritt erstellt wird. Nachdem Sie einen Twitter-Connector im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Microsoft 365-Importdienst die Twitter-Daten aus dem Azure Storage-Speicherort in ein Postfach in Microsoft 365. Wie zuvor im Abschnitt [Vor](#before-you-set-up-a-connector) dem Einrichten eines Connectors erläutert, müssen Sie über ein gültiges Azure-Abonnement verfügen, um ein Azure Storage-Konto zu erstellen.

So stellen Sie den Quellcode für die Twitter-Connector-App zur Bereitstellung:

1. Wechseln Sie [zu dieser GitHub-Website](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Klicken Sie **auf Bereitstellen in Azure**.

Schrittweise Anweisungen finden Sie unter [Deploy the connector web service from GitHub to your Azure account](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Während Sie die schrittweisen Anweisungen zum Abschließen dieses Schritts befolgen, stellen Sie die folgenden Informationen zur Verfügung.

- APISecretKey: Sie erstellen diesen Geheimschlüssel während des Abschlusses dieses Schritts. Es wird in Schritt 5 verwendet.

- tenantId: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Twitter-App in Azure Active Directory in Schritt 1 kopiert haben.

Nachdem Sie diesen Schritt abgeschlossen haben, müssen Sie unbedingt die App-Dienst-URL kopieren (z. B. `https://twitterconnector.azurewebsites.net` ). Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abschließen zu können.

## <a name="step-3-create-developer-app-on-twitter"></a>Schritt 3: Erstellen einer Entwickler-App auf Twitter

Im nächsten Schritt erstellen und konfigurieren Sie eine Entwickler-App auf Twitter. Der benutzerdefinierte Connector, den Sie in Schritt 7 erstellen, verwendet die Twitter-App, um mit der Twitter-API zu interagieren, um Daten aus dem Twitter-Konto Ihrer Organisation zu erhalten.

Schrittweise Anweisungen finden Sie unter [Create the Twitter app](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die App für den Twitter-Connector in Schritt 4 zu konfigurieren.

- Twitter-API-Schlüssel

- Geheimer Twitter-API-Schlüssel

- Twitter-Zugriffstoken

- Geheimer Twitter-Zugriffstoken

## <a name="step-4-configure-the-twitter-connector-app"></a>Schritt 4: Konfigurieren der App für den Twitter-Connector

Im nächsten Schritt fügen Sie der in Schritt 2 bereitgestellten Twitter-Connector-App Konfigurationseinstellungen hinzu. Dazu gehen Sie zur Startseite Ihrer Connector-App und konfigurieren sie.

Schrittweise Anweisungen finden Sie unter [Configure the connector web app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) stellen Sie die folgenden Informationen zur Verfügung (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Twitter-API-Schlüssel (in Schritt 3 erhalten)

- Geheimer Twitter-API-Schlüssel (in Schritt 3 erhalten)

- Twitter-Zugriffstoken (in Schritt 3 erhalten)

- Geheimer Twitter-Zugriffstoken(in Schritt 3 erhalten)

- Azure Active Directory-Anwendungs-ID (die in Schritt 1 erhaltene AAD-Anwendungs-ID)

- Geheimer Azure Active Directory-Anwendungsgeheimnis (der in Schritt 1 ermittelte geheime AAD-Anwendungsgeheimnis)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Twitter-Connectors im Microsoft 365 Compliance Center

Der letzte Schritt besteht im Einrichten des Twitter-Connectors im Microsoft 365 Compliance Center, das Daten aus dem Twitter-Konto Ihrer Organisation in ein angegebenes Postfach in Microsoft 365 importiert. Nachdem Sie diesen Schritt abgeschlossen haben, beginnt der Microsoft 365-Importdienst mit dem Importieren von Daten aus dem Twitter-Konto Ihrer Organisation in Microsoft 365.

Schrittweise Anweisungen finden Sie unter Einrichten eines [Twitter-Connectors im Microsoft 365 Compliance Center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) stellen Sie die folgenden Informationen (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben) zur Verfügung.

- Azure-App-Dienst-URL (in Schritt 2 erhalten, z. B. `https://twitterconnector.azurewebsites.net` )

- APISecretKey (erstellt in Schritt 2)