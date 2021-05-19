---
title: Identitätswechsel-Einblick
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie die Identitätswechsel-Einblicke funktionieren. Sie können schnell ermitteln, welche Absender E-Mails rechtmäßig von Domänen an ihre Organisationen senden, die keine E-Mail-Authentifizierungsprüfungen bestehen (SPF, DKIM oder DMARC).
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a11dd30030ccce886abd50ff72b5a09b10938ece
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52535768"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Identitätswechsel-Einblick in Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.

Der Identitätswechsel ist der Ort, an dem der Absender einer E-Mail-Nachricht einer echten oder erwarteten Absender-E-Mail-Adresse sehr ähnlich sieht. Angreifer haben sich häufig als Absender-E-Mail-Adressen bei Phishing oder anderen Arten von Angriffen als Absender bezeichnet, um das Vertrauen des Empfängers zu gewinnen. Es gibt im Wesentlichen zwei Arten von Identitätswechsel:

- **Domänenwechsel:** Anstelle lila@contoso.com wird die E-Mail-Adresse des imitierten Absenders lila@ćóntoso.com.
- **Benutzerwechsel:** Anstelle michelle@contoso.com wird die E-Mail-Adresse des imitierten Absenders rnichell@contoso.com.

Domänenwechsel unterscheiden sich von [Domänens spoofing,](anti-spoofing-protection.md)da die imitierte Domäne in der Regel eine echte, registrierte Domäne ist. Nachrichten von Absendern in der imitierten Domäne können und häufig regelmäßige E-Mail-Authentifizierungsprüfungen bestehen, die spoofing attempts (SPF, DKIM und DMARC) identifizieren würden.

Identitätswechselschutz ist Teil der Antiphishingrichtlinieneinstellungen), die für Microsoft Defender exklusiv für Office 365. Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365).

Sie können die Identitätswechsel-Einblicke verwenden, um Nachrichten von identitätsidentierten Absendern oder Absenderdomänen, die Sie für den Identitätswechselschutz konfiguriert haben, schnell zu identifizieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zu der Identitätswechsel-Einsicht auf der **Seite "Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - **Organisationsverwaltung**
  - **Sicherheitsadministrator**
  - **Security Reader**
  - **Globaler Leser**

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweis**: Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Security & Compliance _Center_ und Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Sie aktivieren und konfigurieren identitätswechselschutz in Antiphishingrichtlinien in Microsoft Defender für Office 365. Identitätswechselschutz ist standardmäßig nicht aktiviert. Weitere Informationen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="open-the-impersonation-insight-in-the-security--compliance-center"></a>Öffnen Sie die Identitätswechsel-Einblicke im Security & Compliance Center

1. Wechseln Sie im Security & Compliance Center zu Richtlinie für die **Bedrohungsverwaltung** \>  \> **Antiphishing**.

2. Auf der **Hauptseite antiphishing sieht** die Identitätswechsel-Einsicht wie dies aus:

   Diese Einsicht hat zwei Modi:

    - **Einblicksmodus:** Wenn der Identitätswechselschutz in Antiphishingrichtlinien aktiviert und konfiguriert ist, zeigt die Einblicke die Anzahl der erkannten Nachrichten von identitätswechselfähigen Absendern in den letzten sieben Tagen an. Dies ist die Gesamtzahl aller erkannten identitätswechselten Absender aus allen Antiphishingrichtlinien.
    - **Was wäre,** wenn Modus : Wenn der Identitätswechselschutz in aktiven Antiphishingrichtlinien nicht  aktiviert und konfiguriert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Identitätswechselschutzfunktionen erkannt wurden.

   So oder so zeigt **domänenimitierte** Domänen die Anzahl der  Nachrichten von Absendern in geschützten Domänen an, während Benutzer mit Identitätswechsel die Anzahl der Nachrichten von geschützten Benutzern anzeigen.

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Anzeigen von Informationen zu Nachrichten von Absendern in Identitätswechseldomänen

Klicken Sie in der Identitätswechsel-Einsicht auf **Domänen imitiert**. Die **geöffnete Impersonation Insight-Seite** enthält die folgenden Informationen:

