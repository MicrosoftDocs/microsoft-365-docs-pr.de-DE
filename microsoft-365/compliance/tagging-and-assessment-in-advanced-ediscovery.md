---
title: Tagging und Bewertung in Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
titleSuffix: Office 365
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: b5c82de7-ed2f-4cc6-becd-db403faf4d18
ROBOTS: NOINDEX, NOFOLLOW
description: Überprüfen Sie die Schritte zum Durchführen von Bewertungsschulungen, einschließlich tagging dateien, und überprüfen Sie die Bewertungsergebnisse in Advanced eDiscovery.
ms.openlocfilehash: 15bc8254ea1589d9afa17a74eaf3bfbcdfd4bba0
ms.sourcegitcommit: 5ba0015c1554048f817fdfdc85359eee1368da64
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49769190"
---
# <a name="tagging-and-assessment-in-the-relevance-module-in-advanced-ediscovery"></a>Tagging und Bewertung im Relevanzmodul in Advanced eDiscovery
  
In diesem Abschnitt wird das Verfahren für die Bewertung im Relevanzmodul in Advanced eDiscovery beschrieben.
  
## <a name="performing-assessment-training-and-analysis"></a>Durchführen von Bewertungsschulungen und -analysen

1. Klicken Sie **auf der Registerkarte \> Relevanzspur** auf **Bewertung,** um die Fallbewertung zu starten.

    In diesem Verfahren wird beispielsweise ein Beispielbewertungssatz von 500 Dateien erstellt, und die Registerkarte **Tag** wird angezeigt, die den Tagging-Bereich, den angezeigten Dateiinhalt und andere Taggingoptionen enthält. 

    ![Registerkarte Relevanztag für die Bewertung](../media/c8acf891-b1cd-4344-816c-eabb8cbbe742.png)
  
2. Überprüfen Sie jede Datei im Beispiel, bestimmen Sie die Relevanz der Datei für jedes Fallproblem, und markieren Sie die Datei mithilfe der Schaltflächen Relevanz (R), Nicht relevant (NR) und Überspringen im Bereich **Tagging.** 

    > [!NOTE]
    >  Für die Bewertung sind 500 markierte Dateien erforderlich. Wenn Dateien "übersprungen" werden, erhalten Sie weitere Zu markierende Dateien. 
  
