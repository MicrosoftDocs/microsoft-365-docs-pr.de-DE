---
title: Einblick in den Identitätswechsel
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
description: Administratoren können erfahren, wie der Identitätswechsel-Einblick funktioniert. Sie können schnell ermitteln, welche Absender E-Mails von Domänen, die keine E-Mail-Authentifizierungsprüfungen bestehen (SPF, DKIM oder DMARC), legitimerweise an ihre Organisationen senden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 53baecd100851eb5ab05fe79751961baef3acd5c
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029669"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Identitätswechsel-Einblick in Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Die in diesem Artikel beschriebenen Features befinden sich in der Vorschau, können geändert werden und sind nicht in allen Organisationen verfügbar.

Der Identitätswechsel ist der Ort, an dem der Absender einer E-Mail-Nachricht einer echten oder erwarteten Absender-E-Mail-Adresse sehr ähnlich aussieht. Angreifer haben häufig die Identität von Absender-E-Mail-Adressen in Phishing- oder anderen Arten von Angriffen angenommen, um das Vertrauen des Empfängers zu gewinnen. Es gibt im Wesentlichen zwei Arten von Identitätswechsel:

- **Domänenidentitätswechsel:** Anstelle von lila@contoso.com wird die E-Mail-Adresse des imitierten Absenders lila@ćóntoso.com.
- **Benutzeridentitätswechsel:** Anstelle von michelle@contoso.com wird die E-Mail-Adresse des imitierten Absenders rnichell@contoso.com.

Der Domänenidentitätswechsel unterscheidet sich vom [Domänenspoofing,](anti-spoofing-protection.md)da die imitierte Domäne in der Regel eine echte registrierte Domäne ist. Nachrichten von Absendern in der imitierten Domäne können und bestehen häufig regelmäßige E-Mail-Authentifizierungsprüfungen, die andernfalls Spoofingversuche (SPF, DKIM und DMARC) identifizieren würden.

Der Identitätswechselschutz ist Teil der Antiphishingrichtlinieneinstellungen, die ausschließlich für Microsoft Defender für Office 365 gelten. Weitere Informationen zu diesen Einstellungen finden Sie unter [Identitätswechseleinstellungen in Antiphishingrichtlinien in Microsoft Defender für Office 365.](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

Sie können den Identitätswechsel-Einblick im Microsoft 365 Defender Portal verwenden, um Nachrichten von imitierten Absendern oder Absenderdomänen, die Sie für den Identitätswechselschutz konfiguriert haben, schnell zu identifizieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. Um direkt zum Identitätswechsel-Einblick auf der **Antiphishingseite** zu gelangen, verwenden Sie <https://security.microsoft.com/antiphishing> . Verwenden Sie die Folgendes, um direkt zur Seite **"Identitätswechsel-Einblick"** zu <https://security.microsoft.com/impersonationinsight> wechseln.

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Microsoft 365 Defender Portal Berechtigungen zugewiesen werden:
  - **Organisationsverwaltung**
  - **Sicherheitsadministrator**
  - **Sicherheitsleseberechtigter**
  - **Globaler Leser**

  Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)

  **Hinweis:** Das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center bietet Benutzern die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

