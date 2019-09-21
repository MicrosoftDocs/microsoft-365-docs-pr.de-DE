---
title: Bereitstellen eines Connectors zum Archivieren von Facebook-Daten in Office 365
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
description: Administratoren können einen systemeigenen Connector zum Importieren und Archivieren von Facebook-Geschäfts Seiten in Office 365 einrichten. Nachdem diese Daten in Office 365 importiert wurden, können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um die Steuerung der Facebook-Daten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1f5b0f241616cc95e79e80d054a8782f97c5887b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070965"
---
# <a name="deploy-a-connector-to-archive-facebook-data-in-office-365"></a>Bereitstellen eines Connectors zum Archivieren von Facebook-Daten in Office 365

Dieser Artikel enthält den schrittweisen Prozess zur Bereitstellungeines Connectors, der den Office 365 Import Dienst verwendet, um Daten von Facebook-Geschäfts Seiten in Office 365 zu importieren. Eine allgemeine Übersicht über diesen Prozess und eine Liste der erforderlichen Voraussetzungen für die Bereitstellungeines Facebook-Konnektors finden Sie unter [Verwenden eines Beispiel-Konnektors zum Archivieren von Facebook-Daten in Office 365 (Preview)](archive-facebook-data-with-sample-connector.md). 

## <a name="step-1-download-the-package"></a>Schritt 1: Herunterladen des Pakets

Laden Sie das vorgefertigte Paket aus dem Abschnitt Release im GitHub-Repository unter <https://github.com/Microsoft/m365-sample-connector-csharp-aspnet/releases>herunter. Laden Sie die ZIP-Datei mit dem Namen **SampleConnector. zip**unter der neuesten Version herunter. Sie laden diese ZIP-Datei in Schritt 4 in Azure hoch.

## <a name="step-2-create-an-app-in-azure-active-directory"></a>Schritt 2: Erstellen einer APP in Azure Active Directory

1. Wechseln Sie <https://portal.azure.com> zu, und melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administratorkontos an.

    ![Erstellen einer APP in Aad](media/FBCimage1.png)

2. Klicken Sie im linken Navigationsbereich auf **Azure Active Directory**.

    ![](media/FBCimage2.png)

3. Klicken Sie im linken Navigationsbereich auf **App-Registrierungen (Vorschau)** , und klicken Sie dann auf **neue Registrierung**.

    ![](media/FBCimage3.png)

4. Registrieren Sie die Anwendung. Wählen Sie unter Umleitungs-URI die Option Webin der Dropdownliste <https://portal.azure.com> Anwendungstyp aus, und geben Sie dann in das Feld für den URI ein.

   ![](media/FBCimage4.png)

5. Kopieren Sie die Anwendungs-ID **(Client) ID** und **Verzeichnis (Mandanten)** , und speichern Sie Sie in einer Textdatei oder an einem anderen sicheren Ort. Sie verwenden diese IDs in späteren Schritten.

   ![](media/FBCimage5.png)

6. Wechseln Sie zu **Zertifikaten #a0 Geheimnisse für die neue APP.**

   ![](media/FBCimage6.png)

7. Klicken Sie auf **neuer geheimer Client Schlüssel**

   ![](media/FBCimage7.png)

8. Erstellen Sie einen neuen geheimen Schlüssel. Geben Sie im Feld Beschreibung den geheimen Schlüssel ein, und wählen Sie dann einen Ablaufzeitraum aus. 

    ![](media/FBCimage8.png)

9. Kopieren Sie den Wert des geheimen Schlüssels, und speichern Sie ihn in einer Textdatei oder an einem anderen Speicherort. Dies ist der geheime Aad-Anwendungsschlüssel, den Sie in späteren Schritten verwenden.

   ![](media/FBCimage9.png)

10. Wechseln Sie zu **Manifest** , und kopieren Sie die identifierUris (die auch als Aad Application URI bezeichnet wird) wie im folgenden Screenshot hervorgehoben. Kopieren Sie den Aad-Anwendungs-URI in eine Textdatei oder einen anderen Speicherort. Sie verwenden Sie in Schritt 6.

   ![](media/FBCimage10.png)

## <a name="step-3-create-an-azure-storage-account"></a>Schritt 3: Erstellen eines Azure-speicherkontos

1. Wechseln Sie zur Azure-Startseite für Ihre Organisation.

    ![](media/FBCimage11.png)

2. Klicken Sie auf **Ressource erstellen** , und geben Sie **Speicherkonto** in das Suchfeld ein.

    ![](media/FBCimage12.png)

