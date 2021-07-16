---
title: Einrichten ihrer Microsoft 365 Defender Testumgebung oder Pilotumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie dann Ihre Microsoft 365 Defender Testumgebung ein.
keywords: Microsoft 365 Defender Testsetup, Microsoft 365 Defender Piloteinrichtung, testen Sie Microsoft 365 Defender, Microsoft 365 Defender Testumgebungssetup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454733"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a>Einrichten der Microsoft 365 Defender Testversion in einer Testumgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender 

In diesem Thema erfahren Sie, wie Sie eine dedizierte Lab-Umgebung einrichten. Informationen zum Einrichten einer Testversion in der Produktion finden Sie im neuen Leitfaden ["Auswerten und Pilot Microsoft 365 Defender".](eval-overview.md) 

## <a name="create-an-office-365-e5-trial-tenant"></a>Erstellen eines Office 365 E5 Testmandanten
>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen Office 365 E5 Testmandanten überspringen.

1. Wechseln Sie zum [Office 365 E5 Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie **"Kostenlose Testversion"** aus.

   ![Abbildung of_Office 365 E5–Testversionsseite](../../media/mtp-eval-9.png)
  
2. Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (persönlich oder Unternehmensadresse) eingeben. Klicken Sie auf **Konto einrichten.**

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite](../../media/mtp-eval-10.png)

3. Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, Ihren Firmennamen, Ihre Unternehmensgröße und Ihr Land oder Ihre Region ein.  

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Nachnamen, Telefon- und Unternehmensdetails gefragt werden](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Das Land oder die Region, das/die Sie hier festlegen, bestimmt die Rechenzentrumsregion, in der Ihre Office 365 gehostet wird.
  
4. Wählen Sie Ihre Überprüfungseinstellung aus: über eine SMS oder einen Anruf. Klicken Sie auf **"Überprüfungscode senden".** 

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite mit Aufforderung zur Überprüfung](../../media/mtp-eval-12.png)

5. Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **"Weiter".**

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist. Geben Sie **Name** und **Kennwort ein.** Klicken Sie auf **Registrieren**.

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihre Unternehmensidentität festlegen können](../../media/mtp-eval-14.png)

7. Klicken Sie auf **"Zum Setup wechseln",** um die Bereitstellung der Office 365 E5 Testmandanten abzuschließen.

   ![Abbildung der Setupseite für Office 365 E5 Testversion, auf der sie aufgefordert wird, auf die Schaltfläche "Setup wechseln" zu klicken](../../media/mtp-eval-15.png)

8. Verbinden Sie Ihre Unternehmensdomäne an den Office 365 Mandanten weiter. [Optional] Wählen Sie **Verbinden eine Domäne aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein. Klicken Sie auf **Weiter**.

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen. Nachdem Sie ihrer Domäne den TXT- oder MX-Eintrag hinzugefügt haben, wählen Sie **"Überprüfen"** aus.

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie eine TXT mit MX-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. [Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten. Sie können diesen Schritt überspringen, indem Sie auf **"Weiter"** klicken.

    ![Abbildung of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. [Optional] Laden Sie Office Apps herunter. Klicken Sie auf **"Weiter",** um diesen Schritt zu überspringen. 

    ![Abbildung of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. [Optional] Migrieren von E-Mail-Nachrichten. Auch hier können Sie diesen Schritt überspringen.

    ![Abbildung of_Office 365 E5, in dem Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. Wählen Sie Onlinedienste aus. Wählen Sie **Exchange** aus, und klicken Sie auf **"Weiter".** 

    ![Abbildung of_Office 365 E5, in dem Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. Fügen Sie IHRER Domäne MX-, CNAME- und TXT-Einträge hinzu. Wählen Sie nach Abschluss des Vorgangs **"Überprüfen"** aus.

    ![Abbildung of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres Office 365 Mandanten abgeschlossen.

    ![Abbildung of_Office Seite zur Bestätigung des Abschlusses des Setups für 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Aktivieren Microsoft 365 Testabonnements

>[!NOTE]
>Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die Sie für einen Monat verwenden können. Weitere Informationen finden Sie unter ["Testen oder Kaufen eines M365-Abonnements".](../../commerce/try-or-buy-microsoft-365.md)

1. Klicken Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **"Abrechnung",** und navigieren Sie dann zu **"Dienste kaufen".**

2. Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **"Kostenlose Testversion starten".** 

   ![Abbildung of_Microsoft 365 E5 – Startseite der kostenlosen Testversion](../../media/mtp-eval-24.png)

3. Wählen Sie Ihre Überprüfungseinstellung aus: über eine SMS oder einen Anruf. Sobald Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **"Mich anrufen"** oder **"Anrufen"** aus, je nach Auswahl.

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie nach Kontaktdetails gefragt werden, um Code zu senden, um nachzuweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. Geben Sie den Überprüfungscode ein, und klicken Sie auf **"Kostenlose Testversion starten".**

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um nachzuweisen, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. Klicken Sie auf **"Jetzt testen",** um Ihre Microsoft 365 E5 Testversion zu bestätigen.

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie die Schaltfläche "Jetzt testen" anzeigen sollten, um zu starten](../../media/mtp-eval-27.png)
 
6. Wechseln Sie zu den aktiven Benutzern **Microsoft 365 Admin**  >  **Center-Benutzer.**  >   Wählen Sie Ihr Benutzerkonto aus, wählen **Sie "Produktlizenzen verwalten"** und dann die Lizenz von Office 365 E5 in **Microsoft 365 E5** aus. Klicken Sie auf **Speichern**.

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie Microsoft 365 E5 Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann auf **"Benutzernamen verwalten".**

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie "Konto" und dann "Benutzername verwalten" auswählen können](../../media/mtp-eval-29.png)

8. [Optional] Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne, je nachdem, was Sie in den vorherigen Schritten ausgewählt haben. Klicken Sie auf **Änderungen speichern**.

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nächster Schritt
|[Phase 3: Konfigurieren & Onboarding](config-m365d-eval.md) | Konfigurieren Sie jede Microsoft 365 Defender Säulen für Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung, und integrieren Sie Ihre Endpunkte.
|:-------|:-----|
