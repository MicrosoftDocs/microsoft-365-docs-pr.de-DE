---
title: Konfigurieren der E-Mail-Weiterleitung
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Mit der E-Mail-Weiterleitung können Sie E-Mail-Nachrichten, die an ein Microsoft 365 Benutzerpostfach gesendet wurden, an ein anderes Postfach innerhalb oder außerhalb Ihrer Organisation weiterleiten.
ms.openlocfilehash: 07bd6bb1bbfd1ecdfa6ca0d545d78a39e66c7558
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393211"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Konfigurieren der E-Mail-Weiterleitung in Microsoft 365

Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen, was die Einrichtung der E-Mail-Weiterleitung für das Postfach eines Benutzers betrifft. Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.

> [!IMPORTANT]
> Sie können ausgehende Spamfilter-Richtlinien verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern. Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](/microsoft-365/security/office-365-security/external-email-forwarding#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls).

## <a name="configure-email-forwarding"></a>Konfigurieren der E-Mail-Weiterleitung

Bedenken Sie vor dem Einrichten der E-Mail-Weiterleitung Folgendes:

- Zulassen, dass automatisch weitergeleitete Nachrichten an Personen in der Remotedomäne gesendet werden. Weitere Informationen finden Sie unter [Verwalten von Remotedomänen.](/exchange/mail-flow-best-practices/remote-domains/manage-remote-domains)

- Nach dem Einrichten der E-Mail-Weiterleitung werden nur **neue** E-Mails weitergeleitet, die an das *„Von“*-Postfach gesendet wurden.

- Für die E-Mail-Weiterleitung muss das *„Von“*-Konto über eine Lizenz verfügen. Wenn ein Benutzer Ihre Organisation verlassen hat, ist [das Umwandeln seines Postfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) eine alternative Option zum Einrichten der E-Mail-Weiterleitung. Auf diese Art und Weise können mehrere Personen darauf zugreifen. Ein freigegebenes Postfach kann jedoch 50 GB nicht überschreiten.

Um dies durchzuführen, müssen Sie ein Exchange-Administrator oder ein globaler Administrator in Microsoft 365 sein. Weitere Informationen finden Sie im Thema [Info zu Administratorrollen](../add-users/about-admin-roles.md).

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=834822)**.

2. Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, und öffnen Sie dann die Eigenschaftenseite.

3. Wählen Sie auf der Registerkarte **E-Mail** die Option **E-Mail-Weiterleitung verwalten** aus.

4. Wählen Sie auf der Seite zum Weiterleiten von E-Mails die Option **Alle an dieses Postfach gesendeten E-Mails weiterleiten** aus, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Änderungen speichern** aus.

    **Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten. 
    
    1.  Öffnen  von > **Outlook-Startregeln** >  > Auswählen **von Verwaltungsregeln & Warnungen**  
    1. Wählen Sie **"Neue Regel** > **auswählen Regel anwenden" für die Nachricht** aus, die sich am unteren Rand der Liste befindet, und klicken Sie dann auf **"Weiter".**
    1. Klicken Sie auf **"Ja",** wenn Sie gefragt werden, dass diese Regel auf jede empfangene Nachricht angewendet wird. 
    1. Wählen Sie in der nächsten Liste die Aktionen aus, um **sie an Personen oder öffentliche Gruppen umzuleiten,** und beenden Sie die Verarbeitung weiterer **Regeln.**
    1. Klicken Sie im unteren Teil des Fensters auf den unterstrichenen Ausdruck **"Personen" oder** auf die öffentliche Gruppe.
    1. Geben Sie die **E-Mail-Adresse,** an die E-Mails weitergeleitet werden sollen, in das Feld "An" ein, und klicken Sie dann auf **"OK".**
    1. Wählen Sie **"Fertig stellen" aus.**
    

     Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.

5. Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!  Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=847686)**.

2. Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.

3. Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.

4. Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Speichern** aus.

   **Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten. Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.

5. Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz!  Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur Seite **Benutzer** \> **[Aktive Benutzer](https://go.microsoft.com/fwlink/p/?linkid=850628)**.

2. Wählen Sie zum Öffnen der Eigenschaften-Seite den Namen des Benutzers aus, dessen E-Mails Sie weiterleiten wollen.

3. Erweitern Sie **E-Mail-Einstellungen** und wählen Sie dann im Abschnitt **E-Mail-Weiterleitung** die Option **Bearbeiten** aus.

4. Setzen Sie auf der Seite zum Weiterleiten von E-Mails den Schalter auf **Ein**, geben Sie die Weiterleitungsadresse ein, und wählen Sie, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn Sie diese Option nicht sehen, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Speichern** aus.

   **Um an mehrere E-Mail-Adressen weiterzuleiten**, können Sie den Benutzer bitten, eine Outlook-Regel zum Weiterleiten an diese Adressen einzurichten. Weiter Informationen finden Sie unter [Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746).

   Alternativ können Sie im Admin Center [eine Verteilergruppe erstellen](../setup/create-distribution-lists.md), [die Adressen hinzufügen](add-user-or-contact-to-distribution-list.md), und dann die Weiterleitung an die Verteilergruppe einrichten, wie in diesem Artikel beschrieben.

5. Löschen Sie nicht das Konto des Benutzers, dessen E-Mail Sie weiterleiten, und löschen Sie auch nicht dessen Lizenz! Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end

## <a name="related-content"></a>Verwandte Inhalte 

[Erstellen eines freigegebenen Postfachs](../email/create-a-shared-mailbox.md) (Artikel)\
[Senden von E-Mails von einer anderen Adresse](https://support.microsoft.com/office/ccba89cb-141c-4a36-8c56-6d16a8556d2e) (Artikel)\
[Ändern eines Benutzernamens und einer E-Mail-Adresse](../add-users/change-a-user-name-and-email-address.md) (Artikel)
