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
description: In diesem Artikel erfahren Sie, wie Sie eine DLP-Richtlinie entsprechend Ihren Organisationsanforderungen erstellen, testen und optimieren.
ms.openlocfilehash: 3b7f74605c8a825bb03244f3a861ad3cca8f550d
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572573"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Erstellen, Testen und Optimieren einer DLP-Richtlinie

Data Loss Prevention (DLP) hilft Ihnen, die unbeabsichtigte oder versehentliche Weitergabe vertraulicher Informationen zu verhindern.

DLP untersucht E-Mail-Nachrichten und Dateien auf vertrauliche Informationen, z. B. eine Kreditkartennummer. Mithilfe von DLP können Sie vertrauliche Informationen identifizieren und die folgenden Aktionen vorsehen:

- Protokollieren des Ereignisses zu Überwachungszwecken
- Anzeigen einer Warnung für den Endbenutzer, der die E-Mail-Nachricht senden oder die Datei freigeben möchte
- Aktives Blockieren der E-Mail-Nachricht oder der Dateifreigabe

## <a name="permissions"></a>Berechtigungen

Mitglieder des Kompatibilitätsteams, die DLP-Richtlinien erstellen, benötigen Berechtigungen zum Zugreifen auf das Compliance Center. Standardmäßig hat Ihr Mandantenadministrator Zugriff auf Compliance-Beauftragte und andere Personen. Führen Sie die folgenden Schritte aus:
  
1. Erstellen Sie eine Gruppe in Microsoft 365, und fügen Sie dieser Compliance Officers hinzu.
    
2. Erstellen Sie eine Rollengruppe auf der Seite **Berechtigungen** des Security &amp; Compliance Center. 

3. Verwenden Sie beim Erstellen der Rollengruppe den Abschnitt **Rollen auswählen,** um der Rollengruppe die folgende Rolle hinzuzufügen: **DLP-Konformitätsmanagement**.
    
4. Verwenden Sie den Abschnitt **Mitglieder auswählen**, um die zuvor erstellte Microsoft 365-Gruppe der Rollengruppe hinzuzufügen.

Verwenden Sie die Rolle **"Nur Ansichtsansicht" für das DLP-Konformitätsmanagement,** um Rollengruppen mit nur Ansichtsberechtigungen für die DLP-Richtlinien und DLP-Berichte zu erstellen.

Weitere Informationen finden Sie unter [Gewähren des Zugriffs auf das Office 365 Compliance Center](../security/office-365-security/grant-access-to-the-security-and-compliance-center.md).
  
Diese Berechtigungen sind erforderlich, um eine DLP-Richtlinie zu erstellen und anzuwenden, um Richtlinien nicht zu erzwingen.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Wie vertrauliche Informationen durch DLP erkannt werden

DLP findet vertrauliche Informationen durch regulären Ausdruck (RegEx)-Musterabgleich, in Kombination mit anderen Indikatoren wie der Nähe bestimmter Schlüsselwörter zu den übereinstimmenden Mustern. Eine VISA-Kreditkartennummer hat beispielsweise 16 Ziffern. Diese Ziffern können jedoch auf unterschiedliche Weise geschrieben werden, z. B. 1111-1111-1111-1111, 1111 1111 1111 1111 1111 oder 11111111111111111111111111.

Jede 16-stellige Zeichenfolge ist nicht unbedingt eine Kreditkartennummer, es kann eine Ticketnummer von einem Helpdesk-System oder eine Seriennummer eines Hardwareteils sein. Um eine Kreditkartennummer von einer harmlosen 16-stelligen Zeichenfolge zu unterscheiden wird eine Berechnung (Prüfsumme) durchgeführt, um zu überprüfen, ob die Zahlen dem bekannten Muster eines der verschiedenen Kreditkartenanbieter entsprechen.

Wenn DLP Schlüsselwörter wie "VISA" oder "AMEX" findet, nahe Datumswerte, die das Ablaufdatum der Kreditkarte sein könnten, verwendet DLP diese Daten auch, um zu entscheiden, ob die Zeichenfolge eine Kreditkartennummer ist oder nicht.

Mit anderen Worten, DLP ist intelligent genug, um den Unterschied zwischen diesen beiden Textzeichenfolgen in einer E-Mail zu erkennen:

- "Können Sie mir einen neuen Laptop bestellen. Verwenden Sie meine VISA-Nummer 1111-1111-1111-1111, Ablauf 11/22, und senden Sie mir das geschätzte Lieferdatum, wenn Sie es haben."
- "Meine Laptop-Seriennummer ist 2222-2222-2222-2222 und es wurde am 11/2010 gekauft. Übrigens, ist mein Reisevisum noch genehmigt?"

Weitere Informationen finden Sie unter [Definitionen von Vertraulichen Informationstypentitäten,](sensitive-information-type-entity-definitions.md) in denen erläutert wird, wie die einzelnen Informationstypen erkannt werden.

## <a name="where-to-start-with-data-loss-prevention"></a>Erste Schritte mit DLP (Verhinderung von Datenverlust)

Wenn die Risiken von Datenverlust nicht ganz offensichtlich sind, ist es schwierig, herauszufinden, wo genau Sie mit der Implementierung von DLP beginnen sollten. Glücklicherweise können DLP-Richtlinien im "Testmodus" ausgeführt werden, sodass Sie deren Effektivität und Genauigkeit messen können, bevor Sie sie aktivieren.

DLP-Richtlinien für Exchange Online können über das Exchange Admin Center verwaltet werden. Sie können DLP-Richtlinien für alle Arbeitsvorgänge aber auch über das Security & Compliance Center konfigurieren, weshalb ich dies für Demonstrationen in diesem Artikel verwenden werde. Im Security & Compliance Center finden Sie die DLP-Richtlinien unter Richtlinie zur Verhinderung von **Datenverlust**  >  . Wählen Sie **Erstellen einer Richtlinie** aus, um sie zu starten.

Microsoft 365 bietet eine Reihe von [DLP-Richtlinienvorlagen,](what-the-dlp-policy-templates-include.md) die Sie zum Erstellen von Richtlinien verwenden können. Nehmen wir an, Sie sind Inhaber eines australischen Unternehmens. Sie können die Vorlagen in Australien filtern und Finanz-, Medizin- und Gesundheits- und Datenschutzoptionen auswählen.

![Option zur Auswahl von Land oder Region](../media/DLP-create-test-tune-choose-country.png)

Für diese Demonstration wähle ich australische personenbezogene Informationen (PII) aus, welche Informationstypen wie die australische Steuernummer (TFN) sowie die Führerscheinnummer umfassen.

![Option zur Auswahl einer Richtlinienvorlage](../media/DLP-create-test-tune-choose-policy-template.png)

Weisen Sie Ihrer neuen DLP-Richtlinie einen Namen zu. Der Standardname entspricht der DLP-Richtlinienvorlage, Sie sollten jedoch einen aussagekräftigeren Namen auswählen, da mehrere Richtlinien aus derselben Vorlage erstellt werden können.

![Option zum Benennen der Richtlinie](../media/DLP-create-test-tune-name-policy.png)

Wählen Sie die Orte aus, auf die die Richtlinie angewendet werden soll. DLP-Richtlinien können auf Exchange Online, SharePoint Online und OneDrive for Business angewendet werden. Ich werde diese Richtlinie so konfigurieren, dass sie für alle Orte gilt.

![Option zur Auswahl aller Orte](../media/DLP-create-test-tune-choose-locations.png)

Akzeptieren Sie beim ersten **Einstellungen** Schritt einfach die Standardeinstellungen für den Moment. Sie können DLP-Richtlinien anpassen, aber die Standardeinstellungen sind ein guter Ausgangspunkt.

![Optionen zum Anpassen des zu schützenden Inhaltstyps](../media/DLP-create-test-tune-default-customization-settings.png)

Nachdem Sie auf Weiter,** geklickt haben, erhalten Sie eine weitere **Seite Einstellungen mit** weiteren Anpassungsoptionen. Bei einer Richtlinie, die Sie nur testen möchten, können Sie hier einige Anpassungen vornehmen.

- Ich habe die Richtlinientipps vorläufig deaktiviert. Dies ist sinnvoll, wenn Sie nur einen Test durchführen und den Benutzern noch nichts anzeigen möchten. Richtlinientipps zeigen Benutzern Warnungen an, wenn sie dabei sind, gegen eine DLP-Richtlinie zu verstoßen. So wird einem Outlook-Benutzer beispielsweise eine Warnung angezeigt, dass die von ihm angefügte Datei Kreditkartennummern enthält und seine E-Mail deshalb abgelehnt werden wird. Das Ziel von Richtlinientipps besteht darin, das nicht konforme Verhalten zu beenden, bevor es auftritt.
- Außerdem habe ich die Anzahl der Instanzen von 10 auf 1 gesenkt, damit diese Richtlinie jede Freigabe von australischen PII-Daten erkennt, und nicht nur die Massenfreigabe der Daten.
- Ich habe zudem einen weiteren Empfänger zur E-Mail-Adresse für Vorfallsberichte hinzugefügt.

