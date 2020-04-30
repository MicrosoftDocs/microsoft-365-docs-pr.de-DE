---
title: Einrichten eines Connectors zum Archivieren von Facebook-Daten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
description: Administratoren können einen Connector zum Importieren von drittanbieterdaten aus Datenquellen wie Facebook-Geschäfts Seiten, Twitter, LinkedIn Unternehmensseiten und Instant Bloomberg einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Steuerung der drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 21023e380e4065f40edd4c3dea3f4c461d743f04
ms.sourcegitcommit: 60c1932dcca249355ef7134df0ceb0e57757dc81
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/29/2020
ms.locfileid: "43943234"
---
# <a name="set-up-a-connector-to-archive-facebook-data"></a>Einrichten eines Connectors zum Archivieren von Facebook-Daten

Verwenden Sie einen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Daten von Facebook-Geschäfts Seiten nach Microsoft 365. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der Facebook-Geschäftsseite her (auf einer geplanten Basis), konvertiert den Inhalt von Facebook-Elementen in ein e-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Facebook-Daten importiert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung, Kommunikations Konformität und Microsoft 365-Aufbewahrungsrichtlinien auf die Facebook-Daten anwenden. Wenn beispielsweise ein Postfach in ein Beweissicherungsverfahren gestellt oder einer Aufbewahrungsrichtlinie zugewiesen wurde, werden die Facebook-Daten beibehalten. Sie können drittanbieterdaten mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Facebook-Daten mit einer Depotbank in einem erweiterten eDiscovery-Fall gespeichert werden. Das Verwenden eines Connectors zum Importieren und Archivieren von Facebook-Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="prerequisites-for-setting-up-a-connector-for-facebook-business-pages"></a>Voraussetzungen für das Einrichten eines Connectors für Facebook-Geschäfts Seiten

Schließen Sie die folgenden Voraussetzungen ab, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten aus den Facebook-Geschäfts Seiten Ihrer Organisation zu importieren und zu archivieren. 

