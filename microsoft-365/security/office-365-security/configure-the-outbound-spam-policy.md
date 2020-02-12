---
title: Konfigurieren der Richtlinie für ausgehende Spamnachrichten
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
description: Die Filterung ausgehender Spamnachrichten ist immer aktiviert, wenn Sie den Dienst für das Senden ausgehender E-Mails verwenden und dadurch Organisationen, die den Dienst nutzen, und ihre jeweiligen Empfänger schützen.
ms.openlocfilehash: 0fa5ec23eee6144864f16b52d452d02f38b554d7
ms.sourcegitcommit: 4986032867b8664a215178b5e095cbda021f3450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/12/2020
ms.locfileid: "41957340"
---
# <a name="configure-the-outbound-spam-policy"></a>Konfigurieren der Richtlinie für ausgehende Spamnachrichten

Die Filterung ausgehender Spamnachrichten ist immer aktiviert, wenn Sie den Dienst für das Senden ausgehender E-Mails verwenden und dadurch Organisationen, die den Dienst nutzen, und ihre jeweiligen Empfänger schützen. Ähnlich wie bei der eingehenden Filterung besteht eine ausgehende Spamfilterung aus der Verbindungsfilterung und der Inhaltsfilterung und ermöglicht es einigen bestimmten Steuerelementen, ausgehende Nachrichten zu verarbeiten. Richtlinien Einstellungstypen für ausgehende Spamfilter:

- Standard: die Standardrichtlinie für ausgehende Spamfilter wird verwendet, um unternehmensweite Einstellungen für ausgehende Spamfilter zu konfigurieren. Diese Richtlinie kann nicht umbenannt werden und ist immer aktiviert.

- Benutzerdefiniert: benutzerdefinierte Richtlinien für ausgehende Spamfilter können Granular sein und auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation angewendet werden. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie. Sie können die Reihenfolge ändern, in der Ihre benutzerdefinierten Richtlinien ausgeführt werden, indem Sie die Priorität der einzelnen benutzerdefinierten Richtlinien ändern. Wenn der Benutzer mit mehreren Richtlinien übereinstimmt, gilt jedoch nur die höchste Priorität (d. h. die Nummer, die dem Wert am nächsten kommt).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?
<a name="sectionSection0"> </a>

- Geschätzte Zeit bis zum Abschließen des Vorgangs: 5 Minuten

- Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter dem Eintrag „Antispam“ im Thema [Featureberechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions).

- Sie können die Verfahren in diesem Thema auch in Remote-PowerShell ausführen. Mit dem Cmdlet [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy) können Sie Ihre Einstellungen überprüfen und mit dem Cmdlet [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy) Ihre Einstellungen für ausgehende Spamnachrichten bearbeiten.

  Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

## <a name="use-the-security--compliance-center-scc-to-edit-the-default-outbound-spam-policy"></a>Verwenden der Security & Compliance Center (SCC) zum Bearbeiten der standardmäßigen ausgehenden Spam Richtlinie

Verwenden Sie das folgende Verfahren, um die Standardrichtlinie für ausgehende Spamnachrichten zu bearbeiten:

### <a name="to-configure-the-default-outbound-spam-policy"></a>So konfigurieren Sie die Standardrichtlinie für ausgehende Spamnachrichten

1. Navigieren Sie in der SCC zu **Threat Management** \> **Policy** \> **Anti-Spam**

2. Erweitern Sie den Abschnitt Richt **Linie für ausgehende Spamfilter (immer weiter)** , und klicken Sie auf **Richtlinie bearbeiten**.

