---
title: Erstellen, Testen und Optimieren einer DLP-Richtlinie
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.NewPolicyFromTemplate
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
ms.custom:
- seo-marvel-mar2020
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: In diesem Artikel erfahren Sie, wie Sie eine DLP-Richtlinie entsprechend den Anforderungen Ihrer Organisation erstellen, testen und optimieren.
ms.openlocfilehash: 3405fc99f4d12715972b1fd18a9c20dd9334382b
ms.sourcegitcommit: a4926e98b6594bbee68bfca90438c9c764499255
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2020
ms.locfileid: "45092005"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Erstellen, Testen und Optimieren einer DLP-Richtlinie

Bei der Verhinderung von Datenverlust (Data Loss Prevention, DLP) handelt es sich um ein Compliance-Feature, mit dem Ihre Organisation verhindert, dass vertrauliche Informationen unbeabsichtigt oder versehentlich an unerwünschte Personen übertragen werden. DLP hat seinen Ursprung in Exchange Server und Exchange Online und kann auch in SharePoint Online und OneDrive for Business angewendet werden.

DLP verwendet ein Inhaltsanalysemodul, um den Inhalt von E-Mail-Nachrichten und Dateien zu überprüfen und nach vertraulichen Informationen wie Kreditkartennummern und personenbezogenen Informationen (Personally Identifiable Information, PII) zu suchen. Vertrauliche Informationen sollten in der Regel nicht per E-Mail gesendet oder in Dokumente einbezogen werden, ohne zusätzliche Schritte auszuführen, wie z. B. die Verschlüsselung der betreffenden E-Mail-Nachrichten oder Dateien. Mithilfe von DLP können Sie vertrauliche Informationen identifizieren und die folgenden Aktionen vorsehen:

- Protokollieren des Ereignisses zu Überwachungszwecken
- Anzeigen einer Warnung für den Endbenutzer, der die E-Mail-Nachricht senden oder die Datei freigeben möchte
- Aktives Blockieren der E-Mail-Nachricht oder der Dateifreigabe

Manchmal wird DLP von Kunden nicht verwendet, weil sie der Ansicht sind, nicht über Dateitypen zu verfügen, die geschützt werden müssen. Es wird davon ausgegangen, dass vertrauliche Daten (z. B. Patientenakten oder Finanzinformationen) nur für Branchen wie das Gesundheitswesen oder für Unternehmen existieren, die Online Shops betreiben. In jedem Unternehmen können aber vertrauliche Informationen in regelmäßigen Abständen verarbeitet werden, ohne dass man sich dessen immer bewusst ist. Eine Tabelle mit den Namen und Geburtstagen von Mitarbeitern ist genauso vertraulich wie eine Tabelle mit Kundennamen und Kreditkartendetails. Informationen dieser Art zirkulieren oft mehr, als Sie vielleicht erwarten, da Mitarbeiter ihre täglichen Aufgaben ausführen, ohne es etwa als problematisch anzusehen, eine CSV-Datei aus einem System zu exportieren und per E-Mail an eine andere Person zu senden. Möglicherweise wird es Sie auch überraschen, wie oft Mitarbeiter E-Mails mit Kreditkarten- oder Bankdaten versenden, ohne die Konsequenzen zu bedenken.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Wie vertrauliche Informationen durch DLP erkannt werden

Vertrauliche Informationen werden durch reguläre Ausdrücke (Regular Expressions, Regex) in Kombination mit anderen Indikatoren wie der Nähe bestimmter Schlüsselwörter zu den übereinstimmenden Mustern identifiziert. Ein Beispiel hierfür sind Kreditkartennummern. Eine Visa-Kreditkartennummer besteht aus 16 Ziffern. Allerdings können diese Ziffern auf unterschiedliche Weise geschrieben werden, z. B. 1111-1111-1111-1111, 1111 1111 1111 1111 oder 1111111111111111.