- Sie benötigen ein Facebook-Konto für die Geschäfts Seiten Ihrer Organisation (Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten). Derzeit können Sie nur Daten von Facebook-Geschäfts Seiten archivieren; Sie können keine Daten aus einzelnen Facebook-Profilen archivieren.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie über kein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren Sie sich für ein kostenloses Azure-Abonnement für ein Jahr.](https://azure.microsoft.com/free) 

    - [Registrieren für ein Pay-as-you-go Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [﻿Kostenlose Azure Active Directory-Abonnement](use-your-free-azure-ad-subscription-in-office-365.md) , das im Lieferumfang Ihres Microsoft 365-Abonnements enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an, und nehmen Sie dann die Anforderung an.

- Der Benutzer, der den benutzerdefinierten Connector im Microsoft 365 Compliance Center (in Schritt 5) einrichtet, muss in Exchange Online über die Rolle "Post Fach Import-Export" verfügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

Der erste Schritt besteht darin, eine neue app in Azure Active Directory (AAD) zu registrieren. Diese APP entspricht der Webanwendungs Ressource, die Sie in Schritt 4 und Schritt 5 für den Facebook-Connector implementieren. 

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Erstellen einer APP in Azure Active Directory](deploy-facebook-connector.md#step-1-create-an-app-in-azure-active-directory).

Während des Abschlusses dieses Schritts (mit den vorherigen schrittweisen Anweisungen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten im Bereitstellungsprozess verwendet.

- Aad-Anwendungs-ID

- Aad-Anwendungs Geheimnis

- Mandanten-ID

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto

Der nächste Schritt besteht darin, den Quellcode für die Facebook Business Pages-Connector-App bereitzustellen, mit der die Facebook-API verwendet wird, um eine Verbindung mit Ihrem Facebook-Konto herzustellen und Daten zu extrahieren, damit Sie Sie in Microsoft 365 importieren können. Der Facebook-Connector, den Sie für Ihre Organisation bereitstellen, lädt die Elemente von ihren Facebook-Geschäfts Seiten an den in diesem Schritt erstellten Azure-Speicherort hoch. Nachdem Sie einen Facebook Business Pages-Connector im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Import Dienst die Daten der Facebook-Geschäfts Seiten aus dem Azure-Speicherort in ein Postfach in Ihrer Microsoft 365-Organisation. Wie zuvor im Abschnitt [Voraussetzungen](#prerequisites-for-setting-up-a-connector-for-facebook-business-pages) erläutert, benötigen Sie ein gültiges Azure-Abonnement, um ein Azure-Speicherkonto zu erstellen.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto](deploy-facebook-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

In den Schritt-für-Schritt-Anleitungen zum Ausführen dieses Schritts geben Sie die folgenden Informationen an:

- APISecretKey: Sie erstellen diesen Schlüssel während des Abschlusses dieses Schritts. Sie wird in Schritt 5 verwendet.

- Mandantenkennung: die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 1 kopiert haben.

Nachdem Sie diesen Schritt abgeschlossen haben, müssen Sie die Azure-App-Dienst-URL kopieren https://fbconnector.azurewebsites.net)(beispielsweise. Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abzuschließen.

## <a name="step-3-register-the-web-app-on-facebook"></a>Schritt 3: Registrieren der Webanwendung auf Facebook

Der nächste Schritt besteht darin, eine neue APP auf Facebook zu erstellen und zu konfigurieren. Der Facebook Business Pages-Konnektor, den Sie in Schritt 5 erstellen, verwendet die Facebook-Webanwendung, um mit der Facebook-API zu interagieren und Daten von den Facebook-Geschäfts Seiten Ihrer Organisation zu erhalten.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Registrieren der Facebook-App](deploy-facebook-connector.md#step-3-register-the-facebook-app).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die Facebook-Connector-app in Schritt 4 zu konfigurieren.

- Facebook-Anwendungs-ID

- Geheimnis der Facebook-Anwendung

- Facebook webhooks – Überprüfen des Tokens

## <a name="step-4-configure-the-facebook-connector-app"></a>Schritt 4: Konfigurieren der Facebook-Connector-App

Im nächsten Schritt fügen Sie der Facebook Connector-App Konfigurationseinstellungen hinzu, die Sie beim Erstellen der Azure-Webanwendung-Ressource in Schritt 1 hochgeladen haben. Gehen Sie dazu auf die Startseite Ihrer Connector-APP, und konfigurieren Sie Sie.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [configure the Facebook Connector App](archive-facebook-data-with-sample-connector.md#step-4-configure-the-facebook-connector-app).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Facebook-Anwendungs-ID (in Schritt 3 abgerufen)

- Geheimer Facebook-Anwendungsschlüssel (in Schritt 3 abgerufen)

- Überprüfen des Tokens in Facebook-webhooks (in Schritt 3 abgerufen)

- Azure Active Directory Application ID (die Aad-Anwendungs-ID, die in Schritt 1 abgerufen wurde)

- Azure Active Directory Application Secret (der in Schritt 1 abgerufene Aad-Anwendungsschlüssel)

## <a name="step-5-set-up-a-facebook-business-pages-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Facebook Business Pages-Connectors im Microsoft 365 Compliance Center

Der letzte Schritt besteht darin, den Connector im Microsoft 365 Compliance Center einzurichten, mit dem Daten von ihren Facebook-Geschäfts Seiten in ein angegebenes Postfach in Microsoft 365 importiert werden. Nachdem Sie diesen Schritt ausgeführt haben, startet der Office 365-Import Dienst mit dem Importieren von Daten von ihren Facebook-Geschäfts Seiten nach Microsoft 365.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Schritt 5: Einrichten eines Facebook-Connectors im Microsoft 365 Compliance Center](deploy-facebook-connector.md#step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center). 

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- Aad-Anwendungs-ID (in Schritt 1 abgerufen)

- Azure-App-Dienst-URL (in Schritt 1 abgerufen, beispielsweisehttps://fbconnector.azurewebsites.net)

- APISecretKey (das Sie in Schritt 2 erstellt haben)
