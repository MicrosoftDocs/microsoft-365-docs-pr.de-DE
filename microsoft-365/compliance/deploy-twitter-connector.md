---
title: Bereitstellen eines Connectors zum Archivieren von Twitter-Daten
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Twitter-Daten nach Microsoft 365 einrichten. Nachdem diese Daten in Microsoft 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Twitter-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 9bf0be8684eb18fbc022f4eefa798c5c9265b3d7
ms.sourcegitcommit: e872676ec98036a50d3a0cb5071109ea5f5a7ae5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/24/2020
ms.locfileid: "41515696"
---
# <a name="deploy-a-connector-to-archive-twitter-data"></a>Bereitstellen eines Connectors zum Archivieren von Twitter-Daten

Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten aus dem Twitter-Konto Ihrer Organisation nach Microsoft 365 zu importieren. Eine allgemeine Übersicht über diesen Prozess und eine Liste der Voraussetzungen, die für die Bereitstellungeines Twitter-Connectors erforderlich sind, finden Sie unter [Einrichten eines Connectors zum Archivieren von Twitter-Daten ](archive-twitter-data-with-sample-connector.md). 

## <a name="step-1-create-an-app-in-azure-active-directory"></a>Schritt 1: Erstellen einer APP in Azure Active Directory

1. Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.

   ![Bei Azure anmelden](media/TCimage01.png)

2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.

   ![Wechseln Sie zu Azure Active Directory](media/TCimage02.png)

3. Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.

   ![Erstellen einer neuen App-Registrierung](media/TCimage03.png)

