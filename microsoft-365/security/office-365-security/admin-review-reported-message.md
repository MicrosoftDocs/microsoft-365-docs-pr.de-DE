---
title: Überprüfung gemeldeter Nachrichten durch den Administrator
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
ms.openlocfilehash: a9fa6c890f0fa6098a2bb712f79ab82fc1edb68b
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108559"
---
# <a name="admin-review-for-reported-messages"></a>Überprüfung gemeldeter Nachrichten durch den Administrator

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> Die Informationen in diesem Artikel beziehen sich auf ein Vorschauprodukt, das vor der kommerziellen Veröffentlichung erheblich geändert werden kann. Dieses Dokument dient nur zu Evaluierungs- und Untersuchungszwecken.

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern und Microsoft Defender für Office 365 können Administratoren nun Nachrichten mit Vorlagen an Endbenutzer senden, nachdem sie gemeldete Nachrichten überprüft haben. Dies kann für Ihre Organisation angepasst werden und basiert auch auf der Bewertung Ihres Administrators.

Dieses Feature ist darauf ausgelegt, Ihren Benutzern Feedback zu geben, ändert jedoch nicht die Bewertung von Nachrichten im System. Um Microsoft bei der Aktualisierung und Verbesserung seiner Filter zu unterstützen, müssen Sie Nachrichten mithilfe der [Administratorübermittlung](admin-submission.md)zur Analyse übermitteln.

Sie können Benutzer nur dann markieren und über Rezensionsergebnisse informieren, wenn die Nachricht als [falsch positive oder falsch negative](report-false-positives-and-false-negatives.md)Ergebnisse gemeldet wurde.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .

- Um die Konfiguration für Benutzerübermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:
  - Organisationsverwaltung oder Sicherheitsadministrator im [Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)
  - Organisationsverwaltung in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie benötigen auch Zugriff auf Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie einen Fehler, der besagt, dass *eine E-Mail-Adresse in Ihrer Domäne angegeben* wird. Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:
  - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a>Konfigurieren der Nachrichten, die zum Benachrichtigen von Benutzern verwendet werden

1. Wechseln Sie im portal Microsoft 365 Defender zu **E-Mail-& Zusammenarbeitsrichtlinien** & Seite \>  \> **"Richtlinien für Bedrohungsregeln"** im Abschnitt \>  \> **"Benutzer gemeldete Nachrichteneinstellungen".**

2. Wenn Sie auf der Seite **"Benutzerübermittlungen"** den Anzeigenamen des Absenders angeben möchten, aktivieren Sie das Kontrollkästchen für **"Angeben Office 365 E-Mail-Adresse als Absender"** unter dem Abschnitt **"E-Mail-Benachrichtigungen für Administratorüberprüfungsergebnisse",** und geben Sie den Namen ein, den Sie verwenden möchten. Dies ist die E-Mail-Adresse, die in Outlook angezeigt wird und an die Antworten gesendet werden.

3. Wenn Sie eine der Vorlagen anpassen möchten, klicken Sie auf **E-Mail-Benachrichtigung anpassen.** In diesem Flyout können Sie nur Folgendes anpassen:
    - Phishing
    - Junk-E-Mail
    - Keine Bedrohungen gefunden
    - Sensibilisierungsschulung
    - Fußzeile

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**. Um diese Werte zu löschen, klicken Sie auf der Seite "Benutzerübermittlungen" auf **"Verwerfen".**
