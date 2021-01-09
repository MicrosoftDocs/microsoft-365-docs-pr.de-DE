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
description: Erfahren Sie, wie Sie & einen Connector im Microsoft 365 Compliance Center zum Importieren von & von Facebook -Geschäftsseiten nach Microsoft 365 einrichten.
ms.openlocfilehash: df86897defa92788399f704c53c00ebb9e4f4269
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790149"
---
# <a name="set-up-a-connector-to-archive-facebook-data-preview"></a>Einrichten eines Connectors zum Archivieren von Facebook-Daten (Vorschau)

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten von Facebook -Geschäftsseiten in Microsoft 365 zu importieren und zu archivieren. Nachdem Sie den Connector eingerichtet und konfiguriert haben, wird eine Verbindung mit der Facebook -Geschäftsseite (geplant) hergestellt, der Inhalt von Elementen von Facebook in ein E-Mail-Nachrichtenformat konvertiert und dann in ein Postfach in Microsoft 365 importiert.

Nachdem die Daten von Facebook importiert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf die Daten von Facebook anwenden. Wenn z. B. für ein Postfach ein Aufbewahrungsverfahren aktiviert oder einer Aufbewahrungsrichtlinie zugewiesen wird, werden die Daten von Facebook beibehalten. Sie können Drittanbieterdaten mithilfe der Inhaltssuche durchsuchen oder das Postfach, in dem die Daten von Facebook gespeichert sind, einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Connectors zum Importieren und Archivieren von Facebook-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Voraussetzungen für die Einrichtung eines Connectors für Facebook -Geschäftsseiten

Erfüllen Sie die folgenden Voraussetzungen, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten von den Facebook -Geschäftsseiten Ihrer Organisation zu importieren und zu archivieren. 

