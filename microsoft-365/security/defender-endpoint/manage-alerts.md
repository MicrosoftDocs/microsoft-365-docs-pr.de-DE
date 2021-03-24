---
title: Verwalten von Microsoft Defender for Endpoint-Warnungen
description: Ändern Sie den Status von Warnungen, erstellen Sie Unterdrückungsregeln, um Warnungen auszublenden, Kommentare zu übermitteln und den Änderungsverlauf für einzelne Warnungen im Menü Warnung verwalten zu überprüfen.
keywords: Verwalten von Warnungen, Verwalten, Warnungen, Status, neu, in Bearbeitung, aufgelöst, Warnungen auflösen, Unterdrücken, Unterdrückung, Regeln, Kontext, Verlauf, Kommentare, Änderungen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 5acec4e9b43c8af7f85fadd31caefbb15e227029
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062215"
---
# <a name="manage-microsoft-defender-for-endpoint-alerts"></a>Verwalten von Microsoft Defender for Endpoint-Warnungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-managealerts-abovefoldlink)

Defender for Endpoint benachrichtigt Sie über Warnungen über mögliche bösartige Ereignisse, Attribute und Kontextinformationen. Eine Zusammenfassung der neuen Warnungen wird im Dashboard für Sicherheitsvorgänge **angezeigt,** und Sie können auf alle Warnungen in der Benachrichtigungswarteschlange **zugreifen.**

Sie können Warnungen verwalten, indem Sie eine  Warnung in der Warnungswarteschlange oder auf der Registerkarte Warnungen auf der Seite Gerät für ein einzelnes Gerät auswählen.

Wenn Sie eine Warnung an einem dieser Orte auswählen, wird der **Bereich Warnungsverwaltung geöffnet.**

![Abbildung des Warnungsverwaltungsbereichs und der Warnungswarteschlange](images/atp-alerts-selected.png)

## <a name="link-to-another-incident"></a>Link zu einem anderen Vorfall
Sie können einen neuen Vorfall aus der Warnung oder einem Link zu einem vorhandenen Vorfall erstellen. 

## <a name="assign-alerts"></a>Zuweisen von Warnungen
Wenn eine Warnung noch nicht zugewiesen ist, können Sie **Zuweisen** für mich auswählen, um die Warnung selbst zuzuordnen.


## <a name="suppress-alerts"></a>Unterdrücken von Warnungen
Es kann Szenarien gibt, in denen Sie das Anzeigen von Warnungen im Microsoft Defender Security Center unterdrücken müssen. Mit Defender for Endpoint können Sie Unterdrückungsregeln für bestimmte Warnungen erstellen, die als harmlos bekannt sind, z. B. bekannte Tools oder Prozesse in Ihrer Organisation.

Unterdrückungsregeln können aus einer vorhandenen Warnung erstellt werden. Sie können bei Bedarf deaktiviert und erneut aktiviert werden.

Wenn eine Unterdrückungsregel erstellt wird, wird sie ab dem Zeitpunkt wirksam, an dem die Regel erstellt wird. Die Regel wirkt sich nicht auf vorhandene Warnungen aus, die sich bereits in der Warteschlange befinden, vor der Regelerstellung. Die Regel wird nur auf Warnungen angewendet, die die bedingungen erfüllen, die nach dem Erstellen der Regel festgelegt wurden.

Es gibt zwei Kontexte für eine Unterdrückungsregel, aus der Sie auswählen können:

- **Unterdrücken von Warnungen auf diesem Gerät**
- **Unterdrücken von Warnungen in meiner Organisation**

Mit dem Kontext der Regel können Sie anpassen, was im Portal angezeigt wird, und sicherstellen, dass nur echte Sicherheitswarnungen im Portal angezeigt werden.

Anhand der Beispiele in der folgenden Tabelle können Sie den Kontext für eine Unterdrückungsregel auswählen:

| **Context**                           | **Definition**                                                                                                                                              | **Beispielszenarien**                                                                                                                                                                                                  |
|:--------------------------------------|:------------------------------------------------------------------------------------------------------------------------------------------------------------|:-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Unterdrücken von Warnungen auf diesem Gerät**    | Warnungen mit dem gleichen Warnungstitel und nur auf diesem bestimmten Gerät werden unterdrückt. <br /><br />Alle anderen Warnungen auf diesem Gerät werden nicht unterdrückt. | <ul><li>Ein Sicherheitsforscher untersucht ein bösartiges Skript, das zum Angriff auf andere Geräte in Ihrer Organisation verwendet wurde.</li><li>Ein Entwickler erstellt regelmäßig PowerShell-Skripts für sein Team.</li></ul> |
| **Unterdrücken von Warnungen in meiner Organisation** | Warnungen mit dem gleichen Warnungstitel auf jedem Gerät werden unterdrückt.                                                                                         | <ul><li>Ein gutartiges Verwaltungstool wird von allen in Ihrer Organisation verwendet.</li></ul>                                                                                                                               |

### <a name="suppress-an-alert-and-create-a-new-suppression-rule"></a>Unterdrücken Sie eine Warnung, und erstellen Sie eine neue Unterdrückungsregel:
Erstellen Sie benutzerdefinierte Regeln, um zu steuern, wann Warnungen unterdrückt oder aufgelöst werden. Sie können den Kontext steuern, für den eine Warnung unterdrückt wird, indem Sie den Warnungstitel, den Kompromissindikator und die Bedingungen angeben. Nachdem Sie den Kontext angegeben haben, können Sie die Aktion und den Bereich für die Warnung konfigurieren. 

1. Wählen Sie die Warnung aus, die Sie unterdrücken möchten. Dadurch wird der Bereich **Warnungsverwaltung** geöffnet.

2.  Wählen **Sie Unterdrückungsregel erstellen aus.**

    Mit diesen Attributen können Sie eine Unterdrückungsbedingung erstellen. Zwischen jeder Bedingung wird ein AND-Operator angewendet, sodass die Unterdrückung nur erfolgt, wenn alle Bedingungen erfüllt sind.
    
    * Datei SHA1
    * Dateiname – Platzhalter wird unterstützt
    * Ordnerpfad – Platzhalter unterstützt
    * IP-Adresse
    * URL – Platzhalter unterstützt
    * Befehlszeile – Platzhalter unterstützt

3. Wählen Sie **das Auslösende IOC aus.**
    
4. Geben Sie die Aktion und den Bereich für die Warnung an. <br>
   Sie können eine Warnung automatisch auflösen oder im Portal ausblenden. Warnungen, die automatisch aufgelöst werden, werden im Abschnitt "Aufgelöst" der Warnungswarteschlange, der Warnungsseite und der Gerätezeitachse angezeigt und werden als in Defender for Endpoint-APIs aufgelöst angezeigt. <br><br> Warnungen, die als ausgeblendet markiert sind, werden sowohl für die zugeordneten Warnungen des Geräts als auch über das Dashboard aus dem gesamten System unterdrückt und nicht über Defender for Endpoint-APIs gestreamt.


5. Geben Sie einen Regelnamen und einen Kommentar ein.

6. Klicken Sie auf **Speichern**.

#### <a name="view-the-list-of-suppression-rules"></a>Anzeigen der Liste der Unterdrückungsregeln

1. Wählen Sie im Navigationsbereich  >  Einstellungsbenachrichtigungsunterdrückung **aus.**

2. Die Liste der Unterdrückungsregeln zeigt alle Regeln an, die Benutzer in Ihrer Organisation erstellt haben.

Weitere Informationen zum Verwalten von Unterdrückungsregeln finden Sie unter [Manage suppression rules](manage-suppression-rules.md)

## <a name="change-the-status-of-an-alert"></a>Ändern des Status einer Warnung

Sie können Warnungen (als **Neu,** **In Bearbeitung** oder **Aufgelöst**) kategorisieren, indem Sie ihren Status im Verlauf der Untersuchung ändern. Auf diese Weise können Sie organisieren und verwalten, wie Ihr Team auf Warnungen reagieren kann.

Beispielsweise kann ein Teamleiter  alle neuen Warnungen überprüfen und diese zur weiteren Analyse der **Warteschlange In Bearbeitung** zuweisen.

Alternativ kann der Teamleiter die  Warnung der Aufgelösten Warteschlange zuweisen, wenn er weiß, dass die Warnung gutartig ist, von einem gerät kommt, das irrelevant ist (z. B. eines, das einem Sicherheitsadministrator gehört) oder über eine frühere Warnung behandelt wird.



## <a name="alert-classification"></a>Warnungsklassifizierung
Sie können keine Klassifizierung festlegen oder angeben, ob es sich bei einer Warnung um eine echte warnung oder um eine falsche Warnung handelt. Es ist wichtig, die Klassifizierung des echten positiven/falsch positiven Werts zu liefern. Diese Klassifizierung wird verwendet, um die Warnungsqualität zu überwachen und Warnungen genauer zu machen. Das Feld "Bestimmung" definiert zusätzliche Genauigkeit für eine "true positive" Klassifizierung. 

## <a name="add-comments-and-view-the-history-of-an-alert"></a>Hinzufügen von Kommentaren und Anzeigen des Verlaufs einer Warnung
Sie können Kommentare hinzufügen und verlaufshistorische Ereignisse zu einer Warnung anzeigen, um frühere Änderungen an der Warnung zu sehen.

Wann immer eine Änderung oder ein Kommentar an einer Warnung vorgenommen wird, wird sie im Abschnitt **Kommentare und Verlauf** aufgezeichnet.

Hinzugefügte Kommentare werden sofort in diesem Bereich angezeigt.


## <a name="related-topics"></a>Verwandte Themen
- [Verwalten von Unterdrückungsregeln](manage-suppression-rules.md)
- [Anzeigen und Organisieren der Microsoft Defender for Endpoint Alerts-Warteschlange](alerts-queue.md)
- [Untersuchen von Microsoft Defender for Endpoint-Warnungen](investigate-alerts.md)
- [Untersuchen einer Datei, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist](investigate-files.md)
- [Untersuchen von Geräten in der Microsoft Defender for Endpoint Devices-Liste](investigate-machines.md)
- [Untersuchen einer einer Microsoft Defender for Endpoint-Warnung zugeordneten IP-Adresse](investigate-ip.md)
- [Untersuchen einer Domäne, die einer Microsoft Defender for Endpoint-Warnung zugeordnet ist](investigate-domain.md)
- [Untersuchen eines Benutzerkontos in Microsoft Defender for Endpoint](investigate-user.md)
