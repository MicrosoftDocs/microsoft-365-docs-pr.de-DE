---
title: Vom Benutzer gemeldete Nachrichteneinstellungen
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können erfahren, wie Sie ein Postfach konfigurieren, um Spam- und Phishing-E-Mails zu sammeln, die von Benutzern gemeldet werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2dded27d87ee5db0d1e71b643fe8244408ef1a24
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096156"
---
# <a name="user-reported-message-settings"></a>Vom Benutzer gemeldete Nachrichteneinstellungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Exchange Online Postfächern können Sie ein Postfach angeben, um Nachrichten zu empfangen, die Benutzer als bösartig oder nicht bösartig melden. Wenn Benutzer Nachrichten mit den verschiedenen Berichtsoptionen melden, können Sie dieses Postfach verwenden, um Nachrichten abzufangen (nur an das benutzerdefinierte Postfach senden) oder Kopien von Nachrichten zu empfangen (an das benutzerdefinierte Postfach und Microsoft senden). Dieses Feature funktioniert mit den folgenden Optionen für die Meldungsberichterstellung:

- [Das Add-In "Nachricht melden"](enable-the-report-message-add-in.md)
- [Das Add-In "Phishing melden"](enable-the-report-phish-add-in.md)
- [Berichterstellungstools von Drittanbietern](#third-party-reporting-tools)

Wenn Benutzer gemeldete Nachrichten an ein benutzerdefiniertes Postfach statt direkt an Microsoft übermitteln, können Ihre Administratoren Nachrichten mithilfe der Administratorübermittlung selektiv und manuell an Microsoft [melden.](admin-submission.md) Diese Einstellungen wurden früher als Benutzerübermittlungsrichtlinie bezeichnet.

  > [!NOTE]
  > Wenn die Berichterstellung [in Outlook im Web deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, überschreibt das Aktivieren von von Benutzern gemeldeten Nachrichten diese Einstellung und ermöglicht Es Benutzern, Nachrichten in Outlook im Web erneut zu melden.

## <a name="custom-mailbox-prerequisites"></a>Voraussetzungen für benutzerdefinierte Postfächer

Verwenden Sie die folgenden Artikel, um die erforderlichen Komponenten zu konfigurieren, damit vom Benutzer gemeldete Nachrichten an Ihr benutzerdefiniertes Postfach gesendet werden:

- Überspringen Sie die Spamfilterung für das benutzerdefinierte Postfach, indem Sie eine Exchange-Nachrichtenflussregel erstellen, um die Spamzustimmungsstufe festzulegen. Weitere Informationen finden Sie unter [Verwenden des EAC zum Erstellen einer Nachrichtenflussregel, die die SCL einer Nachricht so festlegt, dass](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl#use-the-eac-to-create-a-mail-flow-rule-that-sets-the-scl-of-a-message) die SCL auf **Spamfilterung umgeht.**

- [Erstellen Sie eine Tresor Attachments-Richtlinie,](set-up-safe-attachments-policies.md) die das benutzerdefinierte Postfach enthält, in dem Tresor Attachments Scanning deaktiviert ist (**Tresor Attachments unknown malware response** section \> **Off**).

- [Erstellen Sie eine Tresor Links-Richtlinie,](set-up-safe-links-policies.md) die das benutzerdefinierte Postfach enthält, in dem Tresor Links-Überprüfung deaktiviert ist (**Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichtenabschnitt** \> **"Aus").**

- [Erstellen Sie eine Antischadsoftwarerichtlinie,](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) die das benutzerdefinierte Postfach enthält, in dem die automatische Bereinigung zur Nullstunde (ZAP) für Schadsoftware deaktiviert ist ( Abschnitt **"Schutzeinstellungen** Aktivieren der \> **automatischen Bereinigung** zur Nullstunde für Schadsoftware" ist nicht ausgewählt).

- [Erstellen Sie eine Antispamrichtlinie,](configure-your-spam-filter-policies.md#use-the-microsoft-365-defender-portal-to-create-anti-spam-policies) die das benutzerdefinierte Postfach enthält, in dem ZAP für Spam und ZAP für Phishing deaktiviert sind (**Zero-Hour Auto Purge** Section \> **Enabled zero-hour auto purge (ZAP)** ist nicht ausgewählt).

- Deaktivieren Sie die Junk-E-Mail-Regel im benutzerdefinierten Postfach. Verwenden Sie ["Konfigurieren von Junk-E-Mail-Einstellungen für Exchange Online Postfächer",](configure-junk-email-settings-on-exo-mailboxes.md) um die Junk-E-Mail-Regel zu deaktivieren. Nachdem sie deaktiviert wurde, kann EOP Nachrichten basierend auf der Spamfilter-Bewertungsaktion **"Nachricht in Junk-E-Mail-Ordner** verschieben" oder der Safelist-Sammlung im Postfach nicht in den Junk-E-Mail-Ordner verschieben.

Nachdem Sie sichergestellt haben, dass Ihr Postfach alle anwendbaren Voraussetzungen erfüllt, können Sie die Verfahren in diesem Artikel verwenden, um das Postfach für Benutzerübermittlungen zu konfigurieren.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. Um direkt zur Seite **"Übermittlungen"** zu wechseln, verwenden Sie <https://security.microsoft.com/reportsubmission> .

- Um die Konfiguration für Benutzerübermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  - **Organisationsverwaltung** oder **Sicherheitsadministrator** in den [Berechtigungen im Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)
  - **Organisationsverwaltung** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).

- Sie benötigen Zugriff auf Exchange Online PowerShell. Wenn das Konto, das Sie verwenden möchten, keinen Zugriff auf Exchange Online PowerShell hat, erhalten Sie einen Fehler, der beim Angeben des Übermittlungspostfachs wie folgt aussieht:

  > Angeben einer E-Mail-Adresse in Ihrer Domäne

  Weitere Informationen zum Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell finden Sie in den folgenden Themen:

  - [Aktivieren oder Deaktivieren des Zugriffs auf Exchange Online PowerShell](/powershell/exchange/disable-access-to-exchange-online-powershell) 
  - [Clientzugriffsregeln in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="use-the-microsoft-365-defender-portal-to-configure-the-user-submissions-mailbox"></a>Verwenden des Microsoft 365 Defender-Portals zum Konfigurieren des Postfachs für Benutzerübermittlungen

1. Wechseln Sie im Microsoft 365 Defender Portal zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** \> **Andere** Abschnitt Benutzer gemeldet \> **Nachrichteneinstellungen** \> **Benutzerübermittlungen**.

2. Auf der Seite **"Benutzerübermittlungen"** wird die Anzeige davon bestimmt, ob die **Schaltfläche "Nachricht melden"** von Microsoft Outlook deaktiviert **oder** **eingeschaltet** ist:

   - **Schaltfläche "Nachricht** \> melden" in Microsoft Outlook **Einschalten** ![ Umschaltfläche: ](../../media/scc-toggle-on.png) Wählen Sie diese Option aus, wenn Sie das Add-In "Nachricht melden", das Add-In "Phishing melden" oder die integrierte Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:
     - **Senden Sie die gemeldeten Nachrichten an:** Wählen Sie eine der folgenden Optionen aus:
       - **Microsoft:** Das Postfach für Benutzerübermittlungen wird nicht verwendet (alle gemeldeten Nachrichten gehen an Microsoft).
       - **Microsoft und das Postfach meiner Organisation:** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Benutzerübermittlungen werden sowohl an Microsoft zur Analyse als auch an das benutzerdefinierte Postfach gesendet, das Ihr Administrator- oder Sicherheitsteam analysieren kann.
       - **Postfach meiner Organisation:** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein. Verteilergruppen sind nicht zulässig. Verwenden Sie diese Option, wenn die Nachricht nur zur Analyse an einen Administrator oder das Sicherheitsteam gesendet werden soll. Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet sie selbst weiter.

          > [!IMPORTANT]
          >
          > U.S. Government-Organisationen (GCC, GCC High und DoD) können nur das **Postfach meiner Organisation** konfigurieren. Die beiden anderen Optionen sind deaktiviert.
          >
          > Wenn Organisationen so konfiguriert sind, dass sie nur an ein benutzerdefiniertes Postfach senden, werden gemeldete Nachrichten nicht zur erneuten Überprüfung gesendet, und die Ergebnisse im Portal für vom Benutzer gemeldete Nachrichten sind immer leer.

       Unabhängig vom Wert, den Sie für **das Senden der gemeldeten Nachrichten** ausgewählt haben, sind die folgenden Einstellungen verfügbar:

       - **Zulassen, dass Benutzer auswählen, ob sie ihre Nachricht an Microsoft melden möchten**
       - **Wählen Sie Berichtsoptionen aus, die dem Benutzerbereich zur Verfügung stehen:** Wählen Sie mindestens eine der folgenden Optionen aus:
         - **Fragen Sie mich vor dem Senden der Nachricht**
         - **Nachricht immer melden**
         - **Nachricht niemals melden**

          > [!CAUTION]
          > Wenn Sie die [Junk-E-Mail-Berichterstellung in Outlook im Web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) mit Outlook im Web Postfachrichtlinien deaktiviert haben, Aber Sie eine der vorherigen Einstellungen zum Melden von Nachrichten an Microsoft konfiguriert haben, können Benutzer Nachrichten an Microsoft in Outlook im Web mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" an Microsoft melden.

     - **Abschnitt "Benutzeroberfläche für die Berichterstattung"**
       - **Vor der Registerkarte "Berichterstellung":** Geben Sie in die Felder **"Titel"** und **"Nachricht"** den beschreibenden Text ein, der benutzern angezeigt wird, bevor sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" melden. Sie können die Variable %type% verwenden, um den Übermittlungstyp (Junk, nicht Junk, Phishing usw.) einzuschließen.
       - **Nach der Registerkarte "Berichterstellung":** Geben Sie in die Meldungsfelder **"Titel"** und **"Bestätigung"** den beschreibenden Text ein, der benutzern angezeigt wird, nachdem sie eine Nachricht mithilfe des Add-Ins "Nachricht melden" oder des Add-Ins "Phishing melden" gemeldet haben. Sie können die Variable %type% verwenden, um den Übermittlungstyp einzuschließen.

       Wie auf der Seite gezeigt, wird der Benachrichtigung auch der folgende Text hinzugefügt, wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet:

          > Ihre E-Mail wird zur Analyse wie besehen an Microsoft übermittelt. Einige E-Mails können persönliche oder vertrauliche Informationen enthalten.

   - **Schaltfläche "Nachricht** \> melden" in Microsoft Outlook **Aus** ![ Umschalten: ](../../media/scc-toggle-off.png) Wählen Sie diese Option aus, wenn Sie Berichtstools von Drittanbietern anstelle des Add-Ins "Nachricht melden", des Add-Ins "Phishing melden" oder der integrierten Berichterstellung in Outlook im Web verwenden, und konfigurieren Sie dann die folgenden Einstellungen:
     - Wählen Sie **dieses benutzerdefinierte Postfach verwenden, um vom Benutzer gemeldete Übermittlungen zu empfangen.** Geben Sie in das angezeigte Feld die E-Mail-Adresse eines vorhandenen Exchange Online Postfach ein, das E-Mails empfangen kann.

   Wenn Sie fertig sind, klicken Sie auf **Bestätigen.** Klicken Sie zum Löschen dieser Werte auf **"Wiederherstellen".**

## <a name="third-party-reporting-tools"></a>Berichterstellungstools von Drittanbietern

Sie können Tools für die Berichterstellung von Drittanbietern konfigurieren, um gemeldete Nachrichten an das benutzerdefinierte Postfach zu senden. Dazu legen Sie die **Schaltfläche "Nachricht** melden" von Microsoft Outlook auf **"Aus"** fest und legen das **Postfach der Organisation** auf ein Office 365 Postfach Ihrer Wahl fest.

Die einzige Anforderung besteht darin, dass die ursprüngliche Nachricht als . EML oder . MSG-Anlage (nicht komprimiert) in der Nachricht, die an das benutzerdefinierte Postfach gesendet wird (leiten Sie nicht nur die ursprüngliche Nachricht an das benutzerdefinierte Postfach weiter).

Die Anforderungen an die Nachrichtenformatierung werden im nächsten Abschnitt beschrieben. Die Formatierung ist optional, aber wenn sie nicht dem vorgeschriebenen Format entspricht, werden die Berichte immer als Phishing übermittelt.

## <a name="message-submission-format"></a>Nachrichtenübermittlungsformat

Um die ursprünglichen angefügten Nachrichten korrekt zu identifizieren, erfordern Nachrichten, die an das benutzerdefinierte Postfach gesendet werden, eine bestimmte Formatierung. Wenn die Nachrichten dieses Format nicht verwenden, werden die ursprünglichen angefügten Nachrichten immer als Phishing-Übermittlungen identifiziert.

Wenn Sie den gemeldeten Grund für die ursprünglichen angefügten Nachrichten angeben möchten, müssen Nachrichten, die an das benutzerdefinierte Postfach gesendet werden (die Anlage nicht ändern), mit einem der folgenden Präfixe im Betreff (Briefumschlagtitel) beginnen:

- 1| oder Junk:
- 2| oder nicht Junk
- 3| oder Phishing

Beispiel:

`3|This part is ignored by the system` <br>
`Not Junk:This part of the subject is ignored as well`

- Beide Nachrichten werden basierend auf dem Betreff als "Keine Junk-Nachricht" gemeldet.
- Der Rest wird ignoriert.


Nachrichten, die diesem Format nicht folgen, werden im Übermittlungsportal nicht ordnungsgemäß angezeigt.
