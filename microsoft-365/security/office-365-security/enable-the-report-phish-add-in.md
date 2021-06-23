---
title: Aktivieren des Add-Ins "Phishingbericht"
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
description: Erfahren Sie, wie Sie das Add-In "Phishing melden" für Outlook und Outlook im Web, für einzelne Benutzer oder ihre gesamte Organisation aktivieren.
ms.openlocfilehash: 44113237274d37aabeda954354182fe4da5aa970
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083416"
---
# <a name="enable-the-report-phishing-add-in"></a>Aktivieren des Add-Ins „Phishing melden“

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!NOTE]
> Wenn Sie ein Administrator in einer Microsoft 365 Organisation mit Exchange Online Postfächern sind, wird empfohlen, das Übermittlungsportal im Microsoft 365 Defender-Portal zu verwenden. Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)

Mit den Add-Ins "Nachricht melden" und "Phishing melden" für Outlook und Outlook im Web (früher als Outlook Web App bezeichnet) können Benutzer einfach falsch positive Ergebnisse (als falsch markierte gute E-Mails) oder falsch negative (ungültige E-Mails sind zulässig) an Microsoft und seine Partner zur Analyse melden.

Microsoft verwendet diese Übermittlungen, um die Effektivität von E-Mail-Schutztechnologien zu verbessern. Nehmen wir beispielsweise an, dass Viele Nachrichten mithilfe des Add-Ins "Phishing melden" gemeldet werden. Diese Informationen werden im [Sicherheitsdashboard](security-dashboard.md) und anderen Berichten angezeigt. Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Hinweis darauf verwenden, dass Antiphishingrichtlinien möglicherweise aktualisiert werden müssen.

Sie können entweder das Add-In "Nachricht melden" oder "Phishing melden" installieren. Wenn Ihre Benutzer sowohl Spam- als auch Phishingnachrichten melden sollen, stellen Sie das Add-In "Nachricht melden" in Ihrer Organisation bereit. Weitere Informationen finden Sie unter [Aktivieren des Add-Ins "Nachricht melden".](enable-the-report-message-add-in.md)

Das Add-In "Phishing melden" bietet die Möglichkeit, nur Phishingnachrichten zu melden. Administratoren können das Add-In "Phishing melden" für die Organisation aktivieren, und einzelne Benutzer können es für sich selbst installieren.

Wenn Sie ein einzelner Benutzer sind, können Sie [das Add-In "Phishing melden" für sich selbst aktivieren.](#get-the-report-phishing-add-in-for-yourself)

Wenn Sie ein globaler Administrator oder ein Exchange Online-Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie [das Add-In "Phishing melden" für Ihre Organisation aktivieren.](#get-and-enable-the-report-phishing-add-in-for-your-organization) Der Bericht-Phishing-Add-In ist jetzt über [die zentrale Bereitstellung](../../admin/manage/centralized-deployment-of-add-ins.md)verfügbar.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Das Berichtsphishing-Add-In funktioniert mit den meisten Microsoft 365 Abonnements und den folgenden Produkten:

  - Outlook im Web
  - Outlook 2013 SP1 oder höher
  - Outlook 2016 für Mac oder höher
  - Outlook in Microsoft 365 Apps für Enterprise enthalten
  - Outlook-App für iOS und Android

- Das Berichtsphishing-Add-In ist für freigegebene Postfächer oder Postfächer in lokalen Exchange Organisationen nicht verfügbar.

- Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen angegebenes Postfach kopiert oder umgeleitet werden. Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)

- Ihr vorhandener Webbrowser sollte mit dem Add-In "Phishing melden" funktionieren. Wenn Sie jedoch feststellen, dass das Add-In nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie einen anderen Browser.

- Für Organisationsinstallationen muss die Organisation für die Verwendung der OAuth-Authentifizierung konfiguriert werden. Weitere Informationen finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](../../admin/manage/centralized-deployment-of-add-ins.md)

- Administratoren müssen Mitglied der Rollengruppe "Globale Administratoren" sein. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md).

## <a name="get-the-report-phishing-add-in-for-yourself"></a>Abrufen des Berichtsphishing-Add-Ins für sich selbst

1. Wechseln Sie zu Microsoft AppSource, <https://appsource.microsoft.com/marketplace/apps> und suchen Sie nach dem Add-In "Phishing melden".

2. Klicken Sie **auf "JETZT ABRUFEN".**

3. Überprüfen Sie im daraufhin angezeigten Dialogfeld die Nutzungsbedingungen und die Datenschutzrichtlinie, und klicken Sie dann auf **"Weiter".**

4. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.

Nachdem das Add-In installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie folgt aus:

  ![Outlook im Web Symbol "Phishing-Add-In melden"](../../media/OWA-ReportPhishing.png)

## <a name="get-and-enable-the-report-phishing-add-in-for-your-organization"></a>Abrufen und Aktivieren des Add-Ins "Phishing melden" für Ihre Organisation

> [!NOTE]
> Es kann bis zu 12 Stunden dauern, bis das Add-In in Ihrer Organisation angezeigt wird.

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter , <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

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

## <a name="learn-how-to-use-the-report-phishing-add-in"></a>Erfahren Sie, wie Sie das Add-In "Phishing melden" verwenden

Personen, denen das Add-In zugewiesen wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  ![Add-In-Symbol "Phishing melden" für Outlook](../../media/Outlook-ReportPhishing.png)

- In Outlook im Web sieht das Symbol wie folgt aus:

  ![Outlook im Webbericht-Phishing-Add-In-Symbol](../../media/OWA-ReportPhishing.png)

## <a name="review-or-edit-settings-for-the-report-phishing-add-in"></a>Überprüfen oder Bearbeiten von Einstellungen für das Add-In "Phishing melden"

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite Einstellungen** \> **Add-Ins** unter , <https://admin.microsoft.com/AdminPortal/Home#/Settings/AddIns> wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zum Link **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins** oben auf der Seite **"Integrierte Apps".**

2. Suchen Sie das **Add-In "Phishing melden",** und wählen Sie es aus.

3. Überprüfen und bearbeiten Sie im angezeigten **Flyout "Bericht Phishing bearbeiten"** einstellungen entsprechend Ihrer Organisation. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="view-and-review-reported-messages"></a>Anzeigen und Überprüfen gemeldeter Nachrichten

Zum Überprüfen von Nachrichten, die Benutzer an Microsoft melden, haben Sie die folgenden Optionen:

- Verwenden Sie das Portal für Administratorübermittlungen. Weitere Informationen finden Sie unter [Anzeigen von Benutzerübermittlungen an Microsoft.](admin-submission.md#view-user-submissions-to-microsoft)

- Erstellen Sie eine Nachrichtenflussregel (auch als Transportregel bezeichnet), um Kopien von gemeldeten Nachrichten zu senden. Anweisungen finden Sie unter [Verwenden von Nachrichtenflussregeln, um zu sehen, welche Benutzer An Microsoft melden.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-see-what-users-are-reporting-to-microsoft)
