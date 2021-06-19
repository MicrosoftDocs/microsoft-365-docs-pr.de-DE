---
title: Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"
f1.keywords:
- NOCSH
ms.author: siosulli
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie die Add-Ins "Nachricht melden" oder "Phishing melden" für Outlook und Outlook im Web, für einzelne Benutzer oder für Ihre gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c7e5136e6d1a118df2e0e91f09a79a9a63e88052
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028583"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Aktivieren der Add-Ins "Berichtnachricht" oder "Phishing melden"

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal in Microsoft 365 Defender zu verwenden. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

Mit den Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) können Benutzer einfach falsch positive Ergebnisse (als falsch markierte gute E-Mails) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse melden. 

Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern. Nehmen wir beispielsweise an, dass Viele Nachrichten mithilfe des Add-Ins "Phishing melden" gemeldet werden. Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt. Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen. 

Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren. Wenn Ihre Benutzer sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Add-In "Nachricht melden" in Ihrer Organisation bereit. Weitere Informationen finden Sie unter Aktivieren des Add-Ins "Nachricht melden". 

Das Add-In "Nachricht melden" bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden. Administratoren können das Add-In "Nachricht melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren. 

Das Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden. Administratoren können das Add-In "Phishing melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren. 

Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.

Wenn Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In "Nachricht melden" und das Add-In "Phishing melden" für Ihre Organisation aktivieren. Beide Add-Ins sind jetzt über [die zentrale Bereitstellung](../../admin/manage/centralized-deployment-of-add-ins.md)verfügbar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sowohl das Add-In "Nachricht melden" als auch das Add-In "Phishing melden" funktionieren mit den meisten Microsoft 365 Abonnements und den folgenden Produkten:
  - Outlook im Web 
  - Outlook 2013 SP1 oder höher
  - Outlook 2016 für Mac
  - Outlook in Microsoft 365 Apps für Enterprise enthalten
  - Outlook-App für iOS und Android

- Beide Add-Ins sind nicht für freigegebene Postfächer oder Postfächer in lokalen Exchange Organisationen verfügbar.

- Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch mit "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie einen anderen Browser.

- Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden. Weitere Informationen finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).

- Weitere Informationen zum Melden einer Nachricht mithilfe des Berichtsnachrichtenfeatures finden Sie unter [Bericht falsch positive und falsch negative Ergebnisse in Outlook](report-false-positives-and-false-negatives.md).

> [!IMPORTANT]
> Es wird nicht empfohlen, die integrierte Berichterstellung in Outlook zu verwenden, da die [Benutzerübermittlungsrichtlinie](./user-submission.md)nicht verwendet werden kann. Es wird empfohlen, stattdessen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" zu verwenden.

## <a name="get-the-report-message-add-in"></a>Abrufen des Add-Ins "Berichtnachricht"

### <a name="get-the-add-in-for-yourself"></a>Abrufen des Add-Ins für sich selbst

1. Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Nachricht melden". To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klicken Sie **auf "JETZT ABRUFEN".**

   ![Nachricht melden – Jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**

4. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.

Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  > [!div class="mx-imgBorder"]
  > ![Add-In-Symbol "Nachricht melden" für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Web sieht das Symbol wie folgt aus:

  > [!div class="mx-imgBorder"]
  > ![Outlook im Web Add-In-Symbol "Nachricht melden"](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>Abrufen des Add-Ins für Ihre Organisation

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

2. Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**

4. Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben Sie **"Meldung melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol. Suchen Sie in der Liste der Ergebnisse nach **"Berichtnachricht",** und klicken Sie dann auf **"Hinzufügen".**

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**

7. Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:

   - **Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:

     - **Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**
     - **Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.

   ![Add-In-Seite konfigurieren](../../media/configure-add-in.png)

   Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**

8. Auf der angezeigten Seite **"Berichtnachricht bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**

   ![Seite "Berichtnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Nachricht melden"

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite **Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Suchen sie das Add-In **"Nachricht melden",** und wählen Sie es aus.

3. Überprüfen und bearbeiten Sie im angezeigten Flyout **"Berichtnachricht bearbeiten"** die Einstellungen entsprechend Ihrer Organisation. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für das Add-In "Nachricht melden"](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Abrufen des Berichtsphishing-Add-Ins

### <a name="get-the-add-in-for-yourself"></a>Abrufen des Add-Ins für sich selbst

1. Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Phishing melden".

2. Klicken Sie **auf "JETZT ABRUFEN".**

3. Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**

4. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.

Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie folgt aus:

  > [!div class="mx-imgBorder"]
  > ![Outlook im Web Symbol "Phishing-Add-In melden"](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>Abrufen des Add-Ins für Ihre Organisation

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

2. Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Überprüfen Sie im angezeigten **Flyout "Neues Add-In bereitstellen"** die Informationen, und klicken Sie dann auf **"Weiter".**

4. Klicken Sie auf der nächsten Seite auf **"Aus dem Store auswählen".**

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. Klicken Sie auf der angezeigten **Add-In-Seite "Add-In auswählen"** in das **Suchfeld,** geben **Sie "Phishing melden"** ein, und **klicken** Sie dann auf das ![ ](../../media/search-icon.png) Suchsymbol. Suchen Sie in der Liste der Ergebnisse **nach "Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**

6. Überprüfen Sie im daraufhin angezeigten Dialogfeld die Lizenz- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**

7. Konfigurieren Sie auf der angezeigten Seite **"Add-In konfigurieren"** die folgenden Einstellungen:

   - **Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:

     - **Behoben (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-In zu **Hause** \> **installieren. Add-Ins** werden \> **vom Administrator verwaltet.**
     - **Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann jedoch entfernt werden.

   Wenn Sie fertig sind, klicken Sie auf **"Bereitstellen".**

8. Auf der angezeigten Seite **"Bericht Phishing bereitstellen"** wird ein Statusbericht mit anschließender Bestätigung angezeigt, dass das Add-In bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**

9. Überprüfen Sie auf der angezeigten **Add-In-Seite "Ankündigen"** die Informationen, und klicken Sie dann auf **"Schließen".**

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Phishing melden"

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

2. Suchen Sie das **Add-In "Phishing melden",** und wählen Sie es aus.

3. Überprüfen und bearbeiten Sie im angezeigten **Flyout "Bericht Phishing bearbeiten"** einstellungen entsprechend Ihrer Organisation. Wenn Sie die gewünschten Einstellungen vorgenommen haben, klicken Sie auf **Speichern**.
