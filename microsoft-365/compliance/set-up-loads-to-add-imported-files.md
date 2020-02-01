---
title: Einrichten von Lasten zum Hinzufügen importierter Dateien in Office 365 Advanced eDiscovery
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
titleSuffix: Office 365
ms.date: 9/14/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 0e0a9d04-294f-4f54-8bf1-b32d81345126
description: 'Lesen Sie die Schritte zum Hinzufügen importierter Dateien zur letzten definierten Last oder einem Batch von Dateien, bevor Sie eine Relevanz-Schulung in Office 365 Advanced eDiscovery durchführen.  '
ms.openlocfilehash: 6778666e1ef0e5900a2afcc2949bdc9579c21fd1
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41601462"
---
# <a name="set-up-loads-to-add-imported-files-in-office-365-advanced-ediscovery"></a>Einrichten von Lasten zum Hinzufügen importierter Dateien in Office 365 Advanced eDiscovery

> [!NOTE]
> Für Advanced eDiscovery ist ein Office 365 E3-Abonnement mit dem Add-On für erweiterte Compliance oder ein E5-Abonnement für Ihre Organisation erforderlich. Wenn Sie nicht über diesen Plan verfügen und Advanced eDiscovery ausprobieren möchten, können Sie sich [für eine Testversion von Office 365 Enterprise E5 anmelden](https://go.microsoft.com/fwlink/p/?LinkID=698279). 
  
Bei Advanced eDiscovery ist eine Last ein neuer Batch von Dateien, die einem Fall hinzugefügt wurden. Standardmäßig wird eine Last definiert, und alle importierten Dateien werden hinzugefügt. Vor dem Durchführen von Relevanz-Schulungen müssen importierte Dateien zur Last hinzugefügt werden. 
  
Betrachten Sie dazu die folgenden Szenarien:
  
- Neue Dateien sind bekanntermaßen vergleichbar mit den vorherigen Dateien, die in die falldatenbank geladen wurden, oder das vorherige Laden von Dateien war ein Zufallswert aus der Dateisammlung. In dieser Instanz fügen Sie die importierten Dateien der aktuellen Datei laden.
    
- Neue Dateien unterscheiden sich von den vorherigen (beispielsweise aus einer anderen Quelle), oder Sie haben keine Vorkenntnisse darüber, dass Sie mit den vorherigen Lasten vergleichbar oder unterschiedlich sind. In diesem Szenario fügen Sie die importierten Dateien einer neuen Datei laden. Advanced eDiscovery erkennt dies als Szenario für rollende Lasten, Ruft einen Aufholprozess auf, sperrt die Relevanz-Schulung und Batch Berechnungen, bis catch-up abgeschlossen ist und die neue Last integriert und geschult ist. 
    
## <a name="adding-imported-files-to-the-current-load"></a>Hinzufügen importierter Dateien zur aktuellen Last

Alle importierten Dateien müssen zu einer Last hinzugefügt werden, die in Advanced eDiscovery verarbeitet werden soll. Importierte Dateien werden zur zuletzt definierten Last hinzugefügt. Wenn Sie später zusätzliche Dateien importieren, müssen Sie auch zur Last hinzugefügt werden.
  
1. Wählen Sie auf der Registerkarte **Relevanz \> Relevanz-Setup** die Option **Lasten**aus.
    
    ![Registerkarte "Relevanz-Setup lädt"](media/278aac7f-655f-462f-852a-6baa5d818768.png)
  
2. **Dateien einschließen**: Wählen Sie eine Option für Dateien aus, die eingeschlossen werden sollen. Standardmäßig basiert das Hinzufügen von Dateien zur aktuellen Last auf der Auffüllung "alle Dateien".
    
    > [!TIP]
    > Laden Sie alle verfügbaren gepflückten Dateien in Relevanz. Wenn Sie nur einen Teil der verfügbaren Dateien laden möchten, konsultieren Sie zunächst die Unterstützung, da sich das Laden von Teilmengen negativ auf das Schulungsmaterial für Relevanz auswirken kann. 
  
3. Wählen Sie in Loads **Management**eine Last aus.
    
4. Klicken Sie auf **Dateien hinzufügen**. Die Dateien werden der Last hinzugefügt, und eine Bestätigungsmeldung wird angezeigt. 
    
5. Klicken Sie auf **OK**.
    
Die Dateien können jetzt in der erweiterten eDiscovery-Relevanz für das Training der Dateien verarbeitet werden.
  
## <a name="editing-a-load-name-within-a-case"></a>Bearbeiten eines Lade namens in einem Fall

Wenn Sie den ladenamen ändern, wird empfohlen, einen Namen zu verwenden, der für den Fall von Bedeutung ist.
  
1. Wählen Sie auf der Registerkarte **Relevanz \> Relevanz-Setup** die Option **Lasten**aus.
    
2. Wählen Sie in der Liste **Lasten Verwaltung** eine Last aus, und klicken Sie auf das Symbol **Bearbeiten** . Das Fenster "Laden bearbeiten" wird angezeigt. 
    
3. Geben Sie die Änderungen ein, und klicken Sie dann auf **OK**.
    
## <a name="adding-imported-files-to-a-new-load"></a>Hinzufügen importierter Dateien zu einer neuen Last

Nach dem Starten des Relevanz-Trainings oder der Durchführung der Batch Berechnung möchten Sie möglicherweise einen weiteren Satz von Dateien importieren und verarbeiten. 
  
Während des catch-up können Sie das Catch-up-Paket erstellen, markieren und analysieren. Advanced eDiscovery vergleicht die Bewertung relevanter und nicht relevanter Dateien in der neuen Last mit denen in früheren Lasten. Basierend auf den Ergebnissen werden Sie aufgefordert, erforderlichenfalls catch-up-Entscheidungen zu treffen, und Advanced eDiscovery enthält Empfehlungen basierend auf den Informationen zur aufgelaufenen Relevanz. 
  
Rollende Lasten und Catch-up-Funktionen unterscheiden sich wie folgt: 
  
- Wenn Sie eine neue Datei laden nach der Batch Berechnung importieren, bestimmt Advanced eDiscovery, in welchem Ausmaß die Dateien in eine der folgenden Kategorien fallen:
    
  - Ähnlich (homogen): eine neue, benutzerdefinierte Runde von Relevanz-Training ist nicht erforderlich, und das von der vorherigen Last aufgelaufene wissen kann auf die neue Last angewendet werden. 
    
  - Distinct (heterogen): Es ist eine neue, benutzerdefinierte Runde von Relevanz-Schulungen erforderlich, und das von der vorherigen Last gesammelte Wissen kann nicht angewendet werden. 
    
    Diese Begriffe bezeichnen den Grad der Ähnlichkeit von Dateien zwischen Lasten und nicht innerhalb der Lasten. 
    
- Beim Importieren einer neuen Datei laden während des Relevanz-Trainings (vor der Batch Berechnung) können Sie mit catch-up die Relevanz-Schulung für den United-Dateisatz fortsetzen. Advanced eDiscovery schätzt nicht, ob die neue Last der vorherigen Last ähnelt oder sich von ihr unterscheidet. Es sammelt einfach Informationen über die neue Last und ermöglicht eine Relevanz-Schulung für die Fortsetzung der neuen und vorherigen Dateigruppen. 
    
- Wenn mehrere Probleme in Bezug auf die Relevanz-Schulung sowie Probleme nach der Batch Berechnung vorliegen, wird der Aufholprozess für alle Probleme einmal ausgeführt, und die Ergebnisse werden für jedes Problem berechnet und angezeigt.
    
> [!NOTE]
> Die Größe des catch-up-Beispiels kann variieren. Dies hängt von der Größe der neuen Last im Verhältnis zu den vorherigen Lasten sowie von der Anzahl der abgeschlossenen Beispiele ab, bevor die neue Last hinzugefügt wird. Das Catch-up-Beispiel ist normalerweise ein Datensatz von 200 zu 2.000 Dateien aus der neuen Last. 
  
> [!TIP]
> Catch-up stoppt alle anderen Aufgaben und erfordert eine individuelle Dateikennzeichnung und-Prüfung. Daher können Sie den Overhead reduzieren, wenn Sie neue Dateien in großen Batches hinzufügen. 
  
## <a name="adding-a-new-file-load-using-catch-up-and-rolling-loads"></a>Hinzufügen einer neuen Datei mit catch-up und Rolling Loads

1. Wählen Sie auf der Registerkarte **Relevanz \> Relevanz-Setup** die Option **Lasten**aus.
    
2. Klicken **** Sie unter Loads Management **+** auf das Symbol, um eine Last hinzuzufügen. Eine Bestätigungsmeldung wird angezeigt. 
    
3. Klicken Sie auf **Ja**, um den Vorgang fortzusetzen. Das Dialogfeld **neue Last hinzufügen** wird angezeigt. 
    
    > [!NOTE]
    > Sie können nur dann eine neue Last hinzufügen, wenn Aktionen mit der vorherigen Last ausgeführt wurden. 
  
4. Geben Sie im Dialogfeld **neuen Ladevorgang hinzufügen** Informationen in **Laden Name** und **Beschreibung** ein, und klicken Sie dann auf **OK**. Advanced eDiscovery fügt eine neue Last hinzu.
    
5. Klicken Sie auf **Dateien hinzufügen**, um die neue Lade Datei zu importieren. Dieser Last werden alle neuen Dateien hinzugefügt. Nachdem die Dateien von Advanced eDiscovery importiert wurden, erkennt Sie das Szenario "Rolling Loads" und gibt die Auffangfunktion als nächsten Schritt an.
    
6. Klicken Sie unten im Dialogfeld auf **catch-up** , um das Szenario auszuführen. 
    
    Für alle Probleme wird ein einzelner catch-up-Datensatz erstellt, der normalerweise 200 bis 2.000-Dateien aus der neuen Last enthält, um gleichzeitige Dateimarkierungen zu ermöglichen.
    
    Es werden Details darüber angegeben, ob Lasten ähnlich oder unterschiedlich sind, ob Advanced eDiscovery die Lasten automatisch zusammengeführt oder aufgeteilt wird, sowie Informationen zur Verarbeitung im nächsten Schritt.
    
    Sie können dann Dateien markieren und einen Calculate-Vorgang ausführen. Die Kennzeichnung ermöglicht die Relevanz, um festzustellen, ob Lasten ähnlich oder unterschiedlich sind, und Sie können weiterhin an der neuen Gruppe von Dateien arbeiten.
    
7. Nachdem Sie den auffangsatz überprüft haben, können Sie den **Track zur Relevanz \> ** für die Catch-up-Ergebnisse anzeigen. 
    
1. Wenn die neue Datei Last während des Relevanz-Trainings hinzugefügt wurde (was bedeutet, dass das Problem noch nicht durch die Batch Berechnung fortgesetzt wurde), ist die **Weiterbildung** der nächste Schritt, unabhängig von den Aufhol Ergebnissen. 
    
    Die neuen und vorherigen Lasten werden als eine Last verarbeitet, und die Schulung zur Relevanz wird auf dem United-Gerät fortgesetzt. Sie sind nun mit diesem Verfahren fertig und können die Relevanz-Schulung fortsetzen. 
    
2. Wenn die neue Last nach der Batch Berechnung hinzugefügt wurde, fahren Sie mit den folgenden Schritten fort.
    
8. Für neue Lasten, die nach der Batch Berechnung hinzugefügt wurden, bestimmt Advanced eDiscovery, ob die neue Last wie folgt den vorherigen Lasten ähnelt oder unterscheidet:
    
1. Wenn die Lasten ähnlich festgestellt wurden: Es ist keine zusätzliche Relevanz erforderlich. Das Dashboard zeigt den empfohlenen nächsten Schritt darin, * * Batch Berechnung * * erneut auszuführen, um die Relevanz der Ergebnisse für die neue Last zu berechnen. Die Lasten wurden ähnlich festgestellt, sodass die vorherige Klassifizierungsanalyse für die neuen Dateien ausgeführt werden kann. 
    
2. Wenn Lasten gefunden wurden, um eindeutig zu sein: mehr Relevanz Training ist erforderlich, und der nächste Schritt ist Catch-Up Decision. Wählen Sie eine catch-up-Entscheidung wie folgt aus:
    
    Wenn Sie **Loads zusammenführen**auswählen, werden mit Advanced eDiscovery frühere und neue Lasten für den Schulungs Satz zusammengeführt. Obwohl die erste Last die Batch Berechnung durchlaufen hat, ist mehr Schulung erforderlich. Weiter Schulung neuer und früherer Lasten zusammen. Die Batch Berechnung wird dann erneut ausgeführt, und die vorherigen Batch Berechnungsergebnisse sollten ignoriert werden. Wählen Sie diese Option aus, wenn Relevanzwerte für vorhandene Lasten neu berechnet werden können, beispielsweise, wenn die Überprüfung vorhandener Datei Lasten nicht gestartet wurde.
    
    Wenn Sie **geteilte Lasten**auswählen, können Sie die Relevanz-Schulung nur für die neue Last fortsetzen. In diesem Fall bleiben frühere Berechnungsergebnisse für die Batch Verarbeitung unverändert. Wählen Sie diese Option aus, wenn vorhandene Relevanz-Bewertungen für vorhandene Lasten nicht neu berechnet werden können, beispielsweise, wenn die Überprüfung vorhandener Lasten bereits begonnen hat. Relevanz Scores werden ab diesem Punkt separat verwaltet und können nicht zusammengeführt werden.
    
3. Klicken Sie auf **Schulung fortsetzen**.
    
## <a name="see-also"></a>Siehe auch

[Office 365 Advanced eDiscovery](office-365-advanced-ediscovery.md)
  
[Definieren von Problemen und Zuweisen von Benutzern](define-issues-and-assign-users.md)
  
[Definieren hervorgehobener Schlüsselwörter und erweiterte Optionen](define-highlighted-keywords-and-advanced-options.md)

