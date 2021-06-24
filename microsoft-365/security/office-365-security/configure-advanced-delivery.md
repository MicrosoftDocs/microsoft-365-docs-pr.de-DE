---
title: Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer
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
ms.collection:
- M365-security-compliance
ms.custom: ''
description: Administratoren können erfahren, wie Sie die erweiterte Übermittlungsrichtlinie in Exchange Online Protection (EOP) verwenden, um Nachrichten zu identifizieren, die in bestimmten unterstützten Szenarien (Phishingsimulationen von Drittanbietern und Nachrichten, die an SecOps-Postfächer (Security Operations) übermittelt werden, nicht gefiltert werden sollten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 819f78883aa75fbbdded2e47c1bb85945f080233
ms.sourcegitcommit: ebb1c3b4d94058a58344317beb9475c8a2eae9a7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53108403"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Das in diesem Artikel beschriebene Feature befindet sich in der Vorschau, ist nicht für alle verfügbar und kann geändert werden.

Um Ihre Organisation [standardmäßig zu schützen,](secure-by-default.md)lässt Exchange Online Protection (EOP) keine sicheren Listen oder Filterumgehungen für Nachrichten zu, die als Schadsoftware oder Phishing mit hoher Vertrauenswürdigkeit identifiziert werden. Es gibt jedoch bestimmte Szenarien, die die Übermittlung ungefilterter Nachrichten erfordern. Beispiel:

- **Phishingsimulationen von Drittanbietern:** Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation auswirkt.
- **Sicherheitsvorgänge (SecOps) Postfächer:** Dedizierte Postfächer, die von Sicherheitsteams verwendet werden, um ungefilterte Nachrichten zu sammeln und zu analysieren (sowohl gut als auch schlecht).

Sie verwenden die _erweiterte Übermittlungsrichtlinie_ in Microsoft 365, um zu verhindern, dass diese Nachrichten _in diesen spezifischen Szenarien_ gefiltert werden. <sup>\*</sup> Die erweiterte Übermittlungsrichtlinie stellt sicher, dass Nachrichten in diesen Szenarien die folgenden Ergebnisse erzielen:

- Filter in EOP und Microsoft Defender für Office 365 keine Aktion für diese Nachrichten ausführen.<sup>\*</sup>
- [Zero-Hour Purge (ZAP)](zero-hour-auto-purge.md) for spam and phishing take no action on these messages.<sup>\*</sup>
- [Standardsystemwarnungen](alerts.md) werden für diese Szenarien nicht ausgelöst.
- [AIR und Clustering in Defender für Office 365](office-365-air.md) ignoriert diese Nachrichten.
- Speziell für Phishingsimulationen von Drittanbietern:
  - [Administratorübermittlungen](admin-submission.md) generieren eine automatische Antwort, die besagt, dass die Nachricht Teil einer Phishingsimulationskampagne ist und keine echte Bedrohung ist. Warnungen und AIR werden nicht ausgelöst.
  - [Tresor Links in Defender für Office 365](safe-links.md) blockieren oder detonieren die spezifisch identifizierten URLs in diesen Nachrichten nicht.
  - [Tresor Anlagen in Defender für Office 365](safe-attachments.md) detonieren keine Anlagen in diesen Nachrichten.

<sup>\*</sup> Sie können die Schadsoftwarefilterung oder ZAP für Schadsoftware nicht umgehen.

Nachrichten, die von der erweiterten Übermittlungsrichtlinie identifiziert werden, sind keine Sicherheitsbedrohungen, daher werden die Nachrichten als Systemüberschreibungen gekennzeichnet. Administratoren können diese Systemüberschreibungen in den folgenden Umgebungen filtern und analysieren:

- [Bedrohungs-Explorer/Echtzeiterkennungen in Defender für Office 365 Plan 2](threat-explorer.md)
- Die [Seite "E-Mail-Entität" im Bedrohungs-Explorer/Echtzeiterkennungen](mdo-email-entity-page.md)
- Der [Statusbericht zum Bedrohungsschutz](view-email-security-reports.md#threat-protection-status-report)
- [Erweiterte Suche in Microsoft Defender für Endpunkt](../defender-endpoint/advanced-hunting-overview.md)
- [Kampagnenansichten](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Microsoft 365 Defender-Portal unter <https://security.microsoft.com>. To go directly to the **Advanced delivery** page, open <https://security.microsoft.com/advanceddelivery> .

- Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:
  - Um konfigurierte Einstellungen in der erweiterten Übermittlungsrichtlinie zu erstellen, zu ändern oder zu entfernen, müssen Sie Mitglied der **Rollengruppe "Sicherheitsadministrator"** im **Microsoft 365 Defender-Portal** und Mitglied der **Rollengruppe "Organisationsverwaltung"** in **Exchange Online** sein.  
  - Für den schreibgeschützten Zugriff auf die Erweiterte Übermittlungsrichtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal](permissions-microsoft-365-security-center.md) und ["Berechtigungen" in Exchange Online.](/exchange/permissions-exo/permissions-exo)

  > [!NOTE]
  > Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Verwenden des Microsoft 365 Defender-Portals zum Konfigurieren von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Seite \>  \> **"Regeln für Bedrohungsrichtlinien"** im Abschnitt \>  \> **"Erweiterte Zustellung".**

2. Überprüfen Sie auf der Seite **"Erweiterte Zustellung",** ob die Registerkarte **"SecOps-Postfach"** ausgewählt ist, und führen Sie dann einen der folgenden Schritte aus:
   - Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.
   - Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**

3. Geben Sie im Flyout **"SecOps-Postfächer bearbeiten",** das geöffnet wird, ein vorhandenes Exchange Online Postfach ein, das Sie als SecOps-Postfach festlegen möchten, indem Sie einen der folgenden Schritte ausführen:
   - Klicken Sie in das Feld, lassen Sie die Liste der Postfächer auflösen, und wählen Sie dann das Postfach aus.
   - Klicken Sie in das Feld, um einen Bezeichner für das Postfach (Name, Anzeigename, Alias, E-Mail-Adresse, Kontoname usw.) einzugeben, und wählen Sie das Postfach (Anzeigename) aus den Ergebnissen aus.

     Wiederholen Sie diesen Schritt so oft wie nötig. Verteilergruppen sind nicht zulässig.

     Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

Die von Ihnen konfigurierten SecOps-Postfacheinträge werden auf der Registerkarte **"SecOps-Postfach"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Verwenden des Microsoft 365 Defender Portals zum Konfigurieren von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Portal Microsoft 365 Defender zu **E-Mail-& Richtlinien** für die Zusammenarbeit & Seite \>  \> **"Regeln für Bedrohungsrichtlinien"** im Abschnitt \>  \> **"Erweiterte Zustellung".**

2. Wählen Sie auf der Seite **"Erweiterte Übermittlung"** die Registerkarte **"Phishingsimulation"** aus, und führen Sie dann einen der folgenden Schritte aus:
   - Klicken Sie auf ![ ](../../media/m365-cc-sc-edit-icon.png) **"Bearbeiten"-Symbol**.
   - Wenn keine konfigurierten Phishingsimulationen vorhanden sind, klicken Sie auf **Hinzufügen.**

3. Konfigurieren Sie im Flyout **"Phishingsimulation** von Drittanbietern bearbeiten", das geöffnet wird, die folgenden Einstellungen:

   - **Sendende Domäne:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine E-Mail-Adressdomäne (z. B. contoso.com) ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unterhalb des Felds angezeigt wird. Wiederholen Sie diesen Schritt so oft wie nötig. Sie können bis zu 10 Einträge hinzufügen.
   - **Senden der IP:** Erweitern Sie diese Einstellung, und geben Sie mindestens eine gültige IPv4-Adresse ein, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird. Wiederholen Sie diesen Schritt so oft wie nötig. Sie können bis zu 10 Einträge hinzufügen. Gültige Werte sind:
     - Single IP: For example, 192.168.1.1.
     - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
     - CIDR-IP: Beispiel: 192.168.0.1/25.
   - **Zuzulassende Simulations-URLs:** Erweitern Sie diese Einstellung, und geben Sie optional bestimmte URLs ein, die Teil Ihrer Phishingsimulationskampagne sind, die nicht blockiert oder detoniert werden soll, indem Sie in das Feld klicken, einen Wert eingeben und dann die EINGABETASTE drücken oder den Wert auswählen, der unter dem Feld angezeigt wird. Sie können bis zu 10 Einträge hinzufügen.

   Um einen vorhandenen Wert zu entfernen, klicken Sie auf das ![Symbol „Entfernen“](../../media/m365-cc-sc-remove-selection-icon.png) neben dem Wert.

4. Wenn Sie fertig sind, führen Sie einen der folgenden Schritte aus:
   - **First time**: Click **Add**, and then click **Close**.
   - **Vorhandenes bearbeiten:** Klicken Sie auf **"Speichern"** und dann auf **"Schließen".**

Die von Ihnen konfigurierten Einträge für Phishingsimulationen von Drittanbietern werden auf der Registerkarte **"Phishingsimulation"** angezeigt. Wenn Sie Änderungen vornehmen möchten, klicken Sie ![ auf der Registerkarte auf das ](../../media/m365-cc-sc-edit-icon.png) Bearbeitungssymbol **"Bearbeiten".**

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Zusätzliche Szenarien, für die eine Filterumgehung erforderlich ist

Zusätzlich zu den beiden Szenarien, die Ihnen mit der erweiterten Übermittlungsrichtlinie helfen können, gibt es weitere Szenarien, in denen Sie die Filterung umgehen müssen:

- **Filter von Drittanbietern:** Wenn der MX-Eintrag Ihrer Domäne *nicht* auf Office 365 verweist (Nachrichten werden zuerst an eine andere Stelle weitergeleitet), ist [die Standardmäßige Sicherheit](secure-by-default.md) nicht *verfügbar.*

  Um die Microsoft-Filterung für Nachrichten zu umgehen, die bereits von der Drittanbieterfilterung ausgewertet wurden, verwenden Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet). Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln, um die SCL in Nachrichten festzulegen.](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- **Falsch positive Ergebnisse, die überprüft** werden: Möglicherweise möchten Sie bestimmten Nachrichten, die noch von Microsoft über [Administratorübermittlungen](admin-submission.md) analysiert werden, vorübergehend gestatten, bekannte gute Nachrichten zu melden, die fälschlicherweise als falsch für Microsoft gekennzeichnet sind (falsch positive Ergebnisse). Wie bei allen Außerkraftsetzungen wird **_dringend empfohlen,_** dass diese Außerkraftsetzungen temporär sind.
