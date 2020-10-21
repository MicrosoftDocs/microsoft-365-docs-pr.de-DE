---
title: Zuweisen von Lizenzen an Benutzer
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_TOC
- commerce
ms.custom:
- TopSMBIssues
- SaRA
- okr_SMB
- AdminSurgePortfolio
- manage_licenses
search.appverid:
- MET150
description: Erfahren Sie, wie Sie Benutzern Lizenzen zuweisen.
ms.date: 08/14/2020
ms.openlocfilehash: ec2f9ae2e580987266c636343a66d7c21138e4c3
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48645131"
---
# <a name="assign-licenses-to-users"></a>Zuweisen von Lizenzen an Benutzer

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

::: moniker range="o365-worldwide"

Sie können Benutzern entweder auf der Seite **Aktive Benutzer** oder auf der Seite **Lizenzen** Lizenzen zuweisen. Welche Methode Sie verwenden, hängt davon ab, ob Sie bestimmten Benutzern Produktlizenzen zuweisen oder Benutzern Lizenzen für ein bestimmtes Produkt zuweisen möchten.

::: moniker-end

[Erfahren Sie, wie Sie gleichzeitig einen Benutzer hinzufügen und eine Lizenz zuweisen](../add-users/add-users.md).

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen ein globaler, Lizenz- oder Benutzeradministrator sein, um Lizenzen zuweisen zu können. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen von Microsoft 365](../add-users/about-admin-roles.md).
- Sie können [Lizenzen zu Benutzerkonten mit Office 365 PowerShell zuweisen](https://go.microsoft.com/fwlink/p/?linkid=850410).
- Informationen zur gruppenbasierten Lizenzierung finden Sie unter [Zuweisen von Lizenzen zu Benutzern mithilfe der Gruppenmitgliedschaft in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign).
- Einige Dienste, z. B. Sway, werden Benutzern automatisch zugewiesen und müssen nicht einzeln zugewiesen werden.

::: moniker range="o365-worldwide"

## <a name="use-the-licenses-page-to-assign-licenses-to-users"></a>Verwenden der Seite "Lizenzen", um Benutzern Lizenzen zuzuweisen

Wenn Sie zum Zuweisen von Lizenzen die Seite **Lizenzen** verwenden, können Sie bis zu 20 Benutzern Lizenzen für ein bestimmtes Produkt zuweisen. Auf der Seite **Lizenzen** wird eine Liste aller Produkte angezeigt, die Sie abonniert haben. Außerdem wird die Gesamtanzahl der Lizenzen für jedes Produkt, wie viele Lizenzen zugewiesen sind und wie viele verfügbar sind, angezeigt.

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.
2. Wählen Sie ein Produkt aus.
3. Wählen Sie auf der Seite "Produktdetails" **Lizenzen zuweisen** aus.
4. Beginnen Sie im Bereich **Lizenzen an Benutzer zuweisen** mit der Eingabe eines Namens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen. Sie können bis zu 20 Benutzer gleichzeitig hinzufügen.
5. Wählen Sie **Apps und Dienste aktivieren oder deaktivieren** aus, um bestimmte Elemente zuzuweisen oder zu entfernen.
6. Wählen Sie abschließend **Zuweisen** und dann **Schließen** aus.

Wenn ein Konflikt vorliegt, wird eine Meldung angezeigt, in der Sie erfahren, was das Problem ist und wie Sie es beheben können. Wenn Sie beispielsweise Lizenzen ausgewählt haben, die in Konflikt stehende Dienste enthalten, weist die Fehlermeldung darauf hin, dass Sie die in der jeweiligen Lizenz enthaltenen Dienste überprüfen und es erneut versuchen sollen.

## <a name="change-the-apps-and-services-a-user-has-access-to"></a>Ändern der Apps und Dienste, auf die ein Benutzer zugreifen kann

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a>.
2. Wählen Sie auf der Seite **Lizenzen** die Zeile für einen bestimmten Benutzer aus.
3. Aktivieren bzw. deaktivieren Sie im rechten Bereich die Apps und Dienste, für die Sie Zugriff gewähren oder entfernen möchten.
4. Wählen Sie abschließend **Speichern** und dann **Schließen** aus.

::: moniker-end

::: moniker range="o365-worldwide"

## <a name="use-the-active-users-page-to-assign-licenses"></a>Verwenden der Seite "Aktive Benutzer" zum Zuweisen von Lizenzen

Wenn Sie Lizenzen über die Seite **Aktive Benutzer** zuweisen, weisen Sie einzelnen Benutzern Produktlizenzen zu.

### <a name="assign-licenses-to-multiple-users"></a>Zuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kreise neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.
3. Wählen Sie am oberen Rand **Weitere Optionen** (...) und dann **Produktlizenzen verwalten** aus.
4. Wählen Sie im Bereich **Produktlizenzen verwalten** die Optionen **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.
5. Setzen Sie im Bereich **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** die Umschaltfläche für die Lizenz, die der ausgewählten Benutzer erhalten soll, auf die Stellung **Ein**.\
    Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.
6. Wählen Sie am unteren Rand des Bereichs **Hinzufügen** \> **Schließen** aus.  

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-multiple-users"></a>Zuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.
5. Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.\
    Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.
6. Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-multiple-users"></a>Zuweisen von Lizenzen für mehrere Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Kontrollkästchen neben den Namen der Benutzer, denen Sie Lizenzen zuweisen möchten.
3. Wählen Sie im Bereich **Massenaktionen** die Option **Produktlizenzen bearbeiten** aus.
4. Wählen Sie im Bereich **Produkte zuweisen** nacheinander **Zu vorhandenen Produktlizenzzuweisungen hinzufügen** \> **Weiter** aus.
5. Setzen Sie die Umschaltfläche für die Lizenzen, die die ausgewählten Benutzer erhalten sollen, auf die Stellung **Ein**.\
    Standardmäßig werden alle diesen Lizenzen zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für die Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die die Benutzer nicht erhalten sollen, auf die Stellung **Aus**.
6. Wählen Sie unten im Bereich **Zu vorhandenen Produkten hinzufügen** **Hinzufügen** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-worldwide"

### <a name="assign-licenses-to-one-user"></a>Zuweisen von Lizenzen an einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie die Zeile des Benutzers, dem Sie eine Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich **Lizenzen und Apps** aus.
4. Erweitern Sie den Abschnitt **Lizenzen**, aktivieren Sie die Kontrollkästchen für die Lizenzen, die Sie zuweisen möchten, und wählen Sie dann **Änderungen speichern** aus.

::: moniker-end

::: moniker range="o365-germany"

## <a name="assign-licenses-to-one-user"></a>Zuweisen von Lizenzen an einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.
4. Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.\
    Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für den Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

## <a name="assign-licenses-to-one-user"></a>Zuweisen von Lizenzen an einen Benutzer

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.
2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, dem Sie eine Lizenz zuweisen möchten.
3. Wählen Sie im rechten Bereich in der Zeile **Produktlizenzen** die Option **Bearbeiten** aus.
4. Setzen Sie im Bereich **Produktlizenzen** die Umschaltfläche auf die Stellung **Ein** für die Lizenz, die Sie diesem Benutzer zuweisen möchten.\
    Standardmäßig werden alle dieser Lizenz zugeordneten Dienste dem Benutzer automatisch zugewiesen. Sie können die für den Benutzer verfügbaren Dienste einschränken. Setzen Sie die Umschaltfläche für die Dienste, die dieser Benutzer nicht erhalten soll, auf die Stellung **Aus**.
5. Wählen Sie unten im Bereich **Produktlizenzen** nacheinander **Speichern** \> **Schließen** \> **Schließen** aus.

::: moniker-end

## <a name="assign-a-license-to-a-guest-user"></a>Zuweisen einer Lizenz an einen Gastbenutzer

Sie können Gastbenutzer einladen, mit Ihrer Organisation im Azure Active Directory Admin Center zusammenzuarbeiten. Informationen über Gastbenutzer finden Sie unter [Was ist Gastbenutzerzugriff in Azure Active Directory B2B?](https://docs.microsoft.com/azure/active-directory/external-identities/what-is-b2b) Wenn Sie keine Gastbenutzer haben, siehe [Schnellstart: Hinzufügen von Gastbenutzern zu Ihrem Verzeichnis im Azure-Portal](https://docs.microsoft.com/azure/active-directory/external-identities/b2b-quickstart-add-guest-users-portal).

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

Wenn Ihre Benutzer die Office-Apps noch nicht installiert haben, können Sie die [Mitarbeiter-Kurzanleitung](https://support.microsoft.com/office/b9700090-ce64-4046-ab92-ce8488a7bc0f) für Ihre Benutzer freigeben, um Dinge einzurichten, z. B. [wie Microsoft 365 oder Office 2019 heruntergeladen und auf einem PC oder Mac installiert wird](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658), und [wie Office-Apps und E-Mails auf einem mobilen Gerät eingerichtet werden](https://support.microsoft.com/office/7dabb6cb-0046-40b6-81fe-767e0b1f014f).

## <a name="related-content"></a>Verwandte Inhalte

[Grundlegendes zu Abonnements und Lizenzen](../../commerce/licenses/subscriptions-and-licenses.md) (Artikel)\
[Aufheben der Zuweisung von Benutzerlizenzen](remove-licenses-from-users.md) (Artikel)\
[Kaufen oder Entfernen von Lizenzen für Ihr Abonnement](../../commerce/licenses/buy-licenses.md) (Artikel)