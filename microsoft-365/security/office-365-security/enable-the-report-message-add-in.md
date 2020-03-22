---
title: Aktivieren des Berichtsnachrichts-Add-Ins
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 4250c4bc-6102-420b-9e0a-a95064837676
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie das Add-in "Berichtsnachricht" für Outlook und Outlook im Internet für einzelne Benutzer oder die gesamte Organisation aktivieren.
ms.openlocfilehash: 32b4ab318237ca220b63c87bd4a664cfb69d0b45
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893754"
---
# <a name="enable-the-report-message-add-in"></a>Aktivieren des Berichtsnachrichts-Add-Ins

> [!NOTE]
> Das Berichtsnachrichten-Add-in für Outlook und Outlook im Internet ist nicht genau dasselbe wie der [Outlook-Junk-e-Mail-Filter](https://support.office.com/article/5ae3ea8e-cf41-4fa0-b02a-3b96e21de089), obwohl beide dazu verwendet werden können, e-Mails als Junk-e-Mail, nicht als Junk-oder als Phishing-Versuch zu kennzeichnen. Der Unterschied besteht darin, dass das Add-in "Berichtsnachricht" für Outlook und Outlook im Internet Microsoft über falsch klassifizierte e-Mails benachrichtigt, während der Outlook-Junk-e-Mail-Filter zum Organisieren von e-Mail-Nachrichten im Postfach eines Benutzers verwendet wird.

## <a name="overview"></a>Übersicht

Das Berichtsnachrichten-Add-in für Outlook und Outlook im Internet (ehemals Outlook Web App genannt) ermöglicht Benutzern das einfache Melden von vertraulichen oder böswilligen e-Mail-Nachrichten an Microsoft und seine Partner zur Analyse. Microsoft verwendet diese Übermittlungen, um die Effektivität von e-Mail-Schutztechnologien zu verbessern. Wenn Ihre Organisation [Office 365 Advanced Threat Protection Plan 1](office-365-atp.md) oder [Plan 2](office-365-ti.md)verwendet, bietet das Add-in "Berichtsnachricht" außerdem nützliche Informationen zum Überprüfen und Aktualisieren von Sicherheitsrichtlinien, die dem Sicherheitsteam Ihrer Organisation zur Verfügung stehen.

Nehmen wir beispielsweise an, dass Personen viele Nachrichten als Phishing melden. Diese Informationen werden im [Sicherheits Dashboard](security-dashboard.md) und in anderen Berichten unter Oberflächen angezeigt. Das Sicherheitsteam Ihrer Organisation kann diese Informationen als Anhaltspunkt dafür verwenden, dass Anti-Phishing-Richtlinien möglicherweise aktualisiert werden müssen. Oder wenn Personen viele Nachrichten melden, die als Junk-e-Mail als nicht-Junk mithilfe des Berichtsnachrichten-Add-ins gekennzeichnet wurden, muss das Sicherheitsteam Ihrer Organisation möglicherweise [Anti-Spam-Richtlinien](configure-your-spam-filter-policies.md)anpassen.

Das Add-in "Berichtsnachricht" funktioniert mit den meisten Office 365-Abonnements und den folgenden Produkten:

- Outlook im Web
- Outlook 2013 SP1
- Outlook 2016
- Outlook 2016 für Mac
- Outlook im Lieferumfang von Office 365 ProPlus

Das Add-in "Berichtsnachricht" steht derzeit nicht zur Verfügung für:

- Postfächer in lokalen Exchange-Organisationen
- Gcc-, gcc-High-oder DoD-Abonnements

Ihr vorhandener Webbrowser sollte ausreichen, damit das Add-in "Berichtsnachricht" funktioniert. Wenn Sie jedoch feststellen, dass das Add-in nicht verfügbar ist oder nicht wie erwartet funktioniert, versuchen Sie es mit einem anderen Browser.

Wenn Sie ein einzelner Benutzer sind, können Sie [das Add-in "Berichtsnachricht" für sich selbst aktivieren](#get-the-report-message-add-in-for-yourself).

Wenn Sie ein Office 365 globaler Administrator oder ein Exchange Online Administrator sind und Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert ist, können Sie [das Add-in "Berichtsnachricht" für Ihre Organisation aktivieren](#get-and-enable-the-report-message-add-in-for-your-organization). Das Add-in "Berichtsnachricht" ist jetzt über eine [zentralisierte Bereitstellung](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins)verfügbar.

## <a name="get-the-report-message-add-in-for-yourself"></a>Abrufen des Berichtsnachrichten-Add-Ins für sich selbst

1. Suchen Sie in [Microsoft AppSource](https://appsource.microsoft.com/marketplace/apps)nach dem [Add-in "Berichtsnachricht](https://appsource.microsoft.com/product/office/wa104381180)".

2. Wählen Sie **get it now**aus.

   ![Berichtsnachricht – jetzt abrufen](../../media/ReportMessageGETITNOW.png)

3. Lesen Sie die Nutzungsbedingungen und Datenschutzrichtlinien. Wählen Sie dann **Continue** aus.

4. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-oder Schulkonto (für geschäftliche Zwecke) oder Ihrem Microsoft-Konto (zur persönlichen Verwendung) an.

Nachdem das Add-in installiert und aktiviert wurde, werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Internet (früher bekannt als Outlook Web App) sieht das Symbol wie folgt aus:

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> Im nächsten Schritt erfahren Sie, wie Sie [das Add-in "Berichtsnachricht" verwenden](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="get-and-enable-the-report-message-add-in-for-your-organization"></a>Abrufen und Aktivieren des Berichtsnachrichten-Add-Ins für Ihre Organisation

> [!IMPORTANT]
> Sie müssen ein Office 365 globaler Administrator oder ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können. Darüber hinaus muss Exchange für die Verwendung der OAuth-Authentifizierung konfiguriert sein, um weitere Informationen zu erhalten, siehe [Exchange-Anforderungen (zentralisierte Bereitstellung von Add-Ins)](https://docs.microsoft.com/office365/admin/manage/centralized-deployment-of-add-ins).

1. Wechseln Sie zur [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) im Microsoft 365 Admin Center.

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Wählen Sie **+ Deploy Add-in aus**.

   ![Auswählen von "Add-in bereitstellen"](../../media/ServicesAddIns-ChooseDeployAddIn.png)

3. Überprüfen Sie im **neuen Add-in-** Bildschirm die Informationen, und wählen Sie dann **weiter**aus.

   ![Neue Add-in-Details](../../media/NewAddInScreen1.png)

4. Wählen Sie **Ich möchte ein Add-in aus dem Office Store hinzufügen aus**, und klicken Sie dann auf **weiter**.

   ![Ich möchte ein neues Add-in hinzufügen](../../media/NewAddInScreen2.png)

5. Suchen Sie nach **Berichtsnachricht**, und wählen Sie in der Ergebnisliste neben dem **Add-in "Berichtsnachricht**" die Option **Hinzufügen**aus.

   ![Suchen Sie nach Berichtsnachricht, und wählen Sie dann hinzufügen](../../media/NewAddInScreen3.png)

6. Überprüfen Sie auf dem Bildschirm **Bericht Meldung** die Informationen, und wählen Sie dann **weiter**aus.

   ![Berichtsnachrichten Details](../../media/ReportMessageAdd-InNewScreen4.png)

7. Geben Sie die Standardeinstellungen des Benutzers für Outlook an, und klicken Sie dann auf **weiter**.

   ![Berichtsnachrichten Standardeinstellungen für Outlook](../../media/ReportMessageOptionsScreen5.png)

8. Geben Sie an, wer das Add-in "Berichtsnachricht" abruft, und wählen Sie dann **Speichern**aus.

   ![Wer ruft das Add-in "Berichtsnachricht" ab](../../media/ReportMessageOptionsScreen6.png)

> [!TIP]
> Es [wird empfohlen, eine Regel einzurichten, um eine Kopie der von Ihren Benutzern gemeldeten e-Mail-Nachrichten zu erhalten](#set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users).

Je nachdem, was Sie beim Einrichten des Add-Ins (Schritte 7-8 oben) ausgewählt haben, ist das [Add-in "Berichtsnachricht](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2) " für Personen in Ihrer Organisation verfügbar. Personen in Ihrer Organisation werden die folgenden Symbole angezeigt:

- In Outlook sieht das Symbol wie folgt aus:

  ![Add-in-Symbol für Berichtsnachricht für Outlook](../../media/OutlookReportMessageIcon.png)

- In Outlook im Internet sieht das Symbol wie folgt aus:

  ![Outlook im Add-in-Symbol für den Webbericht-Nachrichtendienst](../../media/d9326d0b-1769-4bc2-ae58-51f0ebc69a17.png)

> [!TIP]
> Wenn Sie Benutzer über das Add-in "Berichtsnachricht" informieren, fügen Sie einen Link zur [Verwendung des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)hinzu.

## <a name="set-up-a-rule-to-get-a-copy-of-email-messages-reported-by-your-users"></a>Einrichten einer Regel zum Abrufen einer Kopie von von Ihren Benutzern gemeldeten e-Mail-Nachrichten

> [!IMPORTANT]
> Sie müssen ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können.

Sie können eine Regel einrichten, um eine Kopie der von Benutzern in Ihrer Organisation gemeldeten e-Mail-Nachrichten zu erhalten. Dies tun Sie, nachdem Sie das Add-in "Berichtsnachricht" für Ihre Organisation heruntergeladen und aktiviert haben.

1. Wählen Sie in der Exchange-Verwaltungskonsole **Nachrichtenfluss** \> **Regeln**aus.

2. Wählen **+** \> Sie **neue Regel erstellen**aus.

3. Geben Sie im Feld **Name** einen Namen ein, beispielsweise Übermittlungen.

4. Wählen Sie in der Liste **diese Regel anwenden, wenn** **die Option Empfängeradresse enthält...** aus.

5. Klicken Sie im Bildschirm **Wörter oder Ausdrücke angeben** auf Hinzufügen `junk@office365.microsoft.com` , und `phish@office365.microsoft.com`wählen Sie dann **OK**aus.

   ![Angeben der Junk-und Phishing-e-Mail-Adressen für die Regel](../../media/018c1833-f336-4333-a45c-f2e8b75cd698.png)

6. Wählen Sie in der Liste **ausführen die folgende...** die Option **Bcc die Nachricht an...** aus.

7. Fügen Sie einen globalen Administrator, Sicherheitsadministrator und/oder Sicherheits Leser hinzu, der eine Kopie jeder e-Mail-Nachricht erhalten soll, die Personen an Microsoft melden, und wählen Sie dann **OK**aus.

   ![Hinzufügen eines globalen oder Sicherheitsadministrators zum Empfangen einer Kopie jeder gemeldeten Nachricht](../../media/a91ab9d1-66f2-4a2e-9dc1-f9f81a2298ad.png)

8. Wählen Sie **diese Regel mit Schweregrad überwachen**aus, und wählen Sie **Medium**aus.

9. Wählen Sie unter **Modus für diese Regel auswählen die**Option **erzwingen**aus.

   ![Einrichten einer Regel zum Abrufen einer Kopie jeder gemeldeten Nachricht](../../media/f1cd95ce-e40d-4a8a-8f48-893469eba691.png)

10. Wählen Sie **Speichern** aus.

Wenn diese Regel erfüllt ist, erhält Ihr globaler Administrator, Sicherheitsadministrator und/oder Sicherheits Leser eine Kopie dieser Nachricht, wenn jemand in Ihrer Organisation eine e-Mail-Nachricht mithilfe des Berichtsnachrichten-Add-ins meldet. Diese Informationen können Ihnen das Einrichten oder Anpassen von Richtlinien ermöglichen, beispielsweise Office 365 Richtlinien für [ATP-sichere Links](atp-safe-links.md) oder Ihre [Anti-Spam-](anti-spam-protection.md) Einstellungen.

## <a name="learn-how-to-use-the-report-message-add-in"></a>Informationen zur Verwendung des Berichtsnachrichten-Add-ins

Siehe [Verwenden des Berichtsnachrichten-Add-ins](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2).

## <a name="review-or-edit-settings-for-the-report-message-add-in"></a>Überprüfen oder Bearbeiten der Einstellungen für das Add-in "Berichtsnachricht"

Sie können die Standardeinstellungen für das Add-in "Berichtsnachricht" auf der [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns)überprüfen und bearbeiten.

> [!IMPORTANT]
> Sie müssen ein Office 365 globaler Administrator oder ein Exchange Online Administrator sein, um diese Aufgabe ausführen zu können.

1. Wechseln Sie zur [Seite Dienste &-Add-ins](https://admin.microsoft.com/AdminPortal/Home#/Settings/ServicesAndAddIns) im Microsoft 365 Admin Center.

   ![Seite "Dienste und Add-Ins" im neuen Microsoft 365 Admin Center](../../media/ServicesAddInsPageNewM365AdminCenter.png)

2. Suchen Sie das Add-in Berichtsnachricht, und wählen Sie es aus.

   ![Suchen und auswählen des Add-Ins "Berichtsnachricht"](../../media/FindReportMessageAddIn.png)

3. Überprüfen und bearbeiten Sie auf dem Bildschirm Bericht Meldung die Einstellungen entsprechend Ihrer Organisation.

   ![Einstellungen für das Add-in "Berichtsnachricht"](../../media/EditReportMessageAddIn.png)

## <a name="related-topics"></a>Verwandte Themen

[Verwenden des Add-Ins "Berichtsnachricht"](https://support.office.com/article/b5caa9f1-cdf3-4443-af8c-ff724ea719d2)

[Anzeigen von e-Mail-Sicherheits &amp; Berichten im Security Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)

[Verwenden des Explorers im Security &amp; Compliance Center](threat-explorer.md)
