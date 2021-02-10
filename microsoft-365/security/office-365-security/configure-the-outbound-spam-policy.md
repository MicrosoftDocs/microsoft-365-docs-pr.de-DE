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
description: Administratoren können erfahren, wie Sie Richtlinien für ausgehende Spamnachrichten in Exchange Online Protection (EOP) anzeigen, erstellen, ändern und löschen.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b7ba1e398466c448de37060db340c1d20cb1504
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165763"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>Konfigurieren der Filterung ausgehender Spamnachrichten in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden ausgehende E-Mail-Nachrichten, die über EOP gesendet werden, automatisch auf Spam und ungewöhnliche Sendeaktivitäten überprüft.

Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein gefährdetes Konto hin. Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam Confidence Level oder SCL) und über den Pool für besonders riskante Zustelldienste geroutet, um die Reputation des Diensts zu schützen (d. h. microsoft [365-Quell-E-Mail-Server](high-risk-delivery-pool-for-outbound-messages.md) von ip-Sperrlisten zu schützen). Administratoren werden automatisch über verdächtige ausgehende E-Mail-Aktivitäten und blockierte Benutzer über [Warnungsrichtlinien benachrichtigt.](../../compliance/alert-policies.md)

EOP verwendet Richtlinien für ausgehende Spamnachrichten als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Spam. Weitere Informationen finden Sie unter [Antispamschutz](anti-spam-protection.md).

Administratoren können die standardrichtlinie für ausgehende Spamnachrichten anzeigen, bearbeiten und konfigurieren (aber nicht löschen). Für eine höhere Granularität können Sie auch benutzerdefinierte Richtlinien für ausgehende Spamnachrichten erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der standardmäßigen Richtlinie, die Priorität (Reihenfolge der Ausführung) Ihrer benutzerdefinierten Richtlinien können Sie jedoch ändern.

Sie können Richtlinien für ausgehende Spamnachrichten im Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online-Postfächer).

Die grundlegenden Elemente einer Richtlinie für ausgehende Spamnachrichten in EOP sind:

- **Die Filterrichtlinie für ausgehende Spamnachrichten:** Gibt die Aktionen für Filterungen für ausgehende Spamnachrichten und die Benachrichtigungsoptionen an.
- **Die Filterregel für ausgehende Spamnachrichten:** Gibt die Prioritäts- und Empfängerfilter (für wen die Richtlinie gilt) für eine Filterrichtlinie für ausgehende Spamnachrichten an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie richtlinien für ausgehende Spamnachrichten im Security & Compliance Center verwalten:

- Wenn Sie eine Richtlinie erstellen, erstellen Sie tatsächlich eine Filterregel für ausgehende Spamnachrichten und die zugeordnete Filterrichtlinie für ausgehende Spamnachrichten gleichzeitig mit demselben Namen für beide.
- Wenn Sie eine Richtlinie ändern, ändern Einstellungen im Zusammenhang mit name, priority, enabled or disabled und recipient filters die Filterregel für ausgehende Spamnachrichten. Alle anderen Einstellungen ändern die zugeordnete Filterrichtlinie für ausgehende Spamnachrichten.
- Wenn Sie eine Richtlinie entfernen, werden die Filterregel für ausgehende Spamnachrichten und die zugeordnete Filterrichtlinie für ausgehende Spamnachrichten entfernt.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell verwalten Sie die Richtlinie und die Regel getrennt. Weitere Informationen finden Sie im Abschnitt "Verwenden von Exchange Online PowerShell oder der eigenständigen [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) zum Konfigurieren von Richtlinien für ausgehende Spamnachrichten" weiter unten in diesem Artikel.

Jede Organisation verfügt über eine integrierte Richtlinie für ausgehende Spamnachrichten mit dem Namen "Standard", die über die folgenden Eigenschaften verfügt:

