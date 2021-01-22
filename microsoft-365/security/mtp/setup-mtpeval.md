---
title: Einrichten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung
description: Greifen Sie auf Das Microsoft 365 Security Center zu, und richten Sie dann Ihre Microsoft 365 Defender-Testumgebung ein.
keywords: Einrichtung der Microsoft Threat Protection-Testversion, Microsoft Threat Protection-Pilotinstallation, Testen der Microsoft Threat Protection- und Microsoft Threat Protection-Evaluierungsumgebung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932982"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Einrichten ihrer Microsoft 365 Defender-Testumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender 


Das Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung und deren Bereitstellung besteht aus drei Phasen:

|[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)<br/>[Phase 1: Vorbereiten](prepare-mtpeval.md) |![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)<br/>Phase 2: Einrichten |[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)<br/>[Phase 3: Onboarding](config-mtpeval.md) | [![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)<br/>[Zurück zum Pilot-Playbook](mtp-pilot.md) |
|--|--|--|--|
||*Sie sind hier!*  | | |


Sie sind derzeit in der Einrichtungsphase. Nehmen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center vor, und richten Sie dann Ihre Testumgebung oder Pilotumgebung ein.

Registrieren Sie sich für ein Office 365- oder Azure Active Directory-Abonnement, um einen *.onmicrosoft.com-Mandanten* zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz registrieren können. 

>[!NOTE]
>Wenn Sie bereits über ein Vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testversionen oder Pilot-Mandanten überspringen.

In dieser Phase werden Sie geführt zu:
- Erstellen eines Office 365 E5-Test-Mandanten
- Aktivieren des Microsoft 365-Testabonnements


## <a name="create-an-office-365-e5-trial-tenant"></a>Erstellen eines Office 365 E5-Test-Mandanten
>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen des Office 365 E5-Test-Mandanten überspringen.

1. Wechseln Sie zum [Office 365 E5-Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie kostenlose **Testversion aus.**

   ![Abbildung of_Office 365 E5 ( kostenlose Testversion)](../../media/mtp-eval-9.png)
  
2. Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (persönlich oder unternehmensanmeldend) eingeben. Klicken **Sie auf Konto einrichten**.

   ![Abbildung of_Office 365 E5-Testregistrierungsseite](../../media/mtp-eval-10.png)

3. Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße sowie das Land oder die Region ein.  

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Nach Namen, Telefon und Unternehmensdetails gefragt werden](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Das Land oder die Region, das Sie hier festgelegt haben, bestimmt die Rechenzentrumsregion, in der Office 365 gehostet wird.
  
4. Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf. Klicken **Sie auf "Überprüfungscode senden".** 

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Die Überprüfungseinstellung angezeigt wird](../../media/mtp-eval-12.png)

5. Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten, und klicken Sie dann auf **Weiter**.

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist. Geben Sie **"Name"** und **"Password" ein.** Klicken Sie auf **Anmelden**.

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Sie Ihre Unternehmensidentität festlegen können](../../media/mtp-eval-14.png)

7. Klicken **Sie auf "Setup",** um die Bereitstellung des Office 365 E5-Test-Mandanten abzuschließen.

   ![Abbildung der Office 365 E5-Testregistrierungsseite, auf der Sie aufgefordert werden, auf die Schaltfläche "Setup wechseln" zu klicken](../../media/mtp-eval-15.png)

8. Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365-Mandanten. [Optional] Wählen **Sie "Verbinden" aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen. Nachdem Sie Den TXT- oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **"Überprüfen" aus.**

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie einen TXT-mx-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. [Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten. Sie können diesen Schritt überspringen, indem Sie auf **"Weiter" klicken.**

    ![Abbildung of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. [Optional] Laden Sie Die Office-Apps herunter. Klicken Sie **auf "Weiter",** um diesen Schritt zu überspringen. 

    ![Bild of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. [Optional] Migrieren von E-Mail-Nachrichten. Auch hier können Sie diesen Schritt überspringen.

    ![Abbildung of_Office 365 E5, in der Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. Wählen Sie Onlinedienste aus. Wählen Sie **Exchange** aus, und klicken Sie auf **"Weiter".** 

    ![Abbildung of_Office 365 E5, in der Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. Fügen Sie Ihrer Domäne MX-, CNAME- und #A0 hinzu. Wenn Sie fertig sind, wählen Sie **"Überprüfen"** aus.

    ![Abbildung of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres Office 365-Mandanten abgeschlossen.

    ![Abbildung of_Office 365 E5-Einrichtungsbestätigungsseite](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivieren des Microsoft 365-Testabonnements

>[!NOTE]
>Wenn Sie sich für eine Testversion anmelden, erhalten Sie 25 Benutzerlizenzen für einen Monat. Weitere [Informationen finden Sie unter "Testen oder Kaufen eines M365-Abonnements".](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1)

1. Klicken [Sie im Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **"Abrechnung",** und navigieren Sie dann zu **"Dienste kaufen".**

2. Wählen **Sie Microsoft 365 E5** aus, und klicken **Sie auf "Kostenlose Testversion starten".** 

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testversion](../../media/mtp-eval-24.png)

3. Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf. Nachdem Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **"Text me"** oder **"Call me"** aus, je nach Ihrer Auswahl.

   ![Abbildung of_Microsoft 365 E5 - Kostenlose Testseite, auf der Sie nach Kontaktdetails gefragt werden, um Code zu senden, um nachzuweisen, dass Sie kein Robot sind](../../media/mtp-eval-25.png)
 
4. Geben Sie den Überprüfungscode ein, und klicken **Sie auf "Kostenlose Testversion starten".**

   ![Abbildung of_Microsoft 365 E5 - Kostenlose Testseite, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um zu bestätigen, dass Sie kein Robot sind](../../media/mtp-eval-26.png)

5. Klicken **Sie auf "Jetzt testen",** um Ihre Microsoft 365 E5-Testversion zu bestätigen.

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testversionsseite, auf der Sie die Schaltfläche "Jetzt testen" zum Starten probieren sollten](../../media/mtp-eval-27.png)
 
6. Wechseln Sie zu den aktiven Benutzern im **Microsoft 365 Admin**  >    >  Center. Wählen Sie Ihr Benutzerkonto aus, **wählen** Sie "Produktlizenzen verwalten" aus, und tauschen Sie dann die Lizenz von Office 365 E5 zu **Microsoft 365 E5 aus.** Klicken Sie auf **Speichern**.

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann **auf "Benutzername verwalten".**

   ![Abbildung of_Microsoft 365 Admin Center- Seite, auf der Sie "Konto" und dann "Benutzernamen verwalten" auswählen können](../../media/mtp-eval-29.png)

8. [Optional] Ändern Sie die Domäne *von onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben. Klicken Sie auf **Änderungen speichern**.

   ![Abbildung of_Microsoft 365 Admin Center- Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nächster Schritt
|[Phase 3: Konfigurieren & Onboarding](config-mtpeval.md) | Konfigurieren Sie jede Microsoft 365 Defender-Säulen für Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung, und integrieren Sie Ihre Endpunkte.
|:-------|:-----|
