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
description: Administratoren erfahren, wie Sie ausgehende Spamrichtlinien in EOP Exchange Online Protection anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ead8aa75c0218dd2c4cad96e50e37ed3ddc12815
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583193"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurieren der Filterung ausgehender Spamnachrichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden ausgehende E-Mail-Nachrichten, die über EOP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.

Ausgehender Spam von einem Benutzer in Ihrer Organisation weist in der Regel auf ein gefährdetes Konto hin. Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spamzuvertrauungsstufe oder SCL) und durch den Pool mit hohem Risiko für die Zustellung geroutet, um die Reputation des Diensts zu schützen (d. h., Microsoft 365 [Quell-E-Mail-Server](high-risk-delivery-pool-for-outbound-messages.md) von IP-Sperrlisten abzuschalten). Administratoren werden automatisch über Benachrichtigungsrichtlinien über verdächtige ausgehende E-Mail-Aktivitäten und [blockierte Benutzer benachrichtigt.](../../compliance/alert-policies.md)

EOP verwendet ausgehende Spamrichtlinien als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Spam. Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).

Administratoren können die standardmäßige ausgehende Spamrichtlinie anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte ausgehende Spamrichtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können ausgehende Spamrichtlinien im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) konfigurieren.

Die grundlegenden Elemente einer ausgehenden Spamrichtlinie in EOP sind:

- **Die Richtlinie für ausgehende Spamfilter**: Gibt die Aktionen für die Filterung ausgehender Spamfilter und die Benachrichtigungsoptionen an.
- **Die Filterregel für ausgehende** Spamnachrichten : Gibt die Priorität und empfängerfilter (auf wen die Richtlinie angewendet wird) für eine Richtlinie für ausgehende Spamfilter an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spamrichtlinien im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilterregel und die zugeordnete Richtlinie für ausgehende Spamfilter gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled or disabled und empfängerfiltern die Filterregel für ausgehende Spamnachrichten. Alle anderen Einstellungen ändern die zugeordnete Richtlinie für ausgehende Spamfilter.
- Wenn Sie eine Richtlinie entfernen, werden die Filterregel für ausgehende Spamnachrichten und die zugehörige Richtlinie für ausgehende Spamfilter entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt Verwenden von [Exchange Online PowerShell oder eigenständiger EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) zum Konfigurieren ausgehender Spamrichtlinien weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte ausgehende Spamrichtlinie mit dem Namen Default, die über die folgenden Eigenschaften verfügt:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, auch wenn der Richtlinie keine ausgehende Spamfilterregel (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität der Filterung ausgehender Spamnachrichten zu erhöhen, können Sie benutzerdefinierte ausgehende Spamrichtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Zum Hinzufügen, Ändern und Löschen ausgehender Spamrichtlinien müssen Sie Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.
  - Für den schreibgeschützten Zugriff auf ausgehende Spamrichtlinien müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  > [!NOTE]
  > - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  > 
  > - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für ausgehende Spamrichtlinien finden Sie unter [EOP-Richtlinieneinstellungen für ausgehende Spamfilter](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings).

- Die [](../../compliance/alert-policies.md) Standardbenachrichtigungsrichtlinien mit dem Namen E-Mail-Sendegrenzwert **überschritten,** verdächtige E-Mail-Sendemuster erkannt und Benutzer, der vom Senden von E-Mails eingeschränkt ist, sendet bereits E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** (**Globale** Administratoren ) über ungewöhnliche ausgehende E-Mail-Aktivitäten und blockierte Benutzer aufgrund ausgehender Spamnachrichten.  Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spamrichtlinien zu verwenden.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Erstellen ausgehender Spamrichtlinien

Beim Erstellen einer benutzerdefinierten ausgehenden Spamrichtlinie im Security & Compliance Center werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf **Ausgehende Richtlinie erstellen.**

3. Konfigurieren Sie **im geöffneten** Fly-Out der Richtlinie für ausgehende Spamfilter die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

4. (Optional) Erweitern Sie den **Abschnitt Benachrichtigungen,** um zusätzliche Benutzer zu konfigurieren, die Kopien und Benachrichtigungen über verdächtige ausgehende E-Mail-Nachrichten erhalten sollen:

   - **Senden einer Kopie verdächtiger** ausgehender E-Mail-Nachrichten an bestimmte Personen: Diese Einstellung fügt die angegebenen Benutzer als Bcc-Empfänger zu den verdächtigen ausgehenden Nachrichten hinzu.

     > [!NOTE]
     > Diese Einstellung funktioniert nur in der standardmäßigen ausgehenden Spamrichtlinie. Es funktioniert nicht in benutzerdefinierten ausgehenden Spamrichtlinien, die Sie erstellen.

     So aktivieren Sie diese Einstellung:

     1. Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.

     1. Klicken **Sie auf Personen hinzufügen**. Im **Angezeigten Flyout** Empfänger hinzufügen oder entfernen:

     1. Geben Sie die E-Mail-Adresse des Absenders ein. Sie können mehrere E-Mail-Adressen angeben, die durch Semikolons getrennt sind (;) oder ein Empfänger pro Zeile.

     1. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) , um die Empfänger hinzuzufügen.

        Wiederholen Sie diese Schritte so oft wie nötig.

        Die hinzugefügten Empfänger werden im Abschnitt **Empfängerliste** des Flyouts angezeigt. Klicken Sie zum Löschen eines Empfängers ![ auf Schaltfläche Entfernen ](../../media/scc-remove-icon.png) .

     1. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

        Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

   - **Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam blockiert wird:**

     > [!IMPORTANT]
     >
     > - Diese Einstellung ist gerade dabei, ausgehende Spamrichtlinien als veraltet zu verstehen.
     >
     > - Die [](../../compliance/alert-policies.md)  **Standardbenachrichtigungsrichtlinie**"Benutzer, der vom Senden von E-Mails eingeschränkt ist" sendet bereits E-Mail-Benachrichtigungen an Mitglieder der **Gruppe TenantAdmins** ( Globale Administratoren ), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt Empfängerbeschränkungen blockiert **werden.** **Es wird dringend empfohlen, die Warnungsrichtlinie** anstelle dieser Einstellung in der Richtlinie für ausgehende Spamnachrichten zu verwenden, um Administratoren und andere Benutzer zu benachrichtigen. Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

