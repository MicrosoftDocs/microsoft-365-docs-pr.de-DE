---
title: Einrichten eines Connectors zum Archivieren von Twitter-Daten
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
ms.custom:
- seo-marvel-apr2020
description: Richten Sie einen Connector zum Importieren von Twitter-Daten in Microsoft 365 ein, damit Sie Compliance-Features wie rechtliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können.
ms.openlocfilehash: 5fb13b3a5eb79c09c2947292b793fe607dae247f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035127"
---
# <a name="set-up-a-connector-to-archive-twitter-data"></a>Einrichten eines Connectors zum Archivieren von Twitter-Daten

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten aus Twitter in Microsoft 365 zu importieren und zu archivieren. Nachdem Sie den Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit dem Twitter-Konto Ihrer Organisation her (planmäßig), konvertiert den Inhalt eines Elements in ein e-Mail-Nachrichtenformat und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Twitter-Daten importiert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf die Twitter-Daten anwenden. Wenn beispielsweise ein Postfach in ein Beweissicherungsverfahren gestellt oder einer Aufbewahrungsrichtlinie zugewiesen wurde, werden die Twitter-Daten beibehalten. Sie können drittanbieterdaten mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Twitter-Daten mit einer Depotbank in einem erweiterten eDiscovery-Fall gespeichert werden. Durch die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 können Sie Ihrer Organisation dabei helfen, mit behördlichen und behördlichen Richtlinien konform zu bleiben.

Nachdem Sie Twitter-Daten importiert haben, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung, Kommunikationsrichtlinien Konformität und Microsoft 365-Aufbewahrungsrichtlinien auf die im Postfach gespeicherten Daten anwenden. Beispielsweise können Sie Twitter-Daten mithilfe der Inhaltssuche durchsuchen oder das Postfach zuordnen, in dem die Daten mit einer Depotbank in einem erweiterten eDiscovery-Fall gespeichert werden. Durch die Verwendung eines Connectors zum Importieren und Archivieren von Twitter-Daten in Microsoft 365 können Sie Ihrer Organisation dabei helfen, mit behördlichen und behördlichen Richtlinien konform zu bleiben.

## <a name="prerequisites-for-setting-up-a-connector-for-twitter"></a>Voraussetzungen für das Einrichten eines Connectors für Twitter

Schließen Sie die folgenden Voraussetzungen ab, bevor Sie einen Connector im Microsoft 365 Compliance Center einrichten und konfigurieren können, um Daten aus dem Twitter-Konto Ihrer Organisation zu importieren und zu archivieren.

- Sie benötigen ein Twitter-Konto für Ihre Organisation; Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector einrichten.