Nicht jede 16-stellige Zeichenfolge ist eine Kreditkartennummer; es kann sich dabei auch um eine Ticketnummer aus einem Helpdesk-System oder um eine fortlaufende Nummer einer Hardwarekomponente handeln. Um eine Kreditkartennummer von einer harmlosen 16-stelligen Zeichenfolge zu unterscheiden wird eine Berechnung (Prüfsumme) durchgeführt, um zu überprüfen, ob die Zahlen dem bekannten Muster eines der verschiedenen Kreditkartenanbieter entsprechen.

Darüber hinaus wird die Nähe von Stichwörtern wie "Visa" oder "Amex" sowie die Nähe zu Datumswerten, die das Ablaufdatum der Kreditkarte sein könnten, auch als Entscheidung darüber betrachtet, ob es sich bei den Daten um eine Kreditkartennummer handelt oder nicht.

Mit anderen Worten: DLP ist normalerweise intelligent genug, um den Unterschied zwischen diesen beiden Texten in einer E-Mail zu erkennen:

- "Können Sie mir einen neuen Laptop bestellen. Verwenden Sie meine Visa Nummer 1111-1111-1111-1111, Verfall 11/22, und senden Sie mir das geschätzte Zustellungsdatum, wenn Sie es haben. "
- "Meine Laptop-Seriennummer ist 2222-2222-2222-2222 und wurde am 11/2010 erworben. Übrigens: ist mein Reisevisum noch freigegeben? "

Ein guter Hinweis zum Beibehalten von Lesezeichen sind [vertrauliche Informationstypen](sensitive-information-type-entity-definitions.md) , in denen erläutert wird, wie die einzelnen Informationstypen erkannt werden.

## <a name="where-to-start-with-data-loss-prevention"></a>Erste Schritte mit DLP (Verhinderung von Datenverlust)

Wenn die Risiken von Datenverlust nicht ganz offensichtlich sind, ist es schwierig, herauszufinden, wo genau Sie mit der Implementierung von DLP beginnen sollten. Glücklicherweise können DLP-Richtlinien im Testmodus ausgeführt werden, sodass Sie ihre Effektivität und Genauigkeit messen können, bevor Sie Sie aktivieren.

DLP-Richtlinien für Exchange Online können über das Exchange Admin Center verwaltet werden. Sie können DLP-Richtlinien für alle Arbeitsvorgänge aber auch über das Security & Compliance Center konfigurieren, weshalb ich dies für Demonstrationen in diesem Artikel verwenden werde. Im Security & Compliance Center finden Sie die DLP-Richtlinien unter **Verhinderung von Datenverlust** > **Richtlinien**. Klicken Sie auf **Richtlinie erstellen**, um zu beginnen.

Microsoft 365 bietet eine Reihe von [DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md) , die Sie zum Erstellen von DLP-Richtlinien verwenden können. Nehmen wir an, Sie sind Inhaber eines australischen Unternehmens. Sie können die Richtlinienvorlagen so filtern, dass nur diejenigen angezeigt werden, die für Australien relevant sind und in die allgemeinen Kategorien Finanzen, Medizin und Gesundheit sowie Datenschutz fallen.

![Option zur Auswahl von Land oder Region](../media/DLP-create-test-tune-choose-country.png)

Für diese Demonstration wähle ich australische personenbezogene Informationen (PII) aus, welche Informationstypen wie die australische Steuernummer (TFN) sowie die Führerscheinnummer umfassen.

![Option zur Auswahl einer Richtlinienvorlage](../media/DLP-create-test-tune-choose-policy-template.png)

Weisen Sie Ihrer neuen DLP-Richtlinie einen Namen zu. Der Standardname entspricht der DLP-Richtlinienvorlage, Sie sollten jedoch einen aussagekräftigeren Namen auswählen, da mehrere Richtlinien aus derselben Vorlage erstellt werden können.

![Option zum Benennen der Richtlinie](../media/DLP-create-test-tune-name-policy.png)