- Die Richtlinie wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine Filterregel für ausgehende Spamnachrichten (Empfängerfilter) zugeordnet ist.
- Die Richtlinie weist den benutzerdefinierten Prioritätswert **Niedrigster** auf, der nicht geändert werden kann (die Richtlinie wird immer als letztes angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer Vorrang vor der Richtlinie „Standard“.
- Die Richtlinie ist die Standardrichtlinie (die **IsDefault**-Eigenschaft hat den Wert `True`), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität der Filterung ausgehender Spamnachrichten zu erhöhen, können Sie benutzerdefinierte Richtlinien für ausgehende Spamnachrichten mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen im Security & Compliance Center Berechtigungen zugewiesen werden.
  - Zum Hinzufügen, Ändern und Löschen von Richtlinien für ausgehende Spamnachrichten müssen Sie Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.
  - Für den schreibgeschützten Zugriff auf Richtlinien für ausgehende  Spamnachrichten müssen Sie Mitglied der Rollengruppe "Globaler Leser" oder **"Sicherheitsleseprogramm"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

  **Hinweise**:

  - Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.

- Die empfohlenen Einstellungen für Richtlinien für ausgehende Spamnachrichten finden Sie unter [EOP outbound spam filter policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- Die [](../../compliance/alert-policies.md) Standardmäßigen Benachrichtigungsrichtlinien mit dem Namen "Grenzwert  für das Senden von E-Mails" wurden **überschritten,** verdächtige E-Mail-Sendemuster wurden erkannt, und der Benutzer, der am Senden von E-Mails eingeschränkt war, sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **"TenantAdmins"** **(globale** Administratoren) zu ungewöhnlichen ausgehenden E-Mail-Aktivitäten und blockierten Benutzern aufgrund ausgehender Spamnachrichten.  Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users) Es wird empfohlen, diese Benachrichtigungsrichtlinien anstelle der Benachrichtigungsoptionen in Richtlinien für ausgehende Spamnachrichten zu verwenden.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von Richtlinien für ausgehende Spamnachrichten

Beim Erstellen einer benutzerdefinierten Richtlinie für ausgehenden Spam im Security & Compliance Center werden die Spamfilterregel und die zugeordnete Spamfilterrichtlinie gleichzeitig mit demselben Namen für beide erstellt.

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie **auf der Seite "Antispameinstellungen"** auf **"Ausgehende Richtlinie erstellen".**

3. Konfigurieren Sie **im geöffneten** Flyout für die Filterrichtlinie für ausgehende Spamnachrichten die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, aussagekräftigen Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

4. (Optional) Erweitern  Sie den Abschnitt "Benachrichtigungen", um weitere Benutzer zu konfigurieren, die Kopien und Benachrichtigungen über verdächtige ausgehende E-Mail-Nachrichten erhalten sollen:

   - **Senden Sie eine Kopie verdächtiger** ausgehender E-Mail-Nachrichten an bestimmte Personen: Diese Einstellung fügt die angegebenen Benutzer als Bcc-Empfänger zu den verdächtigen ausgehenden Nachrichten hinzu.

     > [!NOTE]
     > Diese Einstellung funktioniert nur in der standardrichtlinie für ausgehende Spamnachrichten. Es funktioniert nicht in benutzerdefinierten Richtlinien für ausgehende Spamnachrichten, die Sie erstellen.

     So aktivieren Sie diese Einstellung:

     1. Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.

     1. Klicken Sie **auf Personen hinzufügen.** Im **angezeigten Flyout zum Hinzufügen** oder Entfernen von Empfängern:

     1. Geben Sie die E-Mail-Adresse des Absenders ein. Mehrere E-Mail-Adressen können durch Semikolons getrennt angegeben werden (;) oder ein Empfänger pro Zeile.

     1. Click ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) , um die Empfänger hinzuzufügen.

        Wiederholen Sie diese Schritte so oft wie nötig.

        Die hinzugefügten Empfänger werden im **Flyout im** Abschnitt "Empfängerliste" angezeigt. Klicken Sie auf "Entfernen", um einen ![ Empfänger zu ](../../media/scc-remove-icon.png) löschen.

     1. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

        Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

   - **Bestimmte Personen benachrichtigen, wenn ein Absender aufgrund des Sendens von ausgehenden Spamnachrichten blockiert wird:**

     > [!IMPORTANT]
     >
     > - Diese Einstellung ist dabei, ausgehende Spamrichtlinien als veraltet zu markieren.
     >
     > - Die [](../../compliance/alert-policies.md) standardmäßige  **Warnungsrichtlinie** namens "Benutzer, der am Senden von E-Mails eingeschränkt ist" sendet bereits E-Mail-Benachrichtigungen an Mitglieder der Gruppe **"TenantAdmins** ( Globale Administratoren"), wenn Benutzer aufgrund von Überschreitung der Grenzwerte im Abschnitt **"Empfängerbeschränkungen"** blockiert werden. **Es wird dringend empfohlen, die Warnungsrichtlinie** anstelle dieser Einstellung in der Richtlinie für ausgehende Spamnachrichten zu verwenden, um Administratoren und andere Benutzer zu benachrichtigen. Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer.](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

5. (Optional) Erweitern Sie den **Abschnitt "Empfängerbeschränkungen",** um die Grenzwerte und Aktionen für verdächtige ausgehende E-Mail-Nachrichten zu konfigurieren:

   > [!NOTE]
   > Diese Einstellungen gelten nur für cloudbasierte Postfächer.

   - **Maximale Anzahl von Empfängern pro Benutzer**

     Ein gültiger Wert ist 0 bis 10000. Der Standardwert ist 0, was bedeutet, dass die Diensteinstellungen verwendet werden. Weitere Informationen finden Sie unter [Sendegrenzwerte.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)

     - **Externe Stündlichgrenze:** Die maximale Anzahl von externen Empfängern pro Stunde.

     - **Interner Stundengrenzwert:** Die maximale Anzahl interner Empfänger pro Stunde.

     - **Täglicher Grenzwert:** Die maximale Gesamtanzahl von Empfängern pro Tag.

   - **Aktion, wenn ein Benutzer die** oben genannten Grenzwerte überschreitet: Konfigurieren Sie die Aktion, die beim Überschreiten einer der Empfängergrenzwerte zu ergreifen ist.  Für alle Aktionen erhalten die  in der Richtlinie "Benutzer" angegebenen Empfänger das Senden von E-Mail-Benachrichtigungsrichtlinien (und in der nun **redundanten** Benachrichtigung bestimmter Personen, wenn ein Absender aufgrund des Sendens ausgehender Spameinstellungen in der Richtlinie für ausgehende Spamnachrichten blockiert wurde) E-Mail-Benachrichtigungen.

     - **Benutzer am Senden von E-Mails bis zum folgenden Tag** einschränken: Dies ist der Standardwert. E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann basierend auf der UTC-Zeit erst am folgenden Tag weitere Nachrichten senden. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.

       - Die Aktivitätswarnung mit **dem Namen "Benutzer"** ist am Senden von E-Mails eingeschränkt und benachrichtigt Administratoren (per E-Mail und auf der Seite "Benachrichtigungen anzeigen"). 

       - Alle Empfänger, die in der Richtlinie "Bestimmte Personen benachrichtigen" angegeben sind, **wenn** ein Absender aufgrund des Sendens ausgehender Spameinstellungen in der Richtlinie blockiert wird, werden ebenfalls benachrichtigt.

       - Der Benutzer kann basierend auf der UTC-Zeit erst am folgenden Tag weitere Nachrichten senden. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.

     - **Benutzer** am Senden von E-Mails einschränken: E-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem **Portal [Eingeschränkte Benutzer] <https://sip.protection.office.com/restrictedusers>** im  Security & Compliance Center hinzugefügt, und der Benutzer kann keine E-Mails senden, bis er von einem Administrator aus dem Portal für eingeschränkte Benutzer entfernt wurde. Nachdem ein Administrator den Benutzer aus der Liste entfernt hat, wird der Benutzer für diesen Tag nicht erneut eingeschränkt. Anweisungen finden Sie unter Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer [nach dem Senden von Spam-E-Mails.](removing-user-from-restricted-users-portal-after-spam.md)

     - **Keine Aktion, nur Warnung:** E-Mail-Benachrichtigungen werden gesendet.

6. (Optional) Erweitern **Sie den Abschnitt "Automatische Weiterleitung",** um die automatische E-Mail-Weiterleitung durch Benutzer an externe Absender zu steuern. Weitere Informationen finden Sie unter [Steuern der automatischen externen E-Mail-Weiterleitung in Microsoft 365.](external-email-forwarding.md)

   > [!NOTE]
   >
   > - Vor September 2020 sind diese Einstellungen verfügbar, werden jedoch nicht erzwungen.
   >
   > - Diese Einstellungen gelten nur für cloudbasierte Postfächer.
   >
   > - Wenn die automatische Weiterleitung deaktiviert ist, erhält der Empfänger einen Unzustellbarkeitsbericht (auch als NDR oder Unzustellbarkeitsnachricht bezeichnet), wenn externe Absender E-Mails an ein Postfach senden, für das die Weiterleitung aktiviert ist. Wenn die Nachricht von einem  internen Absender gesendet wird und die Weiterleitungsmethode die Postfach weiterleitung [(auch](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) als SMTP-Weiterleitung _bezeichnet)_ ist, wird der interne Absender den NDR erhalten. Der interne Absender bekommt keinen NDR, wenn die Weiterleitung aufgrund einer Posteingangsregel erfolgt ist.

   Die verfügbaren Werte sind:

   - Automatisch – Systemgesteuert: Ermöglicht die Filterung ausgehender Spamnachrichten zum Steuern der automatischen externen **E-Mail-Weiterleitung.** Dies ist der Standardwert.
   - **On:** Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie nicht deaktiviert.
   - **Aus:** Die automatische externe E-Mail-Weiterleitung wird von der Richtlinie deaktiviert.

7. (Erforderlich) Erweitern Sie **den Abschnitt "Angewendet auf",** um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.

    Sie können eine Bedingung oder Ausnahme nur einmal verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Bei mehreren Werten derselben Bedingung oder Ausnahme wird ODER-Logik verwendet (z. B. _\<sender1\>_ oder _\<sender2\>_). Bei unterschiedlichen Bedingungen oder Ausnahmen wird UND-Logik verwendet (z. B. _\<sender1\>_ und _\<member of group 1\>_).

    Um alle verfügbaren Bedingungen anzuzeigen, ist es am einfachsten, wenn Sie auf **Bedingung hinzufügen** klicken. Sie können auf ![Schaltfläche „Entfernen“](../../media/scc-remove-icon.png) klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.

    - **Die Absenderdomäne ist:** Gibt Absender in einer oder mehreren der konfigurierten akzeptierten Domänen in der Organisation an. Klicken Sie in das Feld **Tag hinzufügen**, um eine Domäne anzuzeigen und auszuwählen. Klicken Sie erneut auf das Feld **Tag hinzufügen**, um weitere Domänen auszuwählen, falls mehrere Domänen verfügbar sind.

    - **Absender:** Gibt einen oder mehrere Benutzer in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das **Feld "Tag hinzufügen",** um weitere Absender auszuwählen.

    - **Absender ist Mitglied von**: Gibt eine oder mehrere Gruppen in Ihrer Organisation an. Klicken Sie auf **Tag hinzufügen**, und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das **Feld "Tag hinzufügen",** um weitere Absender auszuwählen.

    - **Außer wenn**: Klicken Sie zum Angeben von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen**, um alle verfügbaren Ausnahmen anzuzeigen. Die Einstellungen und das Verhalten entsprechen genau den Bedingungen.

8. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von Richtlinien für ausgehende Spamnachrichten

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie **auf der Seite "Antispameinstellungen"** auf das Symbol "Erweitern", ![ um eine Richtlinie für ](../../media/scc-expand-icon.png) ausgehende Spamnachrichten zu erweitern:

   - Die Standardrichtlinie mit dem Namen **"Filterrichtlinie für ausgehende Spamnachrichten"**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **"Typ"** die richtlinie für benutzerdefinierte **ausgehende Spamnachrichten ist.**

3. Die Richtlinieneinstellungen werden in den angezeigten erweiterten Richtliniendetails angezeigt, oder Sie können auf **"Richtlinie bearbeiten" klicken.**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Verwenden des Security & Compliance Centers zum Ändern von Richtlinien für ausgehende Spamnachrichten

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie **auf der Seite "Antispameinstellungen"** auf das Symbol "Erweitern", ![ um eine Richtlinie für ](../../media/scc-expand-icon.png) ausgehende Spamnachrichten zu erweitern:

   - Die Standardrichtlinie mit dem Namen **"Filterrichtlinie für ausgehende Spamnachrichten"**.

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **"Typ"** die richtlinie für benutzerdefinierte **ausgehende Spamnachrichten ist.**

3. Klicken Sie auf **Richtlinie bearbeiten**.

Bei benutzerdefinierten Richtlinien für ausgehende Spamnachrichten sind die verfügbaren Einstellungen im angezeigten Flyout mit den einstellungen identisch, die im Abschnitt "Verwenden des [Security & Compliance Centers](#use-the-security--compliance-center-to-create-outbound-spam-policies) zum Erstellen von Richtlinien für ausgehende Spamnachrichten" beschrieben sind.

Für die standardmäßige Richtlinie für ausgehende  Spamnachrichten mit dem Namen "Filterrichtlinie für ausgehende Spamnachrichten" ist der Abschnitt "Angewendet auf" nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Informationen zum Aktivieren oder Deaktivieren einer Richtlinie, zum Festlegen der Prioritätsreihenfolge der Richtlinien oder zum Konfigurieren der Quarantänebenachrichtigungen für Endbenutzer finden Sie in den folgenden Abschnitten.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivieren oder Deaktivieren von Richtlinien für ausgehende Spamnachrichten

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der **Seite "Antispameinstellungen"** auf das Symbol "Erweitern", um eine von Ihnen erstellte benutzerdefinierte Richtlinie zu erweitern (der Wert in der Spalte "Typ" ist "Benutzerdefinierte Richtlinie für ausgehende ![ ](../../media/scc-expand-icon.png) **Spamnachrichten").** 

3. Achten Sie in den angezeigten erweiterten Richtliniendetails auf den Wert in der Spalte **Ein**.

   Schieben Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Umschaltfläche aus](../../media/scc-toggle-off.png)

   Schieben Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Umschaltfläche ein](../../media/scc-toggle-on.png)

