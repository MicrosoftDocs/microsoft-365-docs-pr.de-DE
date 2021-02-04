---
title: Aktivieren des Berichts-Phish-Add-Ins
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
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
description: Erfahren Sie, wie Sie das Phishing-Add-In "Melden" für Outlook und Outlook im Web, für einzelne Benutzer oder ihre gesamte Organisation aktivieren.
ms.openlocfilehash: abac24e447d0afe9bc725dd8f9a976dce900b278
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094677"
---
# <a name="enable-the-report-phishing-add-in"></a>Aktivieren des Add-Ins „Phishing melden“

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online-Postfächern sind, empfehlen wir die Verwendung des Übermittlungsportals im Security & Compliance Center. Weitere Informationen finden Sie unter ["Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft ".](admin-submission.md)

Die "Nachricht melden" und "Phishing melden"-Add-Ins für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) ermöglichen Es Benutzern, falsch positive Ergebnisse (eine gute E-Mail als schlecht markiert) oder falsch negative Ergebnisse (ungültige E-Mails sind zulässig) einfach zur Analyse an Microsoft und seine Partner zu melden.

Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern. Nehmen wir beispielsweise an, dass Benutzer viele Nachrichten mit dem Phishing-Add-In "Melden" melden. Diese Informationen werden im [Sicherheitsdashboard und](security-dashboard.md) anderen Berichten angezeigt. Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.

Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren. Wenn Ihre Benutzer Sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Report Message-Add-In in Ihrer Organisation zur Verfügung. Weitere Informationen finden Sie unter [Aktivieren des Berichtsnachrichten-Add-Ins.](enable-the-report-message-add-in.md)

Das Phishing-Add-In "Melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden. Administratoren können das Phishing-Add-In "Melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.

Wenn Sie ein einzelner Benutzer sind, können Sie das [Phishing-Add-In "Melden" für sich selbst aktivieren.](#get-the-report-phishing-add-in-for-yourself)

Wenn Sie ein globaler Administrator oder Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie das [Phishing-Add-In](#get-and-enable-the-report-phishing-add-in-for-your-organization)"Melden" für Ihre Organisation aktivieren. Der Phishingbericht Add-In ist jetzt über die [zentrale Bereitstellung verfügbar.](https://docs.microsoft.com/microsoft-365/admin/manage/centralized-deployment-of-add-ins)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Das Phishing-Add-In "Melden" funktioniert mit den meisten Microsoft 365-Abonnements und den folgenden Produkten:

  - Outlook im Web
  - Outlook 2013 SP1 oder höher
  - Outlook 2016 für Mac
  - Outlook im Lieferumfang von Microsoft 365 Apps for Enterprise
  - Outlook-App für iOS und Android

- Das Phishing-Add-In "Melden" ist für Postfächer in lokalen Exchange-Organisationen nicht verfügbar.

- Sie können gemeldete Nachrichten so konfigurieren, dass sie kopiert oder an ein von Ihnen festgelegtes Postfach umgeleitet werden. Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien.](user-submission.md)

- Ihr vorhandener Webbrowser sollte mit dem Phishing-Add-In "Melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es in einem anderen Browser.

- Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden. Weitere Informationen finden Sie unter Ermitteln, ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Das Phishing-Add-In "Melden" für sich selbst erhalten

1. Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Phishing-Add-In "Melden".

2. Klicken **Sie auf "JETZT GET IT".**

3. Überprüfen Sie im angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**

4. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Firmenkonto (zur geschäftlichen Nutzung) oder Ihrem Microsoft-Konto (zur persönlichen Nutzung) an.

Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie hier dargestellt aus:

  ![Melden eines Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie hier dargestellt aus:

  ![Outlook im Web – Symbol für Phishing-Add-In-Bericht](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Erhalten und Aktivieren des Phishing-Add-Ins "Melden" für Ihre Organisation

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-in in Ihrer Organisation angezeigt wird.

1. Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".

2. Wählen Sie oben auf der Seite **"Add-In** bereitstellen" und dann **"Weiter" aus.**

   ![Seite "Dienste und Add-Ins" im Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

3. Überprüfen Sie **im angezeigten Flyout** "Neues Add-In bereitstellen" die Informationen, und klicken Sie dann auf **"Weiter".**

4. Klicken Sie auf der nächsten Seite auf **"Aus Store auswählen".**

   ![Bereitstellen einer neuen Add-In-Seite](../../media/NewAddInScreen2.png)

5. Klicken Sie auf **der angezeigten Seite "Add-In** auswählen" in das  Suchfeld, geben **Sie "Phishing** melden" ein, und klicken Sie dann auf das Suchsymbol  ![ ](../../media/search-icon.png) . Suchen Sie in der Ergebnisliste nach **"Phishing melden",** und klicken Sie dann auf **"Hinzufügen".**

6. Überprüfen Sie im angezeigten Dialogfeld die Lizenzierungs- und Datenschutzinformationen, und klicken Sie dann auf **"Weiter".**

7. Konfigurieren Sie auf der angezeigten Seite **"Add-In** konfigurieren" die folgenden Einstellungen:

   - **Zugewiesene Benutzer:** Wählen Sie einen der folgenden Werte aus:

     - **Jeder** (Standard)
     - **Bestimmte Benutzer/Gruppen**
     - **Nur ich**

   - **Bereitstellungsmethode:** Wählen Sie einen der folgenden Werte aus:

     - **Fixed (Standard):** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt und kann nicht entfernt werden.
     - **Verfügbar:** Benutzer können das Add-in unter **"Home** \> **Get add-ins** \> **Admin-managed" installieren.**
     - **Optional:** Das Add-in wird automatisch für die angegebenen Benutzer bereitgestellt, kann aber entfernt werden.

   Klicken Sie nach Abschluss des Abschlusses auf **"Bereitstellen".**

8. Auf der **angezeigten Seite "Phishingbericht** bereitstellen" wird ein Fortschrittsbericht angezeigt, gefolgt von einer Bestätigung, dass das Add-in bereitgestellt wurde. Klicken Sie nach dem Lesen der Informationen auf **"Weiter".**

9. Überprüfen Sie **auf der angezeigten** Seite "Add-In ankündigen" die Informationen, und klicken Sie dann auf **"Schließen".**

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Informationen zur Verwendung des Phishing-Add-Ins "Melden"

Personen, denen das Add-In zugewiesen ist, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie hier dargestellt aus:

  ![Melden eines Phishing-Add-In-Symbols für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie hier dargestellt aus:

  ![Outlook im Web Report Phishing-Add-In-Symbol](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Phishing-Add-In "Melden"

1. Wechseln Sie im Microsoft 365 Admin Center  zur Seite \> **"Einstellungen-Add-Ins".** Wenn die <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> **Add-In-Seite**  nicht angezeigt wird, wechseln \>  \>   Sie oben auf der Seite "Integrierte Apps" zum Link "Integrierte Apps".

2. Suchen Sie das **Phishing-Add-In "Melden",** und wählen Sie es aus.

3. In the **Edit Report Phishing** flyout that appears, review, and edit settings as appropriate for your organization. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="view-and-review-reported-messages"></a>Anzeigen und Überprüfen von gemeldeten Nachrichten

Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:

- Verwenden Sie das Verwaltungsübermittlungsportal. Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft](admin-submission.md#view-user-submissions-to-microsoft).

- Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien der gemeldeten Nachrichten zu senden. Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, was Ihre Benutzer an Microsoft melden.](use-mail-flow-rules-to-see-what-your-users-are-reporting-to-microsoft.md)
