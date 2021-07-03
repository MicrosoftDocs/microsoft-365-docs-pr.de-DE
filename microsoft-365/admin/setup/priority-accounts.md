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
ms.openlocfilehash: 86e01e591823c94d8279f975ed7de24cc65776dc
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53286141"
---
# <a name="manage-and-monitor-priority-accounts"></a>Verwalten und Überwachen von Prioritätskonten

In jeder Microsoft 365 Organisation gibt es Personen, die wichtig sind, z. B. Führungskräfte, Führungskräfte, Manager oder andere Benutzer, die Zugriff auf vertrauliche, proprietäre oder Informationen mit hoher Priorität haben.

Um Ihre Organisation beim Schutz dieser Konten zu unterstützen, können Sie jetzt bestimmte Benutzer als Prioritätskonten festlegen und app-spezifische Features nutzen, die ihnen zusätzlichen Schutz bieten. In Zukunft werden weitere Apps und Features Prioritätskonten unterstützen. Zunächst haben wir zwei Funktionen angekündigt: **den Schutz von Prioritätskonten** und die Überwachung des **Premium-E-Mail-Flusses.**

- **Prioritätskontoschutz** – Microsoft Defender für Office 365 (früher Office 365 Advanced Threat Protection) unterstützt Prioritätskonten als Tags, die in Filtern in Warnungen, Berichten und Untersuchungen verwendet werden können. Weitere Informationen finden Sie [unter "Benutzertags" in Microsoft Defender für Office 365.](../../security/office-365-security/user-tags.md)

  Eine natürliche Frage lautet: "Haben nicht alle Benutzer Priorität? Warum nicht alle Benutzer als Prioritätskonten festlegen?" Ja, alle Benutzer haben Priorität, aber der Prioritätskontoschutz bietet die folgenden zusätzlichen Vorteile:

  - **Zusätzliche Heuristiken:** Unsere Analyse des Nachrichtenflusses in den Microsoft-Rechenzentren weist darauf hin, dass sich die Nachrichtenflussmuster für Führungskräfte in Unternehmen von den durchschnittlichen Mitarbeitern unterscheiden. Der Schutz vor Prioritätskonten bietet zusätzliche Heuristiken, die speziell auf Führungskräfte des Unternehmens zugeschnitten sind, die keinem regulären Mitarbeiter vorteilen.
  - **Zusätzliche Sichtbarkeit in der Berichterstellung:** Tatsächlich sind Informationen für alle Benutzer (oder alle betroffenen Benutzer) bereits in Warnungen, Berichten und Untersuchungen verfügbar. Mit dem Tag "Prioritätskonten" als Filter können Sie ihre Untersuchungen gezielt ausrichten.

- **Premium E-Mail-Flow-Überwachung** : Ein fehlerfreier Nachrichtenfluss kann für den Geschäftserfolg von entscheidender Bedeutung sein, und Übermittlungsverzögerungen oder -fehler können sich negativ auf das Unternehmen auswirken. Sie können einen Schwellenwert für fehlgeschlagene oder verzögerte E-Mails auswählen, Benachrichtigungen empfangen, wenn dieser Schwellenwert überschritten wird, und einen Bericht über E-Mail-Probleme für Prioritätskonten anzeigen. Weitere Informationen finden Sie [im Bericht "E-Mail-Probleme bei Prioritätskonten" im modernen EAC.](/exchange/monitoring/mail-flow-reports/mfr-email-issues-for-priority-accounts-report)

Bewährte Methoden für die Sicherheit von Prioritätskonten finden Sie unter ["Sicherheitsempfehlungen für Prioritätskonten".](../../security/office-365-security/security-recommendations-for-priority-accounts.md)

## <a name="before-you-begin"></a>Bevor Sie beginnen

Das in diesem Thema beschriebene Feature zum Schutz von **Prioritätskonten** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:

- Microsoft Defender für Office 365 Plan 2, einschließlich derjenigen mit Office 365 E3, Office 365 E5, Microsoft 365 E5 oder Microsoft 365 E5 Security.

Das in diesem Thema beschriebene Feature Premium Überwachung von **E-Mail-Flow** ist nur für Organisationen verfügbar, die die folgenden Anforderungen erfüllen:

- Ihre Organisation muss über eine Lizenzanzahl von mindestens 5.000 aus einem der folgenden Produkte oder einer Kombination der folgenden Produkte verfügen: Office 365 E3, Microsoft 365 E3, Office 365 E5 Microsoft 365 E5. So kann Ihre Organisation beispielsweise über 3000 Office 365 E3-Lizenzen und 2500 Microsoft 365 E5-Lizenzen verfügen, die insgesamt 5500 Lizenzen für berechtigende Produkte ergeben.
- Ihre Organisation muss über mindestens 50 monatlich aktive Exchange Online-Benutzer verfügen.

> [!NOTE]
> Sie können bis zu 250 Prioritätskonten überwachen.

Wenn Sie den Prioritätskontoschutz auf ein Postfach anwenden, sollten Sie den Prioritätskontoschutz auch auf Benutzer anwenden, die Zugriff auf das Postfach haben (z. B. der CEO und der Assistent des CEO, der den Kalender des CEO verwaltet).

### <a name="add-priority-accounts-from-the-setup-page"></a>Hinzufügen von Prioritätskonten von der Setupseite

Hinzufügen von Prioritätskonten von der **Setupseite.**

1. Wechseln Sie zu der Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie zu   >  **"Organisationswissen** einrichten", und wählen Sie **"Anzeigen"** unter **"Ihre wichtigsten Konten überwachen"** aus.

3. Wählen Sie **Erste Schritte** oder **verwalten aus.**

4. Geben Sie auf der Seite **"Prioritätskonten hinzufügen"** im Suchfeld den Namen oder die E-Mail-Adresse der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten. Sie können auch Ihren E-Mail-Schwellenwert für fehlgeschlagene oder verzögerte E-Mails festlegen und einen wöchentlichen Bericht über Probleme für Prioritätskonten erhalten.

5. Wählen Sie den Benutzer aus, und wählen Sie **"Speichern"** aus.

Sie können auch Prioritätskonten auf der Seite "Aktive Benutzer" hinzufügen.

### <a name="add-priority-accounts-from-active-users-page"></a>Hinzufügen von Prioritätskonten von der Seite "Aktive Benutzer"

Hinzufügen von Prioritätskonten auf der Seite "Aktive Benutzer".

1. Wechseln Sie zum Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>.

2. Wechseln Sie zu   >  **"Aktive Benutzer",** und wählen Sie die drei Punkte (weitere Aktionen) oben auf der Seite aus. Wählen Sie **"Prioritätskonten verwalten" aus.**

3. Wählen Sie **"Konten hinzufügen"** aus, und geben Sie auf der Seite **"Prioritätskonten hinzufügen"** im Suchfeld den Namen der Person ein, die Sie der Liste der Prioritätskonten hinzufügen möchten.

4. Wählen Sie den Benutzer aus, und wählen Sie **"Speichern"** aus.

## <a name="remove-a-user-from-the-priority-accounts-list"></a>Entfernen eines Benutzers aus der Liste der Prioritätskonten

1. Wechseln Sie zu der Microsoft 365 Admin Center unter <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> .

2. Wechseln Sie zu   >  **"Organisationswissen** einrichten", und wählen Sie **"Anzeigen"** unter **"Ihre wichtigsten Konten überwachen"** aus.

3. Wählen Sie auf der Seite **"Ihre meisten Konten überwachen"** unter **"Dieses Feature verwalten"** die Option **"Prioritätskonten"** aus.

4. Wählen Sie auf der Seite **"Prioritätskonten"** den Benutzer aus, den Sie aus der Liste entfernen möchten, und wählen Sie **"Konten entfernen"** aus.

## <a name="related-topics"></a>Verwandte Themen

[Verwenden von Prioritätskonten in Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/using-priority-accounts-in-microsoft-365/ba-p/1873314)
