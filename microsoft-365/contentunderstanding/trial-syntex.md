---
title: Ausführen einer Testversion von Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie ein Testpilotprogramm für SharePoint Syntex in Ihrer Organisation planen und ausführen.
ms.openlocfilehash: 2668c0c85d6b8c73d377ac9efffc7f777fc7add6
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327118"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>Ausführen einer Testversion von Microsoft SharePoint Syntex

In diesem Artikel wird beschrieben, wie Sie ein Testpilotprogramm einrichten und ausführen, um SharePoint Syntex in Ihrer Organisation bereitzustellen. Außerdem werden bewährte Methoden für die Testversion empfohlen.

## <a name="sign-up-for-a-trial"></a>Registrieren für eine Testversion

Die Testversion von SharePoint Syntex bietet 300 Benutzern 30 Tage Lang Zugriff.

> [!NOTE]
> Bis zu 300 Benutzer sind in der Testversion enthalten, um die automatische Hinzufügung von 1 Million AI Builder-Guthaben sicherzustellen. Sie müssen nicht 300 Benutzer einschließen, damit eine Testversion erfolgreich ist.

Sie können die Testversion aus einer der folgenden Quellen abrufen:

- Die [SharePoint Syntex Produktseite](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- Die [Microsoft 365 Admin Center](https://admin.microsoft.com)
    1.  Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
    2.  Wechseln Sie zu  >  **Abrechnungskaufdienste**.
    3.  Blättern Sie nach unten zum Bereich **Add-Ons**.
    4.  Wählen Sie auf der Kachel SharePoint Syntex **Details** aus.
    5.  Wählen Sie **Kostenlose Testversion abrufen** aus.
    6.  Um die Testversion zu bestätigen, führen Sie die verbleibenden Schritte des Assistenten aus.

Sie müssen ein Microsoft 365 globaler Administrator oder Abrechnungsadministrator sein, um eine Testversion zu aktivieren.

### <a name="who-should-be-involved-in-a-trial"></a>Wer an einer Testversion beteiligt sein sollten

|Rolle  |Aktivität  |
|---------|---------|
|Microsoft 365 globaler Administrator oder Abrechnungsadministrator    |     Aktivieren der Testversion und Zuweisen von Lizenzen    |
|Microsoft 365 globaler Administrator oder SharePoint-Administrator     |   Konfigurieren SharePoint Syntex und Erstellen von Inhaltscentern      |
|Geschäftsbenutzer     |    Modellerstellung und -tests     |

### <a name="before-you-activate-a-trial"></a>Vor der Aktivierung einer Testversion

Um eine SharePoint Syntex Testversion erfolgreich zu planen, berücksichtigen Sie die folgenden Faktoren:

- Die aussagekräftigsten Tests werden in "realen" Szenarien und Daten durchgeführt.
- Sie können eine SharePoint Syntex Testversion nur einmal pro Mandant aktivieren.

Ein Test- oder Demomandant kann als "Trockenlauf" verwendet werden, um die Aktivierungsschritte und administrativen Kontrollen zu durchlaufen. Aber es ist wahrscheinlich am besten, das Modell basierend auf einem Produktionsmandanten zu bewerten.

Um den Wert einer Testversion für einen Produktionsmandanten zu maximieren, sind Planung und geschäftliches Engagement unerlässlich. Sie sollten einen oder mehrere Geschäftsbereiche einbeziehen, um drei bis sechs Anwendungsfälle zu identifizieren, die möglicherweise von SharePoint Syntex behoben werden können. Diese Anwendungsfälle sollten:

- Schließen Sie Szenarien ein, die entweder durch die Formularverarbeitung oder das Dokumentverständnismodell gelöst werden können.
- Sie haben ein klares Verständnis des Zwecks für alle extrahierten Metadaten; Beispiel: Ansichtsformatierung oder Automatisierung mithilfe von Power Automate. Während sich SharePoint Syntex auf das Klassifizieren von Dokumenten und das Extrahieren von Metadaten konzentriert, ermöglicht diese Metadaten den zu quantifizierenden Wert.
- Basieren auf einem definierten Satz von Daten; Beispielsweise bestimmte SharePoint Websites oder Bibliotheken. Ein häufiges Missverständnis von SharePoint Syntex besteht darin, dass allgemeine Modelle auf alle Organisationsinhalte angewendet werden können. Eine genauere Ansicht ist, dass Modelle entwickelt wurden, um bestimmte Geschäftsprobleme an zielgerichteten Standorten zu lösen.

Alle diese Anwendungsfälle sind möglicherweise nicht gut geeignet für SharePoint Syntex. Das Ziel einer Qualitätsprüfung besteht nicht darin, nachzuweisen, dass SharePoint Syntex in alle Szenarien passt. Stattdessen sollte ihnen die Testversion helfen, den Wert des Produkts besser zu verstehen.

Identifizieren Sie für jeden der geplanten Anwendungsfälle Benutzer, die Fachexperten in den verwandten Inhalten oder Prozessen sind. Die Erstellung SharePoint Syntex Modelle konzentriert sich auf Domänenexperten in den Inhalten und nicht auf IT-Experten oder Entwicklerressourcen.

## <a name="activate-a-trial"></a>Aktivieren einer Testversion

Wenn Sie eine Testversion initiieren, müssen Sie:

- Weisen Sie den relevanten Benutzern Lizenzen zu.
- Führen Sie [eine zusätzliche Einrichtung von SharePoint Syntex](set-up-content-understanding.md)aus.
    - Möglicherweise möchten Sie [zusätzliche Inhaltscenter erstellen.](create-a-content-center.md)

Nachdem die Testversion aktiviert wurde, können Sie Modelle erstellen und Dateien verarbeiten. Siehe [Anleitung für die Modellerstellung.](create-a-content-center.md)

## <a name="during-a-trial"></a>Während einer Testversion

Testzeitraume sind begrenzt. Daher sollten Sie sich zunächst darauf konzentrieren, ob SharePoint Syntex Modelle Dokumente klassifizieren und Metadaten für die definierten Anwendungsfälle extrahieren können. Nach Ablauf des Testzeitraums können Sie auswerten, wie die Metadaten ausgenutzt werden können.

## <a name="after-a-trial"></a>Nach einer Testversion

Basierend auf dem Ergebnis der Testversion können Sie entscheiden, ob Sie mit der Produktionsverwendung von SharePoint Syntex fortfahren möchten.

### <a name="proceed-to-production-use"></a>Fahren Sie mit der Produktionsverwendung fort

Um die Kontinuität des Dienstes sicherzustellen, müssen Sie die erforderliche Anzahl von Lizenzen erwerben und diese Lizenzen Benutzern zuweisen. Testbenutzer, die am Ende des Testzeitraums nicht über eine Volllizenz verfügen, können SharePoint Syntex nicht vollständig nutzen.

Möglicherweise müssen Sie die geplante Verwendung der Formularverarbeitung abschätzen und den erwarteten Umfang des AI Builder-Guthabens planen. Hilfe finden Sie unter ["Schätzen der AI Builder-Kapazität, die für Sie geeignet ist".](https://powerapps.microsoft.com/ai-builder-calculator/)

### <a name="dont-proceed-to-production-use"></a>Fahren Sie nicht mit der Produktionsverwendung fort

Wenn Sie nach der Testversion keine Lizenzen erwerben:

- Sie können keine neuen Modelle erstellen.
- Bibliotheken, in denen Modelle ausgeführt wurden, klassifizieren nicht mehr automatisch Dateien oder extrahieren Modelle.
- Alle zuvor klassifizierten Dateien oder extrahierten Metadaten sind davon nicht betroffen. 
- Inhaltscenter und alle Dokumentverständnismodelle werden nicht automatisch gelöscht. Diese bleiben für die Verwendung verfügbar, wenn Sie sich entscheiden, in Zukunft Lizenzen zu erwerben.
- Formularverarbeitungsmodelle werden in der Common Data Services (CDS)-Instanz der Standardmäßigen Power Platform-Umgebung gespeichert. Diese können mit zukünftiger Lizenzierung für SharePoint Syntex oder mit AI Builder-Funktionen in der Power Platform verwendet werden.

## <a name="see-also"></a>Siehe auch

[Einführung von Microsoft SharePoint Syntex: Erste Schritte](adoption-getstarted.md)