- Sie aktivieren und konfigurieren den Identitätswechselschutz in Antiphishingrichtlinien in Microsoft Defender für Office 365. Der Identitätswechselschutz ist standardmäßig nicht aktiviert. Weitere Informationen finden Sie unter [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>Öffnen Sie den Identitätswechsel-Einblick im Microsoft 365 Defender Portal

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \>  \> **Regelbedrohungsrichtlinien** \>  im Abschnitt \> **"Antiphishing".**

2. Auf der **Antiphishingseite** sieht der Identitätswechsel-Einblick wie folgt aus:

   ![Einblick in Identitätswechsel und Spoofing auf der Seite "Antiphishingrichtlinie"](../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png)

   Der Einblick hat zwei Modi:

    - **Insight-Modus:** Wenn der Identitätswechselschutz in antiphishing-Richtlinien aktiviert und konfiguriert ist, zeigt der Einblick die Anzahl der erkannten Nachrichten von imitierten Domänen und imitierten Benutzern (Absendern) in den letzten sieben Tagen an. Dies ist die Summe aller erkannten Absender mit Identitätswechsel aus allen Antiphishingrichtlinien.
    - **Was wäre, wenn der Modus**: Wenn der Identitätswechselschutz in aktiven Antiphishingrichtlinien nicht aktiviert und konfiguriert ist, zeigt ihnen der Einblick, wie viele Nachrichten von unseren Identitätswechselschutzfunktionen in den letzten sieben Tagen erkannt worden *wären.*

Um Informationen zu den Identitätswechselerkennungen anzuzeigen, klicken Sie im Identitätswechsel-Insight auf **"Identitätswechsel anzeigen".**

   > [!NOTE]
   > Informationen zum Einblick in die Spoofintelligenz finden Sie unter [Spoof Intelligence Insight in EOP.](learn-about-spoof-intelligence.md)

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>Anzeigen von Informationen zu Nachrichten von Absendern in imitierten Domänen

Überprüfen Sie auf der Seite **"Identitätswechseleinblick",** die angezeigt wird, nachdem Sie im Identitätswechsel-Insight auf **"Identitätswechsel** anzeigen" geklickt haben, ob die Registerkarte **"Domänen"** ausgewählt ist. Die Registerkarte **"Domänen"** enthält die folgenden Informationen:

- **Absenderdomäne:** Die Identität der Domäne, bei der es sich um die Domäne handelt, die zum Senden der E-Mail-Nachricht verwendet wurde.
- **Nachrichtenanzahl:** Die Anzahl der Nachrichten, die in den letzten 7 Tagen vom Identitätswechsel der Absenderdomäne stammen.
- **Identitätswechseltyp:** Dieser Wert zeigt den erkannten Speicherort des Identitätswechsels an (z. B. **Domäne in Adresse).**
- **Imitierte Domäne(n):** Die imitierte Domäne, die der Domäne, die für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert ist, sehr ähnlich sein sollte.
- **Domänentyp:** Dieser Wert ist **"Unternehmensdomäne"** für interne Domänen oder **"Benutzerdefinierte Domäne"** für benutzerdefinierte Domänen.
- **Richtlinie:** Die Antiphishingrichtlinie, die die imitierte Domäne erkannt hat.
- **Identitätswechsel zulässig:** Einer der folgenden Werte:
  - **Ja:** Die Domäne wurde in der Antiphishingrichtlinie als vertrauenswürdige Domäne (eine Ausnahme für identitätswechselschutz) konfiguriert. Nachrichten von Absendern in der imitierten Domäne wurden erkannt, aber zulässig.
  - **Nein:** Die Domäne wurde für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert. Nachrichten von Absendern in der imitierten Domäne wurden basierend auf der Aktion für imitierte Domänen in der Antiphishingrichtlinie erkannt und ausgeführt.

Sie können auf ausgewählte Spaltenüberschriften klicken, um die Ergebnisse zu sortieren.

Um die Ergebnisse zu filtern, können Sie das ![ ](../../media/m365-cc-sc-search-icon.png) **Suchsymbol-Suchfeld** verwenden, um eine durch Trennzeichen getrennte Liste von Werten einzugeben, um die Ergebnisse zu filtern.

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>Anzeigen von Details zu Nachrichten von Absendern in imitierten Domänen

Wählen Sie auf der Registerkarte **"Domänen"** auf der Seite **"Identitätswechsel-Einblick"** eine der verfügbaren Identitätswechselerkennungen aus. Das angezeigte Detail-Flyout enthält die folgenden Informationen und Features:

- **Auswahlidentitätswechselrichtlinie, die geändert werden soll:** Wählen Sie die betroffene Antiphishingrichtlinie aus, die Sie ändern möchten. Nur Richtlinien, bei denen die imitierte Domäne in der Richtlinie definiert ist, sind verfügbar. Auf der vorherigen Seite finden Sie Informationen dazu, welche Richtlinie tatsächlich für die Erkennung der imitierten Domäne verantwortlich war (wahrscheinlich basierend auf dem Empfänger und der Priorität der Richtlinie).
- **Zur Liste der zulässigen Identitätswechsel** hinzufügen: Verwenden Sie diese Umschaltfläche, um den Absender zu den **vertrauenswürdigen Absendern und Domänen** (Identitätswechsel-Ausnahmen) für die von Ihnen ausgewählte Antiphishingrichtlinie hinzuzufügen oder daraus zu entfernen:
  - Wenn der Wert **Zulässig zum Imitieren** für diesen Eintrag **Nein** lautet, ist die Umschaltfläche deaktiviert. Um alle Absender in dieser Domäne von der Auswertung durch Identitätswechselschutz auszunehmen, ziehen Sie die Umschaltfläche ein: ![ Umschalten ](../../media/scc-toggle-on.png) ein. Die Domäne wird der Liste **der vertrauenswürdigen Domänen** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie hinzugefügt.
  - Wenn der Wert **Zulässiger Imitieren** für diesen Eintrag **Ja** lautet, ist die Umschaltfläche aktiviert. Um alle Absender in dieser Domäne an die Auswertung durch Identitätswechselschutz zurückzugeben, ziehen Sie die Umschaltfläche auf "Aus": ![ Umschalten ](../../media/scc-toggle-off.png) aus. Die Domäne wird aus der Liste **der vertrauenswürdigen Domänen** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie entfernt.
- Warum wir dies abgefangen haben.
- Was Sie tun müssen.
- Eine Domänenzusammenfassung, die die imitierte Domäne auflistet.
- WhoIs-Daten über den Absender.
- Ein Link zum Öffnen [des Bedrohungs-Explorers,](threat-explorer.md) um weitere Details zum Absender anzuzeigen.
- Ähnliche Nachrichten vom gleichen Absender, die an Ihre Organisation übermittelt wurden.

## <a name="view-information-about-messages-from-impersonated-senders"></a>Anzeigen von Informationen zu Nachrichten von imitierten Absendern

Klicken Sie auf der Seite **"Identitätswechsel-Einblick",** die angezeigt wird, nachdem Sie im Identitätswechsel-Insight auf **"Identitätswechsel"** geklickt haben, auf die Registerkarte **"Benutzer".** Die Registerkarte **"Benutzer"** enthält die folgenden Informationen:

- **Absender:** Die E-Mail-Adresse des Absenders, der die E-Mail gesendet hat.
- **Nachrichtenanzahl:** Die Anzahl der Nachrichten vom Absender, der die Identität angenommen hat, in den letzten 7 Tagen.
- **Identitätswechseltyp:** Dieser Wert ist **"Benutzer im Anzeigenamen".**
- **Angenommene Benutzer:** Die E-Mail-Adresse des imitierten Absenders, die dem Benutzer, der für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert ist, sehr ähnlich sein sollte.
- **Benutzertyp:** Dieser Wert zeigt die Art des angewendeten Schutzes an (z. B. **geschützter Benutzer** oder **Mailbox Intelligence).**
- **Richtlinie:** Die Antiphishingrichtlinie, die den imitierten Absender erkannt hat.
- **Identitätswechsel zulässig:** Einer der folgenden Werte:
  - **Ja:** Der Absender wurde in der Antiphishingrichtlinie als vertrauenswürdiger Benutzer (eine Ausnahme für identitätswechselschutz) konfiguriert. Nachrichten vom imitierten Absender wurden erkannt, aber zulässig.
  - **Nein:** Der Absender wurde für den Identitätswechselschutz in der Antiphishingrichtlinie konfiguriert. Nachrichten des imitierten Absenders wurden basierend auf der Aktion für imitierte Benutzer in der Antiphishingrichtlinie erkannt und darauf reagiert.

Sie können auf ausgewählte Spaltenüberschriften klicken, um die Ergebnisse zu sortieren.

Um die Ergebnisse zu filtern, können Sie das **Feld Absender filtern** verwenden, um eine durch Kommas getrennte Liste von Werten zum Filtern der Ergebnisse einzugeben.

### <a name="view-details-about-messages-from-impersonated-senders"></a>Anzeigen von Details zu Nachrichten von imitierten Absendern

Wählen Sie auf der Registerkarte **"Benutzer"** auf der Seite **"Identitätswechsel-Einblick"** eine der verfügbaren Identitätswechselerkennungen aus. Das angezeigte Detail-Flyout enthält die folgenden Informationen und Features:

- **Auswahlidentitätswechselrichtlinie, die geändert werden soll:** Wählen Sie die betroffene Antiphishingrichtlinie aus, die Sie ändern möchten. Nur Richtlinien, bei denen der imitierte Absender in der Richtlinie definiert ist, sind verfügbar. Auf der vorherigen Seite finden Sie Informationen dazu, welche Richtlinie tatsächlich für die Erkennung des imitierten Absenders verantwortlich war (wahrscheinlich basierend auf dem Empfänger und der Priorität der Richtlinie).
- **Zur Liste der zulässigen Identitätswechsel** hinzufügen: Verwenden Sie diese Umschaltfläche, um den Absender zu den **vertrauenswürdigen Absendern und Domänen** (Identitätswechsel-Ausnahmen) für die von Ihnen ausgewählte Antiphishingrichtlinie hinzuzufügen oder daraus zu entfernen:
  - Wenn der Wert **Zulässig zum Imitieren** für diesen Eintrag **Nein** lautet, ist die Umschaltfläche deaktiviert. Um den Absender von der Auswertung durch Identitätswechselschutz auszunehmen, ziehen Sie die Umschaltfläche ein: ![ Umschalten ](../../media/scc-toggle-on.png) ein. Der Absender wird der Liste **der vertrauenswürdigen Benutzer** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie hinzugefügt.
  - Wenn der Wert **Zulässiger Imitieren** für diesen Eintrag **Ja** lautet, ist die Umschaltfläche aktiviert. Um den Absender durch Identitätswechselschutz zur Auswertung zurückzugeben, ziehen Sie die Umschaltfläche auf ![ "Aus": Umschalten ](../../media/scc-toggle-off.png) aus. Der Absender wird aus der Liste der **vertrauenswürdigen Benutzer** in den Identitätswechselschutzeinstellungen der Antiphishingrichtlinie entfernt.
- Warum wir dies abgefangen haben.
- Was Sie tun müssen.
- Eine Absenderzusammenfassung, die den imitierten Absender auflistet.
- WhoIs-Daten über den Absender.
- Ein Link zum Öffnen [des Bedrohungs-Explorers,](threat-explorer.md) um weitere Details zum Absender anzuzeigen.
- Ähnliche Nachrichten vom gleichen Absender, die an Ihre Organisation übermittelt wurden.