4. Registrieren Sie die Anwendung. Wählen Sie unter **Umleitungs-URI (optional)** in der Dropdownliste Anwendungstyp die `https://portal.azure.com` Option **Webseite** aus, und geben Sie dann in das Feld für den URI ein.

   ![Typ https://portal.azure.com für den Umleitungs-URI ](media/TCimage04.png)

5. Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort. Sie verwenden diese IDs in späteren Schritten.

    ![Kopieren und Speichern der Anwendungs-ID und der Verzeichnis-ID](media/TCimage05.png)

6. Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP** und unter **Client Secrets** auf **neuen geheimen Client Schlüssel**.

   ![Erstellen eines neuen geheimen Client Schlüssels](media/TCimage06.png)

7. Erstellen Sie einen neuen geheimen Schlüssel. Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus. 

   ![Geben Sie den geheimen Schlüssel ein und wählen Sie Ablaufzeitraum](media/TCimage08.png)

8. Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort. Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.

   ![Kopieren und Speichern des geheimen Schlüssels](media/TCimage09.png)


## <a name="step-2-deploy-the-connector-web-service-from-github-to-your-azure-account"></a>Schritt 2: Bereitstellen des Connector-Webdiensts von GitHub in Ihrem Azure-Konto

1. Wechseln Sie zu [dieser GitHub-Website](https://github.com/microsoft/m365-sample-twitter-connector-csharp-aspnet) , und klicken Sie auf **in Azure bereitstellen**.

    ![Wechseln zur Azure-Startseite](media/FBCimage11.png)

2. Nachdem Sie auf **in Azure bereitstellen**klicken, werden Sie zu einem Azure-Portal mit einer benutzerdefinierten Vorlagenseite umgeleitet. Füllen Sie die Details **Grundlagen** und **Einstellungen** aus, und klicken Sie dann auf **kaufen**.

   ![Klicken Sie auf Ressource erstellen, und geben Sie Speicherkonto ein.](media/FBCimage12.png)

    - **Abonnement:** Wählen Sie Ihr Azure-Abonnement aus, für das Sie den Twitter Connector-Webdienst bereitstellen möchten.
    
    - **Ressourcengruppe:** Wählen oder erstellen Sie eine neue Ressourcengruppe. Eine Ressourcengruppe ist ein Container, der verwandte Ressourcen für eine Azure-Lösung bereit hält.

    - **Speicherort:** Wählen Sie einen Speicherort aus.

    - **Name der Webanwendung:** Geben Sie einen eindeutigen Namen für die Connector-Webanwendung an. Th Name muss zwischen 3 und 18 Zeichen lang sein. Dieser Name wird zum Erstellen der Azure-App-Dienst-URL verwendet. Wenn Sie beispielsweise den Namen der Webanwendung von **twitterconnector** angeben, wird die Azure-App-Dienst-URL **twitterconnector.azurewebsites.net**.
    
    - **Mandanten** -Nr: Die Mandanten-ID Ihrer Microsoft 365-Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 1 kopiert haben.
    
   - **APISecretKey:** Sie können einen beliebigen Wert als geheimen Schlüssel eingeben. Dies wird verwendet, um in Schritt 5 auf die Connector-Webanwendung zuzugreifen.

3. Nachdem die Bereitstellung erfolgreich war, sieht die Seite ähnlich wie der folgende Screenshot aus:

    ![Klicken Sie auf Speicher, und klicken Sie dann auf Speicherkonto](media/FBCimage13.png)

## <a name="step-3-create-the-twitter-app"></a>Schritt 3: Erstellen der Twitter-APP

1. Wechseln Sie https://developer.twitter.comzu, melden Sie sich mit den Anmeldeinformationen für das Entwicklerkonto für Ihre Organisation an, und klicken Sie dann auf **apps**.

   ![Wechseln Sie https://developer.twitter.com zu und melden Sie sich an.](media/TCimage25-5.png)
2. Klicken Sie auf **app erstellen**.
   
   ![Zur Seite "Apps" wechseln, um eine APP zu erstellen](media/TCimage26.png)

3. Fügen Sie unter **App-Details**Informationen zur Anwendung hinzu.

   ![Eingeben von Informationen zur APP](media/TCimage27.png)

4. Wählen Sie im Twitter Developer Dashboard die soeben erstellte App aus, und kopieren Sie die angezeigte APP-ID, und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort. Klicken Sie dann auf **Details**.
   
   ![Kopieren und Speichern der APP-ID](media/TCimage28.png)

5. Kopieren Sie auf der Registerkarte **Schlüssel und Token** unter **Consumer-API-Schlüssel** den geheimen Schlüssel der API, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort. Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.
   
   ![Geheimer Schlüssel "Kopieren und speichern in API"](media/TCimage29.png)

   Klicken Sie dann auf **Erstellen** , um ein Zugriffstoken und einen Zugriffstoken Schlüssel zu generieren, und kopieren Sie diese in eine Textdatei oder einen anderen Speicherort.

6. Klicken Sie auf die Registerkarte **Berechtigungen** , und konfigurieren Sie die Berechtigungen wie im folgenden Screenshot dargestellt:

   ![Konfigurieren von Berechtigungen](media/TCimage30.png)

7. Nachdem Sie die Berechtigungseinstellungen gespeichert haben, klicken Sie auf die Registerkarte **App-Details** , und klicken Sie dann auf **Bearbeiten #a0 bearbeiten von Details**.

   ![Bearbeiten der App-Details](media/TCimage31.png)

8. Führen Sie die folgenden Aufgaben aus:

   - Aktivieren Sie das Kontrollkästchen, damit sich die Connector-App bei Twitter anmelden kann.
   
   - Fügen Sie den OAuth-Umleitungs-URI mit dem folgenden Format hinzu: ** \<connectorserviceuri>/views/twitteroauth**, wobei der Wert von *connectorserviceuri* die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: https://twitterconnector.azurewebsites.net/Views/TwitterOAuth.

    ![Connector-App erlauben, sich bei Twitter anzumelden und OAuth-Umleitungs-URI hinzuzufügen](media/TCimage32.png)

Die Twitter-Entwickler-App ist jetzt einsatzfähig.

## <a name="step-4-configure-the-connector-web-app"></a>Schritt 4: Konfigurieren der Connector-Webanwendung 

1. Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei **AzureAppResourceName** der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben). Wenn der Name beispielsweise **twitterconnector**lautet, wechseln Sie zu https://twitterconnector.azurewebsites.net. Die Startseite der APP sieht wie im folgenden Screenshot aus:

   ![Seite zur Azure-App-Ressource wechseln](media/FBCimage41.png)

2. Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.

   ![Klicken Sie auf konfigurieren, um die Anmeldeseite anzuzeigen.](media/FBCimage42.png)

3. Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein. Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite Konfigurationsdetails anzuzeigen.

   ![Anmelden mithilfe der Mandanten-ID und des geheimen Schlüssels der API](media/TCimage35.png)

4. Geben Sie die folgenden Konfigurationseinstellungen ein: 

   - **Twitter-API-Schlüssel:** Die APP-ID für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.
   
   - **Geheimer Twitter-API-Schlüssel:** Der geheime API-Schlüssel für die Twitter-Anwendung, die Sie in Schritt 3 erstellt haben.
   
   - **Twitter-Zugriffs Token:** Das Zugriffstoken, das Sie in Schritt 3 erstellt haben.
   
   - **Geheimer Twitter-Zugriffs Token:** Der geheime Zugriffstoken, den Sie in Schritt 3 erstellt haben.
   
   - **Aad-Anwendungs-ID:** Die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 1 erstellt haben
   
   - **Aad-Anwendungsschlüssel:** Der Wert für den geheimen APISecretKey, den Sie in Schritt 1 erstellt haben.

5. Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.

## <a name="step-5-set-up-a-twitter-connector-in-the-microsoft-365-compliance-center"></a>Schritt 5: Einrichten eines Twitter-Konnektors im Microsoft 365 Compliance Center

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann im linken Navigationsbereich auf **Datenverbindungen** .

2. Klicken Sie auf der Seite **Daten Konnektoren (Vorschau)** unter **Twitter**auf **Ansicht**.

3. Klicken Sie auf der Seite **Twitter** auf **Connector hinzufügen**.

4. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

5. Geben Sie auf der Seite **Anmeldeinformationen für ihre Connector-app hinzufügen** die folgenden Informationen ein, und klicken Sie dann auf **Verbindung überprüfen**.

   ![Eingeben von Connector-App-Anmeldeinformationen](media/TCimage38.png)

    - Geben Sie im Feld **Name** einen Namen für den Connector ein, beispielsweise **Twitter help handle**.
    
    - Geben Sie im Feld **Connector-URL** die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel `https://twitterconnector.azurewebsites.net`.
    
    - Geben Sie in das Feld **Kennwort** den Wert des APISecretKey ein, den Sie in Schritt 2 erstellt haben, oder fügen Sie ihn ein.
    
    - Geben Sie in das Feld **Azure-APP-ID** den Wert der Azure Application-APP-ID (auch als *Client-ID*bezeichnet) ein, oder fügen Sie ihn ein, den Sie in Schritt 1 erhalten haben.

6. Nachdem die Verbindung erfolgreich überprüft wurde, klicken Sie auf **weiter**.

7. Geben Sie auf der Seite **Microsoft 365 zum Importieren von Daten autorisieren** den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login-webapp**.

8. Klicken Sie auf **Login mit Twitter**.

9. Melden Sie sich auf der Twitter-Anmeldeseite mit den Anmeldeinformationen für das Twitter-Konto Ihrer Organisation an.

   ![Bei Twitter-Konto anmelden](media/TCimage42.png)

   Nachdem Sie sich angemeldet haben, wird auf der Twitter-Seite die folgende Meldung angezeigt: "Twitter Connector-Auftrag erfolgreich eingerichtet."

10. Klicken Sie auf **weiter** , um die Einrichtung des Twitter-Konnektors abzuschließen.

11. Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente anfänglich zu importieren, die ein bestimmtes Alter aufweisen. Wählen Sie ein Alter aus, und klicken Sie dann auf **weiter**.

12. Geben Sie auf der Seite Speicherort **auswählen** die e-Mail-Adresse des Microsoft 365-Postfachs ein, in das die Twitter-Elemente importiert werden sollen, und klicken Sie dann auf **weiter**.

13. Klicken Sie im die **Zustimmung des Administrators bereit**stellen auf **Zustimmung erteilen** , und führen Sie dann die Schritte aus. Sie müssen ein globaler Administrator sein, um die Zustimmung des Office 365-Import Diensts für den Zugriff auf Daten in Ihrer Organisation zu geben.

14. Klicken Sie auf **weiter** , um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup abzuschließen.

15. Wechseln Sie im Compliance Center zur Seite **Daten Konnektoren** , und klicken Sie auf die Registerkarte **Connectors** , um den Status des Importvorgangs anzuzeigen.
