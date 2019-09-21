---
title: Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365 (Vorschau)
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen systemeigenen Connector zum Importieren von drittanbieterdaten aus Datenquellen wie Facebook-Geschäfts Seiten, Twitter, LinkedIn Unternehmensseiten und Instant Bloomberg einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Office 365 archivieren, sodass Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Steuerung der drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 2dde58e4d3ead0064e28c1ba1bfc04485c7a25df
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081112"
---
# <a name="use-a-sample-connector-to-archive-facebook-data-in-office-365-preview"></a>Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365 (Vorschau)

Das Sample Connector-Feature zum Archivieren von Facebook-Daten in Office 365 befindet sich in der Vorschau.

Verwenden Sie einen Beispiel-Konnektor im Security #a0 Compliance Center in Office 365, um Daten aus Facebook-Geschäfts Seiten in Office 365 zu importieren und zu archivieren. Nachdem Sie einen Sample Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Facebook-Geschäftsseite her (auf einer geplanten Basis), konvertiert den Inhalt von Facebook-Elementen in ein e-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Office 365.

Nachdem die Facebook-Daten importiert wurden, können Sie Office 365 Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung, Überwachung und Office 365 Aufbewahrungsrichtlinien auf Facebook-Daten anwenden. Wenn beispielsweise ein Postfach in ein Beweissicherungsverfahren gestellt oder einer Aufbewahrungsrichtlinie zugewiesen wurde, werden die Facebook-Daten beibehalten. Sie können drittanbieterdaten mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Facebook-Daten mit einer Depotbank in einem erweiterten eDiscovery-Fall gespeichert werden. Das Verwenden eines Connectors zum Importieren und Archivieren von Facebook-Daten in Office 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

> [!NOTE]
> Zu diesem Zeitpunkt stehen nur die Beispiel-Konnektoren für Facebook-Geschäfts Seiten und [Twitter](archive-twitter-data-with-sample-connector.md) für die Vorschau zur Verfügung. Weitere Beispiel-Konnektoren werden in Kürze verfügbar sein.


## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Voraussetzungen für das Einrichten eines Connectors für Facebook-Geschäfts Seiten

Sie müssen die folgenden Voraussetzungen erfüllen, bevor Sie einen Beispiel-Konnektor im Security #a0 Compliance Center einrichten und konfigurieren können, um Daten aus den Facebook-Geschäfts Seiten Ihrer Organisation zu importieren und zu archivieren. 

