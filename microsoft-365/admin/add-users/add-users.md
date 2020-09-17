---
title: Benutzer hinzufügen und Lizenzen zuweisen
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Informationen zum Hinzufügen von Benutzern und Zuweisen von Lizenzen zu Microsoft 365 gleichzeitig.
ms.date: 07/01/2020
ms.openlocfilehash: 95f84ead009b7510699e467bf5f12bf32d8097d8
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/17/2020
ms.locfileid: "47948796"
---
# <a name="add-users-and-assign-licenses-at-the-same-time"></a>Hinzufügen von Benutzern und gleichzeitiges Zuweisen von Lizenzen

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Die Personen in Ihrem Team benötigen jeweils ein Benutzerkonto, bevor Sie sich anmelden und auf [Microsoft 365 for Business](https://www.microsoft.com/microsoft-365/business)zugreifen können. Die einfachste Methode zum Hinzufügen von Benutzerkonten besteht darin, sie im Microsoft 365 Admin Center nacheinander hinzuzufügen. Nachdem Sie diesen Schritt durchführen, verfügen Ihre Benutzer über Microsoft 365-Lizenzen, Anmeldeinformationen und Microsoft 365-Postfächer.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Zum Hinzufügen von Benutzern und Zuweisen von Lizenzen müssen Sie ein globaler, eine Lizenz oder ein Benutzer Administrator sein. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="watch-add-users-in-the-admin-center"></a>Watch: Hinzufügen von Benutzern im Admin Center

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfN?autoplay=false]

> [!NOTE]
> Die im Video verwendeten Schritte zeigen einen anderen Ausgangspunkt für das Hinzufügen von Benutzern, die restlichen Schritte sind jedoch mit dem folgenden Verfahren identisch.

## <a name="add-users-one-at-a-time"></a>Hinzufügen von Benutzern zu einem Zeitpunkt

::: moniker range="o365-worldwide"

1. Wechseln Sie zum Admin Center unter <https://admin.microsoft.com>.
2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Grundlagen einrichten** die grundlegenden Benutzerinformationen ein, und wählen Sie dann **weiter**aus.
    - **Name** Geben Sie den vor-und Nachnamen, den Anzeigenamen und den Benutzernamen ein.
    - **Domäne** Wählen Sie die Domäne für das Konto des Benutzers aus. Wenn beispielsweise der Benutzername Jakob ist und die Domäne contoso.com ist, melden Sie sich mit Jakob@contoso.com an.
    - **Kennworteinstellungen** Wählen Sie aus, ob Sie das automatisch generierte Kennwort verwenden oder ein eigenes sicheres Kennwort für den Benutzer erstellen möchten.
    - Der Benutzer muss sein Kennwort nach 90 Tagen ändern. Sie können aber auch die folgende Option auswählen: **Anfordern, dass dieser Benutzer bei der ersten Anmeldung sein Kennwort ändert**.
    - Wählen Sie aus, ob das Kennwort in einer e-Mail gesendet werden soll, wenn der Benutzer hinzugefügt wird.
4. Wählen Sie im Bereich **Produktlizenzen zuweisen** den Speicherort und die entsprechende Lizenz für den Benutzer aus. Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen. Erweitern Sie **apps** , und wählen Sie Apps aus, um die apps zu begrenzen, für die der Benutzer eine Lizenz besitzt. Wählen Sie **Weiter** aus.
5. Erweitern Sie im Bereich **Optionale Einstellungen die Option** **roles** , um diesen Benutzer zum Administrator zu machen. Erweitern Sie **Profilinformationen** , um zusätzliche Informationen zum Benutzer hinzuzufügen.
6. Wählen Sie **weiter**aus, überprüfen Sie die Einstellungen Ihres neuen Benutzers, nehmen Sie die gewünschten Änderungen vor, und wählen Sie dann **Hinzufügen beenden**und dann **Schließen**aus.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie zum Admin Center unter <https://portal.office.de/adminportal>.
2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein. Wenn Sie fertig sind, wählen Sie **Hinzufügen**aus.
    - **Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. 
    - **Domäne** Wenn beispielsweise der Benutzername Jakob ist und die Domäne contoso.com ist, melden Sie sich an, indem Sie Jakob@contoso.com eingeben.
    - **Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. 
    - **Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie, um ein sicheres Kennwort für den Benutzer anzugeben. Sie müssen Ihr Kennwort nach 90 Tagen ändern. Sie können aber auch die folgende Option auswählen: **Der Benutzer muss sein Kennwort bei der ersten Anmeldung ändern**.
    - **Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. 
    - **Produktlizenzen** Erweitern Sie diesen Abschnitt, und wählen Sie die entsprechende Lizenz aus.  Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie zum Admin Center unter <https://portal.partner.microsoftonline.cn>.
2. Wählen Sie **Benutzer** > **Aktive Benutzer** und **Benutzer hinzufügen** aus.
3. Geben Sie im Bereich **Neuer Benutzer** die nachstehenden Informationen ein. Wenn Sie fertig sind, wählen Sie **Hinzufügen**aus.
    - **Name** Geben Sie den Vornamen, Nachnamen, Anzeigenamen und Benutzernamen ein. 
    - **Domäne** Wenn beispielsweise der Benutzername Jakob ist und die Domäne contoso.com ist, melden Sie sich an, indem Sie Jakob@contoso.com eingeben.
    - **Kontaktinformationen** Erweitern Sie diesen Abschnitt, um eine Mobiltelefonnummer, Anschrift usw. einzugeben. 
    - **Kennwort** Verwenden Sie das automatisch generierte Kennwort, oder erweitern Sie, um ein sicheres Kennwort für den Benutzer anzugeben. Sie müssen Ihr Kennwort nach 90 Tagen ändern. Sie können aber auch die folgende Option auswählen: **Der Benutzer muss sein Kennwort bei der ersten Anmeldung ändern**.
    - **Rollen** Erweitern Sie diesen Abschnitt, wenn der betreffende Benutzer ein Administrator werden soll. 
    - **Produktlizenzen** Erweitern Sie diesen Abschnitt, und wählen Sie die entsprechende Lizenz aus.  Wenn Sie keine Lizenzen zur Verfügung haben, können Sie trotzdem einen Benutzer hinzufügen und zusätzliche Lizenzen kaufen.

::: moniker-end

## <a name="add-multiple-users-at-the-same-time"></a>Gleichzeitiges Hinzufügen mehrerer Benutzer

Sie können eine der folgenden Methoden verwenden, um mehrere Benutzer gleichzeitig hinzuzufügen:

- **Mithilfe einer Kalkulationstabelle können Sie Benutzer in Massen hinzufügen.** Weitere Informationen hierzu finden Sie unter [Gleichzeitiges Hinzufügen von mehreren Benutzern](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time).
- **Automatisieren Sie das Hinzufügen von Konten und Zuweisen von Lizenzen.** Siehe [Erstellen von Benutzerkonten mit Microsoft 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/create-user-accounts-with-microsoft-365-powershell). Wählen Sie diese Methode aus, wenn Sie mit der Nutzung von Windows PowerShell-Cmdlets bereits vertraut sind.
- **Sie verwenden Active Directory?** [Einrichten der Verzeichnissynchronisierung für Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization). Verwenden Sie das Azure AD Connect-Tool, um Active Directory Benutzerkonten (und andere Active Directory-Objekte) in Microsoft 365 zu replizieren. Bei der Synchronisierung werden nur die Benutzerkonten hinzugefügt. Sie müssen den synchronisierten Benutzern Lizenzen zuweisen, bevor Sie e-Mails und andere Office-Apps verwenden können.
- **Sie migrieren aus Exchange?** Hier finden Sie [Möglichkeiten zum Migrieren mehrerer e-Mail-Konten zu Office 365](https://docs.microsoft.com/Exchange/mailbox-migration/mailbox-migration). Wenn Sie mehrere Postfächer mithilfe von Cutover, Staged oder einer Exchange-Hybridmethode zu Microsoft 365 migrieren, fügen Sie automatisch Benutzer im Rahmen der Migration hinzu. Bei der Migration werden nur die Benutzerkonten hinzugefügt. Sie müssen den Benutzern Lizenzen zuweisen, bevor Sie e-Mails und andere Office-Apps verwenden können. Wenn Sie einem Benutzer keine Lizenz zuweisen, wird sein Postfach nach einer Kulanzzeit von 30 Tagen deaktiviert. Erfahren Sie, wie Sie Benutzern im Microsoft 365 Admin Center [Lizenzen zuweisen](../manage/assign-licenses-to-users.md) .

## <a name="next-steps"></a>Nächste Schritte

Nachdem Sie einen Benutzer hinzugefügt haben, erhalten Sie eine e-Mail-Benachrichtigung von Microsoft. Die e-Mail enthält die Benutzer-ID und das Kennwort der Person, damit Sie sich bei Microsoft 365 anmelden können. Verwenden Sie hierzu Ihre normale Vorgehensweise für die Übermittlung neuer Kennwörter. Geben Sie den [Leitfaden für Mitarbeiter Schnellstart](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) mit ihren neuen Benutzern frei, um Dinge einzurichten, beispielsweise zum [herunterladen und Installieren von Office-Apps auf einem PC oder Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658) und zum [Einrichten von Office-Apps und e-Mail auf einem mobilen Gerät](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwandte Inhalte

[Hinzufügen eines neuen Mitarbeiters zu Microsoft 365](add-new-employee.md) (Artikel) \
Gleich [zeitiges Hinzufügen mehrerer Benutzer zu Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/add-several-users-at-the-same-time) (Artikel) \
[Wiederherstellen eines Benutzers in Microsoft 365](restore-user.md) (Artikel) \
[Zuweisen von Lizenzen zu Benutzern](../manage/assign-licenses-to-users.md) (Artikel) \
[Löschen eines Benutzers aus Ihrer Organisation](delete-a-user.md) (Artikel)