- Ihre Organisation muss über ein gültiges Azure-Abonnement verfügen. Wenn Sie über kein vorhandenes Azure-Abonnement verfügen, können Sie sich für eine der folgenden Optionen registrieren:

    - [Registrieren Sie sich für ein kostenloses Azure-Abonnement für ein Jahr.](https://azure.microsoft.com/free) 

    - [Registrieren für ein Pay-as-you-go Azure-Abonnement](https://azure.microsoft.com/pricing/purchase-options/pay-as-you-go/)

    > [!NOTE]
    > Das [﻿Kostenlose Azure Active Directory-Abonnement](use-your-free-azure-ad-subscription-in-office-365.md) , das im Lieferumfang Ihres Microsoft 365-Abonnements enthalten ist, unterstützt die Connectors im Security & Compliance Center nicht.

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines globalen Administrators an, und nehmen Sie dann die Anforderung an.

- Dem Benutzer, der den Twitter Connector im Microsoft 365 Compliance Center (in Schritt 5) eingerichtet hat, muss in Exchange Online die Rolle "Post Fach Import Export" zugewiesen sein. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

Der erste Schritt besteht darin, eine neue app in Azure Active Directory (AAD) zu registrieren. Diese APP entspricht der Webanwendungs Ressource, die Sie in Schritt 2 für den Twitter-Connector implementieren.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Erstellen einer APP in Azure Active Directory](deploy-twitter-connector.md#step-1-create-an-app-in-azure-active-directory).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden in späteren Schritten im Bereitstellungsprozess verwendet.

- Aad-Anwendungs-ID

- Aad-Anwendungs Geheimnis

- Mandanten-ID

## <a name="step-2-deploy-connector-web-service-from-github-repository-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connector-Webdiensts aus dem GitHub-Repository in Ihrem Azure-Konto

Der nächste Schritt ist die Bereitstellung des Quellcodes für die Twitter-Connector-APP, die Twitter-API verwendet, um eine Verbindung mit Ihrem Twitter-Konto herzustellen und Daten zu extrahieren, damit Sie Sie in Microsoft 365 importieren können. Der Twitter-Connector, den Sie für Ihre Organisation bereitstellen, lädt die Elemente aus dem Twitter-Konto Ihrer Organisation an den Azure-Speicherplatz hoch, der in diesem Schritt erstellt wird. Nachdem Sie einen Twitter-Konnektor im Microsoft 365 Compliance Center (in Schritt 5) erstellt haben, kopiert der Office 365-Import Dienst die Twitter-Daten aus dem Azure-Speicherort in ein Postfach in Microsoft 365. Wie zuvor im Abschnitt [Voraussetzungen](#prerequisites-for-setting-up-a-connector-for-twitter) erläutert, benötigen Sie ein gültiges Azure-Abonnement, um ein Azure-Speicherkonto zu erstellen.

So stellen Sie den Quellcode für die Twitter-Connector-App bereit:

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet).

2. Klicken Sie auf **in Azure bereitstellen**.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto](deploy-twitter-connector.md#step-2-deploy-the-connector-web-service-from-github-to-your-azure-account).

Wenn Sie die schrittweisen Anleitungen zum Ausführen dieses Schritts befolgen, geben Sie die folgenden Informationen an:

- APISecretKey: Sie erstellen diesen Schlüssel während des Abschlusses dieses Schritts. Sie wird in Schritt 5 verwendet.

- Mandantenkennung: die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Twitter-app in Azure Active Directory in Schritt 1 kopiert haben.

Nachdem Sie diesen Schritt abgeschlossen haben, müssen Sie die APP-Dienst-URL kopieren ( `https://twitterconnector.azurewebsites.net`beispielsweise). Sie müssen diese URL verwenden, um Schritt 3, Schritt 4 und Schritt 5 abzuschließen.

## <a name="step-3-create-developer-app-on-twitter"></a>Schritt 3: Erstellen der Entwickler-App auf Twitter

Der nächste Schritt besteht darin, eine Entwickler-App auf Twitter zu erstellen und zu konfigurieren. Der benutzerdefinierte Connector, den Sie in Schritt 7 erstellen, verwendet die Twitter-APP für die Interaktion mit der Twitter-API, um Daten aus dem Twitter-Konto Ihrer Organisation zu erhalten.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Create the Twitter APP](deploy-twitter-connector.md#step-3-create-the-twitter-app).

Bei Abschluss dieses Schritts (indem Sie die schrittweisen Anleitungen ausführen) speichern Sie die folgenden Informationen in einer Textdatei. Diese Werte werden verwendet, um die Twitter Connector-app in Schritt 4 zu konfigurieren.

- Twitter-API-Schlüssel

- Geheimer Twitter-API-Schlüssel

- Twitter-Zugriffs Token

- Twitter-Zugriffs Token Secret

## <a name="step-4-configure-the-twitter-connector-app"></a>Schritt 4: Konfigurieren der Twitter Connector-App

Im nächsten Schritt fügen Sie der Twitter Connector-APP, die Sie in Schritt 2 bereitgestellt haben, Konfigurationseinstellungen hinzu. Gehen Sie dazu auf die Startseite Ihrer Connector-APP, und konfigurieren Sie Sie.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [configure the Connector Internet app](deploy-twitter-connector.md#step-4-configure-the-connector-web-app).

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der vorherigen Schritte in eine Textdatei kopiert haben):

- Twitter-API-Schlüssel (in Schritt 3 abgerufen)

- Geheimer Twitter-API-Schlüssel (in Schritt 3 abgerufen)

- Twitter-Zugriffs Token (in Schritt 3 abgerufen)

- Twitter-Zugriffs Token Secret (in Schritt 3 abgerufen)

- Azure Active Directory Application ID (die Aad-Anwendungs-ID, die in Schritt 1 abgerufen wurde)

- Azure Active Directory Application Secret (der in Schritt 1 abgerufene Aad-Anwendungsschlüssel)

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Twitter-Konnektors im Microsoft 365 Compliance Center

Der letzte Schritt besteht darin, den Twitter-Konnektor im Microsoft 365 Compliance Center einzurichten, mit dem Daten aus dem Twitter-Konto Ihrer Organisation in ein angegebenes Postfach in Microsoft 365 importiert werden. Nachdem Sie diesen Schritt ausgeführt haben, startet der Office 365-Import Dienst mit dem Importieren von Daten aus dem Twitter-Konto Ihrer Organisation nach Microsoft 365.

Eine Schritt-für-Schritt-Anleitung finden Sie unter [Einrichten eines Twitter-Konnektors im Microsoft 365 Compliance Center](deploy-twitter-connector.md#step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center). 

Während des Abschlusses dieses Schritts (indem Sie die schrittweisen Anweisungen befolgen) geben Sie die folgenden Informationen an (die Sie nach Abschluss der Schritte in eine Textdatei kopiert haben).

- Azure-App-Dienst-URL (in Schritt 2 abgerufen, `https://twitterconnector.azurewebsites.net`beispielsweise)

- APISecretKey (das Sie in Schritt 2 erstellt haben)