- Sie benötigen ein Facebook-Konto für die Geschäftsseiten Ihrer Organisation (Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten). Derzeit können Sie nur Daten von Facebook #A0 archivieren. Sie können keine Daten aus einzelnen Facebook-Profilen archivieren.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie nicht über ein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren sie sich für ein kostenloses einjähriges Azure-Abonnement.](https://azure.microsoft.com/free)

    - [Registrieren für ein Pay-As-You-Go-Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [kostenlose Azure Active Directory-Abonnement,](use-your-free-azure-ad-subscription-in-office-365.md) das in Ihrem Microsoft 365-Abonnement enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Der Connector für Facebook -Geschäftsseiten kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Facebook -Geschäftselemente an einem Tag verfügbar sind, wird keines dieser Elemente nach Microsoft 365 importiert.

- Dem Benutzer, der den benutzerdefinierten Connector im Microsoft 365 Compliance Center (in Schritt 5) eingerichtet hat, muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer App in Azure Active Directory

Der erste Schritt besteht in der Registrierung einer neuen App in Azure Active Directory (AAD). Diese App entspricht der Web-App-Ressource, die Sie in Schritt 4 und Schritt 5 für den Facebook-Connector implementieren. 

Schrittweise Anweisungen finden Sie unter Erstellen [einer App in Azure Active Directory.](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory)

Während des Abschlusses dieses Schritts (mithilfe der vorherigen schrittweisen Anweisungen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten des Bereitstellungsprozesses verwendet.

- AAD-Anwendungs-ID

- Geheimer AAD-Anwendungsgeheimnis

- Mandanten-ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connectorwebdiensts von GitHub in Ihrem Azure-Konto

Der nächste Schritt besteht im Bereitstellen des Quellcodes für die Facebook Business-Seiten-Connector-App, die die Facebook-API verwendet, um eine Verbindung mit Ihrem Facebook-Konto herzustellen und Daten zu extrahieren, damit Sie sie in Microsoft 365 importieren können. Der Facebook-Connector, den Sie für Ihre Organisation bereitstellen, laden die Elemente von Ihren Facebook -Geschäftsseiten in den Azure Storage-Speicherort hoch, der in diesem Schritt erstellt wird. Nachdem Sie einen Connector für Facebook-Geschäftsseiten im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Importdienst die Daten der Facebook-Geschäftsseiten vom Azure Storage-Speicherort in ein Postfach in Ihrer Microsoft 365-Organisation. Wie zuvor im Abschnitt ["Voraussetzungen"](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) erläutert, müssen Sie über ein gültiges Azure-Abonnement verfügen, um ein Azure -Speicherkonto zu erstellen.

Schrittweise Anweisungen finden Sie unter "Bereitstellen des [Connectorwebdiensts von GitHub in Ihrem Azure-Konto".](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account)

In den schrittweisen Anweisungen zum Abschließen dieses Schritts stellen Sie die folgenden Informationen zur Verfügung:

- APISecretKey: Sie erstellen diesen geheimen Schlüssel während des Abschlusses dieses Schritts. Sie wird in Schritt 5 verwendet.

- TenantId: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-App in Azure Active Directory in Schritt 1 kopiert haben.

Stellen Sie nach Abschluss dieses Schritts sicher, dass Sie die Url des Azure-App-Diensts kopieren (z. https://fbconnector.azurewebsites.net) B. . Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abschließen zu können.

## <a name="step-3-register-the-web-app-on-facebook"></a>Schritt 3: Registrieren der Web App auf Facebook

Der nächste Schritt besteht im Erstellen und Konfigurieren einer neuen App auf Facebook. Der in Schritt 5 erstellten Facebook-Geschäftsseiten-Connector verwendet die Facebook-Web-App, um mit der Facebook-API zu interagieren, um Daten von den Facebook -Geschäftsseiten Ihrer Organisation zu erhalten.

Schrittweise Anweisungen finden Sie unter [Registrieren der Facebook-App.](deploy-facebook-connector.md#step-3-register-the-facebook-app)

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die Facebook-Connector-App in Schritt 4 zu konfigurieren.

- Facebook-Anwendungs-ID

- Geheimer Anwendungsgeheimnis von Facebook

- Überprüfungstoken für Facebook-Webhooks

## <a name="step-4-configure-the-facebook-connector-app"></a>Schritt 4: Konfigurieren der Facebook-Connector-App

Der nächste Schritt besteht im Hinzufügen von Konfigurationseinstellungen zur Facebook-Connector-App, die Sie hochgeladen haben, als Sie die Azure Web -App-Ressource in Schritt 1 erstellt haben. Gehen Sie dazu zur Startseite Ihrer Connector-App, und konfigurieren Sie sie.

Schrittweise Anweisungen finden Sie unter ["Konfigurieren der Facebook-Connector-App".](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app)

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Facebook-Anwendungs-ID (in Schritt 3 erhalten)

- Geheimer Anwendungsgeheimnis von Facebook (in Schritt 3 erhalten)

- Facebook-Webhooks überprüfen Token (erhalten in Schritt 3)

- Azure Active Directory-Anwendungs-ID (die in Schritt 1 erhaltene AAD-Anwendungs-ID)

- Geheimer Azure Active Directory-Anwendungsgeheimnis (der in Schritt 1 erhaltene geheime AAD-Anwendungsgeheimnis)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Facebook Business -Seitenconnector im Microsoft 365 Compliance Center

Der letzte Schritt besteht im Einrichten des Connectors im Microsoft 365 Compliance Center, der Daten von Ihren Facebook -Geschäftsseiten in ein angegebenes Postfach in Microsoft 365 importiert. Nachdem Sie diesen Schritt abgeschlossen haben, beginnt der Microsoft 365-Importdienst mit dem Importieren von Daten von Ihren Facebook Business-Seiten in Microsoft 365.

Schrittweise Anweisungen finden Sie unter Schritt 5: Einrichten eines Facebook-Connectors im [Microsoft 365 Compliance Center.](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center) 

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- AAD-Anwendungs-ID (in Schritt 1 erhalten)

- Azure-App-Dienst-URL (in Schritt 1 erhalten, z. B. https://fbconnector.azurewebsites.net)

- APISecretKey (erstellt in Schritt 2)