5. (Optional) Erweitern Sie den **Abschnitt Empfängerbeschränkungen,** um die Grenzwerte und Aktionen für verdächtige ausgehende E-Mail-Nachrichten zu konfigurieren:

   > [!NOTE]
   > Diese Einstellungen gelten nur für cloudbasierte Postfächer.

   - **Maximale Anzahl von Empfängern pro Benutzer**

     Ein gültiger Wert ist 0 bis 10000. Der Standardwert ist 0, d. h. die Diensteinstellungen werden verwendet. Weitere Informationen finden Sie unter [Senden von Grenzwerten](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1).

     - **Externe Stündlichgrenze:** Die maximale Anzahl externer Empfänger pro Stunde.

     - **Interner Stundengrenzwert:** Die maximale Anzahl interner Empfänger pro Stunde.

     - **Täglicher Grenzwert:** Die maximale Gesamtanzahl von Empfängern pro Tag.

   - **Aktion, wenn ein Benutzer die oben genannten Grenzwerte überschreitet:** Konfigurieren Sie die Aktion, die beim Überschreiten eines der **Empfängergrenzwerte** zu ergreifen ist. Für alle Aktionen erhalten die  empfänger, die in der Richtlinie "Benutzer" das Senden von E-Mail-Benachrichtigungsrichtlinien eingeschränkt haben (und in der nun **redundanten** Benachrichtigung bestimmter Personen, wenn ein Absender aufgrund der Einstellung für ausgehende Spamnachrichten in der Richtlinie für ausgehende Spamnachrichten blockiert ist, E-Mail-Benachrichtigungen.

     - **Beschränken Sie den Benutzer am Senden von E-Mails** bis zum folgenden Tag : Dies ist der Standardwert. E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann erst am folgenden Tag basierend auf der UTC-Zeit weitere Nachrichten senden. Der Administrator kann diesen Block nicht überschreiben.

       - Die Aktivitätswarnung mit **dem Namen Benutzer,** der das Senden von E-Mails beschränkt hat, benachrichtigt Administratoren (per E-Mail und auf der Seite **Benachrichtigungen** anzeigen).

       - Alle empfänger, die in der **Richtlinie Bestimmte Personen** benachrichtigen angegeben werden, wenn ein Absender aufgrund des Sendens ausgehender Spameinstellungen in der Richtlinie blockiert wird, werden ebenfalls benachrichtigt.

       - Der Benutzer kann erst am folgenden Tag basierend auf der UTC-Zeit weitere Nachrichten senden. Der Administrator kann diesen Block nicht überschreiben.

     - Benutzer vom Senden von E-Mails **einschränken:** E-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem **[Eingeschränkten Benutzer]-Portal <https://sip.protection.office.com/restrictedusers>** im  Security & Compliance Center hinzugefügt, und der Benutzer kann keine E-Mails senden, bis er vom Administrator aus dem Portal für eingeschränkte Benutzer entfernt wurde. Nachdem ein Administrator den Benutzer aus der Liste entfernt hat, wird der Benutzer für diesen Tag nicht mehr eingeschränkt. Anweisungen finden Sie unter Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden [von Spam-E-Mails.](removing-user-from-restricted-users-portal-after-spam.md)

     - **Keine Aktion, nur Warnung:** E-Mail-Benachrichtigungen werden gesendet.

6. (Optional) Erweitern Sie den Abschnitt Automatische **Weiterleitung,** um die automatische E-Mail-Weiterleitung durch Benutzer an externe Absender zu steuern. Weitere Informationen finden Sie unter [Steuerung der automatischen externen E-Mail-Weiterleitung in Microsoft 365](external-email-forwarding.md).

   > [!NOTE]
   >
   > - Vor September 2020 sind diese Einstellungen verfügbar, werden jedoch nicht erzwungen.
   >
   > - Diese Einstellungen gelten nur für cloudbasierte Postfächer.
   >
   > - Wenn die automatische Weiterleitung deaktiviert ist, erhält der Empfänger einen Unzustellbarkeitsbericht (auch NDR oder Unzustellbarkeitsnachricht bezeichnet), wenn externe Absender E-Mails an ein Postfach senden, für das die Weiterleitung aktiviert ist. Wenn die Nachricht von einem  internen Absender gesendet wird und die Weiterleitungsmethode die Postfach-Weiterleitung [(auch](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _als SMTP-Weiterleitung_ bezeichnet) ist, wird der interne Absender den NDR erhalten. Der interne Absender bekommt keinen Unndr, wenn die Weiterleitung aufgrund einer Posteingangsregel erfolgt ist.

   Die verfügbaren Werte sind:

   - Automatisch – Systemgesteuert: Ermöglicht die automatische externe **E-Mail-Weiterleitung** durch ausgehende Spamfilterung. Dies ist der Standardwert.
   - **On**: Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.
   - **Off**: Die Richtlinie deaktiviert die automatische externe E-Mail-Weiterleitung.

7. (Erforderlich) Erweitern Sie den **Abschnitt Angewendet auf,** um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.

    Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<sender1\>_ oder _\<sender2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<sender1\>_ und _\<member of group 1\>_).

    Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken. Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.

    - **Die Absenderdomäne ist**: Gibt Absender in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an. Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen. Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.

    - **Absender ist**: Gibt einen oder mehrere Benutzer in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf **das Feld Tag hinzufügen,** um weitere Absender auszuwählen.

    - **Sender ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf **das Feld Tag hinzufügen,** um weitere Absender auszuwählen.

    - **Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

8. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Anzeigen ausgehender Spamrichtlinien mithilfe & Security & Compliance Center

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um eine richtlinie für ausgehende Spamnachrichten zu erweitern:

   - Die Standardrichtlinie mit dem **Namen Ausgehende Spamfilterrichtlinie**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der **Spalte Typ** **benutzerdefinierte ausgehende Spamrichtlinie ist.**

3. Die Richtlinieneinstellungen werden in den angezeigten erweiterten Richtliniendetails angezeigt, oder Sie können auf **Richtlinie bearbeiten klicken.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Ändern ausgehender Spamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um eine richtlinie für ausgehende Spamnachrichten zu erweitern:

   - Die Standardrichtlinie mit dem **Namen Ausgehende Spamfilterrichtlinie**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der **Spalte Typ** **benutzerdefinierte ausgehende Spamrichtlinie ist.**

3. Klicken Sie auf **Richtlinie bearbeiten**.

Für benutzerdefinierte ausgehende Spamrichtlinien sind die verfügbaren Einstellungen im angezeigten Flyout mit den im Abschnitt Verwenden des Security & Compliance Center zum Erstellen ausgehender [Spamrichtlinien](#use-the-security--compliance-center-to-create-outbound-spam-policies) beschriebenen Einstellungen identisch.

Für die standardmäßige ausgehende Spamrichtlinie  **mit** dem Namen Ausgehende Spamfilterrichtlinie ist der Abschnitt Angewendet auf nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivieren oder Deaktivieren ausgehender Spamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf Symbol erweitern, um eine von Ihnen erstellte benutzerdefinierte Richtlinie zu erweitern (der Wert in der Spalte Typ ![ ist ](../../media/scc-expand-icon.png) **Benutzerdefinierte ausgehende Spamrichtlinie**). 

3. Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.

   Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Umschaltfläche ein](../../media/scc-toggle-on.png)

Sie können die standardmäßige richtlinie für ausgehende Spamnachrichten nicht deaktivieren.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten ausgehenden Spamrichtlinien

Standardmäßig erhalten ausgehende Spamrichtlinien eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Benutzerdefinierte ausgehende Spamrichtlinien werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0). Die standardmäßige ausgehende Spamrichtlinie namens **Ausgehende Spamfilterrichtlinie** hat den Prioritätswert **Lowest**, und Sie können sie nicht ändern.

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Suchen Sie auf der Seite **Antispameinstellungen** die Richtlinien, bei denen der Wert in der **Spalte Typ** benutzerdefinierte **ausgehende Spamrichtlinie ist.** Beachten Sie die Werte in der Spalte **Priorität**:

   - Die benutzerdefinierte ausgehende Spamrichtlinie mit der höchsten Priorität hat den Wert ![ Nach-unten-Symbol ](../../media/ITPro-EAC-DownArrowIcon.png) **0**.

   - Die benutzerdefinierte ausgehende Spamrichtlinie mit der niedrigsten Priorität hat den Wert Nach-oben-Symbol n (z. B. ![ ](../../media/ITPro-EAC-UpArrowIcon.png)  ![ Nach-oben-Symbol ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Wenn Sie über drei oder mehr benutzerdefinierte ausgehende Spamrichtlinien verfügen, haben die Richtlinien zwischen der höchsten und der niedrigsten Priorität werte Nach-oben-Symbol Nach-unten-Symbol n (z. B. Nach-oben-Symbol Nach-unten-Symbol ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**).

3. Klicken Sie auf ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) oder ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) , um die benutzerdefinierte ausgehende Spamrichtlinie in der Prioritätsliste nach oben oder unten zu verschieben.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Entfernen ausgehender Spamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der Seite **Antispameinstellungen** auf Symbol erweitern, um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte Typ ![ ist ](../../media/scc-expand-icon.png) **Benutzerdefinierte ausgehende Spamrichtlinie**). 

3. Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.

4. Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Verwenden Exchange Online PowerShell oder eigenständiger EOP PowerShell zum Konfigurieren ausgehender Spamrichtlinien

Wie bereits beschrieben, besteht eine richtlinie für ausgehende Spamnachrichten aus einer Filterrichtlinie für ausgehende Spamnachrichten und einer Filterregel für ausgehende Spamnachrichten.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell ist der Unterschied zwischen ausgehenden Spamfilterrichtlinien und regeln für ausgehende Spamfilter offensichtlich. Sie verwalten ausgehende Spamfilterrichtlinien mithilfe der **\* -HostedOutboundSpamFilterPolicy-Cmdlets,** und Sie verwalten ausgehende Spamfilterregeln mithilfe der **\* Cmdlets -HostedOutboundSpamFilterRule.**

- In PowerShell erstellen Sie zuerst die Richtlinie für ausgehende Spamfilter und dann die Filterregel für ausgehende Spamnachrichten, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Richtlinie für ausgehende Spamfilter und die Filterregel für ausgehende Spamnachrichten separat.
- Wenn Sie eine Richtlinie für ausgehende Spamfilter aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Erstellen ausgehender Spamrichtlinien mithilfe von PowerShell

Das Erstellen einer ausgehenden Spamrichtlinie in PowerShell ist ein zweischrittiger Prozess:

