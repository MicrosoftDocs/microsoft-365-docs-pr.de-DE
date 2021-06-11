---
title: Konfigurieren der Filterung für ausgehende Spamnachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie ausgehende Spamrichtlinien in Exchange Online Protection (EOP) angezeigt, erstellt, geändert und gelöscht werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 13b25300b6e5b42c860c58546f9c084a244b5f1f
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878916"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurieren der ausgehenden Spamfilterung in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online Postfächern werden ausgehende E-Mail-Nachrichten, die über EOP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.

Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein kompromittiertes Konto hin. Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam-Konfidenzstufe oder SCL) und werden über den [Übermittlungspool](high-risk-delivery-pool-for-outbound-messages.md) mit hohem Risiko weitergeleitet, um den Ruf des Diensts zu schützen (d. a. Microsoft 365 Quell-E-Mail-Server von IP-Sperrlisten fernzuhalten). Administratoren werden automatisch über verdächtige ausgehende E-Mail-Aktivitäten benachrichtigt und Benutzer über [Warnungsrichtlinien](../../compliance/alert-policies.md)blockiert.

EOP verwendet ausgehende Spamrichtlinien als Teil des allgemeinen Schutzes Ihrer Organisation gegen Spam. Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).

Administratoren können die standardmäßige richtlinie für ausgehende Spamnachrichten anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte ausgehende Spamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können ausgehende Spamrichtlinien im Microsoft 365 Microsoft 365 Defender-Portal oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständiger EOP PowerShell für Organisationen ohne Exchange Online Postfächer).

Die grundlegenden Elemente einer Richtlinie für ausgehende Spamnachrichten in EOP sind:

- Die Richtlinie für **den ausgehenden Spamfilter:** Gibt die Aktionen für ausgehende Spamfilterbewertungen und die Benachrichtigungsoptionen an.
- **Die Ausgehende Spamfilterregel:** Gibt die Prioritäts- und Empfängerfilter (für die die Richtlinie gilt) für eine richtlinie für ausgehende Spamfilter an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spamrichtlinien im Microsoft 365 Defender-Portal verwalten:

- Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilterregel und die zugeordnete Richtlinie für den ausgehenden Spamfilter gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie ändern, ändern Einstellungen, die sich auf den Namen, die Priorität, aktiviert oder deaktiviert beziehen, und Empfängerfilter die ausgehende Spamfilterregel. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für ausgehende Spamfilter.
- Wenn Sie eine Richtlinie entfernen, werden die Filterregel für ausgehende Spamnachrichten und die zugeordnete Richtlinie für den ausgehenden Spamfilter entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt ["Use Exchange Online PowerShell or standalone EOP PowerShell to configure outbound spam policies"](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte richtlinie für ausgehende Spamnachrichten mit dem Namen "Standard", die über die folgenden Eigenschaften verfügt:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine ausgehende Spamfilterregel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität der ausgehenden Spamfilterung zu erhöhen, können Sie benutzerdefinierte Richtlinien für ausgehende Spamnachrichten mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com> . Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://security.microsoft.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um ausgehende Spamrichtlinien hinzuzufügen, zu ändern und zu löschen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf ausgehende Spamrichtlinien müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Unsere empfohlenen Einstellungen für ausgehende Spamrichtlinien finden Sie unter [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).

- Die [Standardmäßige Warnungsrichtlinien](../../compliance/alert-policies.md) namens **"E-Mail-Sendegrenzwert" wurde überschritten,** **verdächtige E-Mail-Versandmuster erkannt,** und der Benutzer, dem das **Senden von E-Mails eingeschränkt** ist, sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **"TenantAdmins** (**Globale Administratoren)**" über ungewöhnliche ausgehende E-Mail-Aktivitäten und blockierte Benutzer aufgrund ausgehender Spamnachrichten. Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spamrichtlinien zu verwenden.

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Erstellen ausgehender Spamrichtlinien

Beim Erstellen einer benutzerdefinierten Richtlinie für ausgehende Spamnachrichten im Microsoft 365 Defender-Portal werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-&** \> **Zusammenarbeitsrichtlinien & Richtlinien** für \> **Bedrohungsrichtlinien** für Regeln \>  \> **Antispam**.

2. Klicken Sie auf der Seite **"Antispamrichtlinien"** auf ![ das Symbol ](../../media/m365-cc-sc-create-icon.png) **"Richtlinie erstellen",** und wählen Sie dann in der Dropdownliste **"Ausgehend"** aus.

3. Der Richtlinienassistent wird geöffnet. Konfigurieren Sie auf der Seite **Benennen Sie Ihre Richtlinie** diese Einstellungen:
   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.
   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

4. Auf der dann angezeigten Seite **Benutzer, Gruppen und Domänen** identifizieren Sie die internen Empfänger, für welche die Richtlinie gilt (Empfängerbedingungen):
   - **Benutzer**: Die angegebenen Postfächer, E-Mail-Benutzer oder E-Mail-Kontakte in Ihrer Organisation.
   - **Gruppen**: Die angegebenen Verteilergruppen, E-Mail-aktivierten Sicherheitsgruppen oder Microsoft 365-Gruppen in Ihrer Organisation.
   - **Domänen**: Alle Empfänger in der angegebenen [akzeptierten Domäne](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in Ihrer Organisation.

   Klicken Sie auf das entsprechende Feld, beginnen Sie mit der Eingabe eines Wertes, und wählen Sie den gewünschten Wert aus den Ergebnissen aus. Wiederholen Sie diesen Vorgang so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   Für Benutzer oder Gruppen können Sie die meisten Bezeichner verwenden (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.), aber in den Ergebnissen wird der entsprechende Anzeigename angezeigt. Geben Sie für Benutzer einen einzelnen Stern (\*) ein, um alle verfügbaren Werte anzuzeigen.

   Mehreren Werten in der gleichen Bedingung verwenden die „ODER“-Logik (z. B. _\<recipient1\>_ ODER _\<recipient2\>_). Unterschiedlichen Bedingungen verwenden die „UND“-Logik (z. B. _\<recipient1\>_ UND _\<member of group 1\>_).

   - **Ausschließen dieser Benutzer, Gruppen und Domänen**: Um Ausnahmen für die internen Empfänger hinzuzufügen, für welche die Richtlinie gilt (Empfängerausnahmen), wählen Sie diese Option und konfigurieren Sie die Ausnahmen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

5. Konfigurieren Sie auf der seite **"Schutzeinstellungen",** die geöffnet wird, die folgenden Einstellungen:
   - **Nachrichtengrenzwerte:** Die Einstellungen in diesem Abschnitt konfigurieren die Grenzwerte für ausgehende E-Mail-Nachrichten von **Exchange Online** Postfächern:
     - **Festlegen eines Grenzwerts für externe Nachrichten:** Die maximale Anzahl externer Empfänger pro Stunde.
     - **Legen Sie ein internes Nachrichtenlimit fest:** Die maximale Anzahl interner Empfänger pro Stunde.
     - **Legen Sie ein tägliches Nachrichtenlimit fest:** Die maximale Gesamtanzahl von Empfängern pro Tag.

     Ein gültiger Wert ist 0 bis 10000. Der Standardwert ist 0, was bedeutet, dass die Dienststandardwerte verwendet werden. Weitere Informationen finden Sie unter [Senden von Grenzwerten.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

    Geben Sie einen Wert in das Feld ein, oder verwenden Sie die Pfeile zum Vergrößern/Verkleinern des Felds.

   - **Einschränkung für Benutzer, die das Nachrichtenlimit erreichen:** Wählen Sie eine Aktion aus der Dropdownliste aus, wenn eine der Grenzwerte im Abschnitt **"Schutzeinstellungen"** überschritten wird.

     Für alle Aktionen erhalten die im Benutzer angegebenen Empfänger, die das **Senden von E-Mail-Warnungsrichtlinien eingeschränkt** haben (und in der jetzt redundanten **Benachrichtigung dieser Benutzer und Gruppen, wenn ein Absender aufgrund des Sendens ausgehender Spam-Einstellungen** später auf dieser Seite blockiert wird) E-Mail-Benachrichtigungen.

     - **Beschränken Sie das Senden von E-Mails durch den Benutzer bis zum folgenden Tag:** Dies ist der Standardwert. E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann basierend auf der UTC-Zeit bis zum folgenden Tag keine weiteren Nachrichten mehr senden. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.
       - Die Aktivitätswarnung namens **"Benutzer, der das Senden von E-Mails eingeschränkt** hat" benachrichtigt Administratoren (per E-Mail und auf der Seite **"Warnungen anzeigen").**
       - Alle Empfänger, die in der Richtlinie **"Bestimmte Personen benachrichtigen" angegeben sind, wenn ein Absender aufgrund des Sendens ausgehender Spam-Einstellungen** in der Richtlinie blockiert wird, werden ebenfalls benachrichtigt.
       - Der Benutzer kann basierend auf der UTC-Zeit bis zum folgenden Tag keine weiteren Nachrichten mehr senden. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.
     - **Beschränken Sie das Senden von E-Mails** durch den Benutzer: E-Mail-Benachrichtigungen werden gesendet, der Benutzer wird eingeschränkten **Benutzern** <https://security.microsoft.com/restrictedusers> im Microsoft 365 Defender-Portal hinzugefügt, und der Benutzer kann keine E-Mails senden, bis er von einem Administrator aus **eingeschränkten Benutzern** entfernt wird. Nachdem ein Administrator den Benutzer aus der Liste entfernt hat, wird der Benutzer für diesen Tag nicht erneut eingeschränkt. Anweisungen finden Sie unter [Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden von Spam-E-Mails.](removing-user-from-restricted-users-portal-after-spam.md)
     - **Keine Aktion, nur Warnung:** E-Mail-Benachrichtigungen werden gesendet.

   - **Weiterleitungsregeln:** Verwenden Sie die Einstellungen in diesem Abschnitt, um die automatische E-Mail-Weiterleitung durch **Exchange Online Postfächer** an externe Absender zu steuern. Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](external-email-forwarding.md).

     > [!NOTE]
     > Wenn die automatische Weiterleitung deaktiviert ist, erhält der Empfänger einen Unzustellbarkeitsbericht (auch als Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bezeichnet), wenn externe Absender E-Mails an ein Postfach senden, das über eine Weiterleitung verfügt. Wenn die Nachricht von einem internen Absender gesendet wird **und** die Weiterleitungsmethode die [Postfachweiterleitung](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) ist (auch bekannt als _SMTP-Weiterleitung),_ erhält der interne Absender den NDR. Der interne Absender erhält keinen NDR, wenn die Weiterleitung aufgrund einer Posteingangsregel erfolgt ist.

     Wählen Sie eine der folgenden Aktionen aus der Dropdownliste "Regeln für die **automatische Weiterleitung"** aus:

     - **Automatisch – systemgesteuert:** Ermöglicht ausgehende Spamfilterung, um die automatische externe E-Mail-Weiterleitung zu steuern. Dies ist der Standardwert.
     - **Aktiviert:** Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.
     - **Deaktiviert:** Alle automatischen externen E-Mail-Weiterleitungen werden von der Richtlinie deaktiviert.

   - **Benachrichtigungen:** Verwenden Sie die Einstellungen im Abschnitt, um zusätzliche Empfänger zu konfigurieren, die Kopien und Benachrichtigungen verdächtiger ausgehender E-Mail-Nachrichten erhalten sollen:

     - **Senden Sie eine Kopie von verdächtigen ausgehenden Nachrichten, die diese Grenzwerte überschreiten, an diese Benutzer und Gruppen:** Diese Einstellung fügt die angegebenen Empfänger zum Bcc-Feld verdächtiger ausgehender Nachrichten hinzu.

       > [!NOTE]
       > Diese Einstellung funktioniert nur in der standardmäßigen Richtlinie für ausgehende Spamnachrichten. Es funktioniert nicht in benutzerdefinierten ausgehenden Spamrichtlinien, die Sie erstellen.

       Aktivieren Sie das Kontrollkästchen, um diese Einstellung zu aktivieren. Klicken Sie in das angezeigte Feld, geben Sie eine gültige E-Mail-Adresse ein, und drücken Sie die EINGABETASTE, oder wählen Sie den vollständigen Wert aus, der unterhalb des Felds angezeigt wird.

       Wiederholen Sie diesen Schritt so oft wie nötig. Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

   - **Diese Benutzer und Gruppen benachrichtigen, wenn ein Absender aufgrund des Sendens ausgehender Spamnachrichten blockiert wird**

     > [!IMPORTANT]
     >
     > - Diese Einstellung ist dabei, von ausgehenden Spamrichtlinien veraltet zu sein.
     >
     > - Die [Standardbenachrichtigungsrichtlinie](../../compliance/alert-policies.md) mit dem Namen **"Benutzer, der das Senden von E-Mails eingeschränkt** hat" sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **TenantAdmins** (**Globale Administratoren**), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt **"Empfängergrenzwerte"** blockiert werden. **Es wird dringend empfohlen, die Warnungsrichtlinie anstelle dieser Einstellung in der Richtlinie für ausgehende Spamnachrichten zu verwenden, um Administratoren und andere Benutzer zu benachrichtigen.** Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

   Wenn Sie fertig sind, klicken Sie auf **Weiter**.

6. Überprüfen Sie auf der angezeigten Seite **Überprüfung** Ihre Einstellungen. Sie können in jedem Abschnitt **Bearbeiten** auswählen, um die Einstellungen in diesem Abschnitt zu ändern. Alternativ können Sie auf **Zurück** klicken oder die entsprechende Seite im Assistenten auswählen.

   Wenn Sie den Vorgang abgeschlossen haben, klicken Sie auf **Erstellen**.

7. Klicken Sie in der angezeigten Bestätigungsseite auf **Fertig**.

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Anzeigen ausgehender Spamrichtlinien

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antispam.**

2. Suchen Sie auf der Seite **Antispamrichtlinien** nach einem der folgenden Werte:
   - Der **Typwert** ist **eine benutzerdefinierte Richtlinie für ausgehende Spamnachrichten.**
   - Der **Name-Wert** ist **eine ausgehende Antispamrichtlinie (Standardeinstellung)**

   Die folgenden Eigenschaften werden in der Liste der Antispamrichtlinien angezeigt:

   - **Name**
   - **Status**
   - **Priorität**
   - **Typ**

3. Wenn Sie eine Richtlinie für ausgehende Spamnachrichten auswählen, indem Sie auf den Namen klicken, werden die Richtlinieneinstellungen in einem Flyout angezeigt.

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Ändern ausgehender Spamrichtlinien

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antispam.**

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** eine ausgehende Spamrichtlinie aus der Liste aus, indem Sie auf den Namen klicken:
   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, bei der der Wert in der Spalte **"Typ"** **eine benutzerdefinierte Richtlinie für ausgehende Spamnachrichten** ist.
   - Die Standardrichtlinie mit dem Namen **Antispam ausgehende Richtlinie (Standard).**

3. Wählen Sie im angezeigten Flyout für die Richtliniendetails in jedem Abschnitt die Option **Bearbeiten** aus, um die Einstellungen innerhalb des Abschnitts zu ändern. Weitere Informationen zu den Einstellungen finden Sie im abschnitt ["Verwenden des Microsoft 365 Defender-Portals zum Erstellen ausgehender Spamrichtlinien"](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies) in diesem Artikel.

   Für die standardmäßige richtlinie für ausgehende Spamnachrichten ist der Abschnitt **"Angewendet auf"** nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>Aktivieren oder Deaktivieren von benutzerdefinierten ausgehenden Spamrichtlinien

Sie können die standardmäßige richtlinie für ausgehende Spamnachrichten nicht deaktivieren.

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antispam.**

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie einen der folgenden Werte sehen:
   - **Richtlinie deaktiviert**: Um die Richtlinie zu aktivieren, klicken Sie auf ![Symbol „Aktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Aktivieren**.
   - **Richtlinie aktiviert**: Um die Richtlinie zu deaktivieren, klicken Sie auf ![Symbol „Deaktivieren“](../../media/m365-cc-sc-turn-on-off-icon.png) **Deaktivieren**.

4. Klicken Sie im angezeigten Bestätigungsdialog auf **Aktivieren** oder **Deaktivieren**.

5. Klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

Zurück auf der Richtlinien-Hauptseite wird der Wert **Status** der Richtlinie **Aktiviert** oder **Deaktiviert** sein.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten ausgehenden Spamrichtlinien

Standardmäßig erhalten ausgehende Spamrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Um die Priorität einer Richtlinie zu ändern, klicken Sie in den Eigenschaften der Richtlinie auf **"Priorität erhöhen"** oder **"Priorität verringern"** (Sie können die **Prioritätsnummer** im Microsoft 365 Defender-Portal nicht direkt ändern). Die Priorität einer Richtlinie zu verändern macht nur Sinn, wenn Sie mehrere Richtlinien haben.

 **Anmerkungen**:

- Im Microsoft 365 Defender-Portal können Sie die Priorität der Richtlinie für ausgehende Spamnachrichten erst ändern, nachdem Sie sie erstellt haben. In PowerShell können Sie die standardmäßige Priorität bereits beim Erstellen der Spamfilterregel überschreiben (was sich auf die Priorität vorhandener Regeln auswirken kann).
- Ausgehende Spamrichtlinien werden in der Reihenfolge verarbeitet, in der sie angezeigt werden (die erste Richtlinie hat den **Prioritätswert** 0). Die standardmäßige richtlinie für ausgehende Spamnachrichten hat den Prioritätswert **Niedrigste**, und Sie können sie nicht ändern.

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antispam.**

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken.

3. Ganz oben im angezeigten Flyout der Richtliniendetails werden Sie **Priorität erhöhen** oder **Priorität verringern** sehen, abhängig vom aktuellen Prioritätswert und der Anzahl der benutzerdefinierten Richtlinien:
   - Für die Richtlinie für ausgehende Spamnachrichten mit dem **Prioritätswert** **0** ist nur die Option **"Priorität verringern"** verfügbar.
   - Für die Richtlinie für ausgehende Spamnachrichten mit dem niedrigsten **Prioritätswert** (z. B. **3)** ist nur die Option **"Priorität erhöhen"** verfügbar.
   - Wenn Sie über drei oder mehr ausgehende Spamrichtlinien verfügen, stehen richtlinien zwischen den Werten mit der höchsten und der niedrigsten Priorität sowohl die Optionen **"Priorität erhöhen"** als auch **"Verringern"** zur Verfügung.

   Klicken Sie auf ![Symbol „Priorität erhöhen“](../../media/m365-cc-sc-increase-icon.png) **Priorität erhöhen** oder ![Symbol „Priorität verringern“](../../media/m365-cc-sc-decrease-icon.png) **Priorität verringern**, um den **Prioritätswert** zu ändern.

4. Wenn Sie den Vorgang abgeschlossen haben, klicken Sie im Flyout der Richtliniendetails auf **Schließen**.

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>Verwenden des Microsoft 365 Defender-Portals zum Entfernen benutzerdefinierter ausgehender Spamrichtlinien

Wenn Sie das Microsoft 365 Defender-Portal verwenden, um eine benutzerdefinierte ausgehende Spamrichtlinie zu entfernen, werden die Spamfilterregel und die entsprechende Spamfilterrichtlinie gelöscht. Sie können die standardmäßige Richtlinie für ausgehende Spamnachrichten nicht entfernen.

1. Wechseln Sie im Microsoft 365 **Defender-Portal zu E-Mail-& Richtlinien** für die Zusammenarbeit & Richtlinien für \> **Bedrohungsrichtlinien** für Regeln \>  \>  \> **Antispam.**

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** eine Richtlinie mit dem **Typwert** **"Benutzerdefinierte ausgehende Spamrichtlinie"** aus der Liste aus, indem Sie auf den Namen klicken. Ganz oben auf dem angezeigten Flyout der Richtliniendetails klicken Sie auf ![Symbol „Weiter Aktionen“](../../media/m365-cc-sc-more-actions-icon.png) **Weitere Aktionen** \> ![Symbol „Richtlinie löschen“](../../media/m365-cc-sc-delete-icon.png) **Richtlinie löschen**.

3. Klicken Sie im angezeigten Bestätigungsdialog auf **Ja**.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies&quot;></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren ausgehender Spamrichtlinien

Wie zuvor beschrieben besteht eine Richtlinie für ausgehende Spamnachrichten aus einer Richtlinie für ausgehende Spamfilter und einer ausgehenden Spamfilterregel.

In Exchange Online PowerShell oder der eigenständigen EOP-PowerShell ist der Unterschied zwischen ausgehenden Spamfilterrichtlinien und ausgehenden Spamfilterregeln offensichtlich. Sie verwalten ausgehende Spamfilterrichtlinien mithilfe der Cmdlets **\* &quot;-HostedOutboundSpamFilterPolicy&quot;** und ausgehende Spamfilterregeln mithilfe der Cmdlets **\* &quot;-HostedOutboundSpamFilterRule&quot;.**

- In PowerShell erstellen Sie zuerst die Richtlinie für den ausgehenden Spamfilter und dann die Ausgehende Spamfilterregel, die die Richtlinie identifiziert, für die die Regel gilt.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für den ausgehenden Spamfilter und die Ausgehende Spamfilterregel separat.
- Wenn Sie eine Richtlinie für ausgehende Spamfilter aus PowerShell entfernen, wird die entsprechende ausgehende Spamfilterregel nicht automatisch entfernt und umgekehrt.

### <a name=&quot;use-powershell-to-create-outbound-spam-policies&quot;></a>Verwenden von PowerShell zum Erstellen ausgehender Spamrichtlinien

Das Erstellen einer Richtlinie für ausgehende Spamnachrichten in PowerShell besteht aus zwei Schritten:

1. Erstellen Sie die Richtlinie für den ausgehenden Spamfilter.
2. Erstellen Sie die Filterregel für ausgehende Spamnachrichten, die die Richtlinie für den ausgehenden Spamfilter angibt, auf die die Regel angewendet wird.

   **Hinweise**:

   - Sie können eine neue ausgehende Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für ausgehende Spamfilter zuweisen. Eine Ausgehende Spamfilterregel kann nicht mehr als einer Richtlinie für ausgehende Spamfilter zugeordnet werden.
   - Sie können die folgenden Einstellungen für neue richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Microsoft 365 Defender-Portal verfügbar sind:
     - Erstellen Sie die neue Richtlinie als deaktiviert _(aktiviert_ `$false` für das Cmdlet **&quot;New-HostedOutboundSpamFilterRule").**
     - Legen Sie die Priorität der Richtlinie während der Erstellung _(Priorität)_ _\<Number\>_ für das Cmdlet **"New-HostedOutboundSpamFilterRule"** fest.
   - Eine neue ausgehende Spamfilterrichtlinie, die Sie in PowerShell erstellen, ist erst im Microsoft 365 Defender-Portal sichtbar, wenn Sie die Richtlinie einer ausgehenden Spamfilterregel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter

Verwenden Sie diese Syntax, um eine Richtlinie für ausgehende Spamfilter zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine neue Richtlinie für ausgehende Spamfilter mit dem Namen Contoso Executives mit den folgenden Einstellungen erstellt:

- Die Empfängerratengrenzen sind auf kleinere Werte beschränkt, die standardmäßig verwendet werden. Weitere Informationen finden Sie unter [Senden von Grenzwerten für Microsoft 365 Optionen.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- Nachdem einer der Grenzwerte erreicht wurde, wird der Benutzer am Senden von Nachrichten gehindert.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine neue ausgehende Spamfilterregel namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Die Richtlinie für ausgehende Spamfilter mit dem Namen Contoso Executives ist der Regel zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Anzeigen ausgehender Spamfilterrichtlinien

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller richtlinien für ausgehende Spamfilter zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die Richtlinie für ausgehende Spamfilter mit dem Namen "Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-HostedOutboundSpamFilterPolicy".](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Anzeigen ausgehender Spamfilterregeln

Verwenden Sie die folgende Syntax, um vorhandene Regeln für ausgehende Spamfilter anzuzeigen:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterregeln zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Führen Sie die folgenden Befehle aus, um die Liste nach aktivierten oder deaktivierten Regeln zu filtern:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten ausgehenden Spamfilterregel zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die Filterregel für ausgehende Spamnachrichten mit dem Namen "Contoso Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-HostedOutboundSpamFilterRule".](/powershell/module/exchange/get-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern ausgehender Spamfilterrichtlinien

Die gleichen Einstellungen sind verfügbar, wenn Sie eine Schadsoftwarefilterrichtlinie in PowerShell ändern, wie beim Erstellen der Richtlinie, wie in [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) weiter oben in diesem Artikel beschrieben.

> [!NOTE]
> Sie können eine Richtlinie für ausgehende Spamfilter nicht umbenennen (das Cmdlet **"Set-HostedOutboundSpamFilterPolicy"** hat keinen _Name-Parameter)._ Wenn Sie eine Richtlinie für ausgehende Spamnachrichten im Microsoft 365 Defender-Portal umbenennen, werden Sie nur die _Filterregel_ für ausgehende Spamnachrichten umbenennen.

Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-HostedOutboundSpamFilterPolicy".](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern ausgehender Spamfilterregeln

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern, ist der _Parameter "Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener ausgehender Spamfilterregeln finden Sie im nächsten Abschnitt.

Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern. Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im [Abschnitt "Schritt 2: Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel"](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Set-HostedOutboundSpamFilterRule".](/powershell/module/exchange/set-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren ausgehender Spamfilterregeln

Das Aktivieren oder Deaktivieren einer ausgehenden Spamfilterregel in PowerShell aktiviert oder deaktiviert die gesamte Richtlinie für ausgehende Spamnachrichten (die Filterregel für ausgehende Spamnachrichten und die zugewiesene Richtlinie für ausgehende Spamfilter). Sie können die standardmäßige Richtlinie für ausgehende Spamnachrichten nicht aktivieren oder deaktivieren (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die ausgehende Spamfilterregel namens "Marketing Department" deaktiviert.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-HostedOutboundSpamFilterRule"](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und ["Disable-HostedOutboundSpamFilterRule".](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität ausgehender Spamfilterregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilterregel in PowerShell festzulegen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Um die Priorität einer neuen Regel beim Erstellen festzulegen, verwenden Sie stattdessen den Parameter _"Priority"_ im Cmdlet **"New-HostedOutboundSpamFilterRule".**
- Die ausgehende Standard-Spamfilterrichtlinie verfügt nicht über eine entsprechende Spamfilterregel, und sie hat immer den unveränderlichen Prioritätswert **Lowest**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Entfernen ausgehender Spamfilterrichtlinien

Wenn Sie PowerShell zum Entfernen einer Richtlinie für ausgehende Spamfilter verwenden, wird die entsprechende Ausgehende Spamfilterregel nicht entfernt.

Verwenden Sie die folgende Syntax, um eine richtlinie für ausgehende Spamfilter in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter mit dem Namen "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Entfernen ausgehender Spamfilterregeln

Wenn Sie PowerShell verwenden, um eine ausgehende Spamfilterregel zu entfernen, wird die entsprechende Richtlinie für den ausgehenden Spamfilter nicht entfernt.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die ausgehende Spamfilterregel namens "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Weitere Informationen

[Entfernen von blockierten Benutzern aus dem Portal „Eingeschränkte Benutzer“](removing-user-from-restricted-users-portal-after-spam.md)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.yml)

[Bericht über automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md)