- **Absenderdomäne**: Die Identitätswechseldomäne, bei der es sich um die Domäne handelt, die zum Senden der E-Mail-Nachricht verwendet wurde. 
- **Anzahl der** Nachrichten: Die Anzahl der Nachrichten, die in den letzten 7 Tagen den Identitätswechsel der Absenderdomäne nach sich selbst gesendet haben.
- **Identitätswechseltyp**: Dieser Wert zeigt den erkannten Speicherort des Identitätswechsels an (z. B. **Domäne in Adresse**).
- **Imitierte** Domäne: Die domäne mit identitätswechseln, die der Domäne ähneln sollte, die für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert ist.
- **Domänentyp:** Dieser Wert ist **Unternehmensdomäne** für interne Domänen oder **Benutzerdefinierte Domäne für** benutzerdefinierte Domänen.
- **Richtlinie**: Die Antiphishingrichtlinie, die die identitätswechselte Domäne erkannt hat.
- **Zulässiger Identitätswechsel:** Einer der folgenden Werte:
  - **Ja**: Die Domäne wurde in der Antispamrichtlinie als vertrauenswürdige Domäne (eine Ausnahme für identitätswechselschutz) konfiguriert. Nachrichten von Absendern in der identitätswechselten Domäne wurden erkannt, aber zulässig.
  - **Nein:** Die Domäne wurde für den Identitätswechselschutz in der Antispamrichtlinie konfiguriert. Nachrichten von Absendern in der imitierten Domäne wurden erkannt und basierend auf der Aktion für Identitätswechseldomänen in der Antispamrichtlinie behandelt.

Sie können auf ausgewählte Spaltenüberschriften klicken, um die Ergebnisse zu sortieren.

Zum Filtern der Ergebnisse können  Sie das Feld Domäne filtern verwenden, um eine durch Kommas getrennte Liste von Werten ein, um die Ergebnisse zu filtern.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Anzeigen von Details zu Nachrichten von Absendern in Identitätswechseldomänen

Wählen Sie **auf der Seite Identitätswechsel-Einblick** eine der verfügbaren Zeilen aus. Das angezeigte Details-Flyout enthält die folgenden Informationen und Features:

- **Zu ändernde Auswahlwechselrichtlinie:** Wählen Sie die betroffene Antiphishingrichtlinie aus, die Sie ändern möchten. Es stehen nur Richtlinien zur Verfügung, bei denen die identitätswechselte Domäne in der Richtlinie definiert ist. Lesen Sie auf der vorherigen Seite, welche Richtlinie tatsächlich für die Erkennung der identitätswechselten Domäne verantwortlich war (wahrscheinlich basierend auf dem Empfänger und der Priorität der Richtlinie).

- **Zur Liste** zugelassener Identitätswechsel hinzufügen: Verwenden Sie diese Umschaltschalte, um den Absender aus den vertrauenswürdigen Absendern und Domänen (Identitätswechselausnahmen) für die von Ihnen ausgewählte Antiphishingrichtlinie hinzuzufügen oder zu entfernen: 
  - Wenn der **Wert für den Identitätswechsel für** diesen Eintrag **"Nein"** war, ist der Umschalter deaktiviert. Um alle Absender in dieser Domäne von der Auswertung durch Identitätswechselschutz aus dem Weg zu lassen, verschieben Sie den Umschalter auf ein: ![ Umschalten auf ](../../media/scc-toggle-on.png) . Die Domäne wird der Liste **Vertrauenswürdige Domänen** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie hinzugefügt.
  - Wenn der **Wert Für den Identitätswechsel zulässiger** Wert für diesen Eintrag **Ja** war, ist der Umschalter an. Um alle Absender in dieser Domäne zur Auswertung durch Identitätswechselschutz zurückzukehren, verschieben Sie den Umschalter auf off: ![ Umschalten ](../../media/scc-toggle-off.png) aus . Die Domäne wird  in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie aus der Liste Vertrauenswürdige Domänen entfernt.

- Warum wir dies erwischt haben.
- Was Sie tun müssen.
- Eine Domänenzusammenfassung, in der die identitätswechselte Domäne aufgeführt ist.
- WhoIs-Daten über den Absender.
- Ein Link zum Öffnen des [Bedrohungs-Explorers,](threat-explorer.md) um weitere Details zum Absender anzuzeigen.
- Ähnliche Nachrichten vom gleichen Absender, die an Ihre Organisation zugestellt wurden.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Anzeigen von Informationen zu Nachrichten von identitätswechselten Absendern