Die standardrichtlinie für ausgehende Spamnachrichten kann nicht deaktiviert werden.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten Richtlinien für ausgehende Spamnachrichten

Standardmäßig erhalten Richtlinien für ausgehende Spamnachrichten eine Priorität, die auf der Reihenfolge basiert, in der sie erstellt wurden (neuere Richtlinien haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in der Reihenfolge der Priorität verarbeitet (Richtlinien mit einer höheren Priorität werden vor Richtlinien mit einer niedrigeren Priorität verarbeitet). Keine zwei Richtlinien können die gleiche Priorität aufweisen, und die Richtlinienverarbeitung endet, nachdem die erste Richtlinie angewendet wurde.

Benutzerdefinierte Richtlinien für ausgehende Spamnachrichten werden in der Reihenfolge angezeigt, in der sie verarbeitet werden (die erste Richtlinie hat den **Prioritätswert** 0). Die standardmäßige Richtlinie für ausgehende **Spamnachrichten** mit dem Namen "Filterrichtlinie für ausgehende Spamnachrichten" hat den Prioritätswert **"Niedrigste",** und Sie können sie nicht ändern.

Zum Ändern der Priorität einer Richtlinie verschieben Sie die Richtlinie in der Liste nach oben oder unten (Sie können den **Priorität**-Wert im Security & Compliance Center nicht direkt ändern).

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Suchen Sie **auf der Seite "Antispameinstellungen"** die Richtlinien, bei denen der Wert in der Spalte **"Typ"** die Richtlinie für benutzerdefinierte **ausgehende Spamnachrichten ist.** Beachten Sie die Werte in der Spalte **Priorität**:

   - Die benutzerdefinierte Richtlinie für ausgehende Spamnachrichten mit der höchsten Priorität hat den Wert ![ "NACH-UNTEN-Symbol ](../../media/ITPro-EAC-DownArrowIcon.png) **0".**

   - Die benutzerdefinierte richtlinie für ausgehende Spamnachrichten mit der niedrigsten Priorität hat den Wert NACH-OBEN-Symbol n (z. B. ![ NACH-OBEN-SYMBOL ](../../media/ITPro-EAC-UpArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Wenn Sie über drei oder mehr benutzerdefinierte Richtlinien für ausgehende Spamnachrichten verfügen, haben die Richtlinien zwischen der höchsten und der niedrigsten Priorität die Werte "NACH-OBEN-SYMBOL NACH-UNTEN-Symbol n" (z. B. NACH-OBEN-SYMBOL NACH-UNTEN-SYMBOL ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2).**

3. Klicken Sie auf ![Pfeil-nach-oben-Symbol](../../media/ITPro-EAC-UpArrowIcon.png) oder ![Pfeil-nach-unten-Symbol,](../../media/ITPro-EAC-DownArrowIcon.png) , um die benutzerdefinierte Richtlinie für ausgehende Spamnachrichten in der Prioritätsliste nach oben oder unten zu verschieben.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Entfernen ausgehender Spamrichtlinien

1. Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.

2. Klicken Sie auf der **Seite "Antispameinstellungen"** auf das Symbol "Erweitern", um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte "Typ" ist "Benutzerdefinierte Richtlinie für ![ ](../../media/scc-expand-icon.png) **ausgehende Spamnachrichten").** 

3. Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.

4. Klicken Sie im angezeigten Dialogfeld mit der Warnung auf **Ja**.

Die Standardrichtlinie kann nicht entfernt werden.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>Verwenden von Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Konfigurieren von Richtlinien für ausgehende Spamnachrichten

Wie zuvor beschrieben, besteht eine Richtlinie für ausgehende Spamnachrichten aus einer Filterrichtlinie für ausgehende Spamnachrichten und einer Filterregel für ausgehende Spamnachrichten.

In Exchange Online PowerShell oder der eigenständigen EOP PowerShell ist der Unterschied zwischen Filterrichtlinien für ausgehende Spamnachrichten und Filterregeln für ausgehende Spamnachrichten offensichtlich. Sie verwalten Filterrichtlinien für ausgehende Spamnachrichten mithilfe der **\* Cmdlets "-HostedOutboundSpamFilterPolicy",** und Sie verwalten Filterregeln für ausgehende Spamnachrichten mithilfe der **\* Cmdlets "-HostedOutboundSpamFilterRule".**

- In PowerShell erstellen Sie zuerst die Filterrichtlinie für ausgehende Spamnachrichten und dann die Filterregel für ausgehende Spamnachrichten, die die Richtlinie identifiziert, auf die die Regel angewendet wird.
- In PowerShell ändern Sie die Einstellungen in der Filterrichtlinie für ausgehende Spamnachrichten und die Filterregel für ausgehende Spamnachrichten separat.
- Wenn Sie eine Filterrichtlinie für ausgehende Spamnachrichten aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht automatisch entfernt und umgekehrt.

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Verwenden von PowerShell zum Erstellen von Richtlinien für ausgehende Spamnachrichten

Das Erstellen einer Richtlinie für ausgehende Spamnachrichten in PowerShell besteht aus zwei Schritte:

1. Erstellen Sie die Filterrichtlinie für ausgehende Spamnachrichten.
2. Erstellen Sie die Filterregel für ausgehende Spamnachrichten, die die Filterrichtlinie für ausgehende Spamnachrichten angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Filterregel für ausgehende Spamnachrichten erstellen und ihr eine vorhandene, nicht zugeordnete Filterrichtlinie für ausgehende Spamnachrichten zuweisen. Eine Filterregel für ausgehende Spamnachrichten kann nicht mehr als einer Filterrichtlinie für ausgehende Spamnachrichten zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die im Security & Compliance Center erst nach dem Erstellen der Richtlinie verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_Aktiviert_ `$false` im Cmdlet **"New-HostedOutboundSpamFilterRule").**
  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Priorität_ ) im _\<Number\>_ **Cmdlet "New-HostedOutboundSpamFilterRule"** festgelegt.

- Eine neue ausgehende Spamfilterrichtlinie, die Sie in PowerShell erstellen, wird erst im Security & Compliance Center angezeigt, wenn Sie die Richtlinie einer Spamfilterregel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Schritt 1: Verwenden von PowerShell zum Erstellen einer Filterrichtlinie für ausgehende Spamnachrichten

Verwenden Sie folgende Syntax, um eine Filterrichtlinie für ausgehende Spamnachrichten zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine neue Filterrichtlinie für ausgehende Spamnachrichten namens "Contoso Executives" mit den folgenden Einstellungen erstellt:

- Die Grenzwerte für die Empfängerrate sind auf kleinere Werte beschränkt, die standardmäßig verwendet werden. Weitere Informationen finden Sie unter [Sendegrenzwerte für Microsoft 365-Optionen.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)

- Nachdem einer der Grenzwerte erreicht wurde, wird der Benutzer am Senden von Nachrichten gehindert.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Schritt 2: Verwenden von PowerShell zum Erstellen einer Filterregel für ausgehende Spamnachrichten

Verwenden Sie folgende Syntax, um eine Filterregel für ausgehende Spamnachrichten zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine neue Filterregel für ausgehende Spamnachrichten namens "Contoso Executives" mit den folgenden Einstellungen erstellt:

- Die Filterrichtlinie für ausgehende Spamnachrichten namens "Contoso Executives" ist der Regel zugeordnet.

- Die Regel gilt für Mitglieder der Gruppe mit dem Namen „Contoso Executive Group“.

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Anzeigen von Filterrichtlinien für ausgehende Spamnachrichten

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller Filterrichtlinien für ausgehende Spamnachrichten zurückzukehren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterrichtlinie für ausgehende Spamnachrichten zurückzukehren:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die Filterrichtlinie für ausgehende Spamnachrichten mit dem Namen "Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Anzeigen von Filterregeln für ausgehende Spamnachrichten

Verwenden Sie die folgende Syntax, um vorhandene Filterregeln für ausgehende Spamnachrichten anzeigen zu können:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

Führen Sie den folgenden Befehl aus, um eine Übersichtsliste aller Filterregeln für ausgehende Spamnachrichten zurückzukehren:

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

In diesem Beispiel werden alle Eigenschaftswerte für die Filterregel "Contoso Executives" für ausgehende Spamnachrichten zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern von Filterrichtlinien für ausgehende Spamnachrichten

Die gleichen Einstellungen sind verfügbar, wenn Sie eine Richtlinie für den Schadsoftwarefilter in PowerShell ändern wie beim Erstellen der Richtlinie, wie in Schritt 1: Verwenden von [PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) beschrieben, um einen Richtlinienabschnitt für ausgehende Spamfilter zu erstellen, der weiter oben in diesem Artikel beschrieben wurde.

> [!NOTE]
> Sie können eine Filterrichtlinie für ausgehende Spamnachrichten nicht umbenennen (das Cmdlet **"Set-HostedOutboundSpamFilterPolicy"** hat keinen _Parameter "Name")._ Wenn Sie eine Richtlinie für ausgehende Spamnachrichten im Security & Compliance Center umbenennen, benennen Sie nur die Filterregel für ausgehende Spamnachrichten _um._

Verwenden Sie folgende Syntax, um eine Filterrichtlinie für ausgehende Spamnachrichten zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern von Filterregeln für ausgehende Spamnachrichten

Die einzige Einstellung, die beim Ändern einer Filterregel für ausgehende Spamnachrichten in PowerShell nicht verfügbar ist, ist der Parameter _"Enabled",_ mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Filterregeln für ausgehende Spamnachrichten finden Sie im nächsten Abschnitt.

Andernfalls sind keine zusätzlichen Einstellungen verfügbar, wenn Sie eine Filterregel für ausgehende Spamnachrichten in PowerShell ändern. Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie in Schritt [2 beschrieben: Verwenden von PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) zum Erstellen einer Filterregel für ausgehende Spamnachrichten weiter oben in diesem Artikel.

Verwenden Sie folgende Syntax, um eine Filterregel für ausgehende Spamnachrichten zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Filterregeln für ausgehende Spamnachrichten

Durch Aktivieren oder Deaktivieren einer Filterregel für ausgehende Spamnachrichten in PowerShell wird die gesamte Richtlinie für ausgehende Spamnachrichten aktiviert oder deaktiviert (die Filterregel für ausgehende Spamnachrichten und die zugewiesene Filterrichtlinie für ausgehende Spamnachrichten). Die standardrichtlinie für ausgehende Spamnachrichten kann nicht aktiviert oder deaktiviert werden (sie wird immer auf alle Empfänger angewendet).

Verwenden Sie folgende Syntax, um eine Filterregel für ausgehende Spamnachrichten in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die Filterregel für ausgehende Spamnachrichten namens "Marketing Department" deaktiviert.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Enable-HostedOutboundSpamFilterRule"](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) und ["Disable-HostedOutboundSpamFilterRule".](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität ausgehender Spamfilterregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie z. B. fünf benutzerdefinierte Regeln haben (Priorität 0 bis 4) und die Priorität einer Regel in 2 ändern, erhält die vorhandene Regel mit Priorität 2 die Priorität 3, und die Regel mit Priorität 3 erhält Priorität 4.

Verwenden Sie die folgende Syntax, um die Priorität einer Filterregel für ausgehende Spamnachrichten in PowerShell zu festlegen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - Verwenden Sie zum Festlegen der Priorität einer neuen Regel beim Erstellen stattdessen den Parameter _"Priority"_ im Cmdlet **"New-HostedOutboundSpamFilterRule".**
>
> - Die Standardfilterrichtlinie für ausgehende Spamnachrichten verfügt nicht über eine entsprechende Spamfilterregel, und sie hat immer den nicht veränderbaren Prioritätswert **"Lowest".**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Entfernen von Filterrichtlinien für ausgehende Spamnachrichten

Wenn Sie powerShell verwenden, um eine Filterrichtlinie für ausgehende Spamnachrichten zu entfernen, wird die entsprechende Filterregel für ausgehende Spamnachrichten nicht entfernt.

Verwenden Sie folgende Syntax, um eine Filterrichtlinie für ausgehende Spamnachrichten in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Filterrichtlinie für ausgehende Spamnachrichten namens "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Entfernen ausgehender Spamfilterregeln

Wenn Sie PowerShell verwenden, um eine Filterregel für ausgehende Spamnachrichten zu entfernen, wird die entsprechende Filterrichtlinie für ausgehende Spamnachrichten nicht entfernt.

Verwenden Sie folgende Syntax, um eine Filterregel für ausgehende Spamnachrichten in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die Filterregel für ausgehende Spamnachrichten namens "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule).

## <a name="for-more-information"></a>Weitere Informationen

[Entfernen von blockierten Benutzern aus dem Portal „Eingeschränkte Benutzer“](removing-user-from-restricted-users-portal-after-spam.md)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)

[Bericht über automatisch weitergeleitete Nachrichten](mfi-auto-forwarded-messages-report.md)
