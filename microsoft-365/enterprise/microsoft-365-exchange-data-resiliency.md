---
title: Exchange Online-Datenresilienz in Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: In diesem Artikel finden Sie eine Erläuterung der verschiedenen Aspekte der Datenausfall Sicherheit in Exchange Online und Microsoft 365.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: dfc53fd48a6de61cf47a0441cd2f8b0fa35a73f1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695952"
---
# <a name="exchange-online-data-resiliency-in-microsoft-365"></a>Exchange Online-Datenresilienz in Microsoft 365

Es gibt zwei Arten von Beschädigungen, die sich auf eine Exchange-Datenbank auswirken können: physikalische Beschädigungen, die in der Regel durch Hardware (insbesondere Speicherhardware) und logische Beschädigungen verursacht werden, die aufgrund anderer Faktoren auftreten. Im Allgemeinen gibt es zwei Arten von logischen Beschädigungen, die in einer Exchange-Datenbank auftreten können: 
- **Logische Beschädigung der Datenbank** – die Prüfsumme der Datenbankseite entspricht, aber die Daten auf der Seite sind logisch falsch. Dies kann vorkommen, wenn das Datenbankmodul (ESE) versucht, eine Datenbankseite zu schreiben, und obwohl das Betriebssystem eine Erfolgsmeldung zurückgibt, werden die Daten entweder nie auf den Datenträger geschrieben oder an die falsche Stelle geschrieben. Dies wird als *verlorene Leerung* bezeichnet. ESE enthält zahlreiche Features und Schutzvorkehrungen, mit denen die physische Beschädigung einer Datenbank und anderer datenverlustszenarien verhindert werden soll. Um zu verhindern, dass verloren gegangene Daten gelöscht werden, enthält ESE einen Mechanismus zur Erkennung verlorener Leerungen in der Datenbank sowie ein Feature (Einzelseiten Wiederherstellung), um es zu korrigieren. 
- **Logische Beschädigung des Speichers** – Daten werden auf eine Weise hinzugefügt, gelöscht oder manipuliert, die der Benutzer nicht erwartet. Diese Fälle werden im Allgemeinen durch Anwendungen von Drittanbietern verursacht. Es handelt sich im Allgemeinen nur insofern um eine Beschädigung, als der Benutzer sie als Beschädigung betrachtet. Der Exchange-Speicher betrachtet die Transaktion, die zur logischen Beschädigung geführt hat, als eine Folge gültiger MAPI-Operationen. Die [in-situ-Speicherungs](https://docs.microsoft.com/exchange/security-and-compliance/create-or-remove-in-place-holds) Funktionen in Exchange Online bieten Schutz vor logischen Beschädigungen des Speichers (da dadurch verhindert wird, dass Inhalte dauerhaft von einem Benutzer oder einer Anwendung gelöscht werden). 

Exchange Online führt während der Protokoll Überprüfung und der Protokollwiedergabe mehrere Konsistenzprüfungen für replizierte Protokolldateien durch. Durch diese Konsistenzprüfungen wird verhindert, dass physische Beschädigungen vom System repliziert werden. Beispielsweise gibt es bei der Protokoll Überprüfung eine physische Integritätsprüfung, die die Protokolldatei überprüft und überprüft, ob die in der Protokolldatei aufgezeichnete Prüfsumme mit der im Arbeitsspeicher generierten Prüfsumme übereinstimmt. Darüber hinaus wird der Protokolldateiheader überprüft, um sicherzustellen, dass die im Protokollheader aufgezeichnete Protokolldateisignatur mit der der Protokolldatei übereinstimmt. Während der Protokollwiedergabe wird die Protokolldatei weiter überprüft. Die Datenbankkopfzeile enthält beispielsweise auch die Protokollsignatur, die mit der Signatur der Protokolldatei verglichen wird, um sicherzustellen, dass Sie übereinstimmen. 

Der Schutz vor Beschädigung von Postfachdaten in Exchange Online erfolgt mithilfe von Exchange Native Data Protection, einer Ausfall Sicherheitsstrategie, die die Replikation auf Anwendungsebene auf mehreren Servern und mehreren Rechenzentren zusammen mit anderen Features unterstützt, mit denen Daten aufgrund von Beschädigungen oder aus anderen Gründen vor dem Verlust geschützt werden. Diese Features umfassen systemeigene Features, die von Microsoft oder der Exchange Online Anwendung selbst verwaltet werden, beispielsweise:

- [Daten Verfügbarkeitsgruppen](https://docs.microsoft.com/exchange/back-up-email)
- Einzel Bit-Korrektur 
- Online-Daten Bank Scans 
- Erkennung der verlorenen Leerung 
- Wiederherstellung einzelner Seiten 
- Postfachreplikationsdienst 
- Protokolldatei Prüfungen 
- Bereitstellung auf einem widerstandsfähigen Datei System 

Um weitere Informationen zu den oben aufgeführten systemeigenen Features zu erhalten, klicken Sie auf die obigen Hyperlinks, und lesen Sie weiter unten Weitere Informationen und Details zu Elementen ohne Hyperlinks. Zusätzlich zu diesen systemeigenen Features umfasst Exchange Online auch Datenausfall Sicherheitsfeatures, die Kunden verwalten können, beispielsweise: 
- [Wiederherstellung einzelner Elemente (standardmäßig aktiviert)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/recover-deleted-messages) 
- [In-Situ-Speicher und Beweissicherungsverfahren](https://docs.microsoft.com/exchange/security-and-compliance/in-place-and-litigation-holds) 
- [Aufbewahrungszeit für gelöschte Elemente und vorläufig gelöschte Postfächer (beide standardmäßig aktiviert)](https://docs.microsoft.com/exchange/recipients-in-exchange-online/delete-or-restore-mailboxes) 

## <a name="database-availability-groups"></a>Datenbankverfügbarkeitsgruppen 
Jede Postfachdatenbank in Microsoft 365 wird in einer [Database Availability Group (DAG)](https://docs.microsoft.com/exchange/back-up-email) gehostet und in geografisch getrennte Rechenzentren innerhalb derselben Region repliziert. Die häufigste Konfiguration besteht aus vier Datenbankkopien in vier Rechenzentren; Einige Regionen weisen jedoch weniger Rechenzentren auf (Datenbankenwerden in drei Rechenzentren in Indien und zwei Rechenzentren in Australien und Japan repliziert). In allen Fällen verfügt jede Postfachdatenbank über vier Kopien, die über mehrere Rechenzentren verteilt sind, wodurch sichergestellt ist, dass die Postfachdaten vor Software-, Hardware-und sogar Rechenzentrums Fehlern geschützt sind. 

Aus diesen vier Kopien werden drei als hoch verfügbar konfiguriert. Die vierte Kopie ist als [verzögerte Datenbankkopie](https://docs.microsoft.com/Exchange/high-availability/manage-ha/activate-lagged-db-copies)konfiguriert. Die verzögerte Datenbankkopie ist nicht für die Wiederherstellung einzelner Postfächer oder Postfachelemente vorgesehen. Ihr Zweck besteht darin, einen Wiederherstellungsmechanismus für das seltene Ereignis von systemweiten, katastrophalen logischen Beschädigungen bereitzustellen. 

Verzögerte Datenbankkopien in Exchange Online werden mit einem siebentägigen Wiedergabe Verzögerungszeitraum von Protokolldateien konfiguriert. Darüber hinaus ist der Exchange-Wiedergabe Verzögerungs-Manager aktiviert, um die dynamische Protokolldateiwiedergabe für verzögerte Kopien bereitzustellen, damit verzögerte Datenbankkopien die Protokolldatei Vergrößerung selbst reparieren und verwalten können. Obgleich verzögerte Datenbankkopien in Exchange Online verwendet werden, ist es wichtig zu verstehen, dass es sich dabei nicht um eine garantierte Sicherung des Zeitpunktes handelt. Verzögerte Datenbankkopien in Exchange Online weisen einen Verfügbarkeits Schwellenwert auf, der in der Regel um 90% liegt, da der Datenträger mit einer verzögerten Kopie aufgrund eines Datenträgerfehlers verloren geht, die verzögerte Kopie zu einer hoch verfügbaren Kopie wird (aufgrund der automatischen Wiedergabe), sowie die Zeiträume, in denen die verzögerte Datenbankkopie die Protokollwiedergabe Warteschlange neu erstellt. 

## <a name="transport-resilience"></a>Transport Ausfallsicherheit 
Exchange Online umfasst zwei Features für die primäre Transport Flexibilität: Shadow-Redundanz und Sicherheitsnetz. Shadow-Redundanz hält eine redundante Kopie einer Nachricht während der Übertragung. Das Sicherheitsnetz speichert eine redundante Kopie einer Nachricht, nachdem die Nachricht erfolgreich zugestellt wurde. 

Bei der Shadow-Redundanz erstellt jeder Exchange Online Transport Server eine Kopie jeder empfangenen Nachricht, bevor er den erfolgreichen Empfang der Nachricht an den sendenden Server bestätigt. Dadurch sind alle Nachrichten in der Transportpipeline während der Übertragung redundant. Wenn Exchange Online feststellt, dass die ursprüngliche Nachricht während der Übertragung verloren ging, wird eine redundante Kopie der Nachricht erneut zugestellt. 

Safety Net ist eine Transportwarteschlange, die dem Transportdienst auf einem Postfachserver zugeordnet ist. In dieser Warteschlange werden Kopien von Nachrichten gespeichert, die vom Server erfolgreich verarbeitet wurden. Wenn für eine Postfachdatenbank oder einen Serverausfall eine veraltete Kopie der Postfachdatenbank aktiviert werden muss, werden Nachrichten in der Sicherheitsnetz Warteschlange automatisch erneut an die neue aktive Kopie der Postfachdatenbank übermittelt. Das Sicherheitsnetz ist ebenfalls redundant, wodurch der Transport als einzelne Anlaufstellen eliminiert wird. Es verwendet das Konzept eines primär Sicherheitsnetzes und eines Shadow-Sicherheitsnetzes, wobei, wenn das primäre Sicherheitsnetz länger als 12 Stunden nicht verfügbar ist, Resubmit-Anforderungen zu Shadow Resubmit-Anforderungen werden und Nachrichten aus dem Shadow-Sicherheitsnetz erneut übermittelt werden.

Die erneute Übermittlung von Nachrichten aus dem Sicherheitsnetz wird automatisch von der Active Manager-Komponente des Microsoft Exchange Replikationsdiensts initiiert, der DAGs-und Postfachdatenbankkopien verwaltet. Zum erneuten Übermitteln von Nachrichten aus dem Sicherheitsnetz sind keine manuellen Aktionen erforderlich. 

## <a name="single-bit-correction"></a>Einzel Bit-Korrektur 
ESE umfasst einen Mechanismus zum erkennen und lösen von CRC-Fehlern mit einem Bit (aka Single-Bit-Flips), die das Ergebnis von Hardwarefehlern sind (und als solche physische Beschädigungen darstellen). Wenn diese Fehler auftreten, korrigiert ESE diese automatisch und protokolliert ein Ereignis im Ereignisprotokoll. 

## <a name="online-database-scanning"></a>Online-Daten Bank Scans 
Online-Daten Bank Scans (auch bekannt als *Datenbank-checksumming*) ist der Vorgang, bei dem eine ESE eine Datenbank-Konsistenzprüfung verwendet, um jede Seite zu lesen und auf Seiten Beschädigungen zu prüfen. Der primäre Zweck besteht darin, physische Beschädigungen und verlorene Leerungen zu erkennen, die möglicherweise nicht durch transaktionale Vorgänge erkannt werden. Bei der Datenbankprüfung werden auch Absturz Vorgänge nach dem Speichern ausgeführt. Der Speicherplatz kann aufgrund von Abstürzen durchgesickert sein, und die Online-Datenbankprüfung sucht und stellt verlorenen Speicherplatz wieder her. Das System ist mit der Erwartung konzipiert, dass jede Datenbank einmal alle sieben Tage vollständig überprüft wird. 

## <a name="lost-flush-detection"></a>Erkennung der verlorenen Leerung 
Bei einem Datenbankschreibvorgang, bei dem das als abgeschlossen zurückgegebene Datenträgersubsystem/Betriebssystem nicht tatsächlich auf den Datenträger geschrieben oder an einem falschen Speicherort geschrieben wurde, tritt ein verlorener Flush auf. Verloren gegangene Flush-Vorfälle können zu einer Daten Bank logischen Beschädigung führen, sodass ESE einen verlorenen Erkennungsmechanismus enthält, um zu verhindern, dass verloren gegangene Daten gelöscht werden. Wenn Datenbankseiten in passive Kopien geschrieben werden, erfolgt eine Überprüfung der verlorenen Leerungen in der aktiven Kopie. Wenn ein verloren gegangene Flush erkannt wird, kann ESE den Prozess mithilfe eines Seiten Patchings reparieren. 

## <a name="single-page-restore"></a>Wiederherstellung einzelner Seiten 
Die Wiederherstellung einzelner Seiten, aka *Page Patching*, ist ein automatischer Vorgang, bei dem beschädigte Datenbankseiten durch gesunde Kopien aus einem fehlerfreien Replikat ersetzt werden. Der Reparaturprozess für eine beschädigte Seite hängt davon ab, ob die Datenbankkopie aktiv oder passiv ist. Wenn eine aktive Datenbankkopie auf eine beschädigte Seite stößt, kann Sie eine Seite aus einem ihrer Replikate kopieren, vorausgesetzt, die kopierte Seite ist vollständig auf dem neuesten Stand. Dies wird erreicht, indem eine Anforderung für die Seite in den Protokolldatenstrom gestellt wird, der die Basis für die Replikation der Postfachdatenbank ist. Sobald ein Replikat die Seitenanforderung findet, antwortet es, indem es eine Kopie der Seite an die anfordernde Datenbankkopie sendet. Die Wiederherstellung einzelner Seiten stellt auch einen asynchronen Kommunikationsmechanismus bereit, mit dem Active eine Seite von Replikaten anfordern kann, selbst wenn die Replikate derzeit offline sind. 

Bei Beschädigungen in einer passiven Datenbankkopie, einschließlich einer verzögerten Datenbankkopie, da diese Kopien immer hinter ihrer aktiven Kopie stehen, ist es immer sicher, eine Seite aus der aktiven Kopie in eine passive Kopie zu kopieren. Eine passive Datenbankkopie ist von Natur aus hoch verfügbar, daher wird beim Patchen von Seiten die Protokollwiedergabe angehalten, aber der Protokollkopiervorgang wird fortgesetzt. Die passive Datenbankkopie Ruft eine Kopie der beschädigten Seite aus der aktiven Kopie ab und wartet, bis die Protokolldatei, die die maximal erforderliche Protokoll Generierungs Anforderung erfüllt, kopiert und überprüft wird, und dann die beschädigte Seite Patches. Nachdem die Seite gepatcht wurde, wird die Protokollwiedergabe fortgesetzt. Der Prozess ist für die verzögerte Datenbankkopie identisch, mit dem Unterschied, dass die verzögerte Datenbank zunächst alle Protokolldateien wiedergibt, die zum Erreichen eines patchable-Status erforderlich sind. 

## <a name="mailbox-replication-service"></a>Postfachreplikationsdienst 
Das Verschieben von Postfächern ist ein wichtiger Bestandteil der Verwaltung eines umfangreichen e-Mail-Diensts. Es gibt immer aktualisierte Technologien und Hardware-und Versionsupgrades, mit einem robusten, gedrosselten System, mit dem unsere Techniker diese Aufgaben durchführen können, während die Postfachverschiebungen für Benutzer transparent sind (indem Sie sicherstellen, dass Sie während des gesamten Prozesses online bleiben) und sicherstellen, dass der Prozess ordnungsgemäß skaliert wird, wenn die Postfächer immer größer werden. 

Der Exchange-Postfachreplikationsdienst (Mrs) ist für das Verschieben von Postfächern zwischen Datenbanken zuständig. Während des Wechsels führt Mrs eine Konsistenzprüfung für alle Elemente im Postfach aus. Wenn ein Konsistenzproblem gefunden wird, korrigiert Mrs das Problem entweder oder überspringt die beschädigten Elemente, wodurch die Beschädigung aus dem Postfach entfernt wird. 

Da Mrs eine Komponente von Exchange Online ist, können wir Änderungen an Ihrem Code vornehmen, um neue Formen von Beschädigungen zu beheben, die in der Zukunft erkannt werden. Wenn wir beispielsweise ein Konsistenzproblem feststellen, das Mrs nicht beheben kann, können wir die Beschädigung analysieren, den Mrs-Code ändern und die Inkonsistenz korrigieren (wenn wir verstehen, wie dies der Fall ist). 

## <a name="log-file-checks"></a>Protokolldatei Prüfungen 
Alle Transaktionsprotokolldateien, die von einer Exchange-Datenbank generiert werden, werden mehreren Arten von Konsistenzprüfungen unterzogen. Wenn eine Protokolldatei erstellt wird, wird als erstes ein Bitmuster geschrieben, und dann wird eine Reihe von Protokollschreib Vorgängen ausgeführt. Auf diese Weise können Exchange Online eine Reihe von Prüfungen (Flush, CRC und andere Prüfungen) ausführen, um jede Protokolldatei so zu validieren, wie Sie geschrieben wurde, und erneut, während Sie repliziert wird. 

## <a name="deployment-on-resilient-file-system"></a>Bereitstellung auf einem widerstandsfähigen Datei System 
Um zu verhindern, dass Beschädigungen auf Dateisystemebene auftreten, werden Exchange Online auf ReFS-Partitionen bereitgestellt, um verbesserte Wiederherstellungsfunktionen bereitzustellen. ReFS ist ein Dateisystem in Windows Server 2012 und höher, das so konzipiert ist, dass es widerstandsfähiger gegen Datenbeschädigungen ist, wodurch die Verfügbarkeit und Integrität der Daten maximiert wird. Konkret bringt ReFS Verbesserungen bei der Art und Weise, wie Metadaten aktualisiert werden, wodurch Daten besser geschützt werden und Daten Korruptionsfälle reduziert werden. Außerdem werden Prüfsummen verwendet, um die Integrität von Dateidaten und Metadaten zu überprüfen, um sicherzustellen, dass die Datenbeschädigung problemlos gefunden und repariert werden kann. 

Exchange Online nutzt mehrere ReFS-Vorteile: 
- Mehr Ausfallsicherheit in der Datenintegrität bedeutet weniger Daten Beschädigungs Vorfälle. Das Reduzieren der Anzahl von Beschädigungs Vorfällen bedeutet weniger unnötige Daten Bank reseeds. 
- Prüfsumme, die auf Metadaten ausgeführt wird, sodass Erkennungen von Beschädigungs Fällen schneller und deterministischer möglich werden, sodass die Beschädigung von Kundendaten behoben werden kann, bevor graue Fehler auf Datenvolumen auftreten.
- Entwickelt für eine gute Zusammenarbeit mit extrem großen Datasets – Petabyte und größer – ohne Leistungseinbußen
- Unterstützung für andere von Exchange Online verwendete Features, wie die BitLocker-Verschlüsselung. 

Exchange Online profitiert auch von anderen ReFS-Features: 
- **Integrity (Integrity Streams)** -ReFS speichert Daten so, dass Sie vor vielen gängigen Fehlern geschützt werden, die normalerweise zu Datenverlusten führen können. Die Microsoft 365-Suche verwendet Integritätsdaten Ströme zur Unterstützung der frühzeitigen Festplatten-Beschädigungserkennung und der Prüfsummen von Dateiinhalten. Das Feature reduziert außerdem Beschädigungs Ereignisse, die durch "gerissene Schreibvorgänge" verursacht werden (wenn ein Schreibvorgang aufgrund von Stromausfällen nicht abgeschlossen wird usw.). 
- **Verfügbarkeit (Restwert)** -ReFS priorisiert die Verfügbarkeit von Daten. In der Vergangenheit waren Dateisysteme häufig anfällig für Datenbeschädigungen, die erfordern, dass das System zur Reparatur offline geschaltet würde. Obwohl selten, wenn eine Beschädigung auftritt, ReFS implementiert Bergung, ein Feature, das die beschädigten Daten aus dem Namespace auf einem Live-Volume entfernt und sichergestellt, dass gute Daten nicht durch nicht reparierbar beschädigte Daten beeinträchtigt wird. Durch die Anwendung des Bergungs Features und das Isolieren von Datenbeschädigungen auf Exchange Online Daten Bank Volumes können wir nicht betroffene Datenbanken auf einem beschädigten Volume zwischen dem Zeitpunkt der Beschädigung und der Reparaturaktion aufbewahren. Dadurch wird die Verfügbarkeit von Datenbanken erhöht, die normalerweise von solchen Datenträgerbeschädigungen betroffen wären. 