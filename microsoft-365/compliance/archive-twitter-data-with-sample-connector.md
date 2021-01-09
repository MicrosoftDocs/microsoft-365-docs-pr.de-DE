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
description: Erfahren Sie, wie Administratoren einen nativen Connector einrichten und verwenden können, um Die -Twitter-Daten in Microsoft 365 zu importieren.
ms.openlocfilehash: 5b35259985664ac47b9d1f6265c8ca4282a4cd31
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790063"
---
# <a name="set-up-a-connector-to-archive-twitter-data-preview"></a>Einrichten eines Connectors zum Archivieren von Twitter-Daten (Vorschau)

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten aus Twitter in Microsoft 365 zu importieren und zu archivieren. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit dem Twitter-Konto Ihrer Organisation (geplant) und konvertiert den Inhalt eines Elements in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Daten von Twitter importiert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf die Twitter-Daten anwenden. Wenn z. B. für ein Postfach das Aufbewahrungsverfahren aktiviert oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden die Daten von Twitter beibehalten. Sie können Drittanbieterdaten mithilfe der Inhaltssuche durchsuchen oder das Postfach, in dem die Daten von Twitter gespeichert sind, einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

Nachdem die Daten von Twitter importiert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf die im Postfach gespeicherten Daten anwenden. Sie können z. B. mithilfe der Inhaltssuche Nach -Twitter-Daten durchsuchen oder das Postfach, in dem die Daten gespeichert sind, einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

Erfüllen Sie die folgenden Voraussetzungen, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten aus dem Twitterkonto Ihrer Organisation zu importieren und zu archivieren.