3. Klicken Sie auf **Speicher**, und klicken Sie dann auf **Speicherkonto**.

    ![](media/FBCimage13.png)

4. Wählen Sie auf der Seite **Speicherkonto erstellen** im Feld Abonnement die Option **Pay-as-you-go** oder **﻿Kostenlose Testversion** je nach Typ des Azure-Abonnements aus. Wählen Sie dann eine Ressourcengruppe aus, oder erstellen Sie eine.

    ![](media/FBCimage14.png)

5. Geben Sie einen Namen für das Speicherkonto ein.

    ![](media/FBCimage15.png)

6. Überprüfen Sie, und klicken Sie dann auf **Erstellen** , um das Speicherkonto zu erstellen.

    ![](media/FBCimage16.png)

7. Klicken Sie nach einigen Momenten auf **Aktualisieren** , und klicken Sie dann auf **Ressource wechseln** , um zum Speicherkonto zu navigieren.

    ![](media/FBCimage17.png)

8. Klicken Sie im linken Navigationsbereich auf **Zugriffstasten** .

    ![](media/FBCimage18.png)

9. Kopieren Sie eine **Verbindungszeichenfolge** , und speichern Sie Sie in einer Textdatei oder an einem anderen Speicherort. Verwenden Sie diese Option, wenn Sie eine Webanwendungs Ressource erstellen.

    ![](media/FBCimage19.png)

## <a name="step-4-create-a-new-web-app-resource-in-azure"></a>Schritt 4: Erstellen einer neuen webapp-Ressource in Azure

1. Klicken Sie auf der **Start** Seite im Azure-Portal auf **Ressource \> : alles \> -Webanwendung erstellen**. Klicken Sie auf der Seite **Webanwendung** auf **Erstellen**. 

   ![](media/FBCimage20.png)

2. Geben Sie die Details ein (wie unten dargestellt), und erstellen Sie dann die Webanwendung. Beachten Sie, dass der Name, den Sie im Feld **App-Name** eingeben, zum Erstellen der Azure-App-Dienst-URL verwendet wird. Beispiel: FBconnector.azurewebsites.net.

   ![](media/FBCimage21.png)

3. Wechseln Sie zur neu erstellten Webanwendungs-Ressource, und klicken Sie im linken Navigationsbereich auf **Anwendungseinstellungen** . Klicken Sie unter Anwendungseinstellungen auf neue Einstellung hinzufügen, und fügen Sie die folgenden drei Einstellungen hinzu: Verwenden Sie die Werte (die Sie in die Textdatei aus den vorherigen Schritten kopiert haben): 

    – **APISecretKey** – Sie können einen beliebigen Wert als geheimen Schlüssel eingeben. Dieser wird für den Zugriff auf die Connector-Webanwendung in Schritt 7 verwendet.

    – * * StorageAccountConnectionString – der Verbindungszeichenfolgen-URI, den Sie nach dem Erstellen des Azure-speicherkontos in Schritt 3 kopiert haben.

    – **Mandanten** Kennung – die Mandanten-ID Ihrer Office 365 Organisation, die Sie nach dem Erstellen der Facebook-Connector-app in Azure Active Directory in Schritt 2 kopiert haben.

    ![](media/FBCimage22.png)

4. Klicken Sie unter **Allgemeine Einstellungen** **auf neben** dem **immer ein**. Klicken Sie oben auf der Seite auf **Speichern** , um Anwendungseinstellungen zu speichern.

   ![](media/FBCimage23.png)

5. Der letzte Schritt besteht darin, den Quellcode der Connector-app in Azure hochzuladen, den Sie in Schritt 1 heruntergeladen haben. Wechseln Sie in einem Webbrowser zu https://<AzureAppResourceName>. SCM.azurewebsites.net/ZipDeployUi. Wenn beispielsweise der Name Ihrer Azure-App-Ressource (die Sie in Schritt 2 in diesem Abschnitt genannt haben) **FBconnector**lautet, gehen Sie zu https://fbconnector.scm.azurewebsites.net/ZipDeployUi. 

6. Ziehen Sie das SampleConnector. zip-Menü (das Sie in Schritt 1 heruntergeladen haben) auf diese Seite. Nachdem die Dateien hochgeladen wurden und die Bereitstellung erfolgreich war, sieht die Seite wie im folgenden Screenshot aus:

   ![](media/FBCimage24.png)

## <a name="step-5-register-the-facebook-app"></a>Schritt 5: Registrieren der Facebook-App

