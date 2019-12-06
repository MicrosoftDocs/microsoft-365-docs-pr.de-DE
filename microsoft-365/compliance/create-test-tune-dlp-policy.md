---
title: Erstellen, Testen und Optimieren einer DLP-Richtlinie
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
ms.assetid: 59414438-99f5-488b-975c-5023f2254369
description: 'Die einfachste und gängigste Methode für den Einstieg in DLP-Richtlinien ist die Verwendung der in Office 365 enthaltenen Vorlagen. '
ms.openlocfilehash: f51c0648025b65be1030a84409dd3686fe616b1a
ms.sourcegitcommit: ba223b4fd069fc6fd09c2a2e34c770a18bc7b2a2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39866357"
---
# <a name="create-test-and-tune-a-dlp-policy"></a>Erstellen, Testen und Optimieren einer DLP-Richtlinie

Bei der Verhinderung von Datenverlust handelt es sich um ein Compliance-Feature von Office 365, das Ihre Organisation bei der Vermeidung der beabsichtigten oder versehentlichen Exposition vertraulicher Informationen an unerwünschte Personen unterstützen soll. DLP hat seine Wurzeln in Exchange Server und Exchange Online und gilt auch für SharePoint Online und OneDrive für Unternehmen.

DLP verwendet ein Inhaltsanalyse Modul, um den Inhalt von e-Mail-Nachrichten und Dateien zu untersuchen und auf vertrauliche Informationen wie Kreditkartennummern und personenbezogene Informationen (PII) zu suchen. Vertrauliche Informationen sollten normalerweise nicht per e-Mail gesendet oder in Dokumente eingeschlossen werden, ohne dass zusätzliche Schritte wie das Verschlüsseln der e-Mail-Nachricht oder von Dateien erforderlich sind. Mithilfe von DLP können Sie vertrauliche Informationen erkennen und Maßnahmen ergreifen, beispielsweise:

- Protokollieren des Ereignisses zu Überwachungszwecken
- Zeigt eine Warnung an den Endbenutzer an, der die e-Mail sendet oder die Datei freigegeben hat.
- Aktives Blockieren der e-Mail-oder Dateifreigabe stattfinden

Manchmal schließen Kunden DLP aus, da Sie sich nicht für den Typ von Daten halten, die geschützt werden müssen. Es wird davon ausgegangen, dass vertrauliche Daten wie medizinische Aufzeichnungen oder Finanzinformationen nur für Branchen wie die Gesundheitsversorgung oder für Unternehmen, in denen Online Shops ausgeführt werden, vorhanden sind. Jedes Unternehmen kann jedoch regelmäßig vertrauliche Informationen verarbeiten, selbst wenn Sie es nicht erkennen. Eine Tabelle mit Mitarbeiternamen und Geburtsdaten ist ebenso sensibel wie eine Tabelle mit Kundennamen und Kreditkartendetails. Und diese Art von Informationen neigt dazu, um mehr herum schweben, als Sie vielleicht erwarten, da Mitarbeiter ruhig über Ihre täglichen Aufgaben zu gehen, denken nichts von Exportieren einer CSV-Datei aus einem System und e-Mail an jemanden. Sie werden möglicherweise auch überrascht sein, wie oft Mitarbeiter e-Mails mit Kreditkarten-oder Bankinformationen senden, ohne die Konsequenzen zu berücksichtigen.

## <a name="how-sensitive-information-is-detected-by-dlp"></a>Wie vertrauliche Informationen von DLP erkannt werden

Vertrauliche Informationen werden durch reguläre Ausdrücke (Regular Expressions, Regex) in Kombination mit anderen Indikatoren wie der Nähe bestimmter Schlüsselwörter zu den übereinstimmenden Mustern identifiziert. Ein Beispiel hierfür sind Kreditkartennummern. Eine Kreditkartennummer für Visa verfügt über 16 Ziffern. Diese Ziffern können jedoch auf unterschiedliche Weise geschrieben werden, beispielsweise 1111-1111-1111-1111, 1111 1111 1111 1111 oder 1111111111111111.

