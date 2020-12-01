---
title: Verwalten und Überwachen von Prioritäts Konten
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
ms.custom: AdminSurgePortfolio
description: Überwachen von fehlerhaften und verzögerten e-Mail-Nachrichten, die an oder von Konten mit hohem geschäftlichen Einfluss gesendet wurden.
ms.openlocfilehash: bc191873b3bbdcd84122a5430adeffe2b8c29fb1
ms.sourcegitcommit: 5ce64d510b15c6e2df32b78e6086f77156731e3c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/30/2020
ms.locfileid: "49477613"
---
# <a name="manage-and-monitor-priority-accounts"></a>Verwalten und Überwachen von Prioritäts Konten

In jeder Microsoft 365-Organisation gibt es wichtige Personen wie Führungskräfte, Führungskräfte, Führungskräfte oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder Informationen mit hoher Priorität haben.

Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie nun bestimmte Benutzer als Prioritäts Konten festlegen und App-spezifische Features nutzen, die Ihnen zusätzlichen Schutz bieten. In Zukunft unterstützen weitere apps und Features vorrangige Konten, und zunächst haben wir zwei Funktionen angekündigt: **Priority Account Protection** und **Premium-Nachrichtenfluss Überwachung**.

- **Priority Account Protection** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritäts Konten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können. Weitere Informationen finden Sie unter [Benutzer Tags in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/user-tags?view=o365-worldwide).
- **Premium-Nachrichtenfluss Überwachung** – ein einwandfreier Nachrichtenfluss kann für den geschäftlichen Erfolg von entscheidender Bedeutung sein, und Übermittlungsverzögerungen oder-Fehler können sich negativ auf das Unternehmen auswirken. Sie können einen Schwellenwert für fehlerhafte oder verzögerte e-Mails auswählen, Warnungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über e-Mail-Probleme für Prioritäts Konten anzeigen. Weitere Informationen finden Sie [in der modernen Exchange-Verwaltungskonsole unter e-Mail Issues for Priority Accounts Report](https://docs.microsoft.com/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report).

## <a name="before-you-begin"></a>Vorbereitung

Das in diesem Thema beschriebene Feature für den **Priority-Kontoschutz** steht nur Organisationen zur Verfügung, die die folgenden Anforderungen erfüllen:

- Microsoft Defender für Office 365 Plan 2, einschließlich der Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.

Das Feature für die **erstklassige Nachrichtenfluss Überwachung** , das in diesem Thema beschrieben wird, steht nur Organisationen zur Verfügung, die die folgenden Anforderungen erfüllen:

- Ihre Organisation muss eine Lizenzanzahl von mindestens 10.000, entweder aus einer oder aus einer Kombination der folgenden Produkte haben: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Beispielsweise kann Ihre Organisation 3000 Office 365 E3-Lizenzen und 8500 Microsoft 365 E5 für insgesamt 11.500 Lizenzen von den qualifizierten Produkten haben.
- Ihre Organisation muss mindestens 50 monatliche aktive Exchange Online Benutzer haben.

> [!NOTE]
> Sie können bis zu 250-Prioritäts Konten überwachen.

### <a name="add-priority-accounts-from-the-setup-page"></a>Hinzufügen von Prioritäts Konten auf der Seite "Setup"

Fügen Sie auf der **Seite Setup** die Prioritäts Konten hinzu.

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie zu **Setup**  >  **Organizational Knowledge**, und wählen Sie **Ansicht** unter **Überwachen Sie Ihre wichtigsten Konten**.

3. Wählen Sie **Erste Schritte** oder **Verwaltung** aus.

4. Geben Sie auf der Seite " **Prioritäts Konten hinzufügen** " im Suchfeld den Namen oder die e-Mail-Adresse der Person ein, die Sie der Liste Priority Accounts hinzufügen möchten. Sie können auch Ihren e-Mail-Schwellenwert für fehlerhafte oder verzögerte e-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritäts Konten erhalten.

5. Wählen Sie den Benutzer aus, und klicken Sie auf **Speichern**.

Sie können auch Prioritäts Konten von der Seite aktive Benutzer hinzufügen.

### <a name="add-priority-accounts-from-active-users-page"></a>Seite "aktive Benutzer" Hinzufügen von Prioritäten Konten

Fügen Sie auf der Seite aktive Benutzer Prioritäts Konten hinzu.

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Wechseln Sie zu **Benutzer**  >  **aktive Benutzer** , und wählen Sie oben auf der Seite. **..** aus. Wählen Sie **Prioritäten Konten verwalten** aus.

3. Wählen Sie **Konten hinzufügen** aus, und geben Sie auf der Seite **Priority Accounts hinzufügen** im Suchfeld den Namen der Person ein, die Sie der Liste Priority Accounts hinzufügen möchten.

4. Wählen Sie den Benutzer aus, und klicken Sie auf **Speichern**.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Entfernen eines Benutzers aus der Liste "Priority Accounts"

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie zu **Setup**  >  **Organizational Knowledge**, und wählen Sie **Ansicht** unter **Überwachen Sie Ihre wichtigsten Konten**.

3. Wählen Sie auf der Seite "die **meisten Konten überwachen** " unter **Diese Funktion verwalten** die Option **Priority Accounts** aus.

4. Wählen Sie auf der Seite **Priority Accounts** die Benutzer aus der Liste aus, die Sie entfernen möchten, und klicken Sie dann auf **Konten entfernen**.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Prioritäts Konten in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)