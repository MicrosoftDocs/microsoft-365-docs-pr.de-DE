---
title: Konfigurieren der ausgehenden Spamfilterung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
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
ms.openlocfilehash: e788310ae8fd3c0da7f1a39fbba2dc0d6e369d30
ms.sourcegitcommit: fce0d5cad32ea60a08ff001b228223284710e2ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/21/2020
ms.locfileid: "42893908"
---
# <a name="configure-outbound-spam-filtering-in-office-365"></a>Konfigurieren der ausgehenden Spamfilterung in Office 365

Wenn Sie ein Office 365er Kunde mit Postfächern in Exchange Online oder einem eigenständigen Exchange Online Schutz-Kunden (EoP) ohne Exchange Online Postfächer sind, werden ausgehende e-Mail-Nachrichten, die über EoP gesendet werden, automatisch auf Spam und ungewöhnlich überprüft. sendende Aktivität.

Ausgehende Spamnachrichten von einem Benutzer in Ihrer Organisation weisen in der Regel auf ein kompromittiertes Konto hin. Verdächtige ausgehende Nachrichten werden als Spam gekennzeichnet (unabhängig von der Spam Konfidenz Stufe oder der SCL-Bewertung) und werden über den [risikoreichen Zustellungs Pool](high-risk-delivery-pool-for-outbound-messages.md) weitergeleitet, um die Reputation des Diensts zu schützen (also Office 365 Quell-e-Mail-Server von IP-Sperrlisten fernzuhalten). Administratoren werden automatisch über verdächtige ausgehende e-Mail-Aktivitäten und blockierte Benutzer über [Warnungsrichtlinien](../../compliance/alert-policies.md)benachrichtigt.

EoP verwendet ausgehende Spam Richtlinien als Teil der gesamten Abwehr von Spam in Ihrer Organisation. Weitere Informationen finden Sie unter [Anti-Spam Protection in Office 365](anti-spam-protection.md).

Administratoren können die standardmäßige ausgehende Spam Richtlinie anzeigen, bearbeiten und konfigurieren (jedoch nicht löschen). Um eine höhere Granularität zu erzielen, können Sie auch benutzerdefinierte ausgehende Spam Richtlinien erstellen, die für bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation gelten. Benutzerdefinierte Richtlinien haben immer Vorrang vor der Standardrichtlinie, aber Sie können die Priorität (Ausführungsreihenfolge) Ihrer benutzerdefinierten Richtlinien ändern.

Sie können ausgehende Spam Richtlinien im Office 365 Security & Compliance Center oder in PowerShell konfigurieren (Exchange Online PowerShell für Office 365 Kunden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).

## <a name="outbound-spam-policies-in-the-office-365-security--compliance-center-vs-exchange-online-powershell-or-exchange-online-protection-powershell"></a>Ausgehende Spam Richtlinien im Office 365 Security & Compliance Center vs Exchange Online PowerShell oder Exchange Online Protection PowerShell

Die grundlegenden Elemente einer ausgehenden Spam Richtlinie in EoP sind:

- **Die Richtlinie für ausgehende Spamfilter**: gibt die Aktionen für ausgehende Spamfilter Urteile und die Benachrichtigungsoptionen an.

- **Die ausgehende Spamfilter Regel**: gibt die Priorität und die Empfängerfilter (für wen die Richtlinie gilt) für eine Richtlinie für ausgehende Spamfilter an.

Der Unterschied zwischen diesen beiden Elementen ist nicht offensichtlich, wenn Sie ausgehende Spam Richtlinien im Security & Compliance Center verwalten:

- Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center erstellen, erstellen Sie tatsächlich eine ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam gleichzeitig unter Verwendung desselben Namens für beide.

- Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center ändern, ändern die Einstellungen im Zusammenhang mit dem Namen, der Priorität, den aktivierten oder deaktivierten und den Empfänger filtern die ausgehende Spamfilter Regel. Bei allen anderen Einstellungen wird die zugehörige Filterrichtlinie für ausgehende Spam geändert.

- Wenn Sie eine ausgehende Spam Richtlinie aus dem Security & Compliance Center entfernen, werden die ausgehende Spamfilter Regel und die zugehörige Filterrichtlinie für ausgehende Spam entfernt.