Eine 16-stellige Zeichenfolge ist nicht unbedingt eine Kreditkartennummer, es kann sich um eine Ticketnummer von einem helpdesksystem oder eine Seriennummer einer Hardwarekomponente handeln. Um den Unterschied zwischen einer Kreditkartennummer und einer harmlosen 16-stelligen Zeichenfolge zu erkennen, wird eine Berechnung durchgeführt (checksum), um zu bestätigen, dass die Zahlen einem bekannten Muster aus den verschiedenen Kreditkarten Marken entsprechen.

Darüber hinaus wird die Nähe von Stichwörtern wie "Visa" oder "Amex" sowie die Nähe zu Datumswerten, die das Ablaufdatum der Kreditkarte sein könnten, auch als Entscheidung darüber betrachtet, ob es sich bei den Daten um eine Kreditkartennummer handelt oder nicht.

Das heißt, DLP ist normalerweise intelligent genug, um den Unterschied zwischen diesen beiden Texten in einer e-Mail zu erkennen:

- "Können Sie mir einen neuen Laptop bestellen. Verwenden Sie meine Visa Nummer 1111-1111-1111-1111, Verfall 11/22, und senden Sie mir das geschätzte Zustellungsdatum, wenn Sie es haben. "
- "Meine Laptop-Seriennummer ist 2222-2222-2222-2222 und wurde am 11/2010 erworben. Übrigens: ist mein Reisevisum noch freigegeben? "

Ein guter Hinweis zum Beibehalten von Lesezeichen ist dieses [Thema für vertrauliche Informationstypen](what-the-sensitive-information-types-look-for.md) , in dem erläutert wird, wie die einzelnen Informationstypen erkannt werden.

## <a name="where-to-start-with-data-loss-prevention"></a>Wo beginnen mit Verhinderung von Datenverlust

Wenn das Risiko von Datenverlust nicht ganz offensichtlich ist, ist es schwierig herauszufinden, wo genau Sie mit der Implementierung von DLP beginnen sollten. Glücklicherweise können DLP-Richtlinien im Testmodus ausgeführt werden, sodass Sie ihre Effektivität und Genauigkeit messen können, bevor Sie Sie aktivieren.

DLP-Richtlinien für Exchange Online können über das Exchange Admin Center verwaltet werden. Sie können jedoch DLP-Richtlinien für alle Arbeitsauslastungen über das Security #a0 Compliance Center konfigurieren, was ich also für Demonstrationen in diesem Artikel verwende. Im Security #a0 Compliance Center finden Sie die DLP-Richtlinien unter > **Richtlinie**zur **Verhinderung von Datenverlust**. Klicken Sie auf **Create a Policy** to Start.

Office 365 enthält eine Reihe von [DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md) , die Sie zum Erstellen von DLP-Richtlinien verwenden können. Lassen Sie uns sagen, dass Sie ein australisches Unternehmen sind. Sie können die Richtlinienvorlagen filtern, um nur diejenigen anzuzeigen, die für Australien relevant sind, die in die allgemeinen Kategorien Finanzen, Medizin und Gesundheit sowie Datenschutz fallen.

![Option zum Auswählen von Land oder Region](media/DLP-create-test-tune-choose-country.png)

Für diese Demonstration wähle ich personenbezogene Daten (PII), die die Informationen der australischen Steuerdatei Nummer (TFN) und der Führerscheinnummer enthalten.

![Option zum Auswählen einer Richtlinienvorlage](media/DLP-create-test-tune-choose-policy-template.png)

Geben Sie Ihrer neuen DLP-Richtlinie einen Namen. Der Standardname stimmt mit der DLP-Richtlinienvorlage überein, Sie sollten jedoch einen aussagekräftigeren Namen auswählen, da mehrere Richtlinien aus derselben Vorlage erstellt werden können.

![Option zum Benennen Ihrer Richtlinie](media/DLP-create-test-tune-name-policy.png)

Wählen Sie die Speicherorte aus, auf die die Richtlinie angewendet werden soll. DLP-Richtlinien können auf Exchange Online, SharePoint Online und OneDrive für Unternehmen angewendet werden. Ich lasse diese Richtlinie so konfiguriert, dass Sie auf alle Standorte angewendet wird.

![Option zum Auswählen aller Speicherorte](media/DLP-create-test-tune-choose-locations.png)

