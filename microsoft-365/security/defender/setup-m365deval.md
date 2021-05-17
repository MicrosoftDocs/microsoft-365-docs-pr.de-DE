---
title: Einrichten ihrer Microsoft 365 Testumgebung oder Pilotumgebung für Defender
description: Access Microsoft 365 Security Center, und richten Sie dann Ihre Microsoft 365 Defender-Testumgebung ein.
keywords: Microsoft 365 Defender-Testeinrichtung, Microsoft 365 defender pilot setup, try Microsoft 365 Defender, Microsoft 365 Defender evaluation lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935425"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Einrichten ihrer Microsoft 365 Defender-Testumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender 


Das Erstellen Microsoft 365 einer Defender-Testumgebung oder Pilotumgebung und deren Bereitstellung ist ein drei phasenweiser Prozess:

|[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)<br/>[Phase 1: Vorbereiten](prepare-m365d-eval.md) |![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)<br/>[Phase 3: Onboarding](config-m365d-eval.md) | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)<br/>[Zurück zum Testspielbuch](m365d-pilot.md) |
|--|--|--|--|
||*Sie sind hier!*  | | |


Sie sind derzeit in der Einrichtungsphase. Ergreifen Sie die ersten Schritte, um auf Microsoft 365 Security Center zu zugreifen, und richten Sie dann Ihre Testumgebung oder Pilotumgebung ein.

Registrieren Sie sich für ein Office 365- oder Azure Active Directory-Abonnement, um einen *.onmicrosoft.com-Mandanten* zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5 registrieren können. 

>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365 oder Azure Active Directory verfügen, können Sie die Schritte Office 365 E5-Test- oder Pilot-Mandantenerstellung überspringen.

In dieser Phase werden Sie geführt zu:
- Erstellen eines Office 365 E5-Test-Mandanten
- Aktivieren Microsoft 365 Testabonnements


## <a name="create-an-office-365-e5-trial-tenant"></a>Erstellen eines Office 365 E5-Test-Mandanten
>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365 oder Azure Active Directory verfügen, können Sie die Schritte zum Erstellen Office 365 E5-Test-Mandanten überspringen.

1. Wechseln Sie zum [Office 365 E5-Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie **Kostenlose Testversion aus.**

   ![Kostenlose of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (privat oder unternehmensanmeldend) eingeben. Klicken **Sie auf Konto einrichten**.

   ![Setupseite of_Office 365 E5-Testversion](../../media/mtp-eval-10.png)

3. Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.  

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der nach Namen, Telefon und Firmendetails gefragt wird](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Das land oder die Region, das Sie hier festgelegt haben, bestimmt die Rechenzentrumsregion, Office 365 gehostet wird.
  
4. Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf. Klicken **Sie auf Überprüfungscode senden**. 

   ![Abbildung of_Office 365 E5-Testregistrierungseinrichtungsseite mit der Bitte um Überprüfungseinstellung](../../media/mtp-eval-12.png)

5. Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten ein, und klicken Sie dann auf **Weiter**.

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist. Geben Sie **Name und** **Kennwort ein.** Klicken Sie auf **Anmelden**.

   ![Abbildung of_Office 365 E5-Testregistrierungseinrichtungsseite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)

7. Klicken **Sie auf Zu Setup** wechseln, um Office 365 E5-Test-Mandantenbereitstellung abzuschließen.

   ![Abbildung der Office 365 E5-Testregistrierungsseite, auf der sie aufgefordert wird, auf Setup gehen zu klicken](../../media/mtp-eval-15.png)

8. Verbinden Ihrer Unternehmensdomäne an den Office 365 mandanten. [Optional] Wählen **Verbinden eine Domäne aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein. Klicken Sie auf **Weiter**.

   ![Bild of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen. Nachdem Sie den TXT- oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **Überprüfen aus.**

   ![Bild of_Office 365 E5-Setupseite, auf der Sie einen TXT-MX-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. [Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten. Sie können diesen Schritt überspringen, indem Sie auf **Weiter klicken.**

    ![Image of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. [Optional] Laden Office Apps herunter. Klicken Sie **auf Weiter,** um diesen Schritt zu überspringen. 

    ![Image of_Office 365 E5-Seite, auf der Sie Ihre Office installieren können](../../media/mtp-eval-19.png)

12. [Optional] Migrieren von E-Mail-Nachrichten. Auch hier können Sie diesen Schritt überspringen.

    ![Image of_Office 365 E5, in dem Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. Wählen Sie Onlinedienste aus. Wählen **Exchange** aus, und klicken Sie auf **Weiter**. 

    ![Bild of_Office 365 E5, in dem Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. Fügen Sie Ihrer Domäne MX-, CNAME- und #A0 hinzu. Wenn Sie abgeschlossen sind, wählen Sie **Überprüfen aus.**

    ![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres mandanten Office 365 abgeschlossen.

    ![Bestätigungsseite of_Office 365 E5-Setupabschluss](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivieren Microsoft 365 Testabonnements

>[!NOTE]
>Wenn Sie sich für eine Testversion anmelden, können Sie 25 Benutzerlizenzen für einen Monat verwenden. Weitere [Informationen finden Sie unter Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)

1. Klicken [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung,** und navigieren Sie dann zu **Dienste kaufen**.

2. Wählen **Microsoft 365 E5** aus, und klicken Sie **auf Kostenlose Testversion starten.** 

   ![Image of_Microsoft 365 E5 Kostenlose Testversion starten](../../media/mtp-eval-24.png)

3. Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf. Nachdem Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text me** oder Rufen Sie **mich** je nach Auswahl auf.

   ![Image of_Microsoft 365 E5 Kostenlose Testseite starten und um Kontaktdetails bitten, um Code zu senden, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. Geben Sie den Überprüfungscode ein, und klicken **Sie auf Kostenlose Testversion starten.**

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testseite starten, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um zu bestätigen, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. Klicken **Sie auf Jetzt** testen, um ihre Microsoft 365 E5 bestätigen.

   ![Image of_Microsoft 365 E5 Kostenlose Testseite starten, auf der Sie die Schaltfläche Jetzt testen zum Starten sehen sollten](../../media/mtp-eval-27.png)
 
6. Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active users**. Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten** aus, und tauschen Sie dann die Lizenz von Office 365 E5 in **Microsoft 365 E5**. Klicken Sie auf **Speichern**.

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie eine Microsoft 365 E5 auswählen können](../../media/mtp-eval-28.png)
 
7. Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann **auf Benutzername verwalten.**

   ![Bild of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzernamen verwalten auswählen können](../../media/mtp-eval-29.png)

8. [Optional] Ändern Sie die Domäne *von onmicrosoft.com* in Ihre eigene Domäne , je nachdem, was Sie bei den vorherigen Schritten ausgewählt haben. Klicken Sie auf **Änderungen speichern**.

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nächster Schritt
|[Phase 3: Konfigurieren & Onboard](config-m365d-eval.md) | Konfigurieren Sie Microsoft 365 Defender-Säule für Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung und integrieren Sie Ihre Endpunkte.
|:-------|:-----|
