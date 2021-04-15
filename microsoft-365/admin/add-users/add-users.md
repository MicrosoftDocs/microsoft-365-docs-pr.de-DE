---
title: Benutzer hinzufügen und Lizenzen zuweisen
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365_Setup
- Adm_O365_TOC
ms.custom:
- okr_smb
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie, wie Sie gleichzeitig mehrere Benutzer hinzufügen und Lizenzen für Microsoft 365 zuweisen können.
ms.date: 07/01/2020
ms.openlocfilehash: a7c5fcf1a129a1d434b6e641688ce4c5d234817d
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760002"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen

Jede Person in Ihrem Team benötigt ein Benutzerkonto, um sich bei [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business) anmelden und darauf zugreifen zu können. Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, sie im Microsoft 365 Admin Center nacheinander hinzuzufügen. Nachdem Sie diesen Schritt durchgeführt haben, verfügen die Benutzer über Microsoft 365-Lizenzen, Anmeldeinformationen und Microsoft 365-Postfächer.

## <a name="before-you-begin"></a>Vorbereitung

Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Benutzer hinzufügen und Lizenzen zuweisen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Video: Hinzufügen von Benutzern im Admin Center

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Die im Video verwendeten Schritte beginnen mit dem Hinzufügen von Benutzern bei einem anderen Ausgangspunkt, aber die übrigen Schritte sind mit dem folgenden Verfahren identisch.

## <a name="add-users-one-at-a-time"></a>Hinzufügen von jeweils einem Benutzer

 ::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann **Weiter** aus.
    - **Name** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername des Benutzers „Jan“ ist und die Domäne „contoso.com“ heißt, meldet er sich durch Eingabe von „jan@contoso.com“ an.
    - **Kennworteinstellungen** Wählen Sie das automatisch generierte Kennwort aus, oder erstellen Sie ein sicheres Kennwort für den Benutzer.
    - Der Benutzer muss sein Kennwort nach 90 Tagen ändern. Sie können aber auch die folgende Option auswählen: **Anfordern, dass dieser Benutzer bei der ersten Anmeldung sein Kennwort ändert**.
    - Wählen Sie aus, ob das Kennwort per E-Mail gesendet werden soll, wenn der Benutzer hinzugefügt wird.
4. Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus. Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen. Erweitern Sie **Apps**, und aktivieren oder deaktivieren Sie Apps, um die Apps einzuschränken, für die der Benutzer eine Lizenz hat. Wählen Sie **Weiter** aus.
5. Erweitern Sie auf der Seite **Optionale Einstellungen** die Option **Rollen**, um diesen Benutzer als Administrator festzulegen. Erweitern Sie **Profilinformationen**, um weitere Informationen zum Benutzer hinzuzufügen.
6. Wählen Sie **Weiter** aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie eventuell Änderungen vor, und wählen Sie dann **Hinzufügen fertig stellen** > **Schließen** aus.

## <a name="add-multiple-users-at-the-same-time"></a>Gleichzeitiges Hinzufügen von mehreren Benutzern

Sie können eine der folgenden Methoden verwenden, um mehrere Benutzer gleichzeitig hinzuzufügen:

- **Mithilfe einer Kalkulationstabelle können Sie Benutzer in Massen hinzufügen.** Weitere Informationen hierzu finden Sie unter [Gleichzeitiges Hinzufügen von mehreren Benutzern](../../enterprise/add-several-users-at-the-same-time.md).
- **Automatisieren Sie das Hinzufügen von Konten und Zuweisen von Lizenzen.** Informationen hierzu finden Sie unter [Erstellen von Benutzerkonten mit Microsoft 365 PowerShell](../../enterprise/create-user-accounts-with-microsoft-365-powershell.md). Wählen Sie diese Methode aus, wenn Sie mit der Nutzung von Windows PowerShell-Cmdlets bereits vertraut sind.
- **Sie verwenden Active Directory?** [Richten Sie die Verzeichnissynchronisierung für Microsoft 365 ein](../../enterprise/set-up-directory-synchronization.md). Mithilfe des Azure AD Connect-Tools können Sie Active Directory-Benutzerkonten (und andere Active Directory-Objekte) in Microsoft 365 replizieren. Bei der Synchronisierung werden nur die Benutzerkonten hinzugefügt. Sie müssen den synchronisierten Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können. 
- **Sie migrieren aus Exchange?** Siehe [Methoden zum Migrieren mehrerer E-Mail-Konten zu Office 365](/Exchange/mailbox-migration/mailbox-migration). Wenn Sie mithilfe einer Übernahmemigration oder mit einer mehrstufigen bzw. hybriden Exchange-Methode mehrere Postfächer zu Microsoft 365 migrieren, werden die Benutzer als Teil der Migration automatisch hinzugefügt. Bei der Migration werden nur die Benutzerkonten hinzugefügt. Sie müssen den Benutzern Lizenzen zuweisen, damit sie E-Mail und andere Office-Apps verwenden können. Wenn Sie einem Benutzer keine Lizenz zuweisen, wird sein Postfach nach Ablauf einer 30-tägigen Kulanzzeit deaktiviert. Erfahren Sie, wie Sie unter Verwendung des Microsoft 365 Admin Centers [Benutzern Lizenzen zuweisen](../manage/assign-licenses-to-users.md).

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine E-Mail-Benachrichtigung von Microsoft. Die E-Mail enthält die Benutzer-ID und das Kennwort der Person, damit sie sich bei Microsoft 365 anmelden kann. Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter. Geben Sie die [Mitarbeiter-Kurzanleitung](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) für Ihre neuen Benutzer frei, um die Umgebung einzurichten, z. B. [wie Office-Apps heruntergeladen und auf einem PC oder Mac installiert werden](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen eines neuen Mitarbeiters zu Microsoft 365](add-new-employee.md) (Artikel)\
[Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (Artikel)\
[Wiederherstellen eines Benutzers in Microsoft 365](restore-user.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](../manage/assign-licenses-to-users.md) (Artikel)\
[Löschen eines Benutzers aus Ihrer Organisation](delete-a-user.md) (Artikel)