Akzeptieren Sie beim ersten **Richtlinien Einstellungs** Schritt einfach die Standardeinstellungen für jetzt. Es gibt eine Vielzahl von Anpassungen, die Sie in DLP-Richtlinien vornehmen können, aber die Standardwerte sind ein guter Ausgangspunkt.

![Optionen zum Anpassen des zu schützenden Inhaltstyps](media/DLP-create-test-tune-default-customization-settings.png)

Nach dem Klicken auf **weiter** wird eine weitere Seite mit **Richtlinieneinstellungen** mit weiteren Anpassungsoptionen angezeigt. Für eine Richtlinie, die Sie gerade testen, können Sie mit den folgenden Schritten beginnen, einige Anpassungen vorzunehmen.

- Ich habe jetzt Richtlinien Tipps deaktiviert, was ein vernünftiger Schritt ist, wenn Sie die Dinge erst testen und den Benutzern noch nichts anzeigen möchten. Richtlinien Tipps zeigen Benutzern Warnungen an, dass Sie gegen eine DLP-Richtlinie verstoßen haben. Beispielsweise wird einem Outlook-Benutzer eine Warnung angezeigt, dass die angefügte Datei Kreditkartennummern enthält und dazu führen, dass Ihre e-Mails abgelehnt werden. Das Ziel von Richtlinien Tipps besteht darin, das nicht konforme Verhalten zu beenden, bevor es geschieht.
- Ich habe auch die Anzahl von Instanzen von 10 auf 1 verringert, sodass diese Richtlinie die Freigabe von australischen PII-Daten erkennt, und nicht nur die Massenfreigabe der Daten.
- Ich habe auch einen weiteren Empfänger zur Vorfall Berichts-e-Mail hinzugefügt.

![Zusätzliche Richtlinieneinstellungen](media/DLP-create-test-tune-more-policy-settings.png)

Schließlich habe ich diese Richtlinie so konfiguriert, dass Sie zunächst im Testmodus ausgeführt wird. Beachten Sie, dass hier auch eine Option zum Deaktivieren von Richtlinien Tipps im Testmodus verfügbar ist. Dadurch erhalten Sie die Flexibilität, in der Richtlinie Richtlinien Tipps zu aktivieren, aber dann zu entscheiden, ob Sie Sie während der Tests anzeigen oder unterdrücken.

![Option zum ersten Testen der Richtlinie](media/DLP-create-test-tune-test-mode.png)

Klicken Sie auf dem Bildschirm abschließende Überprüfung auf **Erstellen** , um das Erstellen der Richtlinie abzuschließen.

## <a name="test-a-dlp-policy"></a>Testen einer DLP-Richtlinie

Die neue DLP-Richtlinie wird innerhalb von etwa einer Stunde wirksam. Sie können sitzen und warten, bis Sie von normaler Benutzeraktivität ausgelöst wird, oder Sie können versuchen, Sie selbst auszulösen. Früher habe ich mit diesem [Thema über Typen für vertrauliche Informationen](what-the-sensitive-information-types-look-for.md)verbunden, in dem Sie Informationen zum Auslösen von DLP-Übereinstimmungen erhalten.

Beispielsweise erkennt die für diesen Artikel erstellte DLP-Richtlinie australische Steuerdatei Nummern (TFN). Gemäß der Dokumentation basiert die Übereinstimmung auf den folgenden Kriterien.

![Dokumentation zur Steuerdatei Nummer in Australien](media/DLP-create-test-tune-Australia-Tax-File-Number-doc.png)
 
Um die TFN-Erkennung auf eine ziemlich unverblümte Weise zu demonstrieren, wird eine e-Mail mit den Worten "Steuerdatei Nummer" und einer 9-stelligen Zeichenfolge in unmittelbarer Nähe ohne Probleme durchfahren. Der Grund dafür, dass die DLP-Richtlinie nicht ausgelöst wird, ist, dass die neunstellige Zeichenfolge die Prüfsumme übergeben muss, die angibt, dass es sich um eine gültige TFN und nicht nur um eine harmlose Zeichenfolge von Zahlen handelt.

![Australien-Steuerdatei Nummer, die keine Prüfsumme übergibt](media/DLP-create-test-tune-email-test1.png)