3. Erweitern Sie den Abschnitt **Benachrichtigungen** , und aktivieren Sie die folgenden Kontrollkästchen im Zusammenhang mit ausgehenden Nachrichten, und wählen Sie dann **Personen hinzufügen** aus, um eine zugeordnete e-Mail-Adresse oder Adressen im zugehörigen Dialogfeld hinzuzufügen. (Dies können Verteilerlisten sein, wenn Sie als gültige SMTP-Ziele aufgelöst werden):

   - **Senden Sie eine Kopie aller Verdächtigen ausgehenden e-Mail-Nachrichten an die folgende e-Mail-Adresse oder Adresse**: Dabei handelt es sich um Nachrichten, die vom Filter als Spam gekennzeichnet sind (unabhängig von der SCL-Bewertung). Sie werden vom Filter nicht zurückgewiesen, sondern durch den Pool für besonders riskante Zustellungen geleitet. Trennen Sie mehrere Adressen durch ein Semikolon. Beachten Sie, dass die angegebenen Empfänger die Nachrichten als "Bcc" (Blind Carbon Copy, nicht sichtbare Kopie) erhalten (in den Feldern "Von" und "An" sind der ursprüngliche Sender und Empfänger angegeben).

   - **Senden einer Benachrichtigung an die folgende e-Mail-Adresse, wenn ein Absender blockiert wird, der ausgehenden Spam sendet**: Trennen Sie mehrere Adressen durch ein Semikolon.

   Wenn von einem bestimmten Benutzer eine erhebliche Menge an Spam oder andere Sende Anomalien erkannt werden, wird der Benutzer vom Senden von e-Mail-Nachrichten und einer Benachrichtigung an die angegebenen e-Mail-Adressen eingeschränkt.

   Der Administrator der Domäne, der in dieser Einstellung angegeben ist, wird darüber informiert, dass ausgehende Nachrichten für diesen Benutzer blockiert werden.  Ein Beispiel für diese Benachrichtigung finden Sie unter [Beispielbenachrichtigung, wenn ein Absender aufgrund des Versendens von ausgehendem Spam blockiert wird](sample-notification-when-a-sender-is-blocked-sending-outbound-spam.md).

   > [!NOTE]
   > Außerdem wird eine Systemwarnung generiert, die angibt, dass der Benutzer eingeschränkt wurde. Weitere Informationen zur Warnung und zum Wiederherstellen des Benutzers finden Sie unter [Entfernen eines Benutzers aus dem eingeschränkten Benutzerportal nach dem Senden von Spam-e-Mails](removing-user-from-restricted-users-portal-after-spam.md).

