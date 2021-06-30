---
title: Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: prkalid, guyb
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- okr_SMB
- AdminSurgePortfolio
- commerce_billing
search.appverid:
- MET150
description: Erfahren Sie, wie Sie verwalten, wer Rechnungsbenachrichtigungs-E-Mails und Rechnungsanlagen empfängt.
ms.date: 03/17/2021
ms.openlocfilehash: a49598cd1b361a85af8455b0aff19e11fcf96526
ms.sourcegitcommit: 99e67bfe1d677c2f51712b05dcc54908b343cf6f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53203244"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen

Auf der Seite **"Abrechnungsbenachrichtigungen"** können Sie verwalten, wer Abrechnungsbenachrichtigungs-E-Mails für Ihre Organisation empfängt. Die Seite bietet auch die Möglichkeit, [die Rechnungen Ihrer Organisation als E-Mail-Anlagen](#receive-your-organizations-invoices-as-email-attachments)zu erhalten.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können. Abrechnungsadministratoren können einige dieser Änderungen vornehmen, wie in den folgenden Abschnitten angegeben. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="change-the-language-you-receive-email-in"></a>Ändern der Sprache, in der Sie eine E-Mail erhalten

Rechnungsbenachrichtigungs-E-Mails werden in der bevorzugten Sprache Ihrer Organisation gesendet. Führen Sie die folgenden Schritte aus, um die bevorzugte Sprache zu ändern.

1. Wechseln Sie im Microsoft 365 Admin Center zur   >  Seite<a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">"Abrechnungsbenachrichtigungen".</a>
2. Wählen Sie im Abschnitt **"Einstellungen für Abrechnungsbenachrichtigungen"** die **Option "Benachrichtigungseinstellungen bearbeiten" aus.**
3. Wählen Sie im Bereich "Einstellungen für **Abrechnungsbenachrichtigungen"** unter **"Bevorzugte Sprache"** die gewünschte Sprache aus, und wählen Sie dann **"Speichern"** aus.

## <a name="change-who-receives-billing-notifications"></a>Ändern, wer Abrechnungsbenachrichtigungen empfängt

Die Abrechnungsbenachrichtigungen Ihrer Organisation werden an die primäre und alternative E-Mail-Adresse jedes globalen und Abrechnungsadministrators gesendet. Führen Sie die folgenden Schritte aus, um zu ändern, welche Benutzer über die Rolle "Globaler Administrator" oder "Abrechnungsadministrator" verfügen.

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>Zuweisen von Administratorrollen über die Seite "Abrechnungsbenachrichtigungen"

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** den Link **"Abrechnungsadministrator"** oder **"Globaler Administrator"** im Beschreibungstext aus.
3. Wählen Sie im rechten Bereich auf der Registerkarte **"Zugewiesene Administratoren"** die Option **"Hinzufügen"** aus.
4. Geben Sie im Bereich **"Administratoren hinzufügen"** den Anzeigenamen oder Benutzernamen des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.
5. Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.
6. Klicken Sie auf **Speichern**. Der Benutzer wird der Liste der zugewiesenen Administratoren hinzugefügt.

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>Entfernen von Administratorrollen über die Seite "Abrechnungsbenachrichtigungen"

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** den Link **"Abrechnungsadministrator"** oder **"Globaler Administrator"** im Beschreibungstext aus.
3. Wählen Sie im rechten Bereich auf der Registerkarte **"Zugewiesene Administratoren"** die Benutzer aus, die aus der Rolle entfernt werden sollen, und wählen Sie dann **"Entfernen"** aus.
4. Wählen Sie im Bestätigungsfeld **"Entfernen" aus.** Der Benutzer wird aus der Liste der zugewiesenen Administratoren entfernt.

## <a name="change-the-email-addresses-for-admins"></a>Ändern der E-Mail-Adressen für Administratoren

Um die primäre und alternative E-Mail-Adresse anderer Administratoren in Ihrer Organisation zu ändern, führen Sie die folgenden Schritte aus.

> [!NOTE]
> Abrechnungsadministratoren können ihre eigenen primären und alternativen E-Mail-Adressen ändern, jedoch nicht für andere Administratoren.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie im Abschnitt **"Administratoren, die Abrechnungsbenachrichtigungen erhalten"** einen Namen aus.
3. Fügen Sie im rechten Bereich die primäre und alternative E-Mail-Adresse nach Bedarf hinzu oder aktualisieren Sie sie, und wählen Sie dann **Speichern** aus.

## <a name="change-your-organizations-contact-email"></a>Ändern der Kontakt-E-Mail-Adresse Ihrer Organisation

Zusätzlich zu Ihren globalen Administratoren und Abrechnungsadministratoren senden wir Abrechnungsbenachrichtigungen an die E-Mail-Kontaktadresse Ihrer Organisation. Führen Sie die folgenden Schritte aus, um die E-Mail-Adresse zu ändern.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie unter **Organisationskontakt, der Abrechnungsbenachrichtigungen empfängt,** den Organisationskontakt aus.
3. Geben Sie im rechten Bereich die E-Mail-Adresse ein, die Sie verwenden möchten, und wählen Sie dann **Speichern** aus.

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>Empfangen der Rechnungen Ihrer Organisation als E-Mail-Anlagen

> [!NOTE]
> Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.

Sie können eine Kopie der Rechnung Ihrer Organisation als PDF-Datei an E-Mails mit Rechnungsbenachrichtigungen anhängen lassen, wenn eine neue Rechnung fertig ist. Gehen Sie folgendermaßen vor, um Rechnungen als Anlagen zu erhalten.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie unter **"Abrechnungsbenachrichtigungseinstellungen"** die Option **"Benachrichtigungseinstellungen bearbeiten" aus.**
3. Aktivieren Sie im Bereich "Einstellungen für **Abrechnungsbenachrichtigungen"** unter **"PDF an Ihre Rechnungs-E-Mails anhängen"** das Kontrollkästchen, und wählen Sie **"Speichern"** aus.

Um den Empfang der Rechnungsanlage jederzeit zu beenden, führen Sie die oben beschriebenen Schritte aus, und deaktivieren Sie das Kontrollkästchen **"PDF an Ihre E-Mails** an Rechnung anhängen" in Schritt 3.

## <a name="what-if-i-have-a-billing-profile"></a>Was geschieht, wenn ich ein Abrechnungsprofil habe?

Wenn Sie über ein Abrechnungsprofil verfügen, können sich einige der in diesem Artikel beschriebenen Schritte für einige Ihrer Abonnements geringfügig unterscheiden. In diesem Abschnitt werden diese Unterschiede beschrieben. [Woher weiß ich, ob ich ein Abrechnungsprofil habe?](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>Wer erhält Abrechnungsbenachrichtigungen?

Abrechnungsbenachrichtigungs-E-Mails werden an die primären und alternativen E-Mail-Adressen für Benutzer gesendet, denen eine der folgenden Rollen zugewiesen ist:

- Besitzer des Abrechnungsprofils
- Abrechnungsprofilmitwirkender
- Rechnungsmanager

Weitere Informationen zu Rollen für Abrechnungsprofilen und deren Verwaltung finden Sie unter ["Grundlegendes zu Verwaltungsrollen der Microsoft-Kundenvereinbarung" in Azure.](/azure/cost-management-billing/manage/understand-mca-roles)

Um zu ändern, wer die Abrechnungsbenachrichtigungen Ihrer Organisation erhält, verwenden Sie die folgenden Schritte, um die Den Benutzern zugewiesenen Rollen zu ändern.

1. Wechseln Sie im Admin Center zur Seite **"Abrechnungsrechnungen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& Zahlungen".</a>
2. Wählen Sie auf der Registerkarte **"Abrechnungsprofil"** ein Abrechnungsprofil aus.
3. Weisen Sie im Abschnitt **"Abrechnungsprofilrollen"** Rollen für den Besitzer des **Abrechnungsprofils,** den **Abrechnungsprofilmitwirkenden** oder **den Rechnungsverwalter** zu oder entfernen Sie diese.

### <a name="receive-invoices-as-email-attachments"></a>Empfangen von Rechnungen als E-Mail-Anlagen

Um Ihre Rechnungen als Anlagen zu Ihren Rechnungsbenachrichtigungen zu erhalten, verwenden Sie die folgenden Schritte, um diese Einstellung für ein bestimmtes Abrechnungsprofil zu aktivieren.

1. Wechseln Sie im Admin Center zur Seite **"Abrechnungsrechnungen**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">& Zahlungen".</a>
2. Wählen Sie die Registerkarte **"Abrechnungsprofile"** und dann ein Abrechnungsprofil aus der Liste aus.
3. Wechseln Sie auf der Seite "Abrechnungsprofildetails" unter **"Rechnungen in E-Mail-Anlagen abrufen"** zu **"Ein".**

## <a name="related-content"></a>Verwandte Inhalte

[Anzeigen Ihrer Rechnung](view-your-bill-or-invoice.md) (Artikel)\
[Abrechnungsinformationen für Microsoft 365 für Unternehmen in Mexiko](mexico-billing-info.md) (Artikel) \
[Grundlegendes zu Ihrer Rechnung für Microsoft 365 business](understand-your-invoice2.md) (Artikel)\
[Gleichzeitiges Hinzufügen von Benutzern und Zuweisen von Lizenzen](../../admin/add-users/add-users.md) (Artikel)