In Exchange Online PowerShell oder eigenständigen Exchange Online Protection-PowerShell wird der Unterschied zwischen ausgehenden Spamfilter Richtlinien und ausgehenden spamfilterregeln deutlich. Sie verwalten Richtlinien für ausgehende Spamfilter ** \*** mithilfe der Cmdlets-hostedcontentfilterpolicy dient zum, und Sie verwalten Filterregeln für ausgehende Spam mithilfe der ** \*Cmdlets-HostedContentFilterRule** .

- In PowerShell erstellen Sie zuerst die Richtlinie für ausgehende Spamfilter, dann erstellen Sie die ausgehende Spamfilter Regel, die die Richtlinie identifiziert, auf die die Regel angewendet wird.

- In PowerShell ändern Sie die Einstellungen in der Richtlinie für ausgehende Spamfilter und der ausgehenden Spamfilter Regel separat.

- Wenn Sie eine ausgehende Spamfilter Richtlinie aus PowerShell entfernen, wird die entsprechende Filterregel für ausgehende Spam nicht automatisch entfernt und umgekehrt.

### <a name="default-outbound-spam-policy"></a>Standardrichtlinie für ausgehende Spamnachrichten

Jede Organisation verfügt über eine integrierte ausgehende Spam Richtlinie mit dem Namen Default, die die folgenden Eigenschaften aufweist:

- Die Richtlinie für ausgehende Spamfilter mit dem Namen Default wird auf alle Empfänger in der Organisation angewendet, obwohl der Richtlinie keine ausgehende Spamfilter Regel (Empfängerfilter) zugeordnet ist.

- Die Richtlinie mit dem Namen Default hat den benutzerdefinierten Prioritätswert **niedrigste** , den Sie nicht ändern können (die Richtlinie wird immer zuletzt angewendet). Alle benutzerdefinierten Richtlinien, die Sie erstellen, haben immer eine höhere Priorität als die Richtlinie "Default".

- Die Richtlinie mit dem Namen Default ist die Standardrichtlinie (die **IsDefault** - `True`Eigenschaft hat den Wert), und die Standardrichtlinie kann nicht gelöscht werden.

Um die Effektivität der ausgehenden Spamfilterung zu verbessern, können Sie benutzerdefinierte ausgehende Spam Richtlinien mit strengeren Einstellungen erstellen, die auf bestimmte Benutzer oder Benutzergruppen angewendet werden.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Wenn Sie direkt zur Seite **Antispameinstellungen** wechseln möchten, verwenden <https://protection.office.com/antispam>Sie.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit einer eigenständigen Exchange Online Schutz-PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie diese Verfahren ausführen können. Zum Hinzufügen, ändern und Löschen von ausgehenden Spam Richtlinien müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein. Für den schreibgeschützten Zugriff auf ausgehende Spam Richtlinien müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein. Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Unsere empfohlenen Einstellungen für ausgehende Spam Richtlinien finden Sie unter [EoP Outbound Spamfilter Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings).

- Die standardmäßigen [Warnungsrichtlinien](../../compliance/alert-policies.md) mit dem Namen " **e-Mail-Sende Grenzwert**" überschritten, **verdächtige e-Mail-Sende Muster wurden erkannt**und Benutzer, die **von e-Mails eingeschränkt** sind, senden bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe der **TenantAdmins** (**globale Administratoren**) über ungewöhnliche ausgehende e-Mail-Aktivitäten und blockierte Benutzer Weitere Informationen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users). Es wird empfohlen, diese Warnungsrichtlinien anstelle der Benachrichtigungsoptionen in ausgehenden Spam Richtlinien zu verwenden.

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien

Durch das Erstellen einer benutzerdefinierten ausgehenden Spam Richtlinie im Security & Compliance Center werden die Spamfilter Regel und die zugehörige Spamfilter Richtlinie gleichzeitig mit dem gleichen Namen für beide erstellt.

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf **ausgehende Richtlinie erstellen**.

3. Konfigurieren Sie in der geöffneten **ausgehenden Spamfilter Richtlinie** , die geöffnet wird, die folgenden Einstellungen:

   - **Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Richtlinie ein.

   - **Beschreibung**: Geben Sie eine optionale Beschreibung für die Richtlinie ein.

