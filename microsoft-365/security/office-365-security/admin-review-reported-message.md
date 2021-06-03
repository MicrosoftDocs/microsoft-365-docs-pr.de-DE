---
title: Administratorüberprüfung für gemeldete Nachrichten
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie gemeldete Nachrichten überprüfen und Ihren Benutzern Feedback geben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 619cd35b6a60f0d50aa6c13e4cad2b8d7ae947a8
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730964"
---
# <a name="admin-review-for-reported-messages"></a>Administratorüberprüfung für gemeldete Nachrichten

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das möglicherweise erheblich geändert wird, bevor es kommerziell veröffentlicht wird. Dieses Dokument wird nur zu Evaluierungs- und Explorationszwecken bereitgestellt.

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern und Microsoft Defender für Office 365 können Administratoren nun vorlagenierte Nachrichten zurück an Endbenutzer senden, nachdem sie die gemeldeten Nachrichten überprüft haben. Dies kann für Ihre Organisation und auch basierend auf dem Urteil Ihres Admins angepasst werden.

Dieses Feature dient dazu, Ihren Benutzern Feedback zu geben, ändert jedoch nicht die Bewertungen von Nachrichten im System. Um Microsoft dabei zu unterstützen, seine Filter zu aktualisieren und zu verbessern, müssen Sie Nachrichten mithilfe der Admin-Übermittlung zur [Analyse übermitteln.](admin-submission.md)

Sie können Die Benutzer nur dann über Die Ergebnisse der Überprüfung markieren und benachrichtigen, wenn die Nachricht als falsch positive oder falsch negative Ergebnisse [gemeldet wurde.](report-false-positives-and-false-negatives.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Zum Ändern der Konfiguration für Benutzerübermittlungen müssen Sie Mitglied einer der folgenden Rollengruppen sein:
    - Organisationsverwaltung oder Sicherheitsadministrator im [Security Center](permissions-microsoft-365-compliance-security.md).
    - Organisationsverwaltung in [Exchange Online](/Exchange/permissions-exo/permissions-exo).

- Sie benötigen auch Zugriff auf die Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, wird eine Fehlermeldung mit der Angabe einer E-Mail-Adresse in Ihrer Domäne *angezeigt.* Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:
    - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
    - [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Konfigurieren der Nachrichten, die zum Benachrichtigen von Benutzern verwendet werden

1. Wechseln Sie [Microsoft 365 Security Center](../defender/overview-security-center.md)zu Richtlinien **&** Regeln \> **Bedrohungsrichtlinien** Vom Benutzer \> **gemeldete Nachrichteneinstellungen**.

2. Wenn Sie den Anzeigenamen des Absenders angeben möchten, aktivieren Sie das Kontrollkästchen **Office 365** E-Mail-Adresse angeben, die als Absender verwendet werden soll, im Abschnitt **E-Mail-Benachrichtigungen** für Administratorüberprüfungsergebnisse, und geben Sie den Namen ein, den Sie verwenden möchten. Dies ist die E-Mail-Adresse, die in Outlook angezeigt wird und an die Antworten gehen.

3. Wenn Sie eine der Vorlagen anpassen möchten, klicken Sie auf **E-Mail-Benachrichtigung anpassen.** In diesem Flyout können Sie nur Folgendes anpassen:
    - Phishing
    - Junk-E-Mail
    - Keine Bedrohungen gefunden
    - Sensibilisierungstraining
    - Fußzeile

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Klicken Sie auf der Seite Benutzerübermittlungen **auf Verwerfen,** um diese Werte zu löschen.
