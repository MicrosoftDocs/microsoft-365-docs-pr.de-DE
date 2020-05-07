---
title: Einrichten Ihrer Microsoft Threat Protection-Testumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie Ihre Microsoft Threat Protection Test Lab-Umgebung ein.
keywords: Microsoft Threat Protection-Test-Setup, testen Sie Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049615"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a>Einrichten Ihrer Microsoft Threat Protection-Testumgebung 

**Gilt für:**
- Microsoft Threat Protection 


Das Erstellen einer Microsoft Threat Protection-Test Umgebungsumgebung und deren Bereitstellung ist ein dreistufiger Prozess:

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Vorbereiten des Microsoft Threat Protection-Evaluierungs Labors" />
      <br/>Phase 1: Vorbereiten</a><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Einrichten Ihres Microsoft Threat Protection-Evaluierungs Labors" />
      <br/>Phase 2: Setup</a><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihre Microsoft Threat Protection-Test Umgebungsumgebung und die Bereitstellung an Bord ihrer Endpunkte" />
      <br/>Phase 3: Konfigurieren von & Onboard</a><br>
</td>


  </tr>
</table>

Sie befinden sich derzeit in der Setupphase. Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und installieren Sie dann die Testumgebung.

Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können. 

>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.

In dieser Phase werden Sie zu folgenden Themen geführt:
- Erstellen eines Office 365 E5-Testmandanten
- Microsoft 365-Testabonnement aktivieren


## <a name="create-an-office-365-e5-trial-tenant"></a>Erstellen eines Office 365 E5-Testmandanten
>[!NOTE]
>Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.

1. Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion**aus.
![Bild of_page](../../media/mtp-eval-9.png) <br>
  
2. Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben. Klicken Sie auf **Konto einrichten**.
![Bild of_page](../../media/mtp-eval-10.png) <br> 

3. Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.  
<br>![Bild of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
>Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.
  
4. Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf. Klicken Sie auf **Bestätigungs Code senden**. 
![Bild of_page](../../media/mtp-eval-12.png) <br>

5. Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.
<br>![Bild of_page](../../media/mtp-eval-13.png) <br>
 
6. Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird. Geben Sie den **Namen** und das **Kennwort ein**. Klicken Sie auf **Anmelden**.
![Bild of_page](../../media/mtp-eval-14.png) <br>
c
7. Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.
<br>![Bild of_page](../../media/mtp-eval-15.png) <br>

8. Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten. Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein. Klicken Sie auf **Weiter**.
<br>![Bild of_page](../../media/mtp-eval-16.png) <br>
 
9. Sie müssen einen txt-oder MX-Eintrag hinzufügen, um den Domänenbesitz zu überprüfen. Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen**aus.
<br>![Bild of_page](../../media/mtp-eval-17.png) <br>
 
10. Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten. Sie können diesen Schritt überspringen, indem Sie auf **weiter**klicken.
![Bild of_page](../../media/mtp-eval-18.png) <br>
 
11. Optional Laden Sie Office-Apps herunter. Klicken Sie auf **weiter** , um diesen Schritt zu überspringen. 
<br>![Bild of_page](../../media/mtp-eval-19.png) <br>

12. Optional Migrieren von e-Mail-Nachrichten Sie können diesen Schritt auch wieder überspringen.
<br>![Bild of_page](../../media/mtp-eval-20.png) <br>
 
13. Wählen Sie Onlinedienste aus. Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**. 
<br>![Bild of_page](../../media/mtp-eval-21.png) <br>

14. Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu. Wählen Sie nach Abschluss die Option **überprüfen**aus.
<br>![Bild of_page](../../media/mtp-eval-22.png) <br>
 
15. Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.
<br>![Bild of_page](../../media/mtp-eval-23.png) <br>

## <a name="enable-microsoft-365-trial-subscription"></a>Microsoft 365-Testabonnement aktivieren

>[!NOTE]
>Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden. Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .

1. Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.

2. Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**. 
![Bild of_page](../../media/mtp-eval-24.png) <br>

3. Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf. Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.
![Bild of_page](../../media/mtp-eval-25.png) <br>
 
4. Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**. 
<br>![Bild of_page](../../media/mtp-eval-26.png) <br>

5. Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.
<br>![Bild of_page](../../media/mtp-eval-27.png) <br>
 
6. Wechseln Sie zum **Microsoft 365 Admin Center** > **Users** > **Active Users**. Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten**aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5**aus. Klicken Sie auf **Speichern**.
![Bild of_page](../../media/mtp-eval-28.png) <br>
 
7. Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.
<br>![Bild of_page](../../media/mtp-eval-29.png) <br>

8. Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben. Klicken Sie auf **Änderungen speichern**.
<br>![Bild of_page](../../media/mtp-eval-30.png) <br>



## <a name="next-step"></a>Nächster Schritt
||| |:-------|:-----| config-Onboard. png) <br>[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie jede Microsoft Threat Protection-Säule für Ihre Microsoft Threat Protection-Test Umgebungsumgebung und ihre Endpunkte an Bord.