Wählen Sie die Orte aus, auf die die Richtlinie angewendet werden soll. DLP-Richtlinien können auf Exchange Online, SharePoint Online und OneDrive for Business angewendet werden. Ich werde diese Richtlinie so konfigurieren, dass sie für alle Orte gilt.

![Option zur Auswahl aller Orte](../media/DLP-create-test-tune-choose-locations.png)

Übernehmen Sie beim ersten Schritt im Rahmen der **Richtlinieneinstellungen** einfach die Standardeinstellungen. Sie können zwar zahlreiche Anpassungen an DLP-Richtlinien vornehmen, die Standardwerte sind aber schon ein guter Ausgangspunkt.

![Optionen zum Anpassen des zu schützenden Inhaltstyps](../media/DLP-create-test-tune-default-customization-settings.png)

Nachdem Sie auf **Weiter** geklickt haben, wird eine weitere Seite für **Richtlinieneinstellungen** mit zusätzlichen Anpassungsoptionen angezeigt. Bei einer Richtlinie, die Sie nur testen möchten, können Sie hier einige Anpassungen vornehmen.

- Ich habe die Richtlinientipps vorläufig deaktiviert. Dies ist sinnvoll, wenn Sie nur einen Test durchführen und den Benutzern noch nichts anzeigen möchten. Richtlinientipps zeigen Benutzern Warnungen an, wenn sie dabei sind, gegen eine DLP-Richtlinie zu verstoßen. So wird einem Outlook-Benutzer beispielsweise eine Warnung angezeigt, dass die von ihm angefügte Datei Kreditkartennummern enthält und seine E-Mail deshalb abgelehnt werden wird. Richtlinientipps sollen Richtlinienverletzungen verhindern, bevor diese stattfinden.
- Außerdem habe ich die Anzahl der Instanzen von 10 auf 1 gesenkt, damit diese Richtlinie jede Freigabe von australischen PII-Daten erkennt, und nicht nur die Massenfreigabe der Daten.
- Ich habe zudem einen weiteren Empfänger zur E-Mail-Adresse für Vorfallsberichte hinzugefügt.

![Zusätzliche Richtlinieneinstellungen](../media/DLP-create-test-tune-more-policy-settings.png)

Als Letztes habe ich diese Richtlinie so konfiguriert, dass sie zunächst nur im Testmodus ausgeführt wird. Beachten Sie, dass es hier auch eine Option zum Deaktivieren von Richtlinientipps im Testmodus gibt. Auf diese Weise können die Tipps in der Richtlinie aktiviert werden, und Sie können dann entscheiden, ob Sie sie während des Tests anzeigen oder deaktivieren möchten.

![Option zum Vorabtesten der Richtlinie](../media/DLP-create-test-tune-test-mode.png)

Klicken Sie auf der abschließenden Überprüfungsseite auf **Erstellen**, um die Erstellung der Richtlinie abzuschließen.

## <a name="test-a-dlp-policy"></a>Testen einer DLP-Richtlinie

Ihre neue DLP-Richtlinie wird innerhalb ungefähr einer Stunde wirksam. Sie können warten, bis sie durch normale Benutzeraktivitäten ausgelöst wird, oder die Auslösung selbst herbeiführen. Früher habe ich mit [vertraulichen Informationstypen Entitätsdefinitionen](sensitive-information-type-entity-definitions.md)verknüpft, die Informationen zum Auslösen von DLP-Übereinstimmungen bereitstellen.

Die DLP-Richtlinie, die ich für diesen Artikel erstellt habe, wird beispielsweise australische Steuernummern (TFN) erkennen. Gemäß der Dokumentation basiert der Abgleich auf den folgenden Kriterien:

