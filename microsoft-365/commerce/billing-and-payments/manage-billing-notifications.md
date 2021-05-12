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
ms.openlocfilehash: d4083dc5a9d70eb8c20b4107389ec5fec65749ad
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52332138"
---
# <a name="manage-billing-notifications-and-invoice-attachments"></a>Verwalten von Benachrichtigungen zur Abrechnung und Rechnungsanlagen

Auf **der Seite Abrechnungsbenachrichtigungen** können Sie verwalten, wer Rechnungsbenachrichtigungs-E-Mails für Ihre Organisation empfängt. Die Seite bietet auch die Möglichkeit, die Rechnungen Ihrer Organisation [als E-Mail-Anlagen zu empfangen.](#receive-your-organizations-invoices-as-email-attachments)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Sie müssen ein globaler Administrator sein, um die in diesem Artikel beschriebenen Schritte ausführen zu können. Abrechnungsadministratoren können einige dieser Änderungen vornehmen, wie in den folgenden Abschnitten erwähnt. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="change-the-language-you-receive-email-in"></a>Ändern der Sprache, in der Sie E-Mails erhalten

> [!NOTE]
> Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.

Abrechnungsbenachrichtigungs-E-Mails werden in der bevorzugten Sprache Ihrer Organisation gesendet. Um die bevorzugte Sprache zu ändern, verwenden Sie die folgenden Schritte.

1. Wechseln Sie im Microsoft 365 Admin Center zur **Seite**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen.</a>
2. Wählen Sie **im Abschnitt Abrechnungsbenachrichtigungseinstellungen** die Option **Benachrichtigungseinstellungen bearbeiten aus.**
3. Wählen Sie **im Bereich** Abrechnungsbenachrichtigungseinstellungen **unter** Bevorzugte Sprache die gewünschte Sprache aus, und wählen Sie dann **Speichern aus.**

## <a name="change-who-receives-billing-notifications"></a>Ändern, wer Abrechnungsbenachrichtigungen erhält

Die Abrechnungsbenachrichtigungen Ihrer Organisation werden an die primäre und alternative E-Mail-Adresse jedes globalen und Abrechnungsadministrators gesendet. Verwenden Sie die folgenden Schritte, um zu ändern, welche Benutzer die Administratorrolle "Global" oder "Abrechnung" haben.

### <a name="assign-admin-roles-by-using-the-billing-notifications-page"></a>Zuweisen von Administratorrollen mithilfe der Seite Abrechnungsbenachrichtigungen

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie **im Abschnitt Admins receiving billing notifications** den Link **Abrechnungsadministrator** oder **globaler** Administrator im Beschreibungstext aus.
3. Wählen Sie im rechten Bereich auf der Registerkarte **Zugewiesene Administratoren** die Option **Hinzufügen aus.**
4. Geben Sie im Bereich Administrator **hinzufügen** den Anzeigenamen oder Benutzernamen des Benutzers ein, und wählen Sie dann den Benutzer aus der Liste der Vorschläge aus.
5. Fügen Sie mehrere Benutzer hinzu, bis Sie fertig sind.
6. Wählen Sie **Speichern** aus. Der Benutzer wird der Liste der zugewiesenen Administratoren hinzugefügt.

### <a name="remove-admin-roles-by-using-the-billing-notifications-page"></a>Entfernen von Administratorrollen mithilfe der Seite Abrechnungsbenachrichtigungen

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie **im Abschnitt Admins receiving billing notifications** den Link **Abrechnungsadministrator** oder **globaler** Administrator im Beschreibungstext aus.
3. Wählen Sie im rechten Bereich auf der Registerkarte Zugewiesene **Administratoren** die Zu entfernenden Benutzer aus der Rolle aus, und wählen Sie dann **Entfernen aus.**
4. Wählen Sie im Bestätigungsfeld Entfernen **aus.** Der Benutzer wird aus der Liste der zugewiesenen Administratoren entfernt.

## <a name="change-the-email-addresses-for-admins"></a>Ändern der E-Mail-Adressen für Administratoren

Verwenden Sie die folgenden Schritte, um die primäre und alternative E-Mail-Adresse anderer Administratoren in Ihrer Organisation zu ändern.

> [!NOTE]
> Abrechnungsadministratoren können ihre eigenen primären und alternativen E-Mail-Adressen ändern, jedoch nicht für andere Administratoren.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen Sie **im Abschnitt Admins receiving billing notifications** einen Namen aus.
3. Fügen Sie im rechten Bereich die primäre und alternative E-Mail-Adresse nach Bedarf hinzu, oder aktualisieren Sie sie, und wählen Sie dann **Speichern aus.**

## <a name="change-your-organizations-contact-email"></a>Ändern der Kontakt-E-Mail Ihrer Organisation

Zusätzlich zu Ihren globalen und Abrechnungsadministratoren senden wir Abrechnungsbenachrichtigungen an die E-Mail-Adresse Ihrer Organisation. Um die E-Mail-Adresse zu ändern, verwenden Sie die folgenden Schritte.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen **Sie unter Organisationskontakt, der Abrechnungsbenachrichtigungen empfängt,** den Organisationskontakt aus.
3. Geben Sie im rechten Bereich die E-Mail-Adresse ein, die Sie verwenden möchten, und wählen Sie dann **Speichern aus.**

## <a name="receive-your-organizations-invoices-as-email-attachments"></a>Empfangen der Rechnungen Ihrer Organisation als E-Mail-Anlagen

> [!NOTE]
> Abrechnungsadministratoren können auch die Schritte in diesem Abschnitt ausführen.

Sie können eine Kopie der Rechnung Ihrer Organisation als PDF-Datei an die Rechnung von Benachrichtigungs-E-Mails angefügt haben, wenn eine neue Rechnung bereit ist. Verwenden Sie die folgenden Schritte, um Rechnungen als Anlagen zu empfangen.

1. Gehen Sie im Admin Center zur Seite **Abrechnung** > <a href="https://go.microsoft.com/fwlink/p/?linkid=853212" target="_blank">Abrechnungsbenachrichtigungen</a>.
2. Wählen **Sie unter Abrechnungsbenachrichtigungseinstellungen** die **Option Benachrichtigungseinstellungen bearbeiten aus.**
3. Aktivieren Sie **im** Bereich Abrechnungsbenachrichtigungseinstellungen unter Anfügen einer PDF an Ihre **Rechnungs-E-Mails** das Kontrollkästchen, und wählen Sie **dann Speichern aus.**

Um den Empfang der Rechnungsanlage jederzeit zu beenden, führen Sie die obigen Schritte aus, und aktivieren Sie das Kontrollkästchen **Pdf** an Ihre Rechnungs-E-Mails anfügen in Schritt 3.

## <a name="what-if-i-have-a-billing-profile"></a>Was passiert, wenn ich ein Abrechnungsprofil habe?

Wenn Sie über ein Abrechnungsprofil verfügen, unterscheiden sich einige der in diesem Artikel beschriebenen Schritte für einige Ihrer Abonnements möglicherweise geringfügig. In diesem Abschnitt werden diese Unterschiede beschrieben. [Wo kann ich wissen, ob ich ein Abrechnungsprofil habe?](manage-billing-profiles.md)

### <a name="who-receives-billing-notifications"></a>Wer empfängt Abrechnungsbenachrichtigungen?

Abrechnungsbenachrichtigungs-E-Mails werden an die primären und alternativen E-Mail-Adressen für Benutzer gesendet, denen eine der folgenden Rollen zugewiesen ist:

- Abrechnungsprofilbesitzer
- Mitwirkender des Abrechnungsprofils
- Rechnungs-Manager

Weitere Informationen zu Abrechnungsprofilrollen und deren Verwaltung finden Sie unter [Understand Microsoft Customer Agreement administrative roles in Azure](/azure/cost-management-billing/manage/understand-mca-roles).

Um zu ändern, wer die Abrechnungsbenachrichtigungen Ihrer Organisation empfängt, verwenden Sie die folgenden Schritte, um die Den Benutzern zugewiesenen Rollen zu ändern.

1. Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Abrechnungsrechnungen & Zahlungen.</a>
2. Wählen Sie **auf der Registerkarte** Abrechnungsprofil ein Abrechnungsprofil aus.
3. Weisen Sie **im Abschnitt Abrechnungsprofilrollen** Rollen für Abrechnungsprofilbesitzer,  **Abrechnungsprofilbeitragszahler** oder **Rechnungs-Manager zu** oder entfernen Sie sie.

### <a name="receive-invoices-as-email-attachments"></a>Empfangen von Rechnungen als E-Mail-Anlagen

Um Ihre Rechnungen als Anlagen zu Ihren Rechnungsbenachrichtigungen zu erhalten, verwenden Sie die folgenden Schritte, um diese Einstellung für ein bestimmtes Abrechnungsprofil zu aktivieren.

1. Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2102895" target="_blank">Abrechnungsrechnungen & Zahlungen.</a>
2. Wählen Sie **die Registerkarte Abrechnungsprofile** aus, und wählen Sie dann ein Abrechnungsprofil aus der Liste aus.
3. Wechseln Sie auf der Seite **Abrechnungsprofildetails** unter Rechnungen in E-Mail-Anlagen erhalten zu **Ein**.

## <a name="related-content"></a>Verwandte Inhalte

[Anzeigen Ihrer Rechnung](view-your-bill-or-invoice.md) (Artikel)\
[Verstehen Ihrer Rechnung oder Rechnung für Microsoft 365 Business](understand-your-invoice2.md) (Artikel)\
[Hinzufügen von Benutzern und gleichzeitiges Zuweisen von Lizenzen](../../admin/add-users/add-users.md) (Artikel)
