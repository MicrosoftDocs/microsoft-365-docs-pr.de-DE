---
title: Sicherheitswarnungen für Microsoft Defender for Identity in Microsoft 365 Defender
description: Erfahren Sie, wie Sie von Microsoft Defender for Identity ausgegebene Sicherheitswarnungen in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: c81f14b92b285359bda7e291bd8d3a8b636ae54d
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228963"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Sicherheitswarnungen für Defender for Identity in Microsoft 365 Defender

**Gilt für:**

- Microsoft 365 Defender
- Defender for Identity

In diesem Artikel werden die Grundlagen der Verwendung von Microsoft Defender for Identity-Sicherheitswarnungen im [Microsoft 365 Security Center erläutert.](/microsoft-365/security/defender/overview-security-center) [](/defender-for-identity)

Defender for Identity-Warnungen sind nativ in das [Microsoft 365 Security Center](https://security.microsoft.com) mit einem dedizierten Identitätswarnungsseitenformat integriert. Dies ist der erste Schritt auf der Reise, um [die vollständige Microsoft Defender for Identity-Erfahrung in Microsoft 365 Defender einzuführen.](/defender-for-identity/defender-for-identity-in-microsoft-365-defender)

Die neue Identitätswarnungsseite bietet Microsoft Defender for Identity-Kunden eine bessere domänenübergreifende Signalanreicherung und neue automatisierte Identitätsantwortfunktionen. Es stellt sicher, dass Sie sicher bleiben, und verbessert die Effizienz Ihrer Sicherheitsvorgänge.

Einer der Vorteile der Untersuchung von Warnungen über [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) besteht darin, dass Microsoft Defender for Identity-Warnungen weiter mit Informationen korreliert werden, die von jedem der anderen Produkte in der Suite abgerufen werden. Diese erweiterten Warnungen stimmen mit den anderen Microsoft 365 Defender Warnungsformaten überein, die von [Microsoft Defender für Office 365](/microsoft-365/security/office-365-security) und Microsoft Defender für [Endpunkt](/microsoft-365/security/defender-endpoint)stammen. Auf der neuen Seite entfällt effektiv die Notwendigkeit, zu einem anderen Produktportal zu navigieren, um mit der Identität verknüpfte Warnungen zu untersuchen.

Warnungen, die von Defender for Identity stammen, können jetzt die Microsoft 365 Defender Air-Funktionen [(Automated Investigation and Response, automatische Untersuchung und Reaktion)](/microsoft-365/security/defender/m365d-autoir) auslösen, einschließlich der automatischen Korrektur von Warnungen und der Minderung von Tools und Prozessen, die zu der verdächtigen Aktivität beitragen können.

> [!IMPORTANT]
> Im Rahmen der Konvergenz mit Microsoft 365 Defender haben sich einige Optionen und Details von ihrem Standort im Defender for Identity-Portal geändert. Lesen Sie die details unten, um herauszufinden, wo Sie die vertrauten und neuen Features finden.

## <a name="review-security-alerts"></a>Überprüfen von Sicherheitswarnungen

Auf Warnungen kann von mehreren Standorten aus zugegriffen werden, einschließlich der Seite **"Warnungen",** der Seite **"Vorfälle",** der Seiten der einzelnen **Geräte** und der Seite **"Erweiterte Suche".** In diesem Beispiel überprüfen wir die **Seite "Warnungen".**

Wechseln [Sie](https://security.microsoft.com/)im Microsoft 365 Security Center zu **Vorfällen & Warnungen** und dann zu **Warnungen.**

![Wechseln Sie zu "Vorfälle und Warnungen" und dann zu "Warnungen".](../../media/defender-identity/incidents-alerts.png)

Um Warnungen von Defender for Identity anzuzeigen, wählen Sie oben rechts **"Filter"** aus, und wählen Sie dann unter **"Dienstquellen"** **Microsoft Defender for Identity** aus, und wählen Sie **"Anwenden"** aus:

![Filtern nach Defender for Identity-Ereignissen](../../media/defender-identity/filter-defender-for-identity.png)

Die Warnungen werden mit Informationen in den folgenden Spalten angezeigt: **Warnungsname**, **Tags**, Schweregrad , **Untersuchungsstatus**, **Status**, **Kategorie**, **Erkennungsquelle**, **betroffene Ressourcen**, **erste Aktivität** und **letzte Aktivität**. 

![Defender for Identity-Ereignisse](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Verwalten von Warnungen

Wenn Sie auf den **Warnungsnamen** für eine der Warnungen klicken, wechseln Sie zur Seite mit Details zur Warnung. Im linken Bereich wird eine Zusammenfassung der **Ereignisse angezeigt:**

![Was in der Warnung passiert ist](../../media/defender-identity/what-happened.png)

Oberhalb des Felds **"Was ist passiert"** befinden sich Schaltflächen für die **Konten,** den **Zielhost** und den **Quellhost** der Warnung. Für andere Warnungen werden möglicherweise Schaltflächen für Details zu zusätzlichen Hosts, Konten, IP-Adressen, Domänen und Sicherheitsgruppen angezeigt. Wählen Sie alle aus, um weitere Details zu den beteiligten Entitäten zu erhalten.

Im rechten Bereich werden die **Warnungsdetails angezeigt.** Hier können Sie weitere Details sehen und verschiedene Aufgaben ausführen:

- **Klassifizieren dieser Warnung** – Hier können Sie diese Warnung als **"True"-** oder **"False"-Warnung** festlegen.

    ![Klassifizieren von Warnungen](../../media/defender-identity/classify-alert.png)

- **Warnungsstatus** : In **"Klassifizierung festlegen"** können Sie die Warnung als **"True"** oder **"False"** klassifizieren. In **Zugewiesen** an können Sie die Warnung selbst zuweisen oder die Zuweisung aufheben.

    ![Warnungsstatus](../../media/defender-identity/alert-state.png)

- **Warnungsdetails** – Unter **"Warnungsdetails"** finden Sie weitere Informationen zu der spezifischen Warnung, folgen Sie einem Link zur Dokumentation zum Typ der Warnung, sehen Sie sich an, mit welchem Vorfall die Warnung verknüpft ist, überprüfen Sie alle automatisierten Untersuchungen, die mit diesem Warnungstyp verknüpft sind, und sehen Sie sich die betroffenen Geräte und Benutzer an.

    ![Warnungsdetails](../../media/defender-identity/alert-details.png)

- **Kommentare & Verlauf** : Hier können Sie Ihre Kommentare zur Warnung hinzufügen und den Verlauf aller aktionen anzeigen, die der Warnung zugeordnet sind.

    ![Kommentare und Verlauf](../../media/defender-identity/comments-history.png)

- **Warnung verwalten** – Wenn Sie **Warnung verwalten** auswählen, wechseln Sie zu einem Bereich, in dem Sie Folgendes bearbeiten können:
  - **Status** : Sie können **neu**, **aufgelöst** oder **in Bearbeitung** auswählen.
  - **Klassifizierung –** Sie können **"True"-** oder **"False"-Warnung** auswählen.
  - **Kommentar** : Sie können einen Kommentar zu der Warnung hinzufügen.

    Wenn Sie die drei Punkte neben **"Warnung verwalten"** auswählen, können Sie **einen Bedrohungsexperten konsultieren,** die Warnung in eine Excel-Datei **exportieren** oder **einen Link zu einem anderen Vorfall erstellen.**

    ![Verwalten von Warnungen](../../media/defender-identity/manage-alert.png)

    > [!NOTE]
    > In der datei Excel stehen nun zwei Links zur Verfügung: **Ansicht in Microsoft Defender for Identity** und Ansicht in **Microsoft 365 Defender**. Über jeden Link gelangen Sie zum entsprechenden Portal und geben Dort Informationen zu der Warnung an.

## <a name="see-also"></a>Siehe auch

- [Untersuchen von Warnungen in Microsoft 365 Defender](../defender/investigate-alerts.md)
