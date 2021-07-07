---
title: Ausführen einer Testversion von Microsoft Viva Topics
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.custom: ''
search.appverid: ''
localization_priority: Normal
description: Erfahren Sie, wie Sie ein Testpilotprogramm für Microsoft Viva Topics in Ihrer Organisation planen und ausführen.
ms.openlocfilehash: 128e82e7664a76baa55d37e983319c9f344624fd
ms.sourcegitcommit: 53aebd492a4b998805c70c8e06a2cfa5d453905c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53327113"
---
# <a name="run-a-trial-of-microsoft-viva-topics"></a>Ausführen einer Testversion von Microsoft Viva Topics

In diesem Artikel wird beschrieben, wie Sie ein Testpilotprogramm einrichten und ausführen, um Viva Topics in Ihrer Organisation bereitzustellen. In diesem Artikel werden auch bewährte Methoden für die Testversion empfohlen.

## <a name="sign-up-for-a-trial"></a>Registrieren für eine Testversion

Testversionen sind aus einer der folgenden Quellen öffentlich verfügbar. Diese Testversionen bieten 25 Benutzern 30 Tage lang Zugriff auf Viva Topics.

- Die [Viva Topics-Produktseite](https://www.microsoft.com/microsoft-viva/topics?activetab=pivot:overviewtab)

- Die [Microsoft 365 Admin Center](https://admin.microsoft.com)
    1.  Melden Sie sich beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.
    2.  Wechseln Sie zu  >  **Abrechnungskaufdienste**.
    3.  Blättern Sie nach unten zum Bereich **Add-Ons**.
    4.  Wählen Sie auf der Kachel **"Themenoberflächen"** die Option **"Details"** aus.
    5.  Wählen Sie **Kostenlose Testversion abrufen** aus.
    6.  Führen Sie die verbleibenden Schritte des Assistenten aus, um die Testversion zu bestätigen.

Sie müssen ein Microsoft 365 globaler Administrator oder Abrechnungsadministrator sein, um eine Testversion zu aktivieren.

> [!NOTE]
> Öffentliche Testversionen können nur einmal für jeden Microsoft 365 Mandanten hinzugefügt werden.

### <a name="who-should-be-involved-in-a-trial"></a>Wer an einer Testversion beteiligt sein sollten

|Rolle  |Aktivität  |
|---------|---------|
|Microsoft 365 globaler Administrator oder Abrechnungsadministrator  |   Aktivieren der Testversion und Zuweisen von Lizenzen      |
|Microsoft 365 globaler Administrator oder SharePoint-Administrator    |       Konfigurieren von Viva Topics und Erstellen von Themencentern  |
|Geschäftsbenutzer     |   Durchführen von Rollen als Wissensmanager, Themenmitwirkender und Themenkunde      |

### <a name="before-you-activate-a-trial"></a>Vor der Aktivierung einer Testversion

Die Planung ist für eine effektive Testversion von Viva Topics unerlässlich. Der Testzeitraum ist begrenzt und muss die Themensuche umfassen und themenbezogene Qualität, Verwaltung und Endbenutzererfahrungen untersuchen.

#### <a name="discovery"></a>Discovery

Es gibt zwei allgemeine Strategieoptionen für die Konfiguration der Themenermittlung während einer Testversion:

- Indizieren Sie alle oder den größten Teil Ihrer SharePoint Onlineinhalte.
   - Bei großen Mandanten kann es bis zu zwei Wochen dauern, bis die Indizierung vollständig erfolgt ist. Während Themen während dieses Zeitraums inkrementell generiert werden, kann die vollständige Indizierung bis zur Hälfte des Testzeitraums beanspruchen.
   - Für Mandanten mit einem erheblichen Datenvolumen kann diese Option eine sehr große Anzahl von Themen erzeugen, möglicherweise Zehntausend.

- Identifizieren Sie eine Teilmenge Ihrer SharePoint Websites für die Indizierung.

Die Auswahl dieser Strategien ist eine Balance zwischen den folgenden beiden Faktoren:

- Genügend Daten, um sinnvolle Themen zu generieren. Die KI in Viva Topics ist auf die Arbeit mit großen Datasets abgestimmt, idealerweise an Datasets mit mehr als 10.000 Dokumenten.
- Es ist überwältigend, während des Testzeitraums nicht so viele Themen zu generieren, dass die Auswertung während des verfügbaren Zeitraums überwältigend ist.

Für die meisten Organisationen ergibt die zweite Strategie das beste Ergebnis.

> [!NOTE]
> Aufgrund der Anzahl von Dokumenten, die für die KI erforderlich sind, empfehlen wir, Viva Topics-Testversionen auf einem Produktionsmandanten auszuführen. Es gibt keine Auswirkungen auf die Leistung des Mandanten während dieses Zeitraums. Nur Benutzer, die über eine Testlizenz verfügen, können auf die Viva Topics-Benutzeroberfläche zugreifen.

#### <a name="roles"></a>Rollen

Während der Testversion müssen drei Rollen aktiv sein, die in der folgenden Tabelle beschrieben werden.

|Rolle  |Aktivität  |
|---------|---------|
|Wissensmanager     |   Steuern der Lebenszyklusphasen von Themen; Themen bestätigen und entfernen; Als Community-Manager für Themenmitwirkende fungieren      |
|Themenmitwirkender    |      Fachexperten für Inhalte, die Folgendes können:<br> Themen überprüfen, um die Qualität von DURCH KI definierten Inhalten zu bewerten<br>Kuratieren von entdeckten Themen mit zusätzlichem Inhalt<br>Erstellen zusätzlicher Themen, die von KI nicht entdeckt wurden   |
|Topic Consumer    |     Themen über Seitenhighlights und Suche nutzen<br>Geben Sie Feedback zum Wert der präsentierten Themen.    |

#### <a name="expected-topics"></a>Themen erwartet

Es kann hilfreich sein, die Themen zu dokumentieren, von denen Sie erwarten, dass sie von der KI generiert werden, auch wenn dies nur auf Annahmen basiert. Diese Aufgabe wird am einfachsten abgeschlossen, wenn Sie eine definierte Teilmenge Ihrer SharePoint Websites indizieren, für die SMEs leicht identifiziert werden können.

Eine dokumentierte Liste hilft Ihnen dabei:

- Überprüfen Sie die Liste der durch KI generierten Themen, die möglicherweise größer als erwartet sind.
- Kennen Sie die Themen, die Sie möglicherweise manuell erstellen müssen oder die Prioritäten für die Kuratierung sind.

Bei einer erfolgreichen Bereitstellung oder Testversion von Viva Topics ist immer eine Mischung aus von KI definierten und vom Menschen erstellten Themen erforderlich.

## <a name="activate-a-trial"></a>Aktivieren einer Testversion

Wenn Sie eine Testversion initiieren, müssen Sie:

- Weisen Sie den relevanten Benutzern Lizenzen zu.
- Führen Sie [eine zusätzliche Einrichtung](set-up-topic-experiences.md) von Viva Topics durch.

Wenn die Testversion aktiviert ist, beginnt der Themenermittlungsprozess.

## <a name="during-a-trial"></a>Während einer Testversion

Der Testzeitraum sollte verwendet werden, um die folgenden Komponenten von Viva Topics zu bewerten:

- Die ki-vorgeschlagenen Themen und Themeninhalte
- Die Endbenutzeroberflächen, das Anzeigen von Themenkarten auf modernen SharePoint Seiten und in Microsoft Search

Die folgenden Faktoren sollten Sie in Ihrem Plan berücksichtigen:

- Damit Viva Topics den maximalen Wert liefern kann, müssen die Inhalte in Themen eine Kombination aus ki-definierten Inhalten und von Menschen zusammengestellten Inhalten sein.
- Alle Benutzeroberflächen sind "Berechtigungskürzung" (einschließlich der Ansicht des Wissensmanagers auf der Seite **"Themen verwalten").** Benutzer sehen ein Thema nur, wenn sie über Berechtigungen zum Anzeigen einiger Ressourcen verfügen, die zum Generieren des Themas verwendet wurden. Dies bedeutet, dass verschiedene Benutzer möglicherweise unterschiedliche Inhalte auf derselben Themenseite sehen.
- Benutzern werden möglicherweise auf der Seite **"Themen verwalten"** mehrere Themen mit demselben Namen angezeigt. Diese Themen sind nicht notwendigerweise Duplikate, sondern können auf einen einzelnen Begriff zurückzuführen sein, der in mehreren Kontexten in den Daten verwendet wird, z. B. einem Projektcodenamen, der von zwei unterschiedlichen Projekten verwendet wird.

## <a name="after-a-trial"></a>Nach einer Testversion

Basierend auf dem Ergebnis der Testversion können Sie entscheiden, ob Sie mit der Produktionsverwendung von Viva Topics fortfahren möchten.

### <a name="proceed-to-production-use"></a>Fahren Sie mit der Produktionsverwendung fort

Um die Kontinuität des Dienstes sicherzustellen, müssen Sie die erforderliche Anzahl von Lizenzen erwerben und diese Lizenzen Benutzern zuweisen. Testbenutzer, die am Ende des Testzeitraums keine Volllizenz haben, können nicht auf Viva Topics-Erfahrungen zugreifen.

### <a name="dont-proceed-to-production-use"></a>Fahren Sie nicht mit der Produktionsverwendung fort

Wenn Sie nach der Testversion keine Lizenzen erwerben:

- Die Themensuche wird beendet.
- Benutzer sehen keine Themenhighlights oder Karten mehr.
- Das Themencenter wird nicht gelöscht, aber die vorgeschlagenen Themen und die Themenverwaltung sind nicht verfügbar.
- Alle ki-definierten Themen sind verloren.
- Themen, die von einem Themenmitwirkenden bearbeitet wurden, verbleiben in der Bibliothek für Themencenterseiten. Nur der manuell bereitgestellte Inhalt verbleibt auf diesen Seiten, nicht auf ki-vorgeschlagenen Inhalten.

## <a name="see-also"></a>Siehe auch

[Erste Schritte zur Einführung von Microsoft Viva Topics](topics-adoption-getstarted.md)