- Sie benötigen ein #A0 für Ihre Organisation. sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie nicht über ein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren sie sich für ein kostenloses einjähriges Azure-Abonnement.](https://azure.microsoft.com/free) 

    - [Registrieren für ein Pay-As-You-Go-Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [kostenlose Azure Active Directory-Abonnement,](use-your-free-azure-ad-subscription-in-office-365.md) das in Ihrem Microsoft 365-Abonnement enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Der Twitter Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Twitter-Elemente an einem Tag verfügbar sind, wird keines dieser Elemente nach Microsoft 365 importiert.

- Dem Benutzer, der den Twitter Connector im Microsoft 365 Compliance Center (in Schritt 5) eingerichtet hat, muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

Der erste Schritt besteht in der Registrierung einer neuen App in Azure Active Directory (AAD). Diese App entspricht der Web-App-Ressource, die Sie in Schritt 2 für den Twitter-Connector implementieren.

Schrittweise Anweisungen finden Sie unter Erstellen [einer App in Azure Active Directory.](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory)

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten des Bereitstellungsprozesses verwendet.

- AAD-Anwendungs-ID

- Geheimer AAD-Anwendungsgeheimnis

- Mandanten-ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connectorwebdiensts aus dem Repository GitHub für Ihr Azure-Konto

Im nächsten Schritt stellen Sie den Quellcode für die Twitter-Connector-App bereit, die die Twitter-API verwendet, um eine Verbindung mit Ihrem Twitter-Konto herzustellen und Daten zu extrahieren, damit Sie sie in Microsoft 365 importieren können. Der Twitter-Connector, den Sie für Ihre Organisation bereitstellen, laden die Elemente aus dem Twitter-Konto Ihrer Organisation in den Azure Storage-Speicherort hoch, der in diesem Schritt erstellt wird. Nachdem Sie einen Twitter Connector im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Microsoft 365-Importdienst die Twitter-Daten vom Azure Storage-Speicherort in ein Postfach in Microsoft 365. Wie bereits im Abschnitt ["Vor](#before-you-set-up-a-connector) dem Einrichten eines Connectors" erläutert, müssen Sie über ein gültiges Azure-Abonnement verfügen, um ein Azure -Speicherkonto zu erstellen.

So stellen Sie den Quellcode für die Twitter-Connector-App zur Bereitstellung:

1. Wechseln Sie [zu dieser GitHub-Website.](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet)

2. Klicken **Sie auf "In Azure bereitstellen".**

Schrittweise Anweisungen finden Sie unter "Bereitstellen des [Connectorwebdiensts von GitHub in Ihrem Azure-Konto".](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

Während Sie die schrittweisen Anweisungen zum Abschließen dieses Schritts befolgen, stellen Sie die folgenden Informationen zur Verfügung:

- APISecretKey: Sie erstellen diesen geheimen Schlüssel während des Abschlusses dieses Schritts. Sie wird in Schritt 5 verwendet.

- tenantId: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie kopiert haben, nachdem Sie die Twitter-App in Azure Active Directory in Schritt 1 erstellt haben.

Stellen Sie nach Abschluss dieses Schritts sicher, dass Sie die App-Dienst-URL kopieren (z. B. `https://twitterconnector.azurewebsites.net` ). Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abschließen zu können.

## <a name="step-3-create-developer-app-on-twitter"></a>Schritt 3: Erstellen einer Entwickler-App auf Twitter

Der nächste Schritt besteht im Erstellen und Konfigurieren einer Entwickler-App auf Twitter. Der benutzerdefinierte Connector, den Sie in Schritt 7 erstellen, verwendet die Twitter-App, um mit der Twitter-API zu interagieren, um Daten aus dem Twitterkonto Ihrer Organisation zu erhalten.

Schrittweise Anweisungen finden Sie unter ["Erstellen der Twitter-App".](deploy-twitter-connector.md#step-3-create-the-twitter-app)

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die Twitter-Connector-App in Schritt 4 zu konfigurieren.

- Twitter-API-Schlüssel

- Geheimer Schlüssel der Twitter-API

- Twitter Access Token

- Geheimer Twitter-Zugriffstoken-Schlüssel

## <a name="step-4-configure-the-twitter-connector-app"></a>Schritt 4: Konfigurieren der Twitter-Connector-App

Der nächste Schritt besteht im Hinzufügen von Konfigurationseinstellungen zur Twitter-Connector-App, die Sie in Schritt 2 bereitgestellt haben. Gehen Sie dazu zur Startseite Ihrer Connector-App, und konfigurieren Sie sie.

Schrittweise Anweisungen finden Sie unter ["Konfigurieren der Connector-Web-App".](deploy-twitter-connector.md#step-4-configure-the-connector-web-app)

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Twitter-API-Schlüssel (in Schritt 3 erhalten)

- Geheimer Twitter-API-Schlüssel (in Schritt 3 erhalten)

- Twitter Access Token (erhalten in Schritt 3)

- Geheimer Twitter-Zugriffstoken-Schlüssel (in Schritt 3 erhalten)

- Azure Active Directory-Anwendungs-ID (die in Schritt 1 erhaltene AAD-Anwendungs-ID)

- Geheimer Azure Active Directory-Anwendungsgeheimnis (der in Schritt 1 erhaltene geheime AAD-Anwendungsgeheimnis)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Twitter Connectors im Microsoft 365 Compliance Center

Der letzte Schritt besteht im Einrichten des Twitter-Connectors im Microsoft 365 Compliance Center, der Daten aus dem Twitterkonto Ihrer Organisation in ein angegebenes Postfach in Microsoft 365 importiert. Nachdem Sie diesen Schritt abgeschlossen haben, beginnt der Microsoft 365-Importdienst mit dem Importieren von Daten aus dem Twitterkonto Ihrer Organisation in Microsoft 365.

Schrittweise Anweisungen finden Sie unter ["Einrichten eines Twitter-Connectors im Microsoft 365 Compliance Center".](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center) 

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- Azure-App-Dienst-URL (in Schritt 2 erhalten, z. B. `https://twitterconnector.azurewebsites.net` )

- APISecretKey (erstellt in Schritt 2)