4. Optional Erweitern Sie den Abschnitt **Benachrichtigungen** , um weitere Benutzer zu konfigurieren, die Kopien und Benachrichtigungen von verdächtigen ausgehenden e-Mail-Nachrichten erhalten sollen:

   - **Senden einer Kopie verdächtiger ausgehender e-Mail-Nachrichten an bestimmte Personen**: mit dieser Einstellung werden den Verdächtigen ausgehenden Nachrichten die angegebenen Benutzer als Bcc-Empfänger hinzugefügt. So aktivieren Sie diese Einstellung:

     a. Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.

     b. Klicken Sie auf **Personen hinzufügen**. Im Flyout **Empfänger hinzufügen oder entfernen** :

     c. Geben Sie die e-Mail-Adresse des Absenders ein. Sie können mehrere e-Mail-Adressen durch Semikolons getrennt angeben (;) oder ein Empfänger pro Reihe.

     d. Klicken Sie auf ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) zum Hinzufügen der Empfänger.

        Wiederholen Sie diese Schritte so oft wie nötig.

        Die Empfänger, die Sie hinzugefügt haben, werden im Flyout im Abschnitt **Empfängerliste** angezeigt. Klicken Sie ![auf die Schaltfläche](../../media/scc-remove-icon.png)entfernen, um einen Empfänger zu löschen.

     e. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

     Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

   - **Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam blockiert wird**:

     > [!NOTE]
     > Die standardmäßige [Warnungs Richtlinie](../../compliance/alert-policies.md) mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " sendet bereits e-Mail-Benachrichtigungen an Mitglieder der Gruppe **TenantAdmins** (**globale Administratoren**), wenn Benutzer aufgrund der Überschreitung der Grenzwerte im Abschnitt **Empfänger Grenzwerte** blockiert werden. Es wird empfohlen, dass Sie die Warnungs Richtlinie anstelle dieser Einstellung in der ausgehenden Spam Richtlinie verwenden, um Administratoren und andere Benutzer zu benachrichtigen. Anweisungen finden Sie unter [Überprüfen der Warnungseinstellungen für eingeschränkte Benutzer](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users).

     So aktivieren Sie diese Einstellung:

     a. Aktivieren Sie das Kontrollkästchen, um die Einstellung zu aktivieren.

     b. Klicken Sie auf **Personen hinzufügen**. Im Flyout **Empfänger hinzufügen oder entfernen** :

     c. Geben Sie die e-Mail-Adresse des Absenders ein. Sie können mehrere e-Mail-Adressen durch Semikolons getrennt angeben (;) oder ein Empfänger pro Reihe.

     d. Klicken Sie auf ![Hinzufügen (Symbol)](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) zum Hinzufügen der Empfänger.

        Wiederholen Sie diese Schritte so oft wie nötig.

        Die Empfänger, die Sie hinzugefügt haben, werden im Flyout im Abschnitt **Empfängerliste** angezeigt. Klicken Sie ![auf die Schaltfläche](../../media/scc-remove-icon.png)entfernen, um einen Empfänger zu löschen.

     e. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

     Deaktivieren Sie das Kontrollkästchen, um diese Einstellung zu deaktivieren.