1. Erstellen Sie die Richtlinie für ausgehende Spamfilter.
2. Erstellen Sie die Filterregel für ausgehende Spamnachrichten, die die Richtlinie für ausgehende Spamfilter angibt, auf die die Regel angewendet wird.

> [!NOTE]
> - Sie können eine neue ausgehende Spamfilterregel erstellen und ihr eine vorhandene, nicht zugeordnete Richtlinie für ausgehende Spamfilter zuweisen. Eine Filterregel für ausgehende Spamnachrichten kann nicht mehr als einer Filterrichtlinie für ausgehende Spamnachrichten zugeordnet werden.
> 
> - Sie können die folgenden Einstellungen für neue ausgehende Spamfilterrichtlinien in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:
> 
>   - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **New-HostedOutboundSpamFilterRule).**
>   - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ _\<Number\>_ ) für das Cmdlet **New-HostedOutboundSpamFilterRule.**
> 
> - Eine neue ausgehende Spamfilterrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Spamfilterregel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Schritt 1: Erstellen einer Richtlinie für ausgehende Spamfilter mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine neue ausgehende Spamfilterrichtlinie namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Die Empfängerrategrenzwerte sind auf kleinere Werte beschränkt, die standardmäßig festgelegt sind. Weitere Informationen finden Sie unter [Senden von Grenzwerten Microsoft 365 Optionen](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Nachdem eine der Grenzwerte erreicht wurde, wird der Benutzer am Senden von Nachrichten gehindert.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Filterregel für ausgehende Spamnachrichten

Verwenden Sie die folgende Syntax, um eine filterregel für ausgehende Spamnachrichten zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine neue ausgehende Spamfilterregel namens Contoso Executives mit den folgenden Einstellungen erstellt:

- Die Richtlinie für ausgehende Spamfilter namens Contoso Executives ist der Regel zugeordnet.
- Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Anzeigen ausgehender Spamfilterrichtlinien mithilfe von PowerShell

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterrichtlinien zurückzukehren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzukehren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilterrichtlinie "Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Anzeigen ausgehender Spamfilterregeln mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um vorhandene Regeln für ausgehende Spamfilter anzeigen zu können:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilterregeln zurückzukehren:

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

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterregel für ausgehende Spamnachrichten zurückzukehren:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilterregel namens Contoso Executives zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern ausgehender Spamfilterrichtlinien

Dieselben Einstellungen sind verfügbar, wenn Sie eine Richtlinie für Schadsoftwarefilter in PowerShell ändern, wie beim Erstellen der Richtlinie, wie im Abschnitt Schritt 1: Verwenden von [PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) beschrieben, um eine Richtlinie für ausgehende Spamfilter zu erstellen.

> [!NOTE]
> Sie können eine Richtlinie für ausgehende Spamfilter nicht umbenennen (das **Cmdlet Set-HostedOutboundSpamFilterPolicy** hat keinen _Name-Parameter)._ Wenn Sie eine ausgehende Spamrichtlinie im Security & Compliance Center umbenennen, wird nur die Filterregel für ausgehende Spamnachrichten _umbenannt._

Verwenden Sie die folgende Syntax, um eine Richtlinie für ausgehende Spamfilter zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern ausgehender Spamfilterregeln

Die einzige Einstellung, die nicht verfügbar ist, wenn Sie eine ausgehende Spamfilterregel in PowerShell ändern, ist der _Parameter Enabled,_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener ausgehender Spamfilterregeln finden Sie im nächsten Abschnitt.

Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine Filterregel für ausgehende Spamnachrichten in PowerShell ändern. Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2:](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) Verwenden von PowerShell zum Erstellen einer ausgehenden Spamfilterregel weiter oben in diesem Artikel beschrieben.

