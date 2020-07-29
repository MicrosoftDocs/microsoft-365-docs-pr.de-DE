---
title: Bereitstellen eines Connectors zum Archivieren von Facebook-Geschäfts Seiten Daten
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
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können einen systemeigenen Connector einrichten, um Facebook-Geschäfts Seiten in Microsoft 365 zu importieren und zu archivieren. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Facebook-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 240ce3a90cf46a05ab5d6030b9318d42d23904d8
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434235"
---
# <a name="deploy-a-connector-to-archive-facebook-business-pages-data"></a>Bereitstellen eines Connectors zum Archivieren von Facebook-Geschäfts Seiten Daten

Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365-Import Dienst verwendet, um Daten von Facebook-Geschäfts Seiten nach Microsoft 365 zu importieren. Eine allgemeine Übersicht über diesen Prozess und eine Liste der Voraussetzungen, die für die Bereitstellungeines Facebook-Konnektors erforderlich sind, finden Sie unter [Einrichten eines Connectors zum Archivieren von Facebook-Daten](archive-facebook-data-with-sample-connector.md).

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

1. Wechseln Sie zu, <https://portal.azure.com> und melden Sie sich mit den Anmeldeinformationen eines globalen Administratorkontos an.

    ![Erstellen einer APP in Aad](../media/FBCimage1.png)

2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.

    ![Klicken Sie auf Azure Active Directory](../media/FBCimage2.png)

3. Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.

    ![Klicken Sie auf * * App-Registrierungen (Vorschau) * * und dann auf * * neue Registrierung * *](../media/FBCimage3.png)

4. Registrieren Sie die Anwendung. Wählen Sie unter Umleitungs-URI die Option Webin der Dropdownliste Anwendungstyp aus, und geben Sie dann <https://portal.azure.com> in das Feld für den URI ein.

   ![Registrieren der App](../media/FBCimage4.png)

5. Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort. Sie verwenden diese IDs in späteren Schritten.

   ![Kopieren Sie die Anwendungs-ID und die Verzeichnis-ID, und speichern Sie Sie.](../media/FBCimage5.png)

6. Wechseln Sie zu **Zertifikaten & Geheimnisse für die neue APP.**

   ![Wechseln Sie zu Zertifikaten & Geheimnisse für die neue APP.](../media/FBCimage6.png)

7. Klicken Sie auf **neuer geheimer Client Schlüssel**

   ![Klicken Sie auf neuer geheimer Client Schlüssel](../media/FBCimage7.png)

8. Erstellen Sie einen neuen geheimen Schlüssel. Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus.

    ![Geben Sie den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum](../media/FBCimage8.png)

9. Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort. Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.

   ![Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn.](../media/FBCimage9.png)

## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-sample-connector-csharp-aspnet) , und klicken Sie auf **in Azure bereitstellen**.

    ![Klicken Sie auf in Azure bereitstellen](../media/FBCGithubApp.png)

2. Nachdem Sie auf **in Azure bereitstellen**klicken, werden Sie zu einem Azure-Portal mit einer benutzerdefinierten Vorlagenseite umgeleitet. Füllen Sie die Details **Grundlagen** und **Einstellungen** aus, und klicken Sie dann auf **kaufen**.

   - **Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, für das Sie den Facebook Business Pages-Connector-Webdienst bereitstellen möchten.

   - **Ressourcengruppe:** Wählen oder erstellen Sie eine neue Ressourcengruppe. Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung bereit hält.

   - **Speicherort:** Wählen Sie einen Speicherort aus.

   - **Name der Webanwendung:** Geben Sie einen eindeutigen Namen für die Connector-Webanwendung an. Th Name muss zwischen 3 und 18 Zeichen lang sein. Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie beispielsweise den Namen der Webanwendung von **FBconnector** angeben, wird die Azure-App-Dienst-URL **FBconnector.azurewebsites.net**.

   - **Mandanten** -Nr: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 1 kopiert haben.

   - **APISecretKey:** Sie können einen beliebigen Wert als geheimen Schlüssel eingeben. Dies wird verwendet, um in Schritt 5 auf die Connector-Webanwendung zuzugreifen.

     ![Klicken Sie auf Ressource erstellen, und geben Sie Speicherkonto ein.](../media/FBCimage12.png)

3. Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich wie der folgende Screenshot aus:

   ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](../media/FBCimage13.png)