4. Erweitern Sie den Abschnitt **Empfänger Grenzwerte** , um die maximale Anzahl von Empfängern anzugeben, die ein Benutzer pro Stunde für interne und externe Empfänger zusammen mit der maximalen Anzahl pro Tag senden kann.

   > [!NOTE]
   > Die maximal zulässige Anzahl von Eingaben beträgt 10000. Weitere Informationen finden Sie unter [empfangen und Senden von Grenzwerten in Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#receiving-and-sending-limits) .

7. Geben Sie die Aktion an, die **ausgeführt** werden soll, wenn ein Benutzer die angegebenen Grenzwerte überschreitet.  Die folgenden Aktionen sind möglich:

   - **Beschränken Sie den Benutzer am Senden von e-Mails bis zum nächsten Tag**.  Sobald die Sende Grenze überschritten ist (intern, extern oder täglich), wird eine Warnung für den Administrator generiert, und der Benutzer kann keine weiteren e-Mails an den folgenden Tag senden, basierend auf UTC-Zeit. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.

   - **Einschränken des Sendens von e-Mails durch den Benutzer**  Sobald die Sende Grenze überschritten ist (intern, extern oder täglich), wird eine Warnung für den Administrator generiert, und der Benutzer kann keine weiteren e-Mails senden, bis der Administrator die Einschränkung entfernt hat.  In diesen Fällen wird der Benutzer auf der Seite mit [eingeschränkten Benutzern](removing-user-from-restricted-users-portal-after-spam.md)aufgeführt.  Nachdem der Benutzer aus der Liste entfernt wurde, wird er für diesen Tag nicht mehr eingeschränkt.

   - **Keine Aktion/Warnung**. Sobald die Sende Grenze überschritten ist (intern, extern oder täglich), wird eine Warnung für den Administrator generiert, aber es wird keine Aktion ausgeführt, um den Benutzer zu beschränken.

6. Erweitern Sie den Abschnitt **gilt für** , und erstellen Sie dann eine bedingungsbasierte Regel, um die Benutzer, Gruppen und Domänen anzugeben, auf die diese Richtlinie angewendet werden soll. Sie können mehrere Bedingungen angeben, wenn diese eindeutig sind.  Hinweis: Benutzer müssen alle Bedingungen erfüllen, wenn mehrere Bedingungen angegeben werden.  

   - Wählen Sie zum Auswählen von Benutzern **die Option Absender ist**aus. Wählen Sie im nachfolgenden Dialogfeld in der Liste Benutzerauswahl einen oder mehrere Absender Ihres Unternehmens aus, und klicken Sie dann auf hinzufügen. Geben Sie Ihre e-Mail-Adressen ein, und klicken Sie dann auf Namen überprüfen, um Absender hinzuzufügen, die nicht in der Liste aufgeführt sind. Nachdem Sie Ihre Auswahl getroffen haben, klicken Sie auf OK, um zum Hauptbildschirm zurückzukehren.

   - Wenn Sie Gruppen auswählen möchten, wählen Sie **den Absender ist Mitglied von**aus. Wählen Sie dann im folgenden Dialogfeld die Gruppen aus, oder geben Sie diese an. Klicken Sie auf OK, um zum Hauptbildschirm zurückzukehren.

   - Wählen Sie zum Auswählen von Domänen **die Option Sender Domain lautet**aus. Fügen Sie dann im folgenden Dialogfeld die Domänen hinzu. Klicken Sie auf OK, um zum Hauptbildschirm zurückzukehren.

   Sie können Ausnahmen innerhalb der Regel erstellen. So können Sie beispielsweise Nachrichten aus allen Domänen mit Ausnahme einer bestimmten Domäne filtern. Klicken Sie auf Ausnahme hinzufügen, und erstellen Sie dann Ihre Ausnahmebedingungen ähnlich wie die anderen Bedingungen.

   Das Anwenden einer ausgehenden Spam Richtlinie auf eine Gruppe wird nur für e-Mail-aktivierte Sicherheitsgruppen unterstützt.

7. Klicken Sie auf **Speichern**.

## <a name="to-create-a-custom-policy-for-a-specific-set-of-users"></a>So erstellen Sie eine benutzerdefinierte Richtlinie für eine bestimmte Gruppe von Benutzern

1. Navigieren Sie in der SCC zu **Threat Management** \> **Policy** \> **Anti-Spam**

2. Klicken Sie auf die Schaltfläche **ausgehende Richtlinie erstellen** .

3. Erweitern Sie den Abschnitt **Benachrichtigungen** , und aktivieren Sie die folgenden Kontrollkästchen im Zusammenhang mit ausgehenden Nachrichten, und wählen Sie dann **Personen hinzufügen** aus, um eine zugeordnete e-Mail-Adresse oder Adressen im zugehörigen Dialogfeld hinzuzufügen.

4. Erweitern Sie den Abschnitt **Empfänger Grenzwerte** , um die maximale Anzahl von Empfängern anzugeben, die ein Benutzer pro Stunde für interne und externe Empfänger und maximale Anzahl pro Tag senden kann.

7. Geben Sie die Aktion an, die **ausgeführt** werden soll, wenn ein Benutzer die angegebenen Grenzwerte überschreitet.

6. Erweitern Sie den Abschnitt **gilt für** , und erstellen Sie eine bedingungsbasierte Regel, um die Benutzer, Gruppen und Domänen anzugeben, auf die diese Richtlinie angewendet werden soll. Sie können mehrere Bedingungen angeben, wenn diese eindeutig sind.  

8. Klicken Sie auf **Speichern**

## <a name="for-more-information"></a>Weitere Informationen

[Entfernen eines Benutzers aus dem Portal für Benutzer mit eingeschränktem Zugriff nach dem Senden von Spam-E-Mails](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)
