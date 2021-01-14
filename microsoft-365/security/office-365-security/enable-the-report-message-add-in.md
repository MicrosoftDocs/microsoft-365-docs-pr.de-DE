---
title: Aktivieren des Add-Ins „Nachrichten melden“
f1.keywords:
- NOCSH
ms.author: siosulli
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie das Report Message-Add-In für Outlook und Outlook im Web, für einzelne Benutzer oder ihre gesamte Organisation aktivieren.
ms.openlocfilehash: 13721317c33cf207f27cd8b98fb6d32864651847
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864996"
---
# <a name="enable-the-report-message-add-in"></a>Aktivieren des Add-Ins „Nachrichten melden“

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center. Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)

Die "Nachricht melden" und "Phishing melden"-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen Es Benutzern, falsch positive Ergebnisse (eine gute E-Mail als schlecht markiert) oder falsch negative Ergebnisse (ungültige E-Mails sind zulässig) zur Analyse an Microsoft und seine Partner zu melden.

Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern. Wenn Benutzer beispielsweise viele Nachrichten melden, die mithilfe des Add-Ins "Nachricht melden" als [Junk-E-Mail](configure-your-spam-filter-policies.md)gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise Antispamrichtlinien anpassen.

Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren. Wenn Ihre Benutzer nur Phishingnachrichten melden sollen, stellen Sie das Phishing-Add-In "Melden" in Ihrer Organisation zur Verfügung. Weitere Informationen finden Sie unter [Enable the Report Phishing add-in](enable-the-report-phish-add-in.md).

Das Report Message-Add-In bietet die Möglichkeit, Sowohl Spam- als auch Phishingnachrichten zu melden. Administratoren können das Report Message-Add-In für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.

Wenn Sie ein einzelner Benutzer sind, können Sie das Add-In "Nachricht [melden" für sich selbst aktivieren.](#get-the-report-message-add-in-for-yourself)

Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Berichtsnachrichten-Add-In für Ihre Organisation aktivieren.](#get-and-enable-the-report-message-add-in-for-your-organization) Die Berichtsnachricht Add-In jetzt über die zentrale [Bereitstellung verfügbar.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Das Report Message-Add-In funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:

  - Outlook im Web
  - Outlook 2013 SP1 oder höher
  - Outlook 2016 für Mac
  - Outlook im Lieferumfang von Microsoft 365 Apps for Enterprise

- Das Report Message-Add-In ist für Postfächer in lokalen Exchange-Organisationen nicht verfügbar.

- Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)

- Ihr vorhandener Webbrowser sollte mit dem Add-In "Nachricht melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es in einem anderen Browser.

- Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden. Weitere Informationen finden Sie unter Ermitteln, ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-message-add-in-for-yourself"></a>Das Berichtnachrichten-Add-In für sich selbst erhalten

1. Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Nachricht melden". To go directly to the Report Message add-in, go to <https://appsource.microsoft.com/product/office/wa104381180> .

2. Klicken **Sie auf "JETZT GET IT".**

   ![Berichtnachricht – Jetzt erhalten](../../media/ReportMessageGETITNOW.png)

3. Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**

4. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Firmenkonto (zur geschäftlichen Nutzung) oder Ihrem Microsoft-Konto (zur persönlichen Nutzung) an.

Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie hier dargestellt aus:

  ![Symbol für Das Add-In"-Symbol "Nachricht melden" für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Web sieht das Symbol wie hier dargestellt aus:

  ![Outlook im Web - Add-In-Symbol "Nachricht melden"](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Informationen zur Verwendung des Add-Ins finden Sie unter [Verwenden des Add-Ins](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)"Nachricht melden".

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Get and enable the Report Message add-in for your organization

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-in in Ihrer Organisation angezeigt wird.

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite Einstellungen, integrierte Apps **&-Add-Ins,** und klicken Sie dann auf <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **"Add-In bereitstellen".**

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Überprüfen Sie **im angezeigten Flyout** "Neues Add-In bereitstellen" die Informationen, und klicken Sie dann auf **"Weiter".**

3. Klicken Sie auf der nächsten Seite auf **"Aus Store auswählen".**

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

4. Klicken Sie auf **der angezeigten Seite "Add-In** auswählen" auf das  Suchfeld, **geben** Sie "Nachricht melden" ein, und klicken Sie dann auf das Suchsymbol  ![ ](../../media/search-icon.png) . Suchen Sie in der Ergebnisliste nach **"Nachricht melden",** und klicken Sie dann auf **"Hinzufügen".**

   ![Auswählen von Add-In-Suchergebnissen](../../media/NewAddInScreen3.png)

5. Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**

6. Konfigurieren Sie auf der angezeigten Seite **"Add-In** konfigurieren" die folgenden Einstellungen:

   - **Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:

     - **Fixed (Standard):** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-in unter **"Home** \> **Get add-ins** \> **Admin-managed" installieren.**
     - **Optional:** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt, kann aber entfernt werden.

   ![Konfigurieren der Add-In-Seite](../../media/configure-add-in.png)

   Klicken Sie nach Abschluss des Abschlusses auf **"Bereitstellen".**

7. Auf der **Seite "Nachricht bereitstellen"** wird ein Fortschrittsbericht angezeigt, gefolgt von einer Bestätigung, dass das Add-in bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**

   ![Seite "Berichtnachricht bereitstellen"](../../media/deploy-report-message-page.png)

8. Überprüfen Sie **auf der angezeigten** Seite "Add-In ankündigen" die Informationen, und klicken Sie dann auf **"Schließen".**

   ![Add-In-Seite ankündigen](../../media/announce-add-in-page.png)

## <a name="learn-how-to-use-the-report-message-add-in"></a>Informationen zur Verwendung des Berichtsnachrichten-Add-Ins

Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie hier dargestellt aus:

  ![Symbol "Nachrichten-Add-In melden" für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Web sieht das Symbol wie hier dargestellt aus:

  ![Outlook im Web Report Message Add-in icon](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

Wenn Sie Benutzer über das Add-In "Nachricht melden" benachrichtigen, fügen Sie einen Link zum Verwenden des Add-Ins "Nachricht [melden" hinzu.](https://support.microsoft.com/office/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Berichtsnachrichten-Add-In

1. Wechseln Sie im Microsoft 365 Admin Center zur Seite "Dienste **&-Add-Ins"** unter <https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns> .

   ![Seite Add-Ins Dienste und Dienste im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Suchen Sie das Add-In **"Nachricht melden",** und wählen Sie es aus.

3. Überprüfen und **bearbeiten Sie im** angezeigten Flyout "Berichtnachricht bearbeiten" die Einstellungen, die für Ihre Organisation geeignet sind. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   ![Einstellungen für das Berichtsnachrichten-Add-In](../../media/EditReportMessageAddIn.png)

## <a name="view-and-review-reported-messages"></a>Anzeigen und Überprüfen von gemeldeten Nachrichten

Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:

- Verwenden Sie das Verwaltungsübermittlungsportal. Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien der gemeldeten Nachrichten zu senden. Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