3. Klicken Sie nach dem Taggen aller Dateien im Beispiel auf **Berechnen**.

    Der aktuelle Fehlerrand und der Aktuelle Fehlerreichtheit der Bewertung werden berechnet und auf der Registerkarte **Relevanzspur** mit erweiterten Details pro Problem angezeigt, wie unten gezeigt. Weitere Details zu diesem Dialogfeld finden Sie im Abschnitt [Überprüfung der Bewertungsergebnisse.](#reviewing-assessment-results)

    ![Relevanzspur – Bewertung](../media/da911ba5-8678-40d6-9ad5-fd0b058355c1.png)
  
    > [!TIP]
    > Standardmäßig wird empfohlen, mit dem standardmäßigen Nächsten Schritt fortzufahren, wenn der Bewertungsfortschrittsindikator für das Problem abgeschlossen ist, der angibt, dass das Bewertungsbeispiel überprüft wurde und genügend relevante Dateien markiert wurden. > Wenn Sie andernfalls die Ergebnisse  der Registerkarte Nachverfolgen anzeigen und den Fehlerrand  und den nächsten Schritt steuern möchten, klicken Sie auf Neben nächstem Schritt **ändern,** wählen Sie Bewertung fortsetzen **aus,** und klicken Sie dann auf **OK**.
  
4. Klicken **Sie rechts** neben dem Kontrollkästchen **Bewertung** auf Ändern, um Bewertungsparameter pro Problem anzeigen und angeben zu können. Wie **im folgenden Beispiel gezeigt,** wird ein Bewertungsebenendialogfeld für jedes Problem angezeigt: 

    ![Fallproblem auf Bewertungsebene](../media/b7113fef-d125-4617-ae1b-c9eb0bf79aec.png)
  
    Die folgenden Parameter für das Problem werden im Dialogfeld Bewertungsebene berechnet **und** angezeigt: 

    **Zielfehlermarge für Rückrufschätzungen**: Basierend auf diesem Wert wird die geschätzte Anzahl zusätzlicher Dateien berechnet, die für die Überprüfung erforderlich sind. Die für den Rückruf verwendete Marge ist größer als 75 % und mit einem Konfidenzniveau von 95 %.

    **Zusätzliche Bewertungsdateien erforderlich:** Gibt an, wie viele weitere Dateien erforderlich sind, wenn die Anforderungen der aktuellen Fehlerspanne nicht erfüllt wurden. 

5. So passen Sie den aktuellen Fehlerrand an, und sehen Sie sich die Auswirkungen verschiedener Fehlerränder (pro Problem) an:

6. Wählen Sie **in der Liste** Problem auswählen ein Problem aus. 

7. Geben **Sie unter Zielfehlermarge für Rückrufschätzungen** einen neuen Wert ein.

8. Klicken **Sie auf Werte aktualisieren,** um die Auswirkungen der Anpassungen zu sehen. 

9. Klicken **Sie im** Dialogfeld **Bewertungsebene** auf Erweitert, um die folgenden zusätzlichen Parameter und Details anzuzeigen: 

    ![Erweiterte Ansicht "Assessment Level Case Issue"](../media/577d7e0e-95df-48c2-9dec-bdeab5e801d8.png)
  
    - **Geschätzter Reichhaltiger**: Geschätzter Reichhaltiger Wert gemäß den aktuellen Bewertungsergebnissen

    - **Für den angenommenen Rückruf**: Standardmäßig gilt die Zielfehlermarge für Rückrufe über 75 %. Klicken **Sie auf Bearbeiten,** wenn Sie diesen Parameter ändern und den Fehlerrand für einen anderen Bereich von Rückrufwerten steuern möchten. 

    - **Konfidenzniveau:** Standardmäßig beträgt die empfohlene Fehlermarge für die Konfidenz 95 %. Klicken **Sie auf Bearbeiten,** wenn Sie diesen Parameter ändern möchten.

    - **Erwartete Richness-Fehlermarge**: Angesichts der aktualisierten Werte ist dies der erwartete Fehlerrand des Richness-Werts, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.

    - **Zusätzliche Bewertungsdateien erforderlich:** Angesichts der aktualisierten Werte die Anzahl der zusätzlichen Bewertungsdateien, die überprüft werden müssen, um das Ziel zu erreichen.

    - **Gesamtbewertungsdateien erforderlich:** Angesichts der aktualisierten Werte sind die Gesamtbewertungsdateien für die Überprüfung erforderlich.

    - **Erwartete Anzahl relevanter** Dateien in der Bewertung: Angesichts der aktualisierten Werte die erwartete Anzahl relevanter Dateien in der gesamten Bewertung, nachdem alle zusätzlichen Bewertungsdateien überprüft wurden.

10. Klicken **Sie auf Werte neu berechnen,** wenn Parameter geändert werden. Wenn sie fertig sind, klicken Sie bei einem Problem auf  **OK,** um die Änderungen zu speichern (oder Weiter, wenn mehrere Probleme zu überprüfen oder zu ändern sind und dann **Fertig stellen**). 

    Wenn mehrere Probleme auftreten, nachdem alle Probleme überprüft  oder angepasst wurden, wird ein Bewertungsdialogfeld angezeigt, wie im folgenden Beispiel gezeigt. 

    ![Zusammenfassung der Bewertungsebene](../media/4997b46d-10a5-4abc-b3b2-7b75a370eb9e.png)
  
    Fahren Sie nach erfolgreichem Abschluss der Bewertung mit der nächsten Stufe der Relevanzschulung fort.

## <a name="reviewing-assessment-results"></a>Überprüfen der Bewertungsergebnisse

Nachdem ein Bewertungsbeispiel markiert wurde, werden die Bewertungsergebnisse berechnet und auf der Registerkarte Relevanzspur angezeigt.
  
Die folgenden Ergebnisse werden in der erweiterten Titelanzeige angezeigt:
  
- Bewertung der aktuellen Fehlerspanne für Rückrufschätzungen

- Geschätzter Reichhaltiger

- Zusätzliche Bewertungsdateien erforderlich (zur Überprüfung)

Die aktuelle Fehlerspanne der Bewertung ist die von Advanced eDiscovery empfohlene Fehlerspanne. Die nummer, die für die "Zusätzlichen Bewertungsdateien erforderlich" angezeigt wird, entspricht dieser Empfehlung.
  
Der Bewertungsfortschrittsindikator zeigt den Abschluss der Bewertung an, wenn die aktuelle Fehlerspanne angegeben wird. Wenn die Bewertung im Gange ist, tagg der Benutzer ein weiteres Bewertungsbeispiel.
  
Wenn der Bewertungsfortschrittsindikator die Bewertung als abgeschlossen anschaut, bedeutet dies, dass die Bewertungsbeispielüberprüfung abgeschlossen wurde und ausreichend relevante Dateien markiert wurden. 
  
Die erweiterte Titelanzeige zeigt den empfohlenen nächsten Schritt, die Bewertungsstatistiken und den Zugriff auf detaillierte Ergebnisse.
  
Wenn der Reichhaltige sehr gering ist, ist die Anzahl zusätzlicher Bewertungsdateien sehr hoch, um eine minimale Anzahl relevanter Dateien zu erreichen, um nützliche Statistiken zu erstellen. Advanced eDiscovery empfiehlt dann den Wechsel zu Schulungen. Der Bewertungsfortschrittsindikator wird schattiert, und es sind keine Statistiken verfügbar.
  
Wenn es keine statistische Stabilisierung gibt, gibt es Ergebnisse mit einem niedrigeren Genauigkeits- und Zuverlässigkeitsgrad. Diese Ergebnisse können jedoch verwendet werden, um relevante Dateien zu finden, wenn Sie den Prozentsatz der gefundenen relevanten Dateien nicht kennen müssen. Auf ähnliche Weise kann dieser Status verwendet werden, um Probleme mit geringem Reichhaltigem zu trainieren, wobei Relevanzergebnisse den Zugriff auf Dateien beschleunigen können, die für ein bestimmtes Problem relevant sind.
  
> [!TIP]
> Auf der **Registerkarte \> Relevanzspur,** erweiterte Problemanzeige, sind die folgenden Anzeigeoptionen verfügbar: 
> 
> Der empfohlene nächste Schritt, z. B. **Nächster Schritt: Tagging**  kann (pro Problem) umgangen werden, indem rechts auf die Schaltfläche Ändern geklickt wird und dann im nächsten Schritt ein anderer Schritt ausgewählt **wird.** Wenn der Bewertungsfortschrittsindikator noch nicht abgeschlossen ist, ist die Bewertung die nächste empfohlene Option, um mehr Bewertungsdateien zu kennzeichnen und die Genauigkeit der Statistiken zu erhöhen. 
> 
> Sie können die Fehlermarge ändern und deren Auswirkungen bewerten, indem Sie im Dialogfeld Bewertungsebene auf **Ändern** **klicken,** die Fehlermarge Ziel für Rückrufschätzungen ändern und auf Werte **aktualisieren klicken.** Darüber hinaus können Sie in diesem Dialogfeld erweiterte Optionen anzeigen, indem Sie auf **Erweitert klicken.** 
> 
> Sie können zusätzliche Bewertungsebenenstatistiken und deren Auswirkungen anzeigen, indem Sie auf **Anzeigen klicken.** Im Dialogfeld "Detailergebnisse" sind Statistiken pro Problem verfügbar, wenn mindestens 500 markierte Bewertungsdateien vorhanden sind und mindestens 18 Dateien als relevant für das Problem gekennzeichnet sind. 