Im Vergleich dazu löst eine e-Mail mit den Worten "Steuerdatei Nummer" und einer gültigen TFN, die die Prüfsumme übergibt, die Richtlinie aus. Für den Eintrag hier wurde das TFN, das ich verwende, von einer Website entnommen, die gültige, aber nicht echte TFNs generiert. Es gibt ähnliche Websites, die [gültige, aber gefälschte Kreditkartennummern](https://www.fakecreditcardgenerator.net/)generieren. Solche Websites sind sehr nützlich, da einer der häufigsten Fehler beim Testen einer DLP-Richtlinie eine gefälschte Nummer verwendet, die nicht gültig ist und die Prüfsumme nicht übergibt (und daher die Richtlinie nicht auslöst).

![Australische Steuerdatei Nummer, die die Prüfsumme übergibt](media/DLP-create-test-tune-email-test2.png)

Die e-Mail-Vorfall Bericht enthält den Typ der vertraulichen Informationen, die erkannt wurden, wie viele Instanzen erkannt wurden, und die Konfidenz Stufe der Erkennung.

![Vorfall Bericht mit ermittelter Steuerdatei Nummer](media/DLP-create-test-tune-email-incident-report.png)

Wenn Sie Ihre DLP-Richtlinie im Testmodus belassen und die Vorfall Berichts-e-Mails analysieren, können Sie damit beginnen, ein Gefühl für die Genauigkeit der DLP-Richtlinie zu erhalten und zu erfahren, wie effektiv Sie bei der Erzwingung sein wird. Zusätzlich zu den Vorfall Berichten können Sie [die DLP-Berichte verwenden](view-the-dlp-reports.md) , um eine aggregierte Ansicht der Richtlinien Übereinstimmungen in Ihrem Mandanten anzuzeigen.

## <a name="tune-a-dlp-policy"></a>Optimieren einer DLP-Richtlinie

Wenn Sie Ihre Richtlinien Treffer analysieren, möchten Sie möglicherweise einige Anpassungen an der Art und Weise vornehmen, wie sich die Richtlinien Verhalten. Als einfaches Beispiel können Sie feststellen, dass ein TFN in e-Mail kein Problem ist (ich denke, dass es immer noch ist, aber lassen Sie uns mit ihm im Interesse der Demonstration gehen), aber zwei oder mehr Instanzen ist ein Problem. Mehrere Instanzen können ein riskantes Szenario sein, beispielsweise ein Mitarbeiter, der einen CSV-Export aus der HR-Datenbank an eine externe Person (beispielsweise einen externen Buchhaltungsdienst) per e-Mail vergibt. Definitiv etwas, das Sie lieber erkennen und blockieren möchten.

Im Security #a0 Compliance Center können Sie eine vorhandene Richtlinie bearbeiten, um das Verhalten anzupassen.

![Option zum Bearbeiten der Richtlinie](media/DLP-create-test-tune-edit-policy.png)
 
Sie können die Standorteinstellungen so anpassen, dass die Richtlinie nur auf bestimmte Arbeitslasten oder auf bestimmte Websites und Konten angewendet wird.

![Optionen zum Auswählen bestimmter Standorte](media/DLP-create-test-tune-edit-locations.png)

Sie können auch die Richtlinieneinstellungen anpassen und die Regeln so bearbeiten, dass Sie Ihren Anforderungen besser entsprechen.

![Option zum Bearbeiten der Regel](media/DLP-create-test-tune-edit-rule.png)

Beim Bearbeiten einer Regel innerhalb einer DLP-Richtlinie können Sie Folgendes ändern:

- Die Bedingungen, einschließlich des Typs und der Anzahl der Instanzen von vertraulichen Daten, die die Regel auslösen werden.
- Die ausgeführten Aktionen, beispielsweise das Einschränken des Zugriffs auf den Inhalt.
- Benutzer Benachrichtigungen, bei denen es sich um Richtlinien Tipps handelt, die dem Benutzer in seinem e-Mail-Client oder Webbrowser angezeigt werden.
- Benutzerüberschreibungen, die festlegen, ob Benutzer trotzdem mit Ihrer e-Mail-oder Dateifreigabe fortfahren können.
- Vorfallberichte zum Benachrichtigen von Administratoren.

![Optionen zum Bearbeiten von Teilen einer Regel](media/DLP-create-test-tune-editing-options.png)

Für diese Demonstration habe ich Benutzer Benachrichtigungen zur Richtlinie hinzugefügt (achten Sie darauf, dies ohne ausreichende Schulung zur Benutzer Aufklärung zu tun), und erlaubten Benutzern, die Richtlinie mit einer geschäftlichen Rechtfertigung außer Kraft zu setzen oder Sie als falsch positives kennzeichnen zu markieren. Beachten Sie, dass Sie auch den Text für e-Mail und richtlinientipp anpassen können, wenn Sie zusätzliche Informationen zu den Richtlinien Ihrer Organisation hinzufügen möchten, oder um Benutzer aufzufordern, sich bei Fragen mit dem Support in Verbindung zu setzen.

![Optionen für Benutzer Benachrichtigungen und Außerkraftsetzungen](media/DLP-create-test-tune-user-notifications.png)

Die Richtlinie enthält zwei Regeln für die Handhabung von hohem und geringem Volumen, daher müssen Sie beide mit den gewünschten Aktionen bearbeiten. Dies ist eine Möglichkeit, die Fälle abhängig von ihren Merkmalen anders zu behandeln. Beispielsweise können Sie Außerkraftsetzungen für Verstöße mit geringem Volumen zulassen, aber keine Außerkraftsetzungen für Verstöße mit hohem Datenvolumen zulassen.

![Eine Regel für hohe Lautstärke und eine Regel für geringes Volumen](media/DLP-create-test-tune-two-rules.png)

Wenn Sie den Zugriff auf Inhalte, die eine Richtlinie verletzen, auch tatsächlich blockieren oder einschränken möchten, müssen Sie dazu eine Aktion für die Regel konfigurieren.

![Option zum Einschränken des Zugriffs auf Inhalte](media/DLP-create-test-tune-restrict-access-action.png)

Nachdem Sie diese Änderungen in den Richtlinieneinstellungen gespeichert haben, muss ich auch zur Seite mit den Haupteinstellungen für die Richtlinie zurückkehren und die Option zum Anzeigen von Richtlinien Tipps für Benutzer aktivieren, während sich die Richtlinie im Testmodus befindet. Dies ist eine effektive Möglichkeit, Ihren Endbenutzern DLP-Richtlinien vorzustellen und Benutzerschulungen durchzuführen, ohne zu viele falsch positive Ergebnisse zu riskieren, die sich auf Ihre Produktivität auswirken.

![Option zum Anzeigen von Richtlinien Tipps im Testmodus](media/DLP-create-test-tune-show-policy-tips.png)

Auf der Serverseite (oder cloudseite, wenn Sie dies bevorzugen) wird die Änderung möglicherweise aufgrund verschiedener Verarbeitungsintervalle nicht sofort wirksam. Wenn Sie eine DLP-Richtlinienänderung vornehmen, mit der neue Richtlinien Tipps für einen Benutzer angezeigt werden, wird der Benutzer möglicherweise nicht sofort in seinem Outlook-Client wirksam, der alle 24 Stunden auf Richtlinienänderungen prüft. Wenn Sie die Dinge für Tests beschleunigen möchten, können Sie diesen Registrierungs Fix verwenden, um [den letzten Downloadzeitstempel aus dem PolicyNudges-Schlüssel zu löschen](https://support.microsoft.com/en-au/help/2823261/changes-to-a-data-loss-prevention-policy-don-t-take-effect-in-outlook?__hstc=18650278.46377037dc0a82baa8a30f0ef07a7b2f.1538687978676.1538693509953.1540315763430.3&__hssc=18650278.1.1540315763430&__hsfp=3446956451). Outlook lädt die neuesten Richtlinieninformationen herunter, wenn Sie das nächste Mal neu starten, und beginnt mit dem Verfassen einer e-Mail-Nachricht.

Wenn Sie Richtlinien Tipps aktiviert haben, wird der Benutzer beginnen, die Tipps in Outlook anzuzeigen, und er kann falsch positive Ergebnisse an Sie melden, wenn diese auftreten.

![Richtlinientipp mit Option zum Melden falsch positiver Ergebnisse](media/DLP-create-test-tune-policy-tip-in-outlook.png)

## <a name="investigate-false-positives"></a>Untersuchen falsch positiver Ergebnisse

DLP-Richtlinienvorlagen sind gerade nicht perfekt. Es ist wahrscheinlich, dass in Ihrer Umgebung falsch positive Ergebnisse auftreten, weshalb es so wichtig ist, den Weg in eine DLP-Bereitstellung zu erleichtern, wobei Sie sich die Zeit nehmen, Ihre Richtlinien angemessen zu testen und zu optimieren.

Hier ist ein Beispiel für eine falsch positive. Diese e-Mail ist ganz harmlos. Der Benutzer stellt seine Mobiltelefonnummer einer Person und einschließlich der e-Mail-Signatur zur Verfügung.

![E-Mail mit falsch positiven Informationen](media/DLP-create-test-tune-false-positive-email.png)
 
Dem Benutzer wird jedoch ein richtlinientipp angezeigt, in dem er warnt, dass die e-Mail vertrauliche Informationen enthält, insbesondere eine australische Führerscheinnummer.

![Option zum Melden von falsch positivem in richtlinientipp](media/DLP-create-test-tune-policy-tip-closeup.png)

Der Benutzer kann das falsch positive melden, und der Administrator kann untersuchen, warum es eingetreten ist. In der Vorfall Berichts-e-Mail ist die e-Mail-Nachricht als falsch positiv gekennzeichnet.

![Vorfall Bericht mit falschem positiv](media/DLP-create-test-tune-false-positive-incident-report.png)

Dieser Führerschein Fall ist ein gutes Beispiel für die Untergrabung. Der Grund, warum dieses falsch positive Ergebnis aufgetreten ist, ist, dass der Typ "australischer Führerschein" durch eine beliebige 9-stellige Zeichenfolge (sogar eine, die Teil einer 10-stelligen Zeichenfolge ist) ausgelöst wird, innerhalb von 300 Zeichen Nähe zu den Schlüsselwörtern "Sydney NSW" (Groß-/Kleinschreibung nicht beachtet). Es wird also durch die Telefonnummer und die e-Mail-Signatur ausgelöst, nur weil der Benutzer zufällig in Sydney ist.

Interessanterweise wird die DLP-Richtlinie nicht ausgelöst, wenn "Sydney, NSW" ein Komma hat. Ich habe keine Ahnung, warum ein Komma hier einen Unterschied macht, und auch nicht, warum andere Städte und Bundesstaaten in Australien nicht in die Schlüsselwörter für den Lizenz Informationstyp des australischen Führers eingebunden sind, aber das geht. Was können wir dagegen tun? Es gibt eine Reihe von Optionen.

Eine Option besteht darin, den Typ des Typs "Lizenzinformationen" des australischen Treibers aus der Richtlinie zu entfernen. Es ist da drin, weil es Teil der DLP-Richtlinienvorlage ist, aber wir sind nicht gezwungen, es zu verwenden. Wenn Sie nur an Steuerdatei Nummern und nicht an die Treiber Lizenzen interessiert sind, können Sie Sie einfach entfernen. Beispielsweise können Sie ihn aus der Regel mit niedrigem Volumen in der Richtlinie entfernen, aber in der Regel für hohe Lautstärke beibehalten, sodass Listen mit mehreren Treiber Lizenzen weiterhin erkannt werden.

![Option zum Löschen des Typs vertraulicher Informationen aus Regel](media/DLP-create-test-tune-delete-low-volume-rule.png)
 
Eine weitere Möglichkeit besteht darin, die Anzahl der Instanzen einfach zu erweitern, sodass ein niedriges Volumen an Treiber Lizenzen nur dann erkannt wird, wenn mehrere Instanzen vorhanden sind.

![Option zum Bearbeiten der instanzenanzahl](media/DLP-create-test-tune-edit-instance-count.png)

Sie können nicht nur die Anzahl der Instanzen ändern, sondern auch die Übereinstimmungs Genauigkeit (oder Konfidenz Stufe) anpassen. Wenn Ihr Typ für vertrauliche Informationen mehrere Muster aufweist, können Sie die Übereinstimmungs Genauigkeit in der Regel anpassen, sodass Ihre Regel nur bestimmte Muster erfüllt. Um beispielsweise falsch positive Ergebnisse zu verringern, können Sie die Übereinstimmungs Genauigkeit Ihrer Regel so festlegen, dass Sie nur dem Muster mit der höchsten Konfidenz Stufe entspricht. Das Verständnis der Berechnung der Zuverlässigkeitsstufe ist etwas knifflig (und über den Rahmen dieses Beitrags hinaus), aber hier finden Sie eine gute Erläuterung, wie Sie die [Zuverlässigkeitsstufe zum Optimieren Ihrer Regeln verwenden](data-loss-prevention-policies.md#match-accuracy).

Wenn Sie sich noch etwas weiter fortgeschrittene wünschen, können Sie alle Arten von vertraulichen Informationen anpassen – beispielsweise können Sie "Sydney NSW" aus der Liste der Schlüsselwörter für den [australischen Führerschein](what-the-sensitive-information-types-look-for.md#australia-drivers-license-number)entfernen, um das oben ausgelöste falsch positive Ergebnis zu eliminieren. Informationen zur Vorgehensweise mithilfe von XML und PowerShell finden Sie in diesem Thema unter [Anpassen eines integrierten Typs vertraulicher Informationen](customize-a-built-in-sensitive-information-type.md).

## <a name="turn-off-a-dlp-policy"></a>Deaktivieren einer DLP-Richtlinie

Wenn Sie sicher sind, dass ihre DLP-Richtlinie vertrauliche Informationstypen genau und effektiv erkennt und die Endbenutzer bereit sind, mit den Richtlinien umzugehen, die in Kraft sind, können Sie die Richtlinie aktivieren.

![Option zum Aktivieren der Richtlinie](media/DLP-create-test-tune-turn-on-policy.png)
 
Wenn Sie darauf warten, dass die Richtlinie wirksam wird, stellen Sie [eine Verbindung mit Security #a0 Compliance Center PowerShell her](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps) , und führen Sie das [Cmdlet Get-DlpCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/get-dlpcompliancepolicy?view=exchange-ps) aus, um die Eigenschaften distributionstatus anzuzeigen.

![Ausführen eines Cmdlets in PowerShell](media/DLP-create-test-tune-PowerShell.png)

Nachdem Sie die DLP-Richtlinie eingeschaltet haben, sollten Sie einige abschließende Tests durchführen, um sicherzustellen, dass die erwarteten Richtlinienaktionen ausgeführt werden. Wenn Sie versuchen, Dinge wie Kreditkartendaten zu testen, gibt es Websites online mit Informationen zum Generieren von Beispiel-Kreditkarten oder anderen persönlichen Informationen, die Prüfsummen übergeben und ihre Richtlinien auslösen.

Richtlinien, die Benutzerüberschreibungen zulassen, stellen diese Option dem Benutzer als Teil des Richtlinien Tipps bereit.

![Richtlinientipp, der eine Benutzer Überschreibung zulässt](media/DLP-create-test-tune-override-option.png)

Richtlinien, die Inhalte einschränken, zeigen dem Benutzer die Warnung als Teil des Richtlinien Tipps an und verhindern, dass die e-Mails gesendet werden.

![Richtlinientipp für eingeschränkten Inhalt](media/DLP-create-test-tune-restrict-warning.png)

## <a name="summary"></a>Zusammenfassung

Richtlinien zur Verhinderung von Datenverlust sind für Organisationen aller Typen hilfreich. Das Testen einiger DLP-Richtlinien ist eine Übung mit niedrigem Risiko aufgrund des Steuerelements, das Sie über Dinge wie Richtlinien Tipps, Überschreibungen von Endbenutzern und Vorfall Berichten haben. Sie können einige DLP-Richtlinien ruhig testen, um zu sehen, welche Art von Verletzungen bereits in Ihrer Organisation vorliegt, und dann Richtlinien mit niedrigen falsch positiven Raten durchführen, Ihre Benutzer darüber informieren, was zulässig ist und nicht zulässig ist, und dann ihre DLP-Richtlinien auf die Organisation.