1. Wechseln Sie <https://developers.facebook.com>zu, melden Sie sich mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an, und klicken Sie dann auf **neue APP hinzufügen**.

   ![](media/FBCimage25.png)

2. Erstellen Sie eine neue APP-ID.

   ![](media/FBCimage26.png)

3. Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf der **Facebook-Anmelde** Kachel auf **Einrichten** .

   ![](media/FBCimage27.png)

4. Klicken Sie auf der Seite Facebook-Anmeldung einbinden auf **Website**.

   ![](media/FBCimage28.png)

5. Hinzufügen der Azure-App-Dienst-URL zum Beispiel https://fbconnector.azurewebsites.net.

   ![](media/FBCimage29.png)

6. Schließen Sie den Abschnitt Quick Start im Facebook-Anmelde Setup ab.

   ![](media/FBCimage30.png)

7. Klicken Sie im linken Navigationsbereich unter **Facebook-Anmeldung**auf **Einstellungen**, und fügen Sie den OAuth-Umleitungs-URI im Feld **gültige OAuth-Umleitungs-URIs** hinzu. Verwenden Sie das Format ** \<connectorserviceuri>/views/facebookoauth**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. Beispiel: https://fbconnector.azurewebsites.net.

   ![](media/FBCimage31.png)

8. Klicken Sie im linken Navigationsbereich auf **Produkte hinzufügen** , und klicken Sie dann auf **webhooks.** Klicken Sie im Pulldown-Menü **Seite** auf **Seite**. 

   ![](media/FBCimage32.png)

9. Fügen Sie die webhooks-Rückruf-URL hinzu, und fügen Sie ein Verify-Token hinzu. Das Format der Rückruf-URL, verwenden Sie das Format ** <connectorserviceuri>/API/FbPageWebhook**, wobei der Wert für connectorserviceuri die Azure-App-Dienst-URL für Ihre Organisation ist. zum Beispiel https://fbconnector.azurewebsites.net. 

    Das Verify-Token sollte einem starken Kennwort ähneln. Kopieren Sie das Verify-Token in eine Textdatei oder einen anderen Speicherort.

     ![](media/FBCimage33.png)

10. Testen und Abonnieren des Endpunkts für Feeds.

    ![](media/FBCimage34.png)

11. Fügen Sie eine Datenschutz-URL, ein App-Symbol und eine geschäftliche Verwendung hinzu. Kopieren Sie außerdem die APP-ID und den App-Schlüssel in eine Textdatei oder einen anderen Speicherort.

    ![](media/FBCimage35.png)

12. Machen Sie die APP öffentlich.

    ![](media/FBCimage36.png)

13. Fügen Sie der Administrator-oder Tester-Rolle einen Benutzer hinzu.

    ![](media/FBCimage37.png)

14. Fügen Sie die **Seite öffentliche Inhalts Zugriffs** Berechtigung hinzu.

    ![](media/FBCimage38.png)

15. Berechtigung zum Hinzufügen von Seiten verwalten.

    ![](media/FBCimage39.png)

16. Holen Sie sich die Anwendung von Facebook überprüft.

    ![](media/FBCimage40.png)

## <a name="step-6-configure-the-connector-web-app"></a>Schritt 6: Konfigurieren der Connector-Webanwendung

1. Wechseln Sie zu\<https://AzureAppResourceName>. azurewebsites.net (wobei AzureAppResourceName der Name Ihrer Azure-App-Ressource ist, die Sie in Schritt 4 benannt haben) Wenn beispielsweise der Name **FBconnector**lautet https://fbconnector.azurewebsites.net, wechseln Sie zu. Die Startseite der APP sieht wie im folgenden Screenshot aus:


   ![](media/FBCimage41.png)

2. Klicken Sie auf **Konfigurieren** , um eine Anmeldeseite anzuzeigen.
 
   ![](media/FBCimage42.png)

3. Geben Sie in das Feld Mandanten-ID die Mandanten-ID ein, die Sie in Schritt 2 erhalten haben, oder fügen Sie Sie ein. Geben Sie in das Feld Kennwort den APISecretKey (den Sie in Schritt 2 erhalten haben) ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Konfigurationseinstellungen festlegen** , um die Seite **Konfigurations Details** anzuzeigen.

    ![](media/FBCimage43.png)


