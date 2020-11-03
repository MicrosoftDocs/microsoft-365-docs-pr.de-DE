---
title: Einrichten Ihrer Microsoft 365 Defender Test Lab-oder Pilotumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie Ihre Microsoft 365 Defender Test Lab-Umgebung ein.
keywords: Microsoft Threat Protection-Test-Setup, Microsoft Threat Protection Pilot-Setup, Testen von Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab-Setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844824"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a>Einrichten Ihrer Microsoft 365 Defender Test Lab-Umgebung 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**Gilt für:**
- Microsoft 365 Defender 


Das Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Vorbereiten Ihres Microsoft 365 Defender-Evaluierungs Labors oder einer Pilotumgebung" />
      <br/>Phase 1: Vorbereiten </a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Einrichten Ihrer Microsoft 365 Defender Test Lab-oder Pilotumgebung" />
      <br/>Phase 2: Setup </a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Konfigurieren der einzelnen Microsoft 365 Defender-Pfeiler für Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung und an Bord ihrer Endpunkte" />
      <br/>Phase 3: Konfigurieren von & Onboard </a><br>
</td>


  </tr>
</table>

Sie befinden sich derzeit in der Setupphase. Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und richten Sie die Testumgebung oder Pilotumgebung ein.

Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können. 

>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Test-oder Pilot Mandanten überspringen.

In dieser Phase werden Sie zu folgenden Themen geführt:
- Erstellen eines Office 365 E5-Testmandanten
- Microsoft 365-Testabonnement aktivieren


## <a name="create-an-office-365-e5-trial-tenant"></a>Erstellen eines Office 365 E5-Testmandanten
>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.

1. Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion** aus.

   ![Image of_Office 365 E5 ﻿kostenlose Test Seite](../../media/mtp-eval-9.png)
  
2. Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben. Klicken Sie auf **Konto einrichten**.

   ![Setup Seite für Bild of_Office 365 E5-Testregistrierung](../../media/mtp-eval-10.png)

3. Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.  

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite Fragen nach Namen, Telefon-und Firmendetails](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.
  
4. Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf. Klicken Sie auf **Bestätigungs Code senden**. 

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite mit der Aufforderung zur Überprüfung bevorzugt](../../media/mtp-eval-12.png)

5. Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird. Geben Sie den **Namen** und das **Kennwort ein**. Klicken Sie auf **Anmelden**.

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)

7. Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.

   ![Bild der Office 365 E5-Test Registrierungsseite, die zum Klicken auf die Schaltfläche "Gehe zu Setup" auffordert](../../media/mtp-eval-15.png)

8. Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten. Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein. Klicken Sie auf **Weiter**.

   ![Image of_Office 365 E5-Setup Seite, auf der Sie Ihre Anmeldung und e-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. Hinzufügen eines txt-oder MX-Eintrags zum Überprüfen des Domänenbesitzes. Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen** aus.

   ![Image of_Office 365 E5-Setup Seite, auf der Sie einen MX-Eintrag txt hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten. Sie können diesen Schritt überspringen, indem Sie auf **weiter** klicken.

    ![Image of_Office 365 E5-Setup Seite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. Optional Laden Sie Office-Apps herunter. Klicken Sie auf **weiter** , um diesen Schritt zu überspringen. 

    ![Image of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. Optional Migrieren von e-Mail-Nachrichten Sie können diesen Schritt auch wieder überspringen.

    ![Image of_Office 365 E5, in dem Sie festlegen können, ob e-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. Wählen Sie Onlinedienste aus. Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**. 

    ![Image of_Office 365 E5, wo Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu. Wählen Sie nach Abschluss die Option **überprüfen** aus.

    ![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.

    ![Bestätigungsseite für Bild of_Office 365 E5-Setup Abschluss](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365-Testabonnement aktivieren

>[!NOTE]
>Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden. Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .

1. Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.

2. Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**. 

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite](../../media/mtp-eval-24.png)

3. Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf. Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite Fragen Sie nach Kontaktdetails zum Senden von Code, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**.

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite, auf der Sie den Überprüfungscode ausfüllen können das System, das zum Nachweis gesendet wird, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.

   ![Image of_Microsoft 365 E5 Startkosten lose Test Seite, auf der Sie die Schaltfläche "jetzt testen" starten sollten](../../media/mtp-eval-27.png)
 
6. Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active Users**. Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten** aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5** aus. Klicken Sie auf **Speichern**.

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzername verwalten können](../../media/mtp-eval-29.png)

8. Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben. Klicken Sie auf **Änderungen speichern**.

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a>Nächster Schritt
|![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png) <br>[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie jede Microsoft 365 Defender-Säule für Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung und an Bord ihrer Endpunkte.
|:-------|:-----|