5. Optional Erweitern Sie den Abschnitt **Empfänger Grenzwerte** , um die Grenzwerte und Aktionen für verdächtige ausgehende e-Mail-Nachrichten zu konfigurieren:]
   - **Maximale Anzahl von Empfängern pro Benutzer**

     Ein gültiger Wert ist 0 bis 10000. Der Standardwert ist 0, was bedeutet, dass die Dienst Standardwerte verwendet werden. Weitere Informationen finden Sie unter [sending Limits Across Office 365 Options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

     - **Externer stündlicher Grenzwert**: die maximale Anzahl externer Empfänger pro Stunde.

     - **Interner stündlicher Grenzwert**: die maximale Anzahl interner Empfänger pro Stunde.

     - **Daily Limit**: die maximale Gesamtzahl der Empfänger pro Tag.

   - **Aktion, wenn ein Benutzer die oben genannten Grenzwerte überschreitet**: Konfigurieren Sie die Aktion, die ausgeführt werden soll, wenn eine der **Empfänger Grenzwerte** überschritten wird. Für alle Aktionen werden die im Benutzer angegebenen Empfänger **vom Senden von e-Mail-** Warnungsrichtlinien eingeschränkt (und im jetzt redundante **Benachrichtigen bestimmter Personen, wenn ein Absender aufgrund des Sendens von ausgehenden Spam** -Einstellungen in der ausgehenden Spam Richtlinie blockiert wird, e-Mail-Benachrichtigungen empfangen.

     - **Beschränken Sie den Benutzer am Senden von e-Mails bis zum folgenden Tag**: Dies ist der Standardwert. E-Mail-Benachrichtigungen werden gesendet, und der Benutzer kann keine weiteren Nachrichten auf der Grundlage der UTC-Zeit bis zum nächsten Tag senden. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.

       - Die Aktivitäts Benachrichtigung mit dem Namen " **Benutzer vom Senden von e-Mails eingeschränkt** " benachrichtigt Administratoren (per e-Mail und auf der Seite **Benachrichtigungen anzeigen** ).

       - Alle Empfänger, die in der Richtlinie in den Einstellungen " **bestimmte Personen Benachrichtigen, wenn ein Absender aufgrund des Sendens ausgehenden Spam blockiert ist** " angegeben werden, werden ebenfalls benachrichtigt.

       - Der Benutzer kann bis zum nächsten Tag keine weiteren Nachrichten senden, basierend auf UTC-Zeit. Es gibt keine Möglichkeit für den Administrator, diesen Block außer Kraft zu setzen.

     - **Einschränken des Benutzers beim Senden von e-Mails**: e-Mail-Benachrichtigungen werden gesendet, der Benutzer wird dem Portal **[<https://sip.protection.office.com/restrictedusers> restricted users]** im Security & Compliance Center hinzugefügt, und der Benutzer kann keine e-Mails senden, bevor er von einem Administrator aus dem Portal für **eingeschränkte Benutzer** entfernt wird. Nachdem der Benutzer von einem Administrator aus der Liste entfernt wurde, wird der Benutzer für diesen Tag nicht mehr eingeschränkt. Anweisungen hierzu finden Sie unter [Entfernen eines Benutzers aus dem Portal für eingeschränkte Benutzer nach dem Senden von Spam-e-Mails](removing-user-from-restricted-users-portal-after-spam.md).

     - **Keine Aktion, nur Warnung**: e-Mail-Benachrichtigungen werden gesendet.

6. Erforderlich Erweitern Sie den Abschnitt **angewendet für** , um die internen Absender zu identifizieren, auf die die Richtlinie angewendet wird.

    Sie können nur einmal eine Bedingung oder Ausnahme verwenden, aber Sie können mehrere Werte für die Bedingung oder Ausnahme angeben. Mehrere Werte der gleichen Bedingung oder Ausnahme Verwendung oder Logik (beispielsweise _ \<sender1\> _ oder _ \<sender2\>_). Unterschiedliche Bedingungen oder Ausnahmen: Verwendung und Logik (Beispiels _ \<Weise\> sender1_ und _ \<Mitglied von Gruppe\>1_).

    Am einfachsten ist es, dreimal auf **Bedingung hinzufügen** zu klicken, um alle verfügbaren Bedingungen anzuzeigen. Sie können auf ![Schaltfläche](../../media/scc-remove-icon.png) entfernen klicken, um Bedingungen zu entfernen, die Sie nicht konfigurieren möchten.

    - **Die Absenderdomäne lautet**: gibt Absender in einer oder mehreren konfigurierten akzeptierten Domänen in Office 365 an. Klicken Sie in das Feld **Add a Tag** , um eine Domäne anzuzeigen und auszuwählen. Klicken Sie erneut auf das Feld **Tag hinzufügen** , um zusätzliche Domänen auszuwählen, wenn mehr als eine Domäne verfügbar ist.

    - **Absender lautet**: gibt einen oder mehrere Benutzer in Ihrer Organisation an. Klicken Sie in das **Add a-Tag** , und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.

    - **Der Absender ist Mitglied von**: gibt eine oder mehrere Gruppen in Ihrer Organisation an. Klicken Sie in das **Add a-Tag** , und beginnen Sie mit der Eingabe, um die Liste zu filtern. Klicken Sie erneut auf das Feld **Tag hinzufügen** , um weitere Absender auszuwählen.

    - **Außer if**: Klicken Sie zum Hinzufügen von Ausnahmen für die Regel dreimal auf **Bedingung hinzufügen** , um alle verfügbaren Ausnahmen anzuzeigen. Die Einstellungen und das Verhalten sind genau wie die Bedingungen.

7. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Anzeigen von ausgehenden Spam Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine ausgehende Spam Richtlinie zu erweitern:

   - Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.

3. Die Richtlinieneinstellungen werden in den erweiterten Richtliniendetails angezeigt, die angezeigt werden, oder Sie können auf **Richtlinie bearbeiten**klicken.

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Ändern von Richtlinien für ausgehende Spamnachrichten

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine ausgehende Spam Richtlinie zu erweitern:

   - Die Standardrichtlinie mit dem Namen " **Outbound Spamfilter Policy**".

   - Eine benutzerdefinierte Richtlinie, die Sie erstellt haben, wobei der Wert in der Spalte **Typ** eine **benutzerdefinierte ausgehende Spam Richtlinie**ist.

3. Klicken Sie auf **Richtlinie bearbeiten**.

Bei benutzerdefinierten ausgehenden Spam Richtlinien sind die verfügbaren Einstellungen im Flyout, die angezeigt werden, mit denen im Abschnitt [Verwenden der Sicherheits & Compliance Center zum Erstellen von ausgehenden Spam Richtlinien](#use-the-security--compliance-center-to-create-outbound-spam-policies) beschrieben identisch.

Für die standardmäßige ausgehende Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie**" ist der Abschnitt " **angewendet für** " nicht verfügbar (die Richtlinie gilt für alle), und Sie können die Richtlinie nicht umbenennen.

Um eine Richtlinie zu aktivieren oder zu deaktivieren, legen Sie die Prioritätsreihenfolge der Richtlinie fest oder konfigurieren Sie die Endbenutzer-Quarantänebenachrichtigungen in den folgenden Abschnitten.

### <a name="enable-or-disable-outbound-spam-policies"></a>Aktivieren oder Deaktivieren von ausgehenden Spam Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um eine benutzerdefinierte Richtlinie zu erweitern, die Sie erstellt haben (der Wert in der Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).

3. Beachten Sie in den erweiterten Richtliniendetails, die angezeigt werden, den Wert in der Spalte " **ein** ".

   Bewegen Sie die Umschaltfläche nach links, um die Richtlinie zu deaktivieren: ![Abschalten](../../media/scc-toggle-off.png)

   Bewegen Sie die Umschaltfläche nach rechts, um die Richtlinie zu aktivieren: ![Einschalten](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

Sie können die standardmäßige ausgehende Spam Richtlinie nicht deaktivieren.

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>Festlegen der Priorität von benutzerdefinierten ausgehenden Spam Richtlinien

Standardmäßig erhalten ausgehende Spam Richtlinien eine Priorität, die auf der Reihenfolge basiert, in der Sie erstellt wurden (neuere Policen haben eine niedrigere Priorität als ältere Richtlinien). Eine niedrigere Prioritätsnummer gibt eine höhere Priorität für die Richtlinie an (0 ist die höchste), und Richtlinien werden in Prioritätsreihenfolge verarbeitet (Richtlinien mit höherer Priorität werden vor Richtlinien mit niedrigerer Priorität verarbeitet). Zwei Richtlinien können nicht dieselbe Priorität haben.

Benutzerdefinierte ausgehende Spam Richtlinien werden in der Reihenfolge angezeigt, in der Sie verarbeitet werden (die erste Richtlinie hat den **Prioritäts** Wert 0). Bei der standardmäßigen ausgehenden Spam Richtlinie mit dem Namen " **ausgehende Spamfilter Richtlinie** " ist der Prioritätswert **niedrig**und kann nicht geändert werden.

Um die Priorität einer Richtlinie zu ändern, müssen Sie die Richtlinie in der Liste nach oben oder unten verschoben (Sie können die **Prioritäts** Nummer im Security & Compliance Center nicht direkt ändern).

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Suchen Sie auf der Seite **Antispameinstellungen** nach den Richtlinien, bei denen es sich bei dem Wert in der Spalte **Typ** um eine **benutzerdefinierte ausgehende Spam Richtlinie**handelt. Beachten Sie die Werte in der Spalte **Priority** :

   - Die benutzerdefinierte Richtlinie für ausgehende Spam mit der höchsten ![Priorität hat den](../../media/ITPro-EAC-DownArrowIcon.png) Abwärtspfeil-Symbolwert **0**.

   - Die benutzerdefinierte Richtlinie für ausgehende Spam mit der niedrigsten ![Priorität hat den](../../media/ITPro-EAC-UpArrowIcon.png) Wert nach oben Pfeilsymbol ![ **n** (beispielsweise nach oben Pfeilsymbol](../../media/ITPro-EAC-UpArrowIcon.png) **3**).

   - Wenn Sie drei oder mehr benutzerdefinierte ausgehende Spam Richtlinien haben, haben die Richtlinien zwischen der höchsten und ![der niedrigsten Priorität](../../media/ITPro-EAC-UpArrowIcon.png)![Werte nach oben](../../media/ITPro-EAC-DownArrowIcon.png) Pfeilsymbol nach unten Pfeil ![Symbol **n** (](../../media/ITPro-EAC-UpArrowIcon.png)![beispielsweise nach](../../media/ITPro-EAC-DownArrowIcon.png) oben Pfeilsymbol nach unten Pfeilsymbol **2**).

3. Click ![Aufwärtspfeil (Symbol)](../../media/ITPro-EAC-UpArrowIcon.png) oder ![Abwärtspfeil (Symbol)](../../media/ITPro-EAC-DownArrowIcon.png) um die benutzerdefinierte Richtlinie für ausgehende Spam in der Liste Priorität nach oben oder nach unten zu verlagern.

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>Verwenden des Security & Compliance Center zum Entfernen von ausgehenden Spam Richtlinien

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam**.

2. Klicken Sie ![auf der Seite **Anti-Spam-Einstellungen** auf](../../media/scc-expand-icon.png) Symbol erweitern, um die benutzerdefinierte Richtlinie zu erweitern, die Sie löschen möchten (die Spalte **Typ** ist eine **benutzerdefinierte ausgehende Spam Richtlinie**).

3. Klicken Sie in den angezeigten erweiterten Richtliniendetails auf **Richtlinie löschen**.

4. Klicken Sie im angezeigten Warndialogfeld auf **Ja** .

Sie können die Standardrichtlinie nicht entfernen.

## <a name="use-exchange-online-powershell-or-exchange-online-protection-powershell-to-configure-outbound-spam-policies"></a>Verwenden von Exchange Online PowerShell oder Exchange Online Protection PowerShell zum Konfigurieren von ausgehenden Spam Richtlinien

### <a name="use-powershell-to-create-outbound-spam-policies"></a>Verwenden von PowerShell zum Erstellen von ausgehenden Spam Richtlinien

Das Erstellen einer ausgehenden Spam Richtlinie in PowerShell erfolgt in einem zweistufigen Prozess:

1. Erstellen Sie die Richtlinie für ausgehende Spamfilter.

2. Erstellen Sie die Filterregel für ausgehende Spam, die die Richtlinie für ausgehende Spamfilter angibt, auf die die Regel angewendet wird.

 **Hinweise**:

- Sie können eine neue Filterregel für ausgehende Spam erstellen und ihr eine vorhandene, nicht zugeordnete Filterrichtlinie für ausgehende Spam zuweisen. Eine ausgehende Spamfilter Regel kann nicht mehr als einer ausgehenden Spamfilter Richtlinie zugeordnet werden.

- Sie können die folgenden Einstellungen für neue Richtlinien für ausgehende Spamfilter in PowerShell konfigurieren, die erst nach dem Erstellen der Richtlinie im Security & Compliance Center verfügbar sind:

  - Erstellen Sie die neue Richtlinie als deaktiviert (_aktiviert_ `$false` im Cmdlet **New-HostedOutboundSpamFilterRule** ).

  - Legen Sie die Priorität der Richtlinie während der Erstellung (_Prioritäts_ _ \<Nummer\>_) für das Cmdlet **New-HostedOutboundSpamFilterRule** fest.

- Eine neue Richtlinie für ausgehende Spamfilter, die Sie in PowerShell erstellen, ist erst im Security & Compliance Center sichtbar, wenn Sie die Richtlinie einer Spamfilter Regel zuweisen.

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>Schritt 1: Erstellen einer ausgehenden Spamfilter Richtlinie mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Filterrichtlinie für ausgehende Spam zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

In diesem Beispiel wird eine neue Richtlinie für ausgehende Spamfilter namens "Contoso Executives" mit den folgenden Einstellungen erstellt:

- Die Empfänger Raten Begrenzungen sind auf kleinere Werte beschränkt, die von den Standardeinstellungen abweichen. Weitere Informationen finden Sie unter [sending Limits Across Office 365 Options](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options).

- Nachdem eine der Grenzwerte erreicht wurde, wird verhindert, dass der Benutzer Nachrichten sendet.

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterpolicy).

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>Schritt 2: Erstellen einer ausgehenden Spamfilter Regel mithilfe von PowerShell

Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu erstellen:

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

In diesem Beispiel wird eine neue ausgehende Spamfilter Regel namens "Contoso Executives" mit den folgenden Einstellungen erstellt:

- Die Richtlinie für ausgehende Spamfilter mit dem Namen "Contoso Executives" ist der Regel zugeordnet.

- Die Regel gilt für Mitglieder der Gruppe "Contoso Executives Group".

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/new-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Anzeigen von Richtlinien für ausgehende Spamfilter

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden Spamfilter Richtlinien zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Richtlinie für ausgehende Spamfilter zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Richtlinie "Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Anzeigen von Regeln für ausgehende Spamfilter

Verwenden Sie die folgende Syntax, um vorhandene Filterregeln für ausgehende Spam anzuzeigen:

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

Führen Sie den folgenden Befehl aus, um eine Zusammenfassungsliste aller ausgehenden spamfilterregeln zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterRule
```

Führen Sie die folgenden Befehle aus, um die Liste durch aktivierte oder deaktivierte Regeln zu filtern:

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

Verwenden Sie die folgende Syntax, um detaillierte Informationen zu einer bestimmten Filterregel für ausgehende Spam Daten zurückzugeben:

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

In diesem Beispiel werden alle Eigenschaftswerte für die ausgehende Spamfilter Regel namens "Contoso Executives" zurückgegeben.

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Ändern von Richtlinien für ausgehende Spamfilter

Die gleichen Einstellungen stehen zur Verfügung, wenn Sie eine Filterrichtlinie für Schadsoftware in PowerShell wie beim Erstellen der Richtlinie wie im Abschnitt [Schritt 1: Verwenden von PowerShell zum Erstellen einer Richtlinie für ausgehende Spamfilter](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) weiter oben in diesem Thema beschrieben ändern.

**Hinweis**: Es ist nicht möglich, eine ausgehende Spamfilter Richtlinie umzubenennen (das Cmdlet " **HostedOutboundSpamFilterPolicy** " hat keinen Parameter " _Name_ "). Wenn Sie eine ausgehende Spam Richtlinie im Security & Compliance Center umbenennen, benennen Sie die ausgehende Spamfilter _Regel_nur um.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Ändern von Regeln für ausgehende Spamfilter

Die einzige Einstellung, die beim Ändern einer ausgehenden Spamfilter Regel in PowerShell nicht verfügbar ist, ist der Parameter _Enabled_ , mit dem Sie eine deaktivierte Regel erstellen können. Informationen zum Aktivieren oder Deaktivieren vorhandener Filterregeln für ausgehende Spamfilter finden Sie im nächsten Abschnitt.

Andernfalls stehen keine zusätzlichen Einstellungen zur Verfügung, wenn Sie eine ausgehende Spamfilter Regel in PowerShell ändern. Die gleichen Einstellungen sind verfügbar, wenn Sie eine Regel erstellen, wie im Abschnitt [Schritt 2: Verwenden von PowerShell zum Erstellen eines Filters für ausgehende Spamfilter](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) weiter oben in diesem Thema beschrieben.

Verwenden Sie die folgende Syntax, um eine Filterregel für ausgehende Spam zu ändern:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Aktivieren oder Deaktivieren von Regeln für ausgehende Spamfilter

Durch Aktivieren oder Deaktivieren einer ausgehenden Spamfilter Regel in PowerShell wird die gesamte ausgehende Spam Richtlinie (die ausgehende Spamfilter Regel und die zugewiesene Richtlinie für ausgehende Spamfilter) aktiviert oder deaktiviert. Sie können die standardmäßige ausgehende Spam Richtlinie nicht aktivieren oder deaktivieren (Sie wird immer auf alle Empfänger angewendet).

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu aktivieren oder zu deaktivieren:

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" deaktiviert.

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

In diesem Beispiel wird dieselbe Regel aktiviert.

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/enable-hostedoutboundspamfilterrule) und [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/disable-hostedoutboundspamfilterrule).

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Festlegen der Priorität von ausgehenden spamfilterregeln

Der höchste Prioritätswert, den Sie für eine Regel festlegen können, ist 0. Der niedrigste Wert, den Sie festlegen können, hängt von der Anzahl von Regeln ab. Wenn Sie z. B. fünf Regeln haben, können Sie die Prioritätswerte 0 bis 4 verwenden. Das Ändern der Priorität einer vorhandenen Regel kann sich entsprechend auf andere Regeln auswirken. Wenn Sie beispielsweise fünf benutzerdefinierte Regeln (Prioritäten 0 bis 4) haben und die Priorität einer Regel auf 2 ändern, wird die vorhandene Regel mit Priorität 2 in Priorität 3 geändert, und die Regel mit der Priorität 3 wird in Priorität 4 geändert.

Verwenden Sie die folgende Syntax, um die Priorität einer ausgehenden Spamfilter Regel in PowerShell festzulegen:

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

In diesem Beispiel wird die Priorität der Regel namens „Marketing Department“ auf 2 festgelegt. Alle vorhandenen Regeln mit Priorität kleiner oder gleich 2 werden um 1 verringert (die Prioritätswerte werden um 1 erhöht).

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**Hinweise**:

- Wenn Sie die Priorität einer neuen Regel beim Erstellen festlegen möchten, verwenden Sie stattdessen den Parameter _Priority_ für das Cmdlet **New-HostedOutboundSpamFilterRule** .

- Die ausgehende standardmäßige Spamfilter Richtlinie verfügt nicht über eine entsprechende Spamfilter Regel, und Sie hat immer den **niedrigsten**Wert für die unveränderbare Priorität.

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>Verwenden von PowerShell zum Entfernen von ausgehenden Spamfilter Richtlinien

Wenn Sie PowerShell zum Entfernen einer ausgehenden Spamfilter Richtlinie verwenden, wird die entsprechende Filterregel für ausgehende Spam nicht entfernt.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Richtlinie in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

In diesem Beispiel wird die Richtlinie für ausgehende Spamfilter namens "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterpolicy).

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>Verwenden von PowerShell zum Entfernen von Filterregeln für ausgehende Spam

Wenn Sie mithilfe von PowerShell eine ausgehende Spamfilter Regel entfernen, wird die entsprechende Filterrichtlinie für ausgehende Spam nicht entfernt.

Verwenden Sie die folgende Syntax, um eine ausgehende Spamfilter Regel in PowerShell zu entfernen:

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

In diesem Beispiel wird die ausgehende Spamfilter Regel namens "Marketing Department" entfernt.

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Remove-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/remove-hostedoutboundspamfilterrule).


## <a name="for-more-information"></a>Weitere Informationen

[Entfernen eines Benutzers aus dem Portal für Benutzer mit eingeschränktem Zugriff nach dem Senden von Spam-E-Mails](https://docs.microsoft.com/office365/SecurityCompliance/removing-user-from-restricted-users-portal-after-spam)

[Pool für besonders riskante Zustellungen für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md)

[Häufig gestellte Fragen zum Antispamschutz](anti-spam-protection-faq.md)
