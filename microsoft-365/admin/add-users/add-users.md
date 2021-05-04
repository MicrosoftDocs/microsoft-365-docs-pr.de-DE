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
ms.custom:
- okr_smb
- AdminSurgePortfolio
search.appverid:
- MET150
description: Erfahren Sie, wie Sie gleichzeitig mehrere Benutzer hinzufügen und Lizenzen für Microsoft 365 zuweisen können.
ms.date: 07/01/2020
ms.openlocfilehash: 6a1361d9cfebd2b305a71248fcbb461d0a68a052
ms.sourcegitcommit: 794f9767aaebe13ab1aead830b214ea674289d19
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52107086"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen

Jede Person in Ihrem Team benötigt ein Benutzerkonto, um sich bei [Microsoft 365 Business](https://www.microsoft.com/microsoft-365/business) anmelden und darauf zugreifen zu können. Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, sie im Microsoft 365 Admin Center nacheinander hinzuzufügen. Nachdem Sie diesen Schritt durchgeführt haben, verfügen die Benutzer über Microsoft 365-Lizenzen, Anmeldeinformationen und Microsoft 365-Postfächer.

## <a name="before-you-begin"></a>Vorbereitung

Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Benutzer hinzufügen und Lizenzen zuweisen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="add-a-user-in-the-admin-simplified-view"></a>Hinzufügen eines Benutzers in der vereinfachten Administrator-Ansicht

Wenn Sie diese Seite im Admin Center sehen, dann befinden Sie sich auf der **vereinfachten Administrator-Ansicht**. Führen Sie die folgenden Schritte aus, um einen Benutzer hinzuzufügen.

:::image type="content" source="../../media/vsb-add-user-view.png" alt-text="Screenshot: Vereinfachte Admin Center-Ansicht":::

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.
2. Wählen Sie **Ein Konto für eine andere Person erstellen** aus.
3. Geben Sie auf der Seite **Benutzerkonto hinzufügen** die Vor- und Nachnamen ein, den Anzeigenamen und den Benutzernamen, den die Person für die Anmeldung verwenden wird.
4. Fügen Sie die E-Mail-Adresse des Benutzers im Textfeld **Bis zu 5 E-Mail-Adressen...** hinzu. Dies wird sicherstellen, dass der neue Benutzer die Informationen erhält, die er für die Anmeldung bei den Microsoft 365-Diensten benötigt.
5. Wählen Sie **Benutzer hinzufügen** und **Anmeldeinformation herunterladen** aus, wenn Sie diese Info speichern wollen.

## <a name="watch-add-users-in-the-dashboard-view"></a>Video: Hinzufügen von Benutzern in der Dashboard-Ansicht

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Die im Video verwendeten Schritte beginnen mit dem Hinzufügen von Benutzern bei einem anderen Ausgangspunkt, aber die übrigen Schritte sind mit dem folgenden Verfahren identisch.

## <a name="add-users-one-at-a-time-in-the-dashboard-view"></a>Benutzer einzeln in der Dashboard-Ansicht hinzufügen

 ::: moniker range="o365-worldwide"

:::image type="content" source="../../media/classic-admin-center.png" alt-text="Screenshot: Dashboard-Ansicht des Admin Centers":::

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.
2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann **Weiter** aus.
    - **Name** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername des Benutzers „Jakob“ ist und die Domäne „contoso.com“ heißt, meldet er sich durch Eingabe von „jakob@contoso.com“ an.
    - **Kennworteinstellungen** Wählen Sie, ob Sie das automatisch generierte Kennwort verwenden oder Ihr eigenes sicheres Kennwort für den Benutzer erstellen möchten.
    - Der Benutzer muss sein Kennwort nach 90 Tagen ändern. Sie können aber auch Folgendes auswählen: **Vom Benutzer verlangen, dass er sein Kennwort bei der ersten Anmeldung ändern muss**.
    - Wählen Sie aus, ob das Kennwort per E-Mail gesendet werden soll, wenn der Benutzer hinzugefügt wird.
4. Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus. Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen. Erweitern Sie **Apps**, und aktivieren oder deaktivieren Sie Apps, um die Apps einzuschränken, für die der Benutzer eine Lizenz hat. Wählen Sie **Weiter** aus.
5. Erweitern Sie auf der Seite **Optionale Einstellungen** die Option **Rollen**, um diesen Benutzer als Administrator festzulegen. Erweitern Sie **Profilinformationen**, um weitere Informationen zum Benutzer hinzuzufügen.
6. Wählen Sie **Weiter** aus, überprüfen Sie die Einstellungen des neuen Benutzers, nehmen Sie eventuell Änderungen vor, und wählen Sie dann **Hinzufügen fertig stellen** > **Schließen** aus.


1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">https://portal.office.de</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">https://portal.partner.microsoftonline.cn</a>.

::: moniker-end 

2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann **Weiter** aus.
    - **Name** Geben Sie den Vor- und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername des Benutzers „Jakob“ ist und die Domäne „contoso.com“ heißt, meldet er sich durch Eingabe von „jakob@contoso.com“ an.
    - **Kennworteinstellungen** Wählen Sie, ob Sie das automatisch generierte Kennwort verwenden oder Ihr eigenes sicheres Kennwort für den Benutzer erstellen möchten.
    - Der Benutzer muss sein Kennwort nach 90 Tagen ändern. Sie können aber auch Folgendes auswählen: **Vom Benutzer verlangen, dass er sein Kennwort bei der ersten Anmeldung ändern muss**.
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

Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine E-Mail-Benachrichtigung von Microsoft. Die E-Mail enthält die Benutzer-ID und das Kennwort der Person, damit sie sich bei Microsoft 365 anmelden kann. Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter. Geben Sie die [Mitarbeiter-Kurzanleitung](../../business-video/employee-quick-setup.md) für Ihre neuen Benutzer frei, um die Umgebung einzurichten, z. B. [wie Office-Apps heruntergeladen und auf einem PC oder Mac installiert werden](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen eines neuen Mitarbeiters zu Microsoft 365](add-new-employee.md) (Artikel)\
[Gleichzeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365](../../enterprise/add-several-users-at-the-same-time.md) (Artikel)\
[Wiederherstellen eines Benutzers in Microsoft 365](restore-user.md) (Artikel)\
[Zuweisen von Lizenzen zu Benutzern ](../manage/assign-licenses-to-users.md) (Artikel)\
[Löschen eines Benutzers aus Ihrer Organisation](delete-a-user.md) (Artikel)