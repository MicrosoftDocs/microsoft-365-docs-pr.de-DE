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
description: Administratoren können erfahren, wie Sie die erweiterte Zustellungsrichtlinie in Exchange Online Protection (EOP) verwenden, um Nachrichten zu identifizieren, die nicht in bestimmten unterstützten Szenarien gefiltert werden sollten (Phishingsimulationen von Drittanbietern und Nachrichten, die an SecOps-Postfächer (Security Operations, SecOps) übermittelt werden.
ms.technology: mdo
ms.prod: m365-security
ROBOTS: NOINDEX
ms.openlocfilehash: 09e07d8406b470fd3dac25944d013b997f2f90c1
ms.sourcegitcommit: 223a36a86753fe9cebee96f05ab4c9a144133677
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51760431"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>Konfigurieren der Übermittlung von Phishingsimulationen von Drittanbietern an Benutzer und ungefilterte Nachrichten an SecOps-Postfächer

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> Das in diesem Artikel beschriebene Feature befindet sich in Preview, ist nicht für alle verfügbar und kann geändert werden.

Wir möchten Ihre Organisation standardmäßig [schützen,](secure-by-default.md)sodass Exchange Online Protection (EOP) keine sicheren Listen oder Filterumgehungen für Nachrichten zu lässt, die zu Schadsoftware oder phishingsicheren Phishing-Urteilen führen. Wir wissen jedoch, dass es bestimmte Szenarien gibt, die die Zustellung ungefilterter Nachrichten erfordern. Beispiel:

- **Phishingsimulationen von** Drittanbietern: Simulierte Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren, bevor sich ein tatsächlicher Angriff auf Ihre Organisation aus wirkt.
- **Sicherheitsvorgänge (SecOps)-Postfächer:** Dedizierte Postfächer, die von Sicherheitsteams zum Sammeln und Analysieren ungefilterter Nachrichten (sowohl gut als auch schlecht) verwendet werden.

Sie verwenden die _erweiterte Zustellungsrichtlinie_ in Microsoft 365, um zu verhindern, dass diese Nachrichten _in_ diesen spezifischen Szenarien gefiltert <sup>\*</sup> werden. Die erweiterte Übermittlungsrichtlinie stellt sicher, dass Nachrichten in diesen Szenarien nicht gefiltert werden:

- Filter in EOP und Microsoft Defender für Office 365 ergreifen keine Aktion für diese Nachrichten.<sup>\*</sup>
- [Die Zero-Hour Purge (ZAP)](zero-hour-auto-purge.md) für Spam und Phishing ergreift keine Aktion für diese Nachrichten.<sup>\*</sup>
- [Standardsystemwarnungen](alerts.md) werden für diese Szenarien nicht ausgelöst.
- [AIR und clustering in Defender for Office 365](office-365-air.md) ignoriert diese Nachrichten.
- Speziell für Phishingsimulationen von Drittanbietern:
  - [Administratorübermittlungen](admin-submission.md) generiert eine automatische Antwort, die besagt, dass die Nachricht Teil einer Phishingsimulationskampagne ist und keine echte Bedrohung ist. Warnungen und AIR werden nicht ausgelöst.
  - [Sichere Links in Defender for Office 365](safe-links.md) blockieren oder detonieren die speziell identifizierten URLs in diesen Nachrichten nicht.
  - [Sichere Anlagen in Defender für Office 365](safe-attachments.md) detonieren anlagen in diesen Nachrichten nicht.

<sup>\*</sup> Sie können Schadsoftwarefilterung oder ZAP für Schadsoftware nicht umgehen.

Nachrichten, die durch die erweiterte Übermittlungsrichtlinie identifiziert werden, sind keine Sicherheitsbedrohungen, daher werden die Nachrichten als Systemüberschreibungen markiert. Administratoren können diese Systemüberschreibungen in den folgenden Erfahrungen filtern und analysieren:

- [Bedrohungs-Explorer/Echtzeiterkennungen in Defender for Office 365 Plan 2](threat-explorer.md)
- Die [Seite der E-Mail-Entität im Bedrohungs-Explorer/Echtzeiterkennungen](mdo-email-entity-page.md)
- Der [Statusbericht zum Bedrohungsschutz](view-email-security-reports.md#threat-protection-status-report)
- [Erweiterte Suche in Microsoft Defender for Endpoint](../defender-endpoint/advanced-hunting-overview.md)
- [Kampagnenansichten](campaigns.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>. Öffnen Sie , um direkt zur **Seite Erweiterte Zustellung zu** <https://protection.office.com/advanceddelivery> wechseln.

- Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden:
  - Zum Erstellen, Ändern oder Entfernen konfigurierter Einstellungen in der Erweiterten Übermittlungsrichtlinie müssen Sie Mitglied der Rollengruppe Sicherheitsadministrator im  **Security & Compliance Center** und Mitglied der Rollengruppe Organisationsverwaltung in Exchange **Online sein.**   
  - Für den schreibgeschützten Zugriff auf die Erweiterte Übermittlungsrichtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.

  Weitere Informationen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md) and Permissions in Exchange [Online](/exchange/permissions-exo/permissions-exo).

## <a name="use-the-security--compliance-center-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>Verwenden des Security & Compliance Center zum Konfigurieren von Phishingsimulationen von Drittanbietern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Security & Compliance Center zu **Threat** \> **Management Policy** Advanced \> **delivery**.

2. Wählen Sie **auf der Seite Erweiterte** Zustellung die Registerkarte **Phishingsimulation** aus, und klicken Sie dann auf **Bearbeiten**.

3. Konfigurieren Sie **im geöffneten** Flyout der Phishingsimulation eines Drittanbieters die folgenden Einstellungen:

   - **Senden einer** Domäne : Mindestens eine E-Mail-Adressdomäne ist erforderlich (z. B. contoso.com). Sie können bis zu 10 Einträge hinzufügen.
   - **Senden von IP:** Mindestens eine gültige IPv4-Adresse ist erforderlich. Sie können bis zu 10 Einträge hinzufügen. Gültige Werte sind:
     - Einzelne IP: Beispiel: 192.168.1.1.
     - IP-Bereich: Beispiel: 192.168.0.1-192.168.0.254.
     - CIDR-IP: Beispiel: 192.168.0.1/25.
   - **Zu erlaubende** Simulations-URLs: Geben Sie optional bestimmte URLs ein, die Teil Ihrer Phishingsimulationskampagne sind, die nicht blockiert oder detoniert werden sollten. Sie können bis zu 10 Einträge hinzufügen.

4. Klicken Sie nach Abschluss des Abschlusses auf **Speichern.**

Die von Ihnen konfigurierten Phishingsimulationseinträge von Drittanbietern werden auf der Registerkarte **Phishingsimulation** angezeigt. Klicken Sie auf der Registerkarte auf **Bearbeiten,** um Änderungen vorzunehmen.

## <a name="use-the-security--compliance-center-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>Verwenden des Security & Compliance Center zum Konfigurieren von SecOps-Postfächern in der erweiterten Übermittlungsrichtlinie

1. Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Advanced delivery**.

2. Wählen Sie **auf der** Seite Erweiterte Zustellung die Registerkarte **SecOps-Postfach** aus, und klicken Sie dann auf **Bearbeiten**.

3. Geben Sie **im geöffneten SecOps-Postfachf** flyout die E-Mail-Adressen vorhandener Exchange Online-Postfächer ein, die Sie als SecOps-Postfächer festlegen möchten. Verteilergruppen sind nicht zulässig.

4. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

Die von Ihnen konfigurierten SecOps-Postfacheinträge werden auf der **Registerkarte SecOps-Postfach** angezeigt. Klicken Sie auf der Registerkarte auf **Bearbeiten,** um Änderungen vorzunehmen.

## <a name="additional-scenarios-that-require-filtering-bypass"></a>Zusätzliche Szenarien, die eine Filterumgehung erfordern

Zusätzlich zu den beiden Szenarien, die Ihnen die erweiterte Übermittlungsrichtlinie helfen kann, gibt es weitere Szenarien, für die Sie die Filterung umgehen müssen:

- **Filter von** Drittanbietern: Wenn der MX-Eintrag Ihrer Domäne nicht auf Office 365 (Nachrichten werden zuerst an einen anderen Ort geroutet) [](secure-by-default.md) verweisen, ist die Sicherheit standardmäßig nicht verfügbar.

  Verwenden Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet), um die Microsoft-Filterung für Nachrichten zu umgehen, die bereits von Drittanbietern ausgewertet wurden. Weitere Informationen finden Sie unter Use mail flow rules to set [the SCL in messages](use-mail-flow-rules-to-set-the-spam-confidence-level-scl-in-messages.md).

- **Falsch positive** Ergebnisse werden überprüft: Möglicherweise möchten Sie vorübergehend zulassen, dass [](admin-submission.md) bestimmte Nachrichten, die noch von Microsoft über Administratorübermittlungen analysiert werden, bekannte gute Nachrichten melden, die fälschlicherweise als schlecht für Microsoft markiert werden (falsch positive Ergebnisse). Wie bei allen Außerkraftsetzungen wird dringend empfohlen, dass diese Zertifikate temporär sind.