![Zusätzliche Richtlinieneinstellungen](../media/DLP-create-test-tune-more-policy-settings.png)

Als Letztes habe ich diese Richtlinie so konfiguriert, dass sie zunächst nur im Testmodus ausgeführt wird. Beachten Sie, dass es hier auch eine Option zum Deaktivieren von Richtlinientipps im Testmodus gibt. Auf diese Weise können die Tipps in der Richtlinie aktiviert werden, und Sie können dann entscheiden, ob Sie sie während des Tests anzeigen oder deaktivieren möchten.

![Option zum Vorabtesten der Richtlinie](../media/DLP-create-test-tune-test-mode.png)

Klicken Sie auf dem Bildschirm für die abschließende Überprüfung auf **Erstellen,** um die Erstellung der Richtlinie abzuschließen.

## <a name="test-a-dlp-policy"></a>Testen einer DLP-Richtlinie

Ihre neue DLP-Richtlinie wird innerhalb ungefähr einer Stunde wirksam. Sie können warten, bis sie durch normale Benutzeraktivitäten ausgelöst wird, oder die Auslösung selbst herbeiführen. Zuvor habe ich mit [den Entitätsdefinitionen des Typs "Sensitive Information Type"](sensitive-information-type-entity-definitions.md)verknüpft, die Ihnen Informationen zum Auslösen von DLP-Übereinstimmungen bereitstellen.

Die DLP-Richtlinie, die ich für diesen Artikel erstellt habe, wird beispielsweise australische Steuernummern (TFN) erkennen. Gemäß der Dokumentation basiert der Abgleich auf den folgenden Kriterien:

![Dokumentation zu australischen Steuernummern](../media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Um die TFN-Erkennung recht unverblümt zu demonstrieren, wird eine E-Mail mit den Worten "Steuerdateinummer" und eine neunstellige Zeichenfolge in unmittelbarer Nähe problemlos durchsegeln. Der Grund, warum die DLP-Richtlinie nicht ausgelöst wird, ist, dass die neunstellige Zeichenfolge die Prüfsumme übergeben muss, die angibt, dass es sich um einen gültigen TFN und nicht nur um eine harmlose Zeichenfolge handelt.

![Australische Steuernummer, die die Prüfsumme nicht zurückgibt](../media/DLP-create-test-tune-email-test1.png)

Im Vergleich dazu löst eine E-Mail mit den Worten "Steuerdateinummer" und einem gültigen TFN, der die Prüfsumme übergibt, die Richtlinie aus. Die TFN, die ich hier verwende, wurde übrigens über eine Website erstellt, die gültige, aber nicht echte TFNs generiert. Solche Websites sind nützlich, da einer der häufigsten Fehler beim Testen einer DLP-Richtlinie die Verwendung einer ungültigen falschen Nummer ist und die Prüfsumme nicht übergibt (und daher die Richtlinie nicht auslöst).

![Australische Steuernummer, die die Prüfsumme zurückgibt](../media/DLP-create-test-tune-email-test2.png)

Die E-Mail-Berichte zu Vorfällen enthalten den Typ der vertraulichen Informationen, die erkannt wurden, die Anzahl der gefundenen Instanzen und das Konfidenzniveau der Erkennung.

![Vorfallbericht mit erkannter Steuernummer](../media/DLP-create-test-tune-email-incident-report.png)

Wenn Sie die DLP-Richtlinie im Testmodus beibehalten und die E-Mailberichte analysieren, können Sie ein Gefühl für die Genauigkeit der DLP-Richtlinie entwickeln und sehen, wie effektiv sie ist, wenn sie durchgesetzt wird. Zusätzlich zu den Vorfallberichten können Sie die [DLP-Berichte](view-the-dlp-reports.md) verwenden, um eine aggregierte Darstellung der Richtlinienübereinstimmungen im gesamten Mandanten anzuzeigen.

## <a name="tune-a-dlp-policy"></a>Optimieren einer DLP-Richtlinie

Wenn Sie Ihre Richtlinientreffer analysieren, sollten Sie einige Anpassungen an der Verhaltensart der Richtlinien vornehmen. Als einfaches Beispiel können Sie feststellen, dass ein TFN in einer E-Mail kein Problem ist (ich denke, es ist immer noch, aber lassen Sie uns mit ihm um der Demonstration willen gehen), aber zwei oder mehr Instanzen sind ein Problem. Mehrere Instanzen könnten ein riskantes Szenario darstellen, z. B. das eines Mitarbeiters, der einen CSV-Export aus der Mitarbeiter-Datenbank an eine Drittpartei wie etwa einen externen Buchhaltungsdienst per E-Mail sendet. Das ist definitiv etwas, das erkannt und blockiert werden sollte.

Im Compliance Center können Sie eine vorhandene Richtlinie bearbeiten, um das Verhalten anzupassen.

![Option zum Bearbeiten einer Richtlinie](../media/DLP-create-test-tune-edit-policy.png)
 
Sie können die Standorteinstellungen so anpassen, dass die Richtlinie nur auf bestimmte Workloads oder auf bestimmte Websites und Konten angewendet wird.

![Optionen zur Auswahl bestimmter Orte](../media/DLP-create-test-tune-edit-locations.png)

Sie können auch die Richtlinieneinstellungen anpassen und die Regeln so bearbeiten, dass sie Ihren Anforderungen besser entsprechen.

![Option zum Bearbeiten von Regeln](../media/DLP-create-test-tune-edit-rule.png)

Wenn Sie eine Regel innerhalb einer DLP-Richtlinie bearbeiten, können Sie:

- Die Bedingungen, einschließlich des Typs und der Anzahl der Instanzen vertraulicher Informationen, durch die die Regel ausgelöst wird.
- Die dann ausgeführten Aktionen wie z. B. das Einschränken des Zugriffs auf die Inhalte.
- Benutzerbenachrichtigungen; dabei handelt es sich um Richtlinientipps, die dem Benutzer in dessen E-Mail-Client oder im Webbrowser angezeigt werden.
- Benutzerüberschreibungen bestimmen, ob Benutzer trotzdem mit ihrer E-Mail- oder Dateifreigabe fortfahren können.
- Vorfallberichte, um Administratoren zu benachrichtigen.

![Optionen zum Bearbeiten von Teilen einer Regel](../media/DLP-create-test-tune-editing-options.png)

Für diese Demonstration habe ich der Richtlinie Benutzerbenachrichtigungen hinzugefügt (seien Sie vorsichtig, wenn Sie dies ohne ausreichende Benutzerschulung tun), und Benutzern gestattet, die Richtlinie mit einer geschäftlichen Begründung außer Kraft zu setzen, oder indem sie sie als falsch positiv kennzeichnen. Sie können auch den E-Mail- und Richtlinientipptext anpassen, wenn Sie zusätzliche Informationen zu den Richtlinien Ihrer Organisation einfügen möchten, oder Benutzer auffordern, sich an den Support zu wenden, wenn sie Fragen haben.

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

Dieser Führerscheinfall ist ein gutes Beispiel, das wir uns näher anschauen sollten. Der Grund, warum dieses falsch positive aufgetreten ist, ist, dass der Typ "Australian Driver es License" durch eine beliebige 9-stellige Zeichenfolge (auch eine, die Teil einer 10-stelligen Zeichenfolge ist) innerhalb von 300 Zeichen in der Nähe der Schlüsselwörter "Sydney nsw" (nicht groß schreibungsabhängig) ausgelöst wird. Hier wird sie also durch die Telefonnummer und die E-Mail-Signatur ausgelöst, nur weil der Benutzer zufällig in Sydney ist.


Eine besteht darin, den Informationstyp "australischer Führerschein" aus der Richtlinie zu entfernen. Sie ist darin enthalten, weil sie Teil der DLP-Richtlinienvorlage ist, wir sind jedoch nicht gezwungen, sie zu verwenden. Wenn Sie nur an Steuernummern und nicht an Führerscheinnummern interessiert sind, können Sie diesen Informationstyp einfach entfernen. So können Sie ihn beispielsweise aus der Regel zu geringen Mengen in der Richtlinie entfernen, ihn in der Regel zu großen Mengen hingegen belassen, sodass Listen mehrerer Führerscheinnummern weiterhin erkannt werden.
 
Eine weitere Möglichkeit besteht darin, die Anzahl der Instanzen zu erhöhen, sodass ein geringes Volumen an Führerscheinen nur erkannt wird, wenn mehrere Instanzen vorhanden sind.

![Option zum Bearbeiten der Instanzenanzahl](../media/DLP-create-test-tune-edit-instance-count.png)

Zusätzlich zum Ändern der Instanzenanzahl können Sie auch die Übereinstimmungsgenauigkeit (oder Konfidenzniveau) anpassen. Wenn Ihr Typ vertraulicher Informationen mehrere Muster aufweist, können Sie die Übereinstimmungsgenauigkeit in Ihrer Regel so anpassen, dass Letztere nur auf bestimmte Muster ausgerichtet ist. Um falsch positive Ergebnisse zu vermeiden, können Sie beispielsweise die Übereinstimmungsgenauigkeit Ihrer Regel so festlegen, dass sie nur dem Muster mit dem höchsten Konfidenzniveau entspricht. Weitere Informationen zum Vertrauensniveau finden Sie unter [Verwenden der Vertrauensstufe zum Optimieren Ihrer Regeln](data-loss-prevention-policies.md#match-accuracy).

Schließlich, wenn Sie noch ein bisschen weiter fortgeschritten sein möchten, können Sie jeden sensiblen Informationstyp anpassen -- zum Beispiel können Sie "Sydney NSW" aus der Liste der Schlüsselwörter für [Australien Sais Führerscheinnummer](sensitive-information-type-entity-definitions.md#australia-drivers-license-number)entfernen, um das falsche Positive zu beseitigen, das oben ausgelöst wurde. Informationen dazu, wie Sie dies mithilfe von XML und PowerShell tun, finden Sie [unter Anpassen eines integrierten vertraulichen Informationstyps](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-on-a-dlp-policy"></a>Aktivieren einer DLP-Richtlinie

Wenn Ihre DLP-Richtlinie vertrauliche Informationstypen genau und effektiv zu Ihrer Zufriedenheit erkennt und Ihre Endbenutzer ausreichend auf den Umgang mit den Richtlinien vorbereitet sind, können Sie die Richtlinie aktivieren.

![Option zum Aktivieren der Richtlinie](../media/DLP-create-test-tune-turn-on-policy.png)
 
Wenn Sie darauf warten, dass die Richtlinie wirksam wird, [stellen Sie eine Verbindung mit dem Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) her, und führen Sie das [Get-DlpCompliancePolicy-Cmdlet](/powershell/module/exchange/get-dlpcompliancepolicy) aus, um den DistributionStatus anzuzeigen.

![Ausführen des Cmdlets in PowerShell](../media/DLP-create-test-tune-PowerShell.png)

Nachdem Sie die DLP-Richtlinie aktiviert haben, sollten Sie einige eigene abschließende Tests durchführen, um sicherzustellen, dass die erwarteten Richtlinienaktionen auftreten. Wenn Sie Dinge wie Kreditkartendaten testen möchten, finden Sie auf spezifischen Websites Informationen dazu, wie Sie Beispiel-Kreditkarten- oder andere persönliche Informationen generieren können, die die Prüfsummen zurückgeben und Ihre Richtlinien auslösen werden.

Richtlinien, die Benutzern Außerkraftsetzungen gestatten, bieten diese Option im Rahmen des Richtlinientipps.

![Richtlinientipp, der eine Außerkraftsetzung erlaubt](../media/DLP-create-test-tune-override-option.png)

Richtlinien, die den Zugriff auf Inhalte einschränken, zeigen dem Benutzer die entsprechende Warnung als Teil des Richtlinientipps an und verhindern, dass sie die E-Mail versenden.

![Richtlinientipp mit dem Hinweis auf Inhalte mit eingeschränktem Zugriff](../media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Zusammenfassung

Richtlinien zur Verhinderung von Datenverlust sind für Organisationen aller Art hilfreich. Das Testen einiger DLP-Richtlinien ist aufgrund der Kontrolle, die Sie über Richtlinientipps, Endbenutzerüberschreibungen und Vorfallberichte haben, eine Übung mit geringem Risiko. Sie können in aller Ruhe einige DLP-Richtlinien testen, um zu sehen, welche Art von Verstößen bereits in Ihrer Organisation vorkommen, und dann Richtlinien mit niedrigen falsch positiven Ergebnisraten erstellen, Ihre Benutzer darin schulen, was erlaubt und was nicht zulässig ist, und schließlich Ihre DLP-Richtlinien in der Organisation bereitstellen.