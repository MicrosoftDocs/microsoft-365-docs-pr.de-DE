---
title: Zuweisen von Lizenzen an Benutzer
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- TopSMBIssues
- SaRA
- okr_SMB
- manage_licenses
- commerce
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Benutzern Lizenzen zuweisen.
ms.openlocfilehash: 9fa8981949215c4cf7779a21ff7089d7534e1ef0
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023749"
---
# <a name="assign-licenses-to-users"></a>Zuweisen von Lizenzen an Benutzer

Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen. Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.

> [!NOTE]
> Als Administrator können Sie keine Lizenzen für ein Self-Service-Kaufabonnement zuweisen oder aufheben, die von einem Benutzer in Ihrer Organisation erworben wurden. Sie können ein [Self-Service-Kaufabonnement übernehmen](../../commerce/subscriptions/manage-self-service-purchases-admins.md#take-over-a-self-service-purchase-subscription)und dann Lizenzen zuweisen oder die Zuweisung von Lizenzen kündigen.

[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen zu Benutzerkonten mit Office 365 PowerShell zuweisen](../../enterprise/assign-licenses-to-user-accounts-with-microsoft-365-powershell.md).
- Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen

Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen. Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben. Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Lizenzen**.
::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Lizenzen**.

::: moniker-end

2. Wählen Sie ein Produkt aus.
3. Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.
4. Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen. Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.
4. Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.
6. Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.

Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können. Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann

::: moniker range="o365-worldwide"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Lizenzen**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Lizenzen**.

::: moniker-end

2. Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.
3. Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.
4. Wählen Sie abschließend **Speichern** und dann **Schließen** aus.

## <a name="use-the-active-users-page-to-assign-licenses"></a>Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen

Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.

### <a name="assign-licenses-to-multiple-users"></a>Zuweisen von Lizenzen für mehrere Benutzer

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Aktive Benutzer**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Aktive Benutzer**.

::: moniker-end

2. Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.
3. Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.
5. Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.\
    Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.
6. Wählen Sie am unteren Rand des Bereichs **Hinzufügen** \> **Schließen** aus.  

### <a name="assign-licenses-to-one-user"></a>Zuweisen von Lizenzen an einen Benutzer

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Aktive Benutzer**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Abrechnung** > **Aktive Benutzer**.

::: moniker-end

2. Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.
4. Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.

## <a name="assign-a-license-to-a-guest-user"></a>Zuweisen einer Lizenz an einen Gastbenutzer

Sie können Gastbenutzer einladen, mit Ihrer Organisation im Azure Active Directory Admin Center zusammenzuarbeiten. Informationen über Gastbenutzer finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](/azure/active-directory/external-identities/what-is-b2b) Wenn Sie keine Gastbenutzer haben, siehe [Schnellstart: Hinzufügen von Gastbenutzern zu Ihrem Verzeichnis im Azure-Portal](/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

> [!IMPORTANT]
> Sie müssen ein globaler Administrator sein, um diese Schritte ausführen zu können.

1. Wechseln Sie zu <a href="https://go.microsoft.com/fwlink/p/?linkid=2067268" target="_blank">Azure Active Directory Admin Center</a>
2. Wählen Sie im Navigationsbereich **Benutzer** aus.
3. Auf der Seite **Benutzer | Alle Benutzer (Vorschau)**, wählen Sie **Filter hinzufügen** aus.
4. Wählen Sie im Menü **Feld auswählen** die Option **Benutzertyp**, und wählen Sie dann **Anwenden** aus.
5. Wählen Sie im nächsten Menü **Gast** aus.
6. Wählen Sie in der Liste der Ergebnisse den Benutzer aus, der eine Lizenz benötigt.
7. Wählen Sie unter **Verwalten** **Lizenzen** aus.
8. Wählen Sie **Zuweisungen** aus.
9. Wählen Sie auf der Seite **Lizenzzuweisungen aktualisieren** das Produkt aus, für das Sie eine Lizenz zuweisen möchten.
10. Deaktivieren Sie auf der rechten Seite die Kontrollkästchen für alle Dienste, auf die der Gastbenutzer nicht zugreifen kann.
11. Wählen Sie **Speichern** aus.

## <a name="next-steps"></a>Nächste Schritte

Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](../../business-video/employee-quick-setup.md) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwandte Inhalte

[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)\
[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)\
[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)