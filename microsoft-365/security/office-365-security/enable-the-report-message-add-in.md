---
title: Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden
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
description: Erfahren Sie, wie Sie die Berichtsnachricht oder die Phishing-Add-Ins für Outlook und Outlook im Web, für einzelne Benutzer oder für Ihre gesamte Organisation aktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dc54c5b74697ac41a1d4ff0818467dba662b31f5
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52295819"
---
# <a name="enable-the-report-message-or-the-report-phishing-add-ins"></a>Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins melden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365 mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden. Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).

Die Phishing-Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen es Benutzern, falsch positive Ergebnisse (gute E-Mails, die als ungültig gekennzeichnet sind) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse zu melden. 

Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern. Angenommen, die Benutzer melden viele Nachrichten mithilfe des Phishing-Add-Ins Melden. Diese Informationen werden im Sicherheitsdashboard und anderen Berichten angezeigt. Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen. 

Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren. Wenn Ihre Benutzer Spam- und Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung. Weitere Informationen finden Sie unter Aktivieren des Berichtsnachrichten-Add-Ins. 

Das Add-In Report Message bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden. Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren. 

Das Phishing-Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden. Administratoren können das Phishing-Add-In melden für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren. 

Wenn Sie ein einzelner Benutzer sind, können Sie beide Add-Ins für sich selbst aktivieren.

f Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das Add-In Nachricht melden und das Phishing-Add-In melden für Ihre Organisation aktivieren. Beide Add-Ins sind jetzt über die zentrale [Bereitstellung verfügbar.](../../admin/manage/centralized-deployment-of-add-ins.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sowohl das Report Message-Add-In als auch das Phishing-Add-In Report funktioniert mit den meisten Microsoft 365 und den folgenden Produkten:

  - Outlook im Web
  - Outlook 2013 SP1 oder höher
  - Outlook 2016 für Mac
  - Outlook in Microsoft 365 apps for Enterprise
  - Outlook App für iOS und Android

- Beide Add-Ins sind nicht für freigegebene Postfächer oder Postfächer in lokalen Organisationen Exchange verfügbar.

- Ihr vorhandener Webbrowser sollte sowohl mit den Add-Ins "Nachricht melden" als auch "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.

- Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden. Weitere Informationen finden Sie unter [Determine if Centralized Deployment of add-ins works for your organization](../../admin/manage/centralized-deployment-of-add-ins.md).

- Administratoren müssen Mitglied der Rollengruppe Globale Administratoren sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Weitere Informationen zum Melden einer Nachricht mithilfe des Berichtsnachrichtenfeatures finden Sie unter Melden falsch positiver und falsch negativer [Outlook](report-false-positives-and-false-negatives.md).

## <a name="get-the-report-message-add-in"></a>Get the Report Message add-in

### <a name="get-the-add-in-for-yourself"></a>Das Add-In für sich selbst

1. Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Add-In Nachricht melden. Um direkt zum Add-In "Nachricht melden" zu wechseln, wechseln Sie zu <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klicken Sie **auf JETZT GET IT**.

   ![Berichtsnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.

4. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.

Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie dies aus:

  > [!div class="mx-imgBorder"]
  > ![Symbol zum Melden von Nachrichten-Add-Ins für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Web sieht das Symbol wie dies aus:

  > [!div class="mx-imgBorder"]
  > ![Outlook im Web Nachrichten-Add-In-Symbol melden](../../media/owa-report-message-icon.png)

### <a name="get-the-add-in-for-your-organization"></a>Das Add-In für Ihre Organisation erhalten

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.

1. Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.

2. Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.

4. Klicken Sie auf der nächsten Seite auf **Auswählen aus Store**.

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Meldung** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) . Suchen Sie in der Liste der Ergebnisse nach **Berichtnachricht,** und klicken Sie dann auf **Hinzufügen**.

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

6. Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.

7. Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:

   - **Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:

     - **Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**
     - **Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.

8. Auf der **angezeigten** Seite Berichtsnachricht bereitstellen wird ein Fortschrittsbericht angezeigt, gefolgt von der Bestätigung, dass das Add-In bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **Weiter**.

   ![Seite "Berichtsnachricht bereitstellen"](../../media/deploy-report-message-page.png)

9. Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Report Message-Add-In

1. Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.

   ![Seite "Dienste Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Suchen Sie das **Add-In Nachricht** melden, und wählen Sie es aus.

3. Überprüfen **und** bearbeiten Sie im angezeigten Flyout Berichtsnachricht bearbeiten die Einstellungen, die für Ihre Organisation geeignet sind. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="get-the-report-phishing-add-in"></a>Das Phishing-Add-In melden

### <a name="get-the-add-in-for-yourself"></a>Das Add-In für sich selbst

1. Wechseln Sie zur Microsoft AppSource <https://appsource.microsoft.com/marketplace/apps> unter, und suchen Sie nach dem Phishing-Add-In Melden.

2. Klicken Sie **auf JETZT GET IT**.

3. Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **Weiter**.

4. Melden Sie sich mit Ihrem Geschäfts- oder Schulkonto (für geschäftliche Nutzung) oder Ihrem Microsoft-Konto (für den persönlichen Gebrauch) an.

Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie dies aus:

  ![Melden des Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie dies aus:

  > [!div class="mx-imgBorder"]
  > ![Outlook im Web Phishing-Add-In-Symbol melden](../../media/OWA-ReportPhishing.png)

### <a name="get-the-add-in-for-your-organization"></a>Das Add-In für Ihre Organisation erhalten

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.

1. Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.

2. Wählen **Sie add-in** bereitstellen oben auf der Seite aus, und wählen Sie dann **Weiter aus.**

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Überprüfen Sie im angezeigten Flyout Bereitstellen eines neuen **Add-Ins** die Informationen, und klicken Sie dann auf **Weiter**.

4. Klicken Sie auf der nächsten Seite auf **Auswählen aus Store**.

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. Klicken Sie auf der angezeigten Seite  **Add-In** auswählen in das Feld Suchen, geben Sie **Phishing** melden ein, und klicken Sie dann auf **Suchsymbol** ![ ](../../media/search-icon.png) . Suchen Sie in der Liste der Ergebnisse nach **Phishing melden,** und klicken Sie dann auf **Hinzufügen**.

6. Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **Weiter**.

7. Konfigurieren Sie auf der angezeigten Seite **Add-In** konfigurieren die folgenden Einstellungen:

   - **Zugewiesene** Benutzer : Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode**: Wählen Sie einen der folgenden Werte aus:

     - **Fixed (Standard):** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-In unter **Home** \> **Get add-ins** \> **Admin-managed installieren.**
     - **Optional:** Das Add-In wird automatisch für die angegebenen Benutzer bereitgestellt, kann es jedoch entfernen.

   Klicken Sie nach Abschluss des Abschlusses auf **Bereitstellen**.

8. Auf der **angezeigten Seite Phishingbericht** bereitstellen sehen Sie einen Fortschrittsbericht, gefolgt von einer Bestätigung, dass das Add-In bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **Weiter**.

9. Überprüfen Sie auf der angezeigten Seite **Add-In** ankündigen die Informationen, und klicken Sie dann auf **Schließen**.

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In melden

1. Wechseln Sie Microsoft 365 Admin Center zur Seite Einstellungen  \> **Add-Ins** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> . Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** Integrierte \>  \> **Apps-Add-Ins**  oben auf der Seite Integrierte Apps.

2. Suchen Sie das **Phishing-Add-In melden,** und wählen Sie es aus.

3. In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization. Wenn Sie die gewünschten Einstellungen vorgenommen haben, klicken Sie auf **Speichern**.