- Sie benötigen ein Facebook-Konto für die Geschäfts Seiten Ihrer Organisation (Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten). Derzeit können Sie nur Daten von Facebook-Geschäfts Seiten archivieren; Sie können keine Daten aus einzelnen Facebook-Profilen archivieren.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie über kein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren Sie sich für ein kostenloses Azure-Abonnement für ein Jahr.](https://azure.microsoft.com/free) 

    - [Registrieren für ein Pay-as-you-go Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [﻿Kostenlose Azure Active Directory-Abonnement](use-your-free-azure-ad-subscription-in-office-365.md) , das in Ihrem Office 365-Abonnement enthalten ist, unterstützt die Beispiel-Konnektoren im Security #a0 Compliance Center nicht.

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administrators an, und nehmen Sie dann die Anforderung an.

- Der Benutzer, der den benutzerdefinierten Connector in der Security #a0 Compliance (in Schritt 7) einrichtet, muss die Rolle "Post Fach Import Export" in Exchange Online zugewiesen haben. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-download-the-pre-built-connector-app-package-from-github"></a>Schritt 1: Herunterladen des vorab erstellten Connector-App-Pakets von GitHub

Der erste Schritt besteht darin, den Quellcode für die vordefinierte Facebook-Connector-APP herunterzuladen, die eine Facebook-API verwendet, um eine Verbindung zu ihren Facebook-Geschäfts Seiten herzustellen und Facebook-Daten zu extrahieren, damit Sie Sie in Office 365 importieren können.

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases). 
2. Klicken Sie unter der letzten Version auf die Datei **SampleConnector. zip** .
3. Speichern Sie die ZIP-Datei an einem Speicherort auf Ihrem lokalen Computer. Sie laden diese ZIP-Datei in Schritt 4 in Azure hoch.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Schritt 2: Erstellen einer APP in Azure Active Directory

Der nächste Schritt besteht darin, eine neue app in Azure Active Directory (AAD) zu registrieren. Diese APP entspricht der Webanwendungs Ressource, die Sie in Schritt 4 für den Facebook-Connector implementieren. 

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Erstellen einer APP in Azure Active Directory](deploy-facebook-connector.md#step-2-create-an-app-in-azure-active-directory).

Während des Abschlusses dieses Schritts (mit den vorherigen schrittweisen Anweisungen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten im Bereitstellungsprozess verwendet.

- Aad-Anwendungs-ID
- Aad-Anwendungs Geheimnis
- Aad-Anwendungs-URI
- Mandanten-ID

## <a name="step-3-create-an-azure-storage-account"></a>Schritt 3: Erstellen eines Azure-speicherkontos

Der Facebook-Connector, den Sie für Ihre Organisation bereitstellen, lädt die Elemente von ihren Facebook-Geschäfts Seiten an den Azure-Speicherort hoch, den Sie in diesem Schritt erstellen. Nachdem Sie einen benutzerdefinierten Connector im Security #a0 Compliance Center (in Schritt 7) erstellt haben, kopiert der Office 365-Import Dienst die Facebook-Daten aus dem Azure-Speicherort in ein Postfach in Office 365. Wie zuvor im Abschnitt [Voraussetzungen](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) erläutert, benötigen Sie ein gültiges Azure-Abonnement, um ein Azure-Speicherkonto zu erstellen.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Erstellen eines Azure-speicherkontos](deploy-facebook-connector.md#step-3-create-an-azure-storage-account).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) speichern Sie den generierten Verbindungszeichenfolgen-URI. Verwenden Sie diese Zeichenfolge beim Erstellen einer webapp-Ressource in Azure in Schritt 4.

## <a name="step-4-create-a-web-app-resource-in-azure"></a>Schritt 4: Erstellen einer webapp-Ressource in Azure

Der nächste Schritt besteht darin, eine Webanwendungs Ressource in Azure für den Facebook-Connector zu erstellen. 

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Erstellen einer neuen webapp-Ressource in Azure](deploy-facebook-connector.md#step-4-create-a-new-web-app-resource-in-azure).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anleitungen befolgen) geben Sie beim Erstellen der Webanwendungs Ressource die folgenden Informationen (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben) an.

- APISecretKey – Sie erstellen diesen Schlüssel während des Abschlusses dieses Schritts; Sie wird in Schritt 7 verwendet.
- StorageAccountConnectionString – der Verbindungszeichenfolgen-URI, den Sie nach dem Erstellen des Azure-speicherkontos in Schritt 3 kopiert haben.
- Mandantenkennung – die Mandanten-ID Ihrer Office 365 Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 2 kopiert haben.

Darüber hinaus laden Sie die SampleConnector. zip-Datei (die Sie in Schritt 1 heruntergeladen haben) in diesem Schritt hoch, um den Quellcode für die Facebook-Connector-App bereitzustellen.

Nachdem Sie diesen Schritt abgeschlossen haben, müssen Sie die APP-Dienst-URL kopieren ( https://fbconnector.azurewebsites.net)beispielsweise. Sie müssen dies verwenden, um Schritt 5, Schritt 6 und Schritt 7 abzuschließen.

## <a name="step-5-register-the-web-app-on-facebook"></a>Schritt 5: Registrieren der Webanwendung auf Facebook

Der nächste Schritt besteht darin, eine neue APP auf Facebook zu erstellen und zu konfigurieren. Der benutzerdefinierte Connector, den Sie in Schritt 7 erstellen, verwendet die Facebook-Webanwendung für die Interaktion mit der Facebook-API, um Daten von den Facebook-Geschäfts Seiten Ihrer Organisation zu erhalten.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Registrieren der Facebook-App](deploy-facebook-connector.md#step-5-register-the-facebook-app).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) speichern Sie die folgenden Informationen in einer Textdatei. Die Werte werden verwendet, um die Facebook-Connector-app in Schritt 6 zu konfigurieren.

- Facebook-Anwendungs-ID
- Geheimnis der Facebook-Anwendung
- Facebook webhooks – Überprüfen des Tokens

## <a name="step-6-configure-the-facebook-connector-app"></a>Schritt 6: Konfigurieren der Facebook-Connector-App

Im nächsten Schritt fügen Sie der Facebook Connector-App Konfigurationseinstellungen hinzu, die Sie beim Erstellen der Azure-Webanwendung-Ressource in Schritt 4 hochgeladen haben. Gehen Sie dazu auf die Startseite Ihrer Connector-APP, und konfigurieren Sie Sie.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Schritt 6: Konfigurieren der Connector-Webanwendung](deploy-facebook-connector.md#step-6-configure-the-connector-web-app).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Facebook-Anwendungs-ID (in Schritt 5 abgerufen)
- Geheimer Facebook-Anwendungsschlüssel (in Schritt 5 abgerufen)
- Überprüfen des Tokens in Facebook-webhooks (in Schritt 5 erhalten)
- Azure Active Directory Application ID (die Aad-Anwendungs-ID, die in Schritt 2 abgerufen wurde)
- Azure Active Directory Application Secret (der in Schritt 2 abgerufene Aad-Anwendungsschlüssel)
- Azure Active Directory Application URI (der in Schritt 2 abgerufene Aad-Anwendungs-URI, beispielsweisehttps://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213)

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Schritt 7: Einrichten eines benutzerdefinierten Connectors im Security #a0 Compliance Center

Der letzte Schritt besteht darin, den benutzerdefinierten Connector im Security #a0 Compliance Center einzurichten, mit dem Daten von ihren Facebook-Geschäfts Seiten in ein angegebenes Postfach in Office 365 importiert werden. Nachdem Sie diesen Schritt ausgeführt haben, startet der Office 365-Import Dienst den Prozess des Importierens von Daten von ihren Facebook-Geschäfts Seiten in Office 365. 

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Einrichten eines benutzerdefinierten Connectors im Security #a0 Compliance Center](deploy-facebook-connector.md#step-7-set-up-a-custom-connector-in-the-security--compliance-center). 

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- Azure-App-Dienst-URL (abgerufen in Schritt 4; Beispiel:https://fbconnector.azurewebsites.net)
- APISecretKey (das Sie in Schritt 4 erstellt haben)