## <a name="step-3-register-the-facebook-app"></a>Schritt 3: Registrieren der Facebook-App

1. Wechseln <https://developers.facebook.com> Sie zu, melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an, und klicken Sie dann auf **neue APP hinzufügen**.

   ![Hinzufügen einer neuen App für Facebook-Geschäftsseite](../media/FBCimage25.png)

2. Erstellen Sie eine neue APP-ID.

   ![Erstellen einer neuen APP-ID](../media/FBCimage26.png)

3. Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf der **Facebook-Anmelde** Kachel auf **Einrichten** .

   ![Klicken Sie auf Produkte hinzufügen.](../media/FBCimage27.png)

4. Klicken Sie auf der Seite Facebook-Anmeldung einbinden auf **Website**.

   ![Klicken Sie auf der Seite Facebook-Anmeldung integrieren auf Website.](../media/FBCimage28.png)

5. Hinzufügen der Azure-App-Dienst-URL zum Beispiel `https://fbconnector.azurewebsites.net` .

   ![Hinzufügen der Azure-App-Dienst-URL](../media/FBCimage29.png)

6. Schließen Sie den Abschnitt Quick Start im Facebook-Anmelde Setup ab.

   ![Abschließen des Schnellstart-Abschnitts](../media/FBCimage30.png)

7. Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung**auf **Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld **gültige OAuth-Umleitungs-URIs** hinzu. Verwenden Sie das Format ** \<connectorserviceuri> /views/FacebookOAuth**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, beispielsweise `https://fbconnector.azurewebsites.net` .

   ![Fügen Sie den OAuth-Umleitungs-URI zum Feld gültige OAuth-Umleitungs-URIs hinzu](../media/FBCimage31.png)

8. Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf **webhooks.** Klicken Sie im Pulldown-Menü **Seite** auf **Seite**.

   ![Klicken Sie auf Produkte hinzufügen, und klicken Sie dann auf * * webhooks.](../media/FBCimage32.png)

9. Fügen Sie die webhooks-Rückruf-URL hinzu, und fügen Sie ein Verify-Token hinzu. Das Format der Rückruf-URL, verwenden Sie das Format ** <connectorserviceuri> /API/FbPageWebhook**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist, zum Beispiel `https://fbconnector.azurewebsites.net` .

   Das Verify-Token sollte einem starken Kennwort ähneln. Kopieren Sie das Verify-Token in eine Textdatei oder einen anderen Speicherort.

   ![Hinzufügen des Überprüfungs Tokens](../media/FBCimage33.png)

10. Testen und Abonnieren des Endpunkts für Feeds.

    ![Testen und Abonnieren des Endpunkts](../media/FBCimage34.png)

11. Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine geschäftliche Verwendung hinzu. Kopieren Sie außerdem die APP-ID und den App-Schlüssel in eine Textdatei oder einen anderen Speicherort.

    ![Hinzufügen einer Datenschutz-URL, eines App-Symbols und einer geschäftlichen Verwendung](../media/FBCimage35.png)

12. Machen Sie die APP öffentlich.

    ![Veröffentlichen der APP](../media/FBCimage36.png)

13. Fügen Sie der Administrator-oder Tester-Rolle einen Benutzer hinzu.

    ![Hinzufügen eines Benutzers zur Administrator-oder Tester-Rolle](../media/FBCimage37.png)

14. Fügen Sie die **Seite öffentliche Inhalts Zugriffs** Berechtigung hinzu.

    ![DD die Seite öffentliche Inhalts Zugriffsberechtigung](../media/FBCimage38.png)

15. Berechtigung zum Hinzufügen von Seiten verwalten.

    ![Berechtigung zum Hinzufügen von Seiten verwalten](../media/FBCimage39.png)

16. Holen Sie sich die Anwendung von Facebook überprüft.

    ![Abrufen der von Facebook überprüften Anwendung](../media/FBCimage40.png)

## <a name="step-4-configure-the-connector-web-app"></a>Schritt 4: Konfigurieren der Connector-Webanwendung

1. Wechseln `https://<AzureAppResourceName>.azurewebsites.net` Sie zu (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben). Wenn der Name beispielsweise **FBconnector**lautet, wechseln Sie zu `https://fbconnector.azurewebsites.net` . Die Startseite der APP sieht wie im folgenden Screenshot aus:

   ![Wechseln Sie zur Connector-Webanwendung](../media/FBCimage41.png)

2. Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.

   ![Klicken Sie auf konfigurieren, um eine Anmeldeseite anzuzeigen.](../media/FBCimage42.png)

3. Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein. Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite Konfigurationsdetails anzuzeigen.

    ![Melden Sie sich mit Ihrer Mandanten-ID und Ihrem Kennwort an, und wechseln Sie zur Seite Konfigurationsdetails.](../media/FBCimage43.png)

4. Geben Sie die folgenden Konfigurationseinstellungen ein:

   - **Facebook-Anwendungs-ID:** Die APP-ID für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.

   - **Geheime Facebook-Anwendung:** Der APP-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 3 erhalten haben.

   - **Facebook webhooks überprüfen Token:** Das Überprüfen-Token, das Sie in Schritt 3 erstellt haben.

   - **Aad-Anwendungs-ID:** Die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 1 erstellt haben.

   - **Aad-Anwendungsschlüssel:** Der Wert für den geheimen APISecretKey, den Sie in Schritt 1 erstellt haben.

5. Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.

## <a name="step-5-set-up-a-facebook-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Facebook-Connectors im Microsoft 365 Compliance Center

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .

2. Klicken Sie auf der Seite **Daten Konnektoren (Vorschau)** unter **Facebook Business Pages**auf **Ansicht**.

3. Klicken Sie auf der Seite **Facebook-Geschäfts Seiten** auf **Connector hinzufügen**.

4. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

5. Geben Sie auf der Seite **Anmeldeinformationen für ihre Connector-app hinzufügen** die folgenden Informationen ein, und klicken Sie dann auf **Verbindung überprüfen**.

   ![Eingeben von Connector-App-Anmeldeinformationen](../media/TCimage38.png)

   - Geben Sie im Feld **Name** einen Namen für den Connector ein, beispielsweise **Facebook-Nachrichtenseite**.

   - Geben Sie im Feld **Verbindungs-URL** die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel `https://fbconnector.azurewebsites.net` .

   - Geben Sie in das Feld **Kennwort** den Wert des APISecretKey ein, den Sie in Schritt 2 hinzugefügt haben, oder fügen Sie ihn ein.

   - Geben Sie in das Feld **Azure-APP-ID** den Wert der Anwendungs-ID Application (Client) ein, die auch als Aad-Anwendungs-ID bezeichnet wird, die Sie in Schritt 1 erstellt haben, oder fügen Sie ihn ein.

6. Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **weiter**.

7. Geben Sie auf der Seite **Microsoft 365 zum Importieren von Daten autorisieren** den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login-webapp**.

8. Klicken Sie auf der Seite **Facebook Connector-App konfigurieren** auf **Anmeldung bei Facebook** , und melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an. Stellen Sie sicher, dass das Facebook-Konto, an dem Sie sich angemeldet haben, der Administratorrolle für die Facebook-Geschäfts Seiten Ihrer Organisation zugewiesen ist.

   ![Melden Sie sich bei Facebook an.](../media/FBCimage50.png)

9. Eine Liste der Geschäfts Seiten, die von dem Facebook-Konto verwaltet werden, in dem Sie sich angemeldet haben, wird angezeigt. Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **weiter**.

   ![Wählen Sie die Geschäftsseite der Organisation aus, die Sie archivieren möchten.](../media/FBCimage52.png)

10. Klicken Sie auf **weiter** , um das Setup der Connector-Dienst-APP zu beenden.

11. Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente anfänglich zu importieren, die ein bestimmtes Alter aufweisen. Wählen Sie ein Alter aus, und klicken Sie dann auf **weiter**.

12. Geben Sie auf der Seite Speicherort **auswählen** die e-Mail-Adresse des Microsoft 365-Postfachs ein, in das die Facebook-Elemente importiert werden sollen, und klicken Sie dann auf **weiter**.

13. Klicken Sie im die **Zustimmung des Administrators bereit**stellen auf **Zustimmung erteilen** , und führen Sie dann die Schritte aus. Sie müssen ein globaler Administrator sein, um die Zustimmung des Office 365-Import Diensts für den Zugriff auf Daten in Ihrer Organisation zu geben.

14. Klicken Sie auf **weiter** , um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup abzuschließen.

15. Wechseln Sie im Compliance Center zur Seite **Daten Konnektoren** , und klicken Sie auf die Registerkarte **Connectors** , um den Status des Importvorgangs anzuzeigen.