![Dokumentation zu australischen Steuernummern](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Um die TFN-Erkennung auf eine ziemlich unverblümte Weise zu demonstrieren, wird eine e-Mail mit den Worten "Steuerdatei Nummer" und einer 9-stelligen Zeichenfolge in unmittelbarer Nähe ohne Probleme durchfahren. Der Grund dafür, dass die DLP-Richtlinie nicht ausgelöst wird, besteht darin, dass die 9-stellige Zeichenfolge die Prüfsumme übergeben muss, die angibt, dass es sich um eine gültige TFN und nicht nur um eine harmlose Zahlenfolge handelt.

![Australische Steuernummer, die die Prüfsumme nicht zurückgibt](../media/DLP-create-test-tune-email-test1.png)

Im Vergleich dazu löst eine e-Mail mit den Worten "Steuerdatei Nummer" und einer gültigen TFN, die die Prüfsumme übergibt, die Richtlinie aus. Die TFN, die ich hier verwende, wurde übrigens über eine Website erstellt, die gültige, aber nicht echte TFNs generiert. Solche Websites sind sehr hilfreich, da einer der häufigsten Fehler beim Testen einer DLP-Richtlinie darin besteht, eine gefälschte Zahl zu verwenden, die ungültig ist und deshalb die Prüfsumme nicht zurückgibt (weshalb die Richtlinie auch nicht ausgelöst wird).

![Australische Steuernummer, die die Prüfsumme zurückgibt](../media/DLP-create-test-tune-email-test2.png)

Die E-Mail-Berichte zu Vorfällen enthalten den Typ der vertraulichen Informationen, die erkannt wurden, die Anzahl der gefundenen Instanzen und das Konfidenzniveau der Erkennung.

![Vorfallbericht mit erkannter Steuernummer](../media/DLP-create-test-tune-email-incident-report.png)

Wenn Sie die DLP-Richtlinie im Testmodus beibehalten und die E-Mailberichte analysieren, können Sie ein Gefühl für die Genauigkeit der DLP-Richtlinie entwickeln und sehen, wie effektiv sie ist, wenn sie durchgesetzt wird. Zusätzlich zu den Vorfallberichten können Sie die [DLP-Berichte](view-the-dlp-reports.md) verwenden, um eine aggregierte Darstellung der Richtlinienübereinstimmungen im gesamten Mandanten anzuzeigen.

## <a name="tune-a-dlp-policy"></a>Optimieren einer DLP-Richtlinie

Die Richtlinientreffer könnten Sie dazu veranlassen, einige Anpassungen im Hinblick auf das Verhalten der Richtlinie vorzunehmen. Als einfaches Beispiel: Sie könnten feststellen, dass eine TFN in einer E-Mail kein Problem darstellt (ich denke, dass sie es weiterhin ist, aber sehen wir für dieses Beispiel davon ab), dass jedoch zwei oder mehr Instanzen problematisch sind. Mehrere Instanzen könnten ein riskantes Szenario darstellen, z. B. das eines Mitarbeiters, der einen CSV-Export aus der Mitarbeiter-Datenbank an eine Drittpartei wie etwa einen externen Buchhaltungsdienst per E-Mail sendet. Das ist definitiv etwas, das erkannt und blockiert werden sollte.

Im Security & Compliance Center können Sie das Verhalten einer vorhandenen Richtlinie anpassen.

![Option zum Bearbeiten einer Richtlinie](../media/DLP-create-test-tune-edit-policy.png)
 
Sie können die Standorteinstellungen so anpassen, dass die Richtlinie nur auf bestimmte Workloads oder auf bestimmte Websites und Konten angewendet wird.

![Optionen zur Auswahl bestimmter Orte](../media/DLP-create-test-tune-edit-locations.png)

Sie können auch die Richtlinieneinstellungen anpassen und die Regeln so bearbeiten, dass sie Ihren Anforderungen besser entsprechen.

![Option zum Bearbeiten von Regeln](../media/DLP-create-test-tune-edit-rule.png)

Wenn Sie eine Regel in einer DLP-Richtlinie bearbeiten, können Sie Folgendes ändern:

- Die Bedingungen, einschließlich des Typs und der Anzahl der Instanzen vertraulicher Informationen, durch die die Regel ausgelöst wird.
- Die dann ausgeführten Aktionen wie z. B. das Einschränken des Zugriffs auf die Inhalte.
- Benutzerbenachrichtigungen; dabei handelt es sich um Richtlinientipps, die dem Benutzer in dessen E-Mail-Client oder im Webbrowser angezeigt werden.
- Benutzeraußerkraftsetzungen, mit denen bestimmt wird, ob die Benutzer trotzdem mit dem Versenden der E-Mail oder der Dateifreigabe fortfahren können.
- Vorfallberichte, um Administratoren zu benachrichtigen.

![Optionen zum Bearbeiten von Teilen einer Regel](../media/DLP-create-test-tune-editing-options.png)

Für diese Demonstration habe ich der Richtlinie Benutzerbenachrichtigungen hinzugefügt (seien Sie vorsichtig, wenn Sie dies ohne ausreichende Benutzerschulung tun), und Benutzern gestattet, die Richtlinie mit einer geschäftlichen Begründung außer Kraft zu setzen, oder indem sie sie als falsch positiv kennzeichnen. Sie können den Text der E-Mail und der Richtlinientipps auch anpassen, wenn Sie z. B. weitere Informationen über die Richtlinien Ihrer Organisation hinzufügen oder die Benutzer auffordern möchten, sich bei Fragen an den Support zu wenden.

![Optionen für Benutzerbenachrichtigungen und Benutzeraußerkraftsetzungen](../media/DLP-create-test-tune-user-notifications.png)

Die Richtlinie enthält zwei Regeln für die Behandlung von großen und geringen Mengen, deshalb sollten Sie beide hinsichtlich der gewünschten Aktionen bearbeiten. Dies bietet die Möglichkeit, Fälle abhängig von ihren Merkmalen zu behandeln. Sie könnten z. B. Außerkraftsetzungen für Verstöße im Hinblick auf geringe Mengen zulassen, für Verstöße hinsichtlich großer Mengen hingegen nicht zulassen.

![Eine Regel für große Mengen und eine Regel für geringe Mengen](../media/DLP-create-test-tune-two-rules.png)

Wenn Sie den Zugriff auf Inhalte, die gegen die Richtlinie verstoßen, blockieren oder einschränken möchten, müssen Sie dazu eine Aktion für die Regel konfigurieren.

![Option zum Einschränken des Zugriffs auf Inhalte](../media/DLP-create-test-tune-restrict-access-action.png)

Nachdem ich diese Änderungen an den Richtlinieneinstellungen gespeichert habe, muss ich zur Hauptseite "Einstellungen" für die Richtlinie zurückkehren und die Option aktivieren, dass Richtlinientipps für Benutzer angezeigt werden sollen, während sich die Richtlinie im Testmodus befindet. Dies ist eine effektive Möglichkeit, um Ihre Endbenutzer mit DLP-Richtlinien vertraut zu machen, und eignet sich zur Benutzerschulung, ohne zu viele falsch positive Ergebnisse zu riskieren, die sich negativ auf die Mitarbeiterproduktivität auswirken könnten.

![Option zum Anzeigen von Richtlinientipps im Testmodus](../media/DLP-create-test-tune-show-policy-tips.png)

Serverseitig (oder cloudseitig) wird die Änderung aufgrund verschiedener Verarbeitungsintervalle möglicherweise nicht sofort wirksam. Wenn Sie eine DLP-Richtlinienänderung vornehmen, durch die neue Richtlinien Tipps für einen Benutzer angezeigt werden, werden diese Änderungen möglicherweise nicht sofort im Benutzer-Outlook-Client wirksam werden, da dieser alle 24 Stunden überprüft, ob es neue Richtlinienänderungen gibt. Wenn Sie die Dinge für den Test beschleunigen möchten, können Sie diesen Registry-Fix verwenden, um den [letzten Downloadzeitstempel aus dem PolicyNudges-Schlüssel zu löschen](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook wird die neuesten Richtlinieninformationen herunterladen, wenn Sie das Programm das nächste Mal starten und mit dem Verfassen einer E-Mail-Nachricht beginnen.

Wenn Richtlinientipps aktiviert sind, werden dem Benutzer diese Tipps in Outlook angezeigt, und er kann Ihnen etwaige falsch positive Fälle melden.

![Richtlinientipp mit der Option, ihn als falsch positiv zu melden](../media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Untersuchen von falsch positiven Ergebnissen

DLP-Richtlinienvorlagen sind nicht von vornherein perfekt. Es kann vorkommen, dass einige falsch positive Ergebnisse in Ihrer Umgebung auftreten. Deshalb ist es so wichtig, dass Sie eine DLP-Bereitstellung erleichtern, indem Sie sich die Zeit nehmen, Ihre Richtlinien adäquat zu testen und zu optimieren.

Hier sehen Sie ein Beispiel für ein falsch positives Ergebnis. Diese E-Mail ist harmlos. Der Benutzer teilt jemandem lediglich seine Mobiltelefonnummer mit und schließt die eigene E-Mail-Signatur mit ein. 

![E-Mail mit falsch positiver Information](../media/DLP-create-test-tune-false-positive-email.png)
 
Dem Benutzer wird jedoch ein Richtlinientipp angezeigt mit der Warnung, dass die E-Mail vertrauliche Informationen enthält, nämlich eine australische Führerscheinnummer.

![Option zum Melden von falsch positiven Informationen in einem Richtlinientipp](../media/DLP-create-test-tune-policy-tip-closeup.png)

Der Benutzer kann die falsch positiven Informationen melden, und der Administrator kann überprüfen, warum es dazu gekommen ist. Im E-Mail-Bericht zu dem Vorfall wird die E-Mail als falsch positives Ereignis gekennzeichnet.

![Vorfallsbericht mit falsch positiven Informationen](../media/DLP-create-test-tune-false-positive-incident-report.png)

Dieser Führerscheinfall ist ein gutes Beispiel, das wir uns näher anschauen sollten. Der Grund, warum dieses falsch positive Ergebnis aufgetreten ist, ist, dass der Typ "australischer Führerschein" durch eine beliebige 9-stellige Zeichenfolge (sogar eine, die Teil einer 10-stelligen Zeichenfolge ist) ausgelöst wird, innerhalb von 300 Zeichen Nähe zu den Schlüsselwörtern "Sydney NSW" (Groß-/Kleinschreibung nicht beachtet). Hier wird sie also durch die Telefonnummer und die E-Mail-Signatur ausgelöst, nur weil der Benutzer zufällig in Sydney ist.


Eine besteht darin, den Informationstyp "australischer Führerschein" aus der Richtlinie zu entfernen. Sie ist darin enthalten, weil sie Teil der DLP-Richtlinienvorlage ist, wir sind jedoch nicht gezwungen, sie zu verwenden. Wenn Sie nur an Steuernummern und nicht an Führerscheinnummern interessiert sind, können Sie diesen Informationstyp einfach entfernen. So können Sie ihn beispielsweise aus der Regel zu geringen Mengen in der Richtlinie entfernen, ihn in der Regel zu großen Mengen hingegen belassen, sodass Listen mehrerer Führerscheinnummern weiterhin erkannt werden.

![Option zum Entfernen von vertraulichen Informationstypen aus einer Regel](../media/DLP-create-test-tune-delete-low-volume-rule.png)
 
Eine andere Option besteht darin, einfach die Instanzenanzahl zu erhöhen, sodass eine geringe Anzahl von Führerscheinnummern nur dann erkannt wird, wenn mehrere Instanzen vorkommen.

![Option zum Bearbeiten der Instanzenanzahl](../media/DLP-create-test-tune-edit-instance-count.png)

Zusätzlich zum Ändern der Instanzenanzahl können Sie auch die Übereinstimmungsgenauigkeit (oder Konfidenzniveau) anpassen. Wenn Ihr Typ vertraulicher Informationen mehrere Muster aufweist, können Sie die Übereinstimmungsgenauigkeit in Ihrer Regel so anpassen, dass Letztere nur auf bestimmte Muster ausgerichtet ist. Um falsch positive Ergebnisse zu vermeiden, können Sie beispielsweise die Übereinstimmungsgenauigkeit Ihrer Regel so festlegen, dass sie nur dem Muster mit dem höchsten Konfidenzniveau entspricht. Die Berechnung des Konfidenzniveaus ist eine etwas komplexe Angelegenheit (und es zu erklären würde den Rahmen dieses Beitrags sprengen). Hier finden Sie eine gute Erläuterung, [wie Sie das Konfidenzniveau einsetzen können, um Ihre Regeln zu optimieren](data-loss-prevention-policies.md#match-accuracy).

Wenn Sie sich noch etwas weiter fortgeschrittene wünschen, können Sie alle Arten von vertraulichen Informationen anpassen – beispielsweise können Sie "Sydney NSW" aus der Liste der Schlüsselwörter für die [australische Führerscheinnummer](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)entfernen, um das oben ausgelöste falsch positive Ergebnis zu eliminieren. Informationen dazu, wie das unter Verwendung von XML und PowerShell geht, finden Sie in dem Beitrag [Anpassen eines benutzerdefinierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-on-a-dlp-policy"></a>Aktivieren einer DLP-Richtlinie

Wenn Ihre DLP-Richtlinie vertrauliche Informationstypen genau und effektiv zu Ihrer Zufriedenheit erkennt und Ihre Endbenutzer ausreichend auf den Umgang mit den Richtlinien vorbereitet sind, können Sie die Richtlinie aktivieren.

![Option zum Aktivieren der Richtlinie](../media/DLP-create-test-tune-turn-on-policy.png)
 
Wenn Sie darauf warten, dass die Richtlinie wirksam wird, [stellen Sie eine Verbindung mit dem Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) her, und führen Sie das [Get-DlpCompliancePolicy-Cmdlet](https://docs.microsoft.com/powershell/module/exchange/get-dlpcompliancepolicy?view=exchange-ps) aus, um den DistributionStatus anzuzeigen.

![Ausführen des Cmdlets in PowerShell](../media/DLP-create-test-tune-PowerShell.png)

Nachdem Sie die DLP-Richtlinie aktiviert haben, sollten Sie einige eigene abschließende Tests durchführen, um sicherzustellen, dass die erwarteten Richtlinienaktionen auftreten. Wenn Sie Dinge wie Kreditkartendaten testen möchten, finden Sie auf spezifischen Websites Informationen dazu, wie Sie Beispiel-Kreditkarten- oder andere persönliche Informationen generieren können, die die Prüfsummen zurückgeben und Ihre Richtlinien auslösen werden.

Richtlinien, die Benutzern Außerkraftsetzungen gestatten, bieten diese Option im Rahmen des Richtlinientipps.

![Richtlinientipp, der eine Außerkraftsetzung erlaubt](../media/DLP-create-test-tune-override-option.png)

Richtlinien, die den Zugriff auf Inhalte einschränken, zeigen dem Benutzer die entsprechende Warnung als Teil des Richtlinientipps an und verhindern, dass sie die E-Mail versenden.

![Richtlinientipp mit dem Hinweis auf Inhalte mit eingeschränktem Zugriff](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Zusammenfassung

Richtlinien zur Verhinderung von Datenverlust sind für Organisationen aller Art hilfreich. Das Testen einiger DLP-Richtlinien ist aufgrund der Kontrolle, die Sie über Dinge wie Richtlinientipps, Außerkraftsetzungen durch Endbenutzer und Vorfallberichte, eine Übungsmöglichkeit mit geringem Risiko. Sie können in aller Ruhe einige DLP-Richtlinien testen, um zu sehen, welche Art von Verstößen bereits in Ihrer Organisation vorkommen, und dann Richtlinien mit niedrigen falsch positiven Ergebnisraten erstellen, Ihre Benutzer darin schulen, was erlaubt und was nicht zulässig ist, und schließlich Ihre DLP-Richtlinien in der Organisation bereitstellen.