Klicken Sie in der Identitätswechsel-Einsicht auf **Benutzer imitiert**. Die **geöffnete Impersonation Insight-Seite** enthält die folgenden Informationen:

- **Sender**: Die E-Mail-Adresse des Absenders, der die E-Mail-Nachricht gesendet hat.
- **Anzahl der** Nachrichten : Die Anzahl der Nachrichten vom Absender, der den Identitätswechsel in den letzten 7 Tagen vornimmt.
- **Identitätswechseltyp:** Dieser Wert ist **Benutzer im Anzeigenamen**.
- **Imitierte** Benutzer: Die E-Mail-Adresse des imitierten Absenders, die dem Benutzer ähneln sollte, der für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert ist.
- **Benutzertyp**: Dieser Wert zeigt den Typ des angewendeten Schutzes an (z. B. geschützte **Benutzer-** oder **Postfachintelligenz**).
- **Richtlinie**: Die Antiphishingrichtlinie, die den identitätswechselten Absender erkannt hat.
- **Zulässiger Identitätswechsel:** Einer der folgenden Werte:
  - **Ja**: Der Absender wurde in der Antispamrichtlinie als vertrauenswürdiger Benutzer (eine Ausnahme für identitätswechselschutz) konfiguriert. Nachrichten vom identitätswechselten Absender wurden erkannt, aber zulässig.
  - **Nein:** Der Absender wurde für den Identitätswechselschutz in der Antispamrichtlinie konfiguriert. Nachrichten des identitätswechselten Absenders wurden erkannt und basierend auf der Aktion für imitierte Benutzer in der Antispamrichtlinie behandelt.

Sie können auf ausgewählte Spaltenüberschriften klicken, um die Ergebnisse zu sortieren.

Zum Filtern der Ergebnisse können  Sie das Feld Absender filtern verwenden, um eine durch Kommas getrennte Liste von Werten ein, um die Ergebnisse zu filtern.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Anzeigen von Details zu Nachrichten von identitätswechselten Absendern

Wählen Sie **auf der Seite Identitätswechsel-Einblick** eine der verfügbaren Zeilen aus. Das angezeigte Details-Flyout enthält die folgenden Informationen und Features:

- **Zu ändernde Auswahlwechselrichtlinie:** Wählen Sie die betroffene Antiphishingrichtlinie aus, die Sie ändern möchten. Es sind nur Richtlinien verfügbar, bei denen der identitätswechselte Absender in der Richtlinie definiert ist. Lesen Sie auf der vorherigen Seite, welche Richtlinie tatsächlich für die Erkennung des identitätswechselten Absenders verantwortlich war (wahrscheinlich basierend auf dem Empfänger und der Priorität der Richtlinie).

- **Zur Liste** zugelassener Identitätswechsel hinzufügen: Verwenden Sie diese Umschaltschalte, um den Absender aus den vertrauenswürdigen Absendern und Domänen (Identitätswechselausnahmen) für die von Ihnen ausgewählte Antiphishingrichtlinie hinzuzufügen oder zu entfernen: 
  - Wenn der **Wert für den Identitätswechsel für** diesen Eintrag **"Nein"** war, ist der Umschalter deaktiviert. Um den Absender von der Auswertung durch Identitätswechselschutz aus dem Weg zu lassen, verschieben Sie den Umschalter auf ein: ![ Umschalten auf ](../../media/scc-toggle-on.png) . Der Absender wird der Liste vertrauenswürdiger **Benutzer** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie hinzugefügt.
  - Wenn der **Wert Für den Identitätswechsel zulässiger** Wert für diesen Eintrag **Ja** war, ist der Umschalter an. Um den Absender durch Identitätswechselschutz zur Auswertung zurückzukehren, verschieben Sie den Umschalter nach aus: ![ Umschalten ](../../media/scc-toggle-off.png) aus . Der Absender wird  in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie aus der Liste vertrauenswürdiger Benutzer entfernt.

- Warum wir dies erwischt haben.
- Was Sie tun müssen.
- Eine Absenderzusammenfassung, die den identitätswechselten Absender auflistet.
- WhoIs-Daten über den Absender.
- Ein Link zum Öffnen des [Bedrohungs-Explorers,](threat-explorer.md) um weitere Details zum Absender anzuzeigen.
- Ähnliche Nachrichten vom gleichen Absender, die an Ihre Organisation zugestellt wurden.
