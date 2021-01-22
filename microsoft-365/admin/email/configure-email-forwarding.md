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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: ab5eb117-0f22-4fa7-a662-3a6bdb0add74
description: Richten Sie die E-Mail-Weiterleitung an ein oder mehrere E-Mail-Konten mithilfe von Office365 ein.
ms.openlocfilehash: 1168b549443de218339b1b8dcb32e57da175a2aa
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926642"
---
# <a name="configure-email-forwarding-in-microsoft-365"></a>Konfigurieren der E-Mail-Weiterleitung in Microsoft 365

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Als Administrator einer Organisation haben Sie möglicherweise Unternehmensanforderungen zum Einrichten der E-Mail-Weiterleitung für das Postfach eines Benutzers. Mit einer E-Mail-Weiterleitung können Sie E-Mails, die an das Postfach eines Benutzers gesendet wurden, an das Postfach eines anderen Benutzers innerhalb oder außerhalb Ihrer Organisation weiterleiten.

> [!IMPORTANT]
> Sie können Filterrichtlinien für ausgehende Spamnachrichten verwenden, um die automatische Weiterleitung an externe Empfänger zu steuern. Weitere Informationen finden Sie unter [Steuern der automatischen externen E-Mail-Weiterleitung in Microsoft 365.](https://docs.microsoft.com/microsoft-365/security/office-365-security/external-email-forwarding?view=o365-worldwide&preserve-view=true#how-the-outbound-spam-filter-policy-settings-work-with-other-automatic-email-forwarding-controls)

## <a name="configure-email-forwarding"></a>Konfigurieren der E-Mail-Weiterleitung

Beachten Sie Folgendes, bevor Sie die E-Mail-Weiterleitung einrichten:

- Nachdem Sie die E-Mail-Weiterleitung eingerichtet haben, **werden** nur neue E-Mails weitergeleitet, die an das  *Von-Postfach*  gesendet werden.

- Für die E-Mail-Weiterleitung muss  *das Konto*  vom Server über eine Lizenz verfügen. Wenn Sie die E-Mail-Weiterleitung einrichten, weil der Benutzer Ihre Organisation verlassen hat, besteht eine weitere Option in der Umwandlung des Postfachs in ein [freigegebenes Postfach.](convert-user-mailbox-to-shared-mailbox.md) Auf diese Weise können mehrere Personen darauf zugreifen. Ein freigegebenes Postfach darf jedoch 50 GB nicht überschreiten.

Sie müssen ein Exchange-Administrator oder globaler Administrator in Microsoft 365 sein, um diese Schritte ausführen zu können. Weitere Informationen finden Sie im Thema zu [Administratorrollen.](../add-users/about-admin-roles.md)

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=834822)**

2. Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.

3. Wählen Sie **auf der Registerkarte "E-Mail"** die Option **"E-Mail-Weiterleitung verwalten" aus.**

4. Wählen Sie auf der Seite für die E-Mail-Weiterleitung alle an dieses Postfach gesendeten E-Mails weiterleiten **aus,** geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Wählen Sie **Änderungen speichern** aus.

    **Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen zu erstellen. Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

     Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann die Weiterleitung so ein, dass sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweisen kann.

5. Löschen Sie nicht das Konto des Benutzers, der seine E-Mail-Adresse weiterleiten oder seine Lizenz entfernen möchte!  Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=847686)**

2. Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.

3. Erweitern Sie die E-Mail-Einstellungen, und wählen Sie dann im Abschnitt **"E-Mail-Weiterleitung"** die Option  **"Bearbeiten" aus.**

4. Legen Sie auf der E-Mail-Weiterleitungsseite die Umschalttaste auf **"Ein"** fest, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Klicken Sie auf **Speichern**.

   **Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen zu erstellen. Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann die Weiterleitung so ein, dass sie mithilfe der Anweisungen in diesem Artikel auf die Verteilerliste verweisen kann.

5. Löschen Sie nicht das Konto des Benutzers, der seine E-Mail-Adresse weiterleiten oder seine Lizenz entfernen möchte!  Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zur **Seite** \> **["Aktive Benutzer".](https://go.microsoft.com/fwlink/p/?linkid=850628)**

2. Wählen Sie den Namen des Benutzers aus, dessen E-Mail Sie weiterleiten möchten, um die Eigenschaftenseite zu öffnen.

3. Erweitern Sie die E-Mail-Einstellungen, und wählen Sie dann im Abschnitt **"E-Mail-Weiterleitung"** die Option  **"Bearbeiten" aus.**

4. Legen Sie auf der E-Mail-Weiterleitungsseite die Umschalttaste auf **"Ein"** fest, geben Sie die Weiterleitungsadresse ein, und wählen Sie aus, ob Sie eine Kopie der weitergeleiteten E-Mails behalten möchten. Wenn diese Option nicht angezeigt wird, stellen Sie sicher, dass dem Benutzerkonto eine Lizenz zugewiesen ist. Klicken Sie auf **Speichern**.

   **Wenn Sie an mehrere E-Mail-Adressen** weiterleiten möchten, können Sie den Benutzer bitten, eine Regel in Outlook zum Weiterleiten an die Adressen einrichten. Weitere Informationen finden Sie unter ["Verwenden von Regeln zum automatischen Weiterleiten von Nachrichten".](https://support.microsoft.com/office/45aa9664-4911-4f96-9663-ece42816d746)

   Oder erstellen Sie im [](../setup/create-distribution-lists.md)Admin Center eine Verteilergruppe, fügen Sie ihr die Adressen [hinzu,](add-user-or-contact-to-distribution-list.md)und richten Sie dann mithilfe der Anweisungen in diesem Artikel die Weiterleitung so ein, dass sie auf die Verteilerliste verweisen kann.

5. Löschen Sie nicht das Konto des Benutzers, der die E-Mail-Adresse, die Sie weiterleiten, weiterleiten oder seine Lizenz entfernen.  Wenn Sie dies tun, wird die E-Mail-Weiterleitung beendet.

::: moniker-end
