---
title: Microsoft Defender for Identity-Sicherheitswarnungen in Microsoft 365 Defender
description: Informationen zum Verwalten und Überprüfen von Sicherheitswarnungen von Microsoft Defender for Identity in Microsoft 365 Defender
ms.date: 05/20/2021
ms.topic: how-to
author: dcurwin
ms.author: dacurwin
ms.service: microsoft-defender-for-identity
manager: raynew
ms.openlocfilehash: 0c48c9076d05cd352229477acc28b32185eef54f
ms.sourcegitcommit: 4f6ef4cd09c3ed36dc0be3702b0636bad6cff8a9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/26/2021
ms.locfileid: "52657851"
---
# <a name="defender-for-identity-security-alerts-in-microsoft-365-defender"></a>Sicherheitswarnungen für Defender for Identity in Microsoft 365 Defender

**Gilt für:**

- Microsoft 365 Defender
- Defender for Identity

In diesem Artikel werden die Grundlagen der Verwendung von [Microsoft Defender for Identity-Sicherheitswarnungen](/defender-for-identity) im Microsoft 365 [erläutert.](/microsoft-365/security/defender/overview-security-center)

Defender for Identity-Warnungen werden nativ in das [Microsoft 365 Security Center](https://security.microsoft.com) mit einem dedizierten Format der Identitätsbenachrichtigungsseite integriert. Dies ist der erste Schritt auf dem Weg zur Einführung der vollständigen [Microsoft Defender for Identity-Erfahrung in Microsoft 365 Defender](/defender-for-identity/defender-for-identity-in-microsoft-365-defender).

Die neue Seite für Identitätsbenachrichtigungen bietet Microsoft Defender for Identity-Kunden eine bessere domänenübergreifende Signalerweiterung und neue automatisierte Funktionen zur Identitätsantwort. Dadurch wird sichergestellt, dass Sie sicher bleiben und die Effizienz Ihrer Sicherheitsvorgänge verbessern.

Einer der Vorteile der Untersuchung von Warnungen über [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) ist, dass Microsoft Defender for Identity-Warnungen weiter mit den Informationen korreliert werden, die von jedem der anderen Produkte in der Suite erhalten wurden. Diese erweiterten Warnungen sind mit den anderen Microsoft 365 Defender-Warnungsformaten konsistent, die von [Microsoft Defender for Office 365](/microsoft-365/security/office-365-security) und Microsoft Defender for Endpoint [stammen.](/microsoft-365/security/defender-endpoint) Die neue Seite entfällt effektiv die Notwendigkeit, zu einem anderen Produktportal zu navigieren, um Warnungen im Zusammenhang mit der Identität zu untersuchen.

Warnungen, die von Defender for Identity stammen, können nun die automatisierten Untersuchungs- und Reaktionsfunktionen [von Microsoft 365 Defender auslösen,](/microsoft-365/security/defender/m365d-autoir) einschließlich der automatischen Behebung von Warnungen und der Minderung von Tools und Prozessen, die zur verdächtigen Aktivität beitragen können.

>[!IMPORTANT]
>Im Rahmen der Konvergenz mit Microsoft 365 Defender haben sich einige Optionen und Details von ihrem Speicherort im Defender for Identity-Portal geändert. Lesen Sie die folgenden Details, um herauszufinden, wo Sie sowohl die vertrauten als auch die neuen Features finden können.

## <a name="review-security-alerts"></a>Überprüfen von Sicherheitswarnungen

Der Zugriff auf Warnungen kann  von mehreren  Speicherorten aus möglich sein, einschließlich der Seite Warnungen, der Seite Vorfälle, der Seiten einzelner Geräte und der Seite Erweiterte **Suche.** In diesem Beispiel wird die Seite "Warnungen" **überprüft.**  

Wechseln Sie [Microsoft 365 Sicherheitscenter](https://security.microsoft.com/)zu Vorfälle **&** Warnungen und dann zu **Warnungen**.

![Wechseln Sie zu Vorfälle und Warnungen und dann zu Warnungen](../../media/defender-identity/incidents-alerts.png)

Um Warnungen von Defender for Identity anzuzeigen, wählen Sie oben rechts **Filter** aus, und wählen Sie dann unter **Dienstquellen** **Microsoft Defender for Identity** aus, und wählen Sie **Übernehmen** aus:

![Filtern nach Defender for Identity-Ereignissen](../../media/defender-identity/filter-defender-for-identity.png)

Die Warnungen werden mit Informationen in den folgenden Spalten **angezeigt:** Warnungsname , **Tags** **,** Schweregrad **,** Untersuchungsstatus , **Status**, **Kategorie**, **Erkennungsquelle** **,** Auswirkungsressourcen , **Erste** Aktivität und **Letzte Aktivität**.

![Defender for Identity-Ereignisse](../../media/defender-identity/filtered-alerts.png)

## <a name="manage-alerts"></a>Verwalten von Warnungen

Wenn Sie auf den **Warnungsnamen** für eine der Warnungen klicken, wechseln Sie zur Seite mit Details zur Warnung. Im linken Bereich sehen Sie eine Zusammenfassung von **Was passiert ist:**

![Was in der Warnung passiert ist](../../media/defender-identity/what-happened.png)

Über dem **Feld Was passiert** ist, befinden sich Schaltflächen für die **Konten,** **den Zielhost** und den **Quellhost** der Warnung. Für andere Warnungen werden möglicherweise Schaltflächen für Details zu zusätzlichen Hosts, Konten, IP-Adressen, Domänen und Sicherheitsgruppen angezeigt. Wählen Sie einen dieser Elemente aus, um weitere Details zu den beteiligten Entitäten zu erhalten.

Im rechten Bereich werden die **Warnungsdetails angezeigt.** Hier können Sie weitere Details anzeigen und verschiedene Aufgaben ausführen:

- **Klassifizieren dieser Warnung** – Hier können Sie diese Warnung als **True- oder** **False-Warnung festlegen.**

    ![Klassifizieren von Warnungen](../../media/defender-identity/classify-alert.png)

- **Warnungsstatus** : Unter **Klassifizierung festlegen** können Sie die Warnung als **True oder** **False klassifizieren.** In **Assigned to** können Sie die Warnung sich selbst zuweisen oder sie nicht mehr zuweisen.

    ![Warnungsstatus](../../media/defender-identity/alert-state.png)

-  Warnungsdetails: Unter Warnungsdetails finden Sie weitere Informationen zu der spezifischen Warnung, folgen Sie einem Link zur Dokumentation zum Typ der Warnung, sehen Sie, welchem Vorfall die Warnung zugeordnet ist, überprüfen Sie alle automatisierten Untersuchungen, die mit diesem Warnungstyp verknüpft sind, und sehen Sie sich die betroffenen Geräte und Benutzer an.

    ![Warnungsdetails](../../media/defender-identity/alert-details.png)

- **Kommentare & -** Hier können Sie Ihre Kommentare zur Warnung hinzufügen und den Verlauf aller Aktionen im Zusammenhang mit der Warnung sehen.

    ![Kommentare und Verlauf](../../media/defender-identity/comments-history.png)

- **Warnung verwalten** : Wenn Sie Warnung **verwalten** auswählen, wechseln Sie zu einem Bereich, in dem Sie die:
  - **Status** : Sie können **Neu,** **Aufgelöst** oder **In Bearbeitung auswählen.**
  - **Klassifizierung** : Sie können True **alert oder** False **alert auswählen.**
  - **Kommentar** : Sie können einen Kommentar zu der Warnung hinzufügen.

    Wenn Sie die drei Punkte neben Warnung verwalten **auswählen,**  können Sie einen Bedrohungsexperten **konsultieren,** die Warnung in eine Excel exportieren oder mit einem anderen Vorfall **verknüpfen**.

    ![Verwalten von Warnungen](../../media/defender-identity/manage-alert.png)

    >[!NOTE]
    >In der Excel haben Sie nun zwei Links verfügbar: **Anzeigen in Microsoft Defender for Identity** und View in Microsoft 365 **Defender**. Jeder Link bringt Sie zum entsprechenden Portal und stellt Dort Informationen zur Warnung zur Verfügung.

## <a name="see-also"></a>Siehe auch

- [Untersuchen von Warnungen in Microsoft 365 Defender](../defender/investigate-alerts.md)
