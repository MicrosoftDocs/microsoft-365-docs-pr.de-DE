---
title: Verwalten und Überwachen von Prioritätskonten
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
description: Überwachen sie fehlgeschlagene und verzögerte E-Mail-Nachrichten, die an oder von Konten gesendet werden, die hohe geschäftliche Auswirkungen haben.
ms.openlocfilehash: 0bba1f87f80de9fea249ce2604e83ceeadfb79ee
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51050642"
---
# <a name="manage-and-monitor-priority-accounts"></a>Verwalten und Überwachen von Prioritätskonten

In jeder Microsoft 365-Organisation gibt es wichtige Personen, z. B. Führungskräfte, Führungskräfte, Manager oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder informationen mit hoher Priorität haben.

Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie nun bestimmte Benutzer als Prioritätskonten festlegen und app-spezifische Features nutzen, die ihnen zusätzlichen Schutz bieten. In Zukunft werden mehr Apps und Features Prioritätskonten unterstützen, und zu Beginn haben wir zwei Funktionen **angekündigt:** Den Schutz von Prioritätskonten und die Premium-Nachrichtenflussüberwachung. 

- **Prioritätskontoschutz** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritätskonten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können. Weitere Informationen finden Sie unter [Benutzertags in Microsoft Defender für Office 365](../../security/defender-365-security/user-tags.md).
- **Premium-Nachrichtenflussüberwachung** – Ein fehlerfreier Nachrichtenfluss kann für den Geschäftserfolg von entscheidender Bedeutung sein, und Verzögerungen oder Fehler bei der Zustellung können sich negativ auf das Unternehmen auswirken. Sie können einen Schwellenwert für fehlgeschlagene oder verzögerte E-Mails auswählen, Benachrichtigungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über E-Mail-Probleme für Prioritätskonten anzeigen. Weitere Informationen finden Sie unter [E-Mail-Probleme für Prioritätskontenbericht in der modernen EAC.](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Bewährte Sicherheitsmethoden für Prioritätskonten finden Sie unter [Sicherheitsempfehlungen für Prioritätskonten](../../security/defender-365-security/security-recommendations-for-priority-accounts.md).

## <a name="before-you-begin"></a>Vorbereitung

Die **in diesem** Thema beschriebene Prioritätskontoschutzfunktion ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:

- Microsoft Defender für Office 365 Plan 2, einschließlich derer mit Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.

Die in diesem Thema beschriebene Premium Mail **Flow Monitoring-Funktion** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:

- Ihre Organisation muss eine Lizenzanzahl von mindestens 10.000 aus einem der folgenden Produkte oder einer Kombination der folgenden Produkte haben: Office 365 E3, Microsoft 365 E3, Office 365 E5, Microsoft 365 E5. Beispielsweise kann Ihre Organisation über 3000 Office 365 E3-Lizenzen und 8500 Microsoft 365 E5 verfügen, für insgesamt 11.500 Lizenzen aus den qualifizierenden Produkten.
- Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.

> [!NOTE]
> Sie können bis zu 250 Prioritätskonten überwachen.

### <a name="add-priority-accounts-from-the-setup-page"></a>Hinzufügen von Prioritätskonten von der Seite "Setup"

Fügen Sie auf der Seite **Setup Prioritätskonten hinzu.**

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie **zu**  >  **Setup-Organisationswissen,** und wählen **Sie Anzeigen** unter Überwachen Ihrer wichtigsten **Konten aus.**

3. Wählen **Sie Erste Schritte** oder Verwalten **aus.**

4. Geben Sie **auf** der Seite Prioritätskonten hinzufügen im Suchfeld den Namen oder die E-Mail-Adresse der Person ein, die Sie der Liste prioritätskonten hinzufügen möchten. Sie können auch Ihren E-Mail-Schwellenwert für fehlgeschlagene oder verzögerte E-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritätskonten erhalten.

5. Wählen Sie den Benutzer aus, und wählen Sie **Speichern aus.**

Sie können auch Prioritätskonten auf der Seite Aktive Benutzer hinzufügen.

### <a name="add-priority-accounts-from-active-users-page"></a>Hinzufügen von Prioritätskonten von der Seite Aktive Benutzer

Fügen Sie auf der Seite Aktive Benutzer Prioritätskonten hinzu.

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Wechseln Sie **zu Benutzer**  >  **Aktive Benutzer,** und wählen Sie **oben** auf der Seite ... aus. Wählen **Sie Verwalten von Prioritätskonten aus.**

3. Wählen **Sie Konten** hinzufügen  aus, und geben Sie auf der Seite Prioritätskonten hinzufügen im Suchfeld den Namen der Person ein, die Sie der Liste prioritätskonten hinzufügen möchten.

4. Wählen Sie den Benutzer aus, und wählen Sie **Speichern aus.**

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Entfernen eines Benutzers aus der Liste der Prioritätskonten

1. Wechseln Sie zum Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie **zu**  >  **Setup-Organisationswissen,** und wählen **Sie Anzeigen** unter Überwachen Ihrer wichtigsten **Konten aus.**

3. Wählen Sie **auf der Seite** Ihre meisten Konten überwachen die Option **Prioritätskonten** unter **Verwalten dieses Features aus.**

4. Wählen Sie **auf der** Seite Prioritätskonten den Benutzer aus, den Sie aus der Liste entfernen möchten, und wählen Sie Konten **entfernen aus.**

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Prioritätskonten in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)