Verwenden Sie die folgende Syntax, um eine filterregel für ausgehende Spamnachrichten zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Aktivieren oder Deaktivieren ausgehender Spamfilterregeln mithilfe von PowerShell

Durch Aktivieren oder Deaktivieren einer ausgehenden Spamfilterregel in PowerShell wird die gesamte richtlinie für ausgehende Spamnachrichten (die Filterregel für ausgehende Spamnachrichten und die zugewiesene Richtlinie für ausgehende Spamfilter) aktiviert oder deaktiviert. Die standardmäßige richtlinie für ausgehende Spamnachrichten kann nicht aktiviert oder deaktiviert werden (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Filterregel für ausgehende Spamnachrichten mit dem Namen Marketing Department deaktiviert.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Festlegen der Priorität ausgehender Spamfilterregeln mithilfe von PowerShell

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilterregel in PowerShell zu setzen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den _Parameter Priority_ im Cmdlet **New-HostedOutboundSpamFilterRule.**
>
> - Die ausgehende Standardmäßige Spamfilterrichtlinie verfügt nicht über eine entsprechende Spamfilterregel und hat immer den nicht veränderbaren Prioritätswert **Lowest**.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Entfernen ausgehender Spamfilterrichtlinien

Wenn Sie PowerShell verwenden, um eine Richtlinie für ausgehende Spamfilter zu entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht entfernt.

Verwenden Sie die folgende Syntax, um eine richtlinie für ausgehende Spamfilter in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Entfernen ausgehender Spamfilterregeln

Wenn Sie PowerShell verwenden, um eine Filterregel für ausgehende Spamnachrichten zu entfernen, wird die entsprechende Richtlinie für ausgehende Spamfilter nicht entfernt.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilterregel in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die filterregel für ausgehende Spamnachrichten mit dem Namen Marketing Department entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Weitere Informationen

[Entfernen von blockierten Benutzern aus dem Portal "Eingeschränkte Benutzer"](removing-user-from-restricted-users-portal-after-spam.md)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.yml)

[Bericht über automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md)