4. Geben Sie unter **Konfigurations Details**die folgenden Konfigurationseinstellungen ein: 

   – **Facebook-Anwendungs-ID** – die APP-ID für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.
   – **Facebook-Anwendungs Geheimnis** – der APP-Schlüssel für die Facebook-Anwendung, die Sie in Schritt 5 erhalten haben.
   – **Facebook webhooks Überprüfen des Tokens** – das Überprüfen-Token, das Sie in Schritt 5 erstellt haben.
   – **Aad-Anwendungs-ID** – die Anwendungs-ID für die Azure Active Directory-APP, die Sie in Schritt 2 erstellt haben.
   – **Aad-Anwendungs Geheimnis** – der Wert für den geheimen Schlüssel "APISecretKey", den Sie in Schritt 4 erstellt haben.
   – **Aad Application URI** – der in Schritt 2 abgerufene Aad-Anwendungs-URI; Beispiel: https://microsoft.onmicrosoft.com/2688yu6n-12q3-23we-e3ee-121111123213.
   – **App Insights Instrumentation Key** – lassen Sie dieses Feld leer.

5. Klicken Sie auf **Speichern** , um die Verbindungseinstellungen zu speichern.

## <a name="step-7-set-up-a-custom-connector-in-the-security--compliance-center"></a>Schritt 7: Einrichten eines benutzerdefinierten Connectors im Security #a0 Compliance Center

1. Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Data Governance \> Import \> Archivieren von drittanbieterdaten**.

   ![](media/FBCimage44.png)

2.  Klicken Sie auf **Connector hinzufügen** , und klicken Sie dann auf **Facebook-Seiten**.

    ![](media/FBCimage46.png)

3.  Geben Sie auf der Seite " **Connector-app hinzufügen** " die folgenden Informationen ein, und klicken Sie dann auf **Connector überprüfen**.

    – Geben Sie im ersten Feld einen Namen für den Connector ein, beispielsweise **Facebook**.
    – Geben Sie im zweiten Feld den Wert des APISecretKey ein, den Sie in Schritt 4 hinzugefügt haben, oder fügen Sie ihn ein.
    – Geben Sie im dritten Feld die Azure-App-Dienst-URL ein, oder fügen Sie Sie ein. zum Beispiel **https://fbconnector.azurewebsites.net**.
 
    Nachdem der Connector erfolgreich überprüft wurde, klicken Sie auf **weiter**.
    
    ![](media/FBCimage47.png)

4.  Klicken Sie auf **Anmeldung mit der Connector-App**.

    ![](media/FBCimage45.png)

5. Geben Sie den APISecretKey erneut ein, oder fügen Sie ihn ein, und klicken Sie dann auf **Login to Connector Service**.

   ![](media/FBCimage48.png)


6. Klicken Sie auf **Anmelden bei Facebook.**

   ![](media/FBCimage49.png)

7. Melden Sie sich auf der Seite **Anmelden bei Facebook** mit den Anmeldeinformationen für das Konto für die Facebook-Geschäfts Seiten Ihrer Organisation an. Stellen Sie sicher, dass das Facebook-Konto, an dem Sie sich angemeldet haben, der Administratorrolle für die Facebook-Geschäfts Seiten Ihrer Organisation zugewiesen ist.

   ![](media/FBCimage50.png)

8. Klicken Sie auf **Seiten auswählen** , um die Geschäfts Seiten Ihrer Organisation auszuwählen, die Sie in Office 365 archivieren möchten.

   ![](media/FBCimage51.png)

9. Eine Liste der Geschäfts Seiten, die von dem Facebook-Konto verwaltet werden, in dem Sie sich angemeldet haben, wird angezeigt. Wählen Sie die zu archivierende Seite aus, und klicken Sie dann auf **Speichern**.

    ![](media/FBCimage52.png)

10. Klicken Sie auf **vorbereiten** , um das Setup der Connector-Dienst-APP zu beenden.

    ![](media/FBCimage53.png)

11. Auf der Seite **Filter festlegen** können Sie einen Filter anwenden, um Elemente zu importieren (und archivieren), die ein bestimmtes Alter aufweisen. Klicken Sie auf **Weiter**.

    ![](media/FBCimage54.png)

12. Wählen Sie auf der Seite **Speicherkonto festlegen** das Office 365 Postfach aus, in das die Elemente der Facebook-Geschäfts Seiten importiert werden, die Sie zuvor ausgewählt haben.

    ![](media/FBCimage55.png)

13. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup im Security #a0 Compliance Center abzuschließen.

    ![](media/FBCimage56.png)

14. Wechseln Sie zur Seite **Archivieren von drittanbieterdaten** , um den Fortschritt des Importvorgangs anzuzeigen.

    ![](media/FBCimage58.png)
