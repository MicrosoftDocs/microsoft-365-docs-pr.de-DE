---
title: Einrichten Tresor Links-Richtlinien in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie Tresor Links-Richtlinien und globale Einstellungen für Tresor Links in Microsoft Defender für Office 365 anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4254d62cfa5844756392c00686e7b93c466d160
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53082756"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>Einrichten Tresor Links-Richtlinien in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> Dieser Artikel richtet sich an Geschäftskunden, die über [Microsoft Defender für Office 365](defender-for-office-365.md) verfügen. Wenn Sie ein Privatbenutzer sind, der nach Informationen zu Safelinks in Outlook sucht, finden Sie weitere Informationen unter [Advanced Outlook.com Security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2).

Tresor Links in [Microsoft Defender für Office 365](defender-for-office-365.md) bieten URL-Überprüfung eingehender E-Mail-Nachrichten im E-Mail-Fluss und Zeitpunkt der Klicküberprüfung von URLs und Links in E-Mail-Nachrichten und an anderen Speicherorten. Weitere Informationen finden Sie unter [Tresor Links in Microsoft Defender für Office 365](safe-links.md).

Es gibt keine integrierte oder standardmäßige Richtlinie für Tresor Links. Um Tresor Links-Überprüfung von URLs zu erhalten, müssen Sie eine oder mehrere Tresor Linkrichtlinien erstellen, wie in diesem Artikel beschrieben.

> [!NOTE]
>
> Sie konfigurieren die globalen Einstellungen für Tresor Links-Schutz **außerhalb** Tresor Links-Richtlinien. Anweisungen finden Sie unter [Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365.](configure-global-settings-for-safe-links.md)
>
> Administratoren sollten die unterschiedlichen Konfigurationseinstellungen für Tresor Links berücksichtigen. Eine der verfügbaren Optionen besteht darin, Benutzerinformationen in Tresor Links einzuschließen. Dieses Feature ermöglicht *es Sicherheitsteams,* potenzielle Benutzerkompromittierungen zu untersuchen, Korrekturmaßnahmen zu ergreifen und kostspielige Verstöße zu begrenzen.

Sie können Tresor Verknüpfungsrichtlinien im Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für berechtigte Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer, aber mit Microsoft Defender für Office 365 Add-On-Abonnements).

Die grundlegenden Elemente einer Tresor Links-Richtlinie sind:

- Die Richtlinie für **sichere Links:** Aktivieren Sie Tresor Linksschutz, aktivieren Sie die URL-Überprüfung in Echtzeit, geben Sie an, ob auf den Abschluss der Echtzeitüberprüfung gewartet werden soll, bevor die Nachricht zuzustellen ist, aktivieren Sie die Überprüfung auf interne Nachrichten, geben Sie an, ob Benutzerklicks auf URLs nachverfolgen sollen, und geben Sie an, ob Benutzer auf die ursprüngliche URL klicken dürfen.
- **Die Regel für sichere Verknüpfungen:** Gibt die Prioritäts- und Empfängerfilter an (für wen die Richtlinie gilt).

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie Tresor Links-Richtlinien im Microsoft 365 Defender-Portal verwalten:

- Wenn Sie eine Tresor Verknüpfungsrichtlinie erstellen, erstellen Sie tatsächlich eine Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Tresor Verknüpfungsrichtlinie ändern, ändern Einstellungen im Zusammenhang mit Dem Namen, Priorität, aktiviert oder deaktiviert und Empfängerfilter die Regel für sichere Verknüpfungen. Alle anderen Einstellungen ändern die zugehörige Richtlinie für sichere Links.
- Wenn Sie eine Tresor Verknüpfungsrichtlinie entfernen, werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt ["Verwenden von Exchange Online PowerShell oder eigenständiger EOP PowerShell" zum Konfigurieren Tresor Richtlinien für Links](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) weiter unten in diesem Artikel.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com/>. To go directly to the **Tresor Links** page, use <https://security.microsoft.com/safelinksv2> .

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:
  - Um Tresor Verknüpfungsrichtlinien zu erstellen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** im Microsoft 365 Defender Portal **und** Mitglied der Rollengruppe **"Organisationsverwaltung"** in Exchange Online sein.
  - Für den schreibgeschützten Zugriff auf Tresor Links-Richtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und ["Berechtigungen" in Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  >
  > - Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  . – Die Rollengruppe **"Organisationsverwaltung nur anzeigen"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) bietet auch schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für Tresor Links-Richtlinien finden Sie unter [Tresor Links Policy Settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

- Es kann bis zu 30 Minuten dauern, bis eine neue oder aktualisierte Richtlinie angewendet wird.

- [Microsoft Defender werden kontinuierlich neue Features für Office 365 hinzugefügt.](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) Wenn neue Features hinzugefügt werden, müssen Sie möglicherweise Anpassungen an Ihren vorhandenen Richtlinien für Tresor Links vornehmen.

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Erstellen Tresor Verknüpfungsrichtlinien

Beim Erstellen einer benutzerdefinierten richtlinie für Tresor Links im Microsoft 365 Defender Portal werden die Regel für sichere Links und die zugehörige Richtlinie für sichere Links gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**

2. Klicken Sie auf der Seite **Tresor Links** auf das ![ Symbol ](../../media/m365-cc-sc-create-icon.png) **"Erstellen".**

3. Der Assistent **für neue Tresor Verknüpfungsrichtlinien** wird geöffnet. Konfigurieren Sie auf der Seite **"Richtlinie benennen"** die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Identifizieren Sie auf der angezeigten Seite **"Benutzer und Domänen"** die internen Empfänger, für die die Richtlinie gilt (Empfängerbedingungen):
   - **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
   - **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
   - **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_). Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie auf der angezeigten Seite **"Schutzeinstellungen"** die folgenden Einstellungen:
   - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Aktivieren Sie **"Ein",** um Tresor Linksschutz für Links in E-Mail-Nachrichten zu aktivieren. Wenn Sie diese Einstellung aktivieren, sind die folgenden Einstellungen verfügbar:
     - **Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links und Links, die auf Dateien verweisen:** Wählen Sie diese Option aus, um die Echtzeitüberprüfung von Links in E-Mail-Nachrichten zu aktivieren. Wenn Sie diese Einstellung aktivieren, ist folgende Einstellung verfügbar:
       - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln:** Wählen Sie diese Option aus, um auf den Abschluss der URL-Überprüfung in Echtzeit zu warten, bevor Sie die Nachricht übermitteln.
     - **Anwenden Tresor Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden:** Wählen Sie diese Option aus, um die Richtlinie Tresor Links auf Nachrichten zwischen internen Absendern und internen Empfängern anzuwenden.
   - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Aktivieren Sie **"Ein",** um Tresor Linksschutz für Links in Teams zu aktivieren.
   - **Benutzerklicks nicht nachverfolgen:** Lassen Sie diese Einstellung deaktiviert, um das Nachverfolgen von Benutzerklicks auf URLs in E-Mail-Nachrichten zu aktivieren.
   - **Benutzer dürfen nicht zur ursprünglichen URL klicken:** Wählen Sie diese Option aus, um zu verhindern, dass Benutzer auf [Warnseiten](safe-links.md#warning-pages-from-safe-links)zur ursprünglichen URL klicken.
   - **Schreiben Sie die folgenden URLs nicht neu:** Ermöglicht den Zugriff auf die angegebenen URLs, die andernfalls durch Tresor Links blockiert würden.

     Geben Sie in das Feld die gewünschte URL oder den gewünschten Wert ein, und klicken Sie dann auf **"Hinzufügen".** Wiederholen Sie diesen Schritt so oft wie nötig.

     Um einen vorhandenen Eintrag zu entfernen, klicken Sie auf ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Eintrag.

     Informationen zur Eintragssyntax finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)

   Ausführliche Informationen zu diesen Einstellungen finden Sie unter [Tresor Links-Einstellungen für E-Mail-Nachrichten](safe-links.md#safe-links-settings-for-email-messages) und [Tresor Links-Einstellungen für Microsoft Teams](safe-links.md#safe-links-settings-for-microsoft-teams).

   Weitere informationen zu den empfohlenen Werten für Standard- und Strict-Richtlinieneinstellungen finden Sie unter [Tresor Links Policy Settings](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings).

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Wählen Sie auf der **angezeigten Benachrichtigungsseite** einen der folgenden Werte **aus: Wie möchten Sie Ihre Benutzer benachrichtigen?**
   - **Verwenden des Standardmäßigen Benachrichtigungstexts**
   - **Verwenden Sie benutzerdefinierten Benachrichtigungstext:** Wenn Sie diesen Wert auswählen, werden die folgenden Einstellungen angezeigt:
     - **Verwenden von Microsoft Translator für die automatische Lokalisierung**
     - **Benutzerdefinierter Benachrichtigungstext:** Geben Sie den benutzerdefinierten Benachrichtigungstext in dieses Feld ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

7. Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

8. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Anzeigen Tresor Verknüpfungsrichtlinien

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**

2. Auf der Seite **Tresor Links** werden die folgenden Eigenschaften in der Liste Tresor Verknüpfungsrichtlinien angezeigt:
   - **Name**
   - **Status**
   - **Priorität**

3. Wenn Sie eine Richtlinie auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>Verwenden des Microsoft 365 Defender Portals zum Ändern Tresor Verknüpfungsrichtlinien

1. Wechseln Sie im Portal Microsoft 365 Defender zu **Richtlinien & Richtlinien** für \>  \> **Bedrohungsrichtlinien** \> **Tresor Links.**

2. Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern. Weitere Informationen zu den Einstellungen finden Sie im vorherigen Abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen Tresor Verknüpfungsrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies) in diesem Artikel.  

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie oder zum Festlegen der Reihenfolge der Richtlinienpriorität finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-safe-links-policies"></a>Aktivieren oder Deaktivieren Tresor Verknüpfungsrichtlinien

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**

2. Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:
   - **Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.
   - **Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.

5. Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.

### <a name="set-the-priority-of-safe-links-policies"></a>Festlegen der Priorität von Richtlinien für Tresor Links

Standardmäßig erhalten Tresor Links eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften einer Richtlinie auf **Priorität erhöhen** oder **Priorität verringern** (Sie können den Zahlenwert der **Priorität** im Microsoft 365 Defender-Portal nicht direkt modifizieren). Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.

**Hinweis**:

- Im Microsoft 365 Defender Portal können Sie die Priorität der Richtlinie Tresor Links erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die Standardpriorität überschreiben, wenn Sie die Regel für sichere Verknüpfungen erstellen (was sich auf die Priorität vorhandener Regeln auswirken kann).
- Tresor Verknüpfungsrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0). Weitere Informationen über die Prioritätsreihenfolge und darüber, wie mehrere Richtlinien ausgewertet und angewendet werden, finden Sie unter [Reihenfolge und Priorität beim E-Mail-Schutz](how-policies-and-protections-are-combined.md).

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**

2. Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:
   - Für die Richtlinie mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.
   - Für die Richtlinie mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.
   - Wenn Sie über drei oder mehr Richtlinien verfügen, stehen für die Richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität die Optionen **"Priorität erhöhen"** und **"Verringern"** zur Verfügung.

   Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.

4. Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>Verwenden sie das Microsoft 365 Defender-Portal, um Tresor Verknüpfungsrichtlinien zu entfernen.

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Tresor Links.**

2. Wählen Sie auf der Seite **Tresor Links** eine Richtlinie aus der Liste aus, indem Sie auf den Namen klicken. Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.

3. Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies&quot;></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren Tresor Verknüpfungsrichtlinien

Wie zuvor beschrieben besteht eine richtlinie für Tresor Links aus einer Richtlinie für sichere Links und einer Regel für sichere Links.

In PowerShell ist der Unterschied zwischen Richtlinien für sichere Links und Regeln für sichere Links offensichtlich. Sie verwalten Richtlinien für sichere Links mithilfe der Cmdlets **\* &quot;-SafeLinksPolicy&quot;,** und Sie verwalten Regeln für sichere Links mithilfe der Cmdlets **\* &quot;-SafeLinksRule&quot;.**

- In PowerShell erstellen Sie zuerst die Richtlinie für sichere Links und dann die Regel für sichere Links, die die Richtlinie identifiziert, für die die Regel gilt.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für sichere Links und die Regel für sichere Links separat.
- Wenn Sie eine Richtlinie für sichere Links aus PowerShell entfernen, wird die entsprechende Regel für sichere Links nicht automatisch entfernt und umgekehrt.

### <a name=&quot;use-powershell-to-create-safe-links-policies&quot;></a>Verwenden von PowerShell zum Erstellen Tresor Verknüpfungsrichtlinien

Das Erstellen einer richtlinie für Tresor Links in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Richtlinie für sichere Links.
2. Erstellen Sie die Regel für sichere Links, die die Richtlinie für sichere Links angibt, auf die die Regel angewendet wird.

> [!NOTE]
>
> - Sie können eine neue Regel für sichere Links erstellen und ihr eine vorhandene Richtlinie für nicht zugeordnete sichere Links zuweisen. Eine Regel für sichere Links kann nicht mehr als einer Richtlinie für sichere Links zugeordnet werden.
>
> - Sie können die folgenden Einstellungen für neue Richtlinien für sichere Links in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender Portal verfügbar sind:
>   - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` für das Cmdlet **&quot;New-SafeLinksRule").**
>   - Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ im Cmdlet **"New-SafeLinksRule"** fest.
>
> - Eine neue Richtlinie für sichere Links, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer Regel für sichere Links zuweisen.

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links zu erstellen:

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - Ausführliche Informationen zur Eintragssyntax, die für den _DoNotRewriteUrls-Parameter_ verwendet werden soll, finden Sie unter [Eintragssyntax für die Liste "Die folgenden URLs nicht neu schreiben".](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)
>
> - Eine zusätzliche Syntax, die Sie für den _DoNotRewriteUrls-Parameter_ verwenden können, wenn Sie vorhandene Richtlinien für sichere Links mithilfe des Cmdlets **"Set-SafeLinksPolicy"** ändern, finden Sie im Abschnitt ["Verwenden von PowerShell zum Ändern](#use-powershell-to-modify-safe-links-policies) von Richtlinien für sichere Verknüpfungen" weiter unten in diesem Artikel.

In diesem Beispiel wird eine Richtlinie für sichere Verknüpfungen namens "Contoso All" mit den folgenden Werten erstellt:

- Aktivieren Sie die URL-Überprüfung und -Umschreibung in E-Mail-Nachrichten.
- Aktivieren Sie die URL-Überprüfung in Teams (nur TAP Preview).
- Aktivieren Sie die Echtzeitüberprüfung von angeklickten URLs, einschließlich angeklickter Links, die auf Dateien verweisen.
- Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln.
- Aktivieren Sie die URL-Überprüfung und das Umschreiben für interne Nachrichten.
- Nachverfolgen von Benutzerklicks im Zusammenhang mit Tresor Links-Schutz (wir verwenden nicht den _DoNotTrackUserClicks-Parameter,_ und der Standardwert ist $false, was bedeutet, dass Benutzerklicks nachverfolgt werden).
- Benutzer dürfen nicht auf die ursprüngliche URL klicken.

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksPolicy](/powershell/module/exchange/new-safelinkspolicy).

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel für sichere Links

Verwenden Sie diese Syntax, um eine Regel für sichere Links zu erstellen:

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

In diesem Beispiel wird eine Regel für sichere Verknüpfungen namens "Contoso All" mit den folgenden Bedingungen erstellt:

- Die Regel ist der Richtlinie für sichere Verknüpfungen namens Contoso All zugeordnet.
- Die Regel gilt für alle Empfänger in der contoso.com Domäne.
- Da der Parameter _"Priority"_ nicht verwendet wird, wird die Standardpriorität verwendet.
- Die Regel ist aktiviert (wir verwenden nicht den Parameter _Enabled,_ und der Standardwert lautet `$true` ).

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-SafeLinksRule](/powershell/module/exchange/new-safelinksrule).

### <a name="use-powershell-to-view-safe-links-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Richtlinien für sichere Links anzuzeigen:

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Richtlinien für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

In diesem Beispiel werden detaillierte Informationen für die Richtlinie für sichere Links namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksPolicy".](/powershell/module/exchange/get-safelinkspolicy)

### <a name="use-powershell-to-view-safe-links-rules"></a>Verwenden von PowerShell zum Anzeigen von Regeln für sichere Links

Verwenden Sie die folgende Syntax, um vorhandene Regeln für sichere Links anzuzeigen:

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

In diesem Beispiel wird eine Zusammenfassungsliste aller Regeln für sichere Links zurückgegeben.

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

In diesem Beispiel werden detaillierte Informationen für die Regel für sichere Links namens Contoso Executives zurückgegeben.

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-SafeLinksRule".](/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für sichere Links

Sie können eine Richtlinie für sichere Links in PowerShell nicht umbenennen (das Cmdlet **"Set-SafeLinksPolicy"** hat keinen _Name-Parameter)._ Wenn Sie eine Tresor Verknüpfungsrichtlinie im Microsoft 365 Defender-Portal umbenennen, benennen Sie nur die _Regel für_ sichere Links um.

Die einzige zusätzliche Überlegung zum Ändern von Richtlinien für sichere Links in PowerShell ist die verfügbare Syntax für den _Parameter "DoNotRewriteUrls"_ (die [Liste "Die folgenden URLs nicht umschreiben"):](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)

- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen, die vorhandene Einträge `"Entry1","Entry2,..."EntryN"` ersetzen:
- Verwenden Sie die folgende Syntax, um Werte hinzuzufügen oder zu entfernen, ohne dass sich dies auf andere Einträge auswirkt: `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Richtlinie für sichere Links erstellen, wie im [Abschnitt "Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für sichere Links"](#step-1-use-powershell-to-create-a-safe-links-policy) weiter oben in diesem Artikel beschrieben.

Verwenden Sie diese Syntax, um eine Richtlinie für sichere Links zu ändern:

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksPolicy".](/powershell/module/exchange/set-safelinkspolicy)

### <a name="use-powershell-to-modify-safe-links-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für sichere Links

Die einzige Einstellung, die beim Ändern einer Regel für sichere Verknüpfungen in PowerShell nicht verfügbar ist, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Regeln für sichere Links finden Sie im nächsten Abschnitt.

Andernfalls sind die gleichen Einstellungen verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer Regel](#step-2-use-powershell-to-create-a-safe-links-rule) für sichere Links" weiter oben in diesem Artikel beschrieben.

Verwenden Sie diese Syntax, um eine Regel für sichere Links zu ändern:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für sichere Links

Das Aktivieren oder Deaktivieren einer Regel für sichere Links in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für Tresor Links (die Regel für sichere Links und die Richtlinie für zugewiesene sichere Links).

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Regel für sichere Links mit dem Namen "Marketing Department" deaktiviert.

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-SafeLinksRule"](/powershell/module/exchange/enable-safelinksrule) und ["Disable-SafeLinksRule".](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von Regeln für sichere Links

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Regel für sichere Links in PowerShell festzulegen:

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-SafeLinksRule".**

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-SafeLinksRule".](/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>Verwenden von PowerShell zum Entfernen von Richtlinien für sichere Links

Wenn Sie PowerShell verwenden, um eine Richtlinie für sichere Links zu entfernen, wird die entsprechende Regel für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Richtlinie für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für sichere Links mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksPolicy](/powershell/module/exchange/remove-safelinkspolicy).

### <a name="use-powershell-to-remove-safe-links-rules"></a>Verwenden von PowerShell zum Entfernen von Regeln für sichere Links

Wenn Sie PowerShell verwenden, um eine Regel für sichere Links zu entfernen, wird die entsprechende Richtlinie für sichere Links nicht entfernt.

Verwenden Sie die folgende Syntax, um eine Regel für sichere Links in PowerShell zu entfernen:

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Regel für sichere Verknüpfungen mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule).

Um zu überprüfen, ob Tresor Links Nachrichten überprüft, überprüfen Sie den verfügbaren Microsoft Defender auf Office 365 Berichte. Weitere Informationen finden Sie unter [Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md) und Verwenden von Explorer im Microsoft 365 Defender [Portal.](threat-explorer.md)

## <a name="how-do-you-know-these-procedures-worked"></a>Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?

Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Tresor Verknüpfungsrichtlinien erfolgreich erstellt, geändert oder entfernt haben:

- Wechseln Sie im portal Microsoft 365 Defender zu **Richtlinien & Regeln** \> **Bedrohungsrichtlinien** Tresor \> **Links**. Überprüfen Sie die Liste der Richtlinien, ihre **Statuswerte** und ihre **Prioritätswerte.** Um weitere Details anzuzeigen, wählen Sie die Richtlinie aus der Liste aus, und zeigen Sie die Details im Flyout an.

- Ersetzen Sie in Exchange Online PowerShell oder Exchange Online Protection PowerShell \<Name\> durch den Namen der Richtlinie oder Regel, führen Sie den folgenden Befehl aus, und überprüfen Sie die Einstellungen:

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
