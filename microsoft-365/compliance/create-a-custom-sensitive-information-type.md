---
title: Erste Schritte mit benutzerdefinierten Typen vertraulicher Informationen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.date: ''
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Erfahren Sie, wie Sie benutzerdefinierten Typen für vertrauliche Informationen für DLP in der grafischen Benutzeroberfläche im Security & Compliance Center erstellen, ändern, entfernen und testen können.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 049c3c123053b4bd833ea95a2413b81366586870
ms.sourcegitcommit: 89095172c9c4793d56645b4c885ac8e30936bd0a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2021
ms.locfileid: "50766366"
---
# <a name="get-started-with-custom-sensitive-information-types"></a>Erste Schritte mit benutzerdefinierten Typen vertraulicher Informationen

Wenn die vorkonfigurierten Typen vertraulicher Informationen nicht Ihren Anforderungen entsprechen, können Sie Ihre eigenen benutzerdefinierten Typen vertraulicher Informationen erstellen, die Sie vollständig selbst definieren, oder Sie können einen der vorkonfigurierten Typen kopieren und dann ändern.

Die benutzerdefinierten Typen vertraulicher Informationen, die Sie mit dieser Methode erstellen, werden zum Regelpaket namens `Microsoft.SCCManaged.CustomRulePack`hinzugefügt.

Es gibt zwei Möglichkeiten, wie ein neuer vertraulicher Informationstyp erstellen werden kann:

- [vom Grund auf, wobei Sie alle Elemente selbst definieren](#create-a-custom-sensitive-information-type)
- [indem Sie einen bereits vorhandenen Typ vertraulicher Informationen kopieren und dann ändern](#copy-and-modify-a-sensitive-information-type)


## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Sie sollten mit den Typen vertraulicher Informationen und deren Zusammenstellung vertraut sein. Informationen hierzu finden Sie unter [Weitere Informationen zu Typen vertraulicher Informationen](sensitive-information-type-learn-about.md). Es ist wichtig, dass Sie die Rollen des Folgenden verstehen:
    - [Reguläre Ausdrücke](https://www.boost.org/doc/libs/1_68_0/libs/regex/doc/html/) – Microsoft 365 Typen vertraulicher Informationen verwenden das Modul Boost.RegEx 5.1.3
    - Schlüsselwortlisten – Sie können Ihre eigenen erstellen, während Sie Ihren Typ vertraulicher Informationen definieren oder aus vorhandenen Schlüsselwortlisten auswählen
    - [Schlüsselwörterbuch](create-a-keyword-dictionary.md)
    - [Funktionen](what-the-dlp-functions-look-for.md)
    - [Konfidenzniveaus](sensitive-information-type-learn-about.md#more-on-confidence-levels)
 
- Sie müssen über globale Administrator-oder Compliance-Administratorberechtigungen verfügen, um über die Benutzeroberfläche einen benutzerdefinierten vertraulichen Informationstyp erstellen, testen und bereitstellen zu können. Informationen hierzu finden Sie unter[Zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles?view=o365-worldwide) in Office 365.

- Ihre Organisation muss über ein Abonnement verfügen, z. B. Office 365 Enterprise, das Verhinderung von Datenverlust (DLP) beinhaltet. Siehe [Nachrichtenrichtlinie und Compliance ServiceDescription](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/messaging-policy-and-compliance-servicedesc). 


> [!IMPORTANT]
> Der Kundendienst und Support von Microsoft kann beim Erstellen benutzerdefinierter Klassifizierungen oder Muster für reguläre Ausdrücke keine Unterstützung anbieten. Die Supportmitarbeiter können eingeschränkten Support für das Feature bereitstellen, beispielsweise Muster für reguläre Ausdrücke zu Testzwecken oder Hilfestellung bei der Problembehandlung eines bestehenden Musters für reguläre Ausdrücke, das nicht wie erwartet ausgelöst wird, es können jedoch keine Zusicherungen dahingehend gegeben werden, dass benutzerdefinierte Entwicklungen für die Inhaltsübereinstimmung Ihre Anforderungen oder Verpflichtungen erfüllen.

## <a name="create-a-custom-sensitive-information-type"></a>Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen

Verwenden Sie dieses Verfahren, um einen neuen Typ vertraulicher Informationen zu erstellen, den Sie vollständig definieren. 

1. Wechseln Sie im Compliance Center zu **Datenklassifizierung** \> **Typen vertraulicher Informationen** und wählen Sie **Informationstyp erstellen** aus.
2. Füllen Sie die Werte für **Name** und **Beschreibung** aus und wählen Sie **Weiter**.
3. Wählen Sie **Muster erstellen**. Während Sie Ihren neuen Typ vertraulicher Informationen definieren, können Sie mehrere Muster erstellen, jedes mit unterschiedlichen Elementen und Konfidenzniveaus.
4. Wählen Sie ein Standard-Konfidenzniveau für das Muster aus. Die Werte sind **Niedrige Konfidenz**, **Mittlere Konfidenz** und **Hohe Konfidenz**.
5. Wählen Sie und definieren Sie das **Primäre Element**. Das primäre Element kann ein **Regulärer Ausdruck** mit einem optionalen Validator, eine **Schlüsselwortliste**, ein **Schlüsselwörterbuch**, oder eine der vorkonfigurierten **Funktionen** sein. Weitere Informationen zu DLP-Funktionen finden Sie unter [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md).
6. Füllen Sie einen Wert für den **Zeichenabstand** aus.
7. (Optional) Wenn Sie welche haben, fügen Sie unterstützende Elemente hinzu. Unterstützende Elemente können ein regulärer Ausdruck mit einem optionalen Validator, eine Schlüsselwortliste, ein Schlüsselwörterbuch, oder eine der vordefinierten Funktionen sein. 
8.  (Optional) Fügen Sie [**zusätzliche Prüfungen**](#more-information-on-additional-checks) aus der Liste der verfügbaren Prüfungen hinzu.
9. Wählen Sie **Erstellen**.
10. Wählen Sie **Weiter** aus.
11. Wählen Sie das **empfohlene Konfidenzniveau** für diesen Typ vertraulicher Informationen aus.
12. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Absenden** aus.

> [!IMPORTANT]
> Microsoft 365 verwendet den Suchcrawler zum Erkennen und Klassifizieren vertraulicher Informationen in SharePoint Online- und OneDrive for Business-Websites. Um den neuen benutzerdefinierten vertraulichen Informationstyp in vorhandenen Inhalten zu identifizieren, müssen die Inhalte erneut durchforstet werden. Inhalte werden basierend auf einem Zeitplan durchforstet, aber Sie können Inhalte für eine Websitesammlung, Liste oder Bibliothek manuell erneut durchforsten. Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizierens einer Website, Bibliothek oder Liste](https://docs.microsoft.com/sharepoint/crawl-site-content).

13. Auf der Seite **Datenklassifizierung** werden Ihnen alle Typen vertraulicher Informationen aufgelistet angezeigt. Wählen Sie **Aktualisieren** und suchen Sie dann nach dem Typ vertraulicher Informationen, den Sie erstellt haben.

## <a name="test-a-sensitive-information-type"></a>Einen vertraulichen Informationstyp testen

Sie können jeden Typ vertraulicher Informationen in der Liste testen. Wir empfehlen jeden Typ vertraulicher Informationen, den Sie erstellen, zu testen, bevor Sie ihn in einer Richtlinie verwenden.

1. Bereiten Sie zwei Dateien vor, wie z. B. ein Word-Dokument. Eins mit einem Inhalt, der den Elementen entspricht, die Sie in Ihren Typen vertraulicher Informationen angegebenen haben, und eins, das ihnen nicht entspricht.
2. Wechseln Sie im Compliance Center zu **Datenklassifizierung** \> **Typen vertraulicher Informationen** und wählen Sie den Typ vertraulicher Informationen aus der Liste aus, um den Detailbereich zu öffnen, und wählen Sie dann **Test**.
3. Laden Sie eine Datei hoch und wählen Sie **Test**.
4. Überprüfen Sie die Ergebnisse auf der Seite **Stimmt mit den Ergebnissen überein**, und wählen Sie **Fertigstellen** aus.

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>Ändern von benutzerdefinierten Typen vertraulicher Informationen im Compliance Center

1. Wechseln Sie im Compliance Center zu **Datenklassifizierung** \> **Typen vertraulicher Informationen** und wählen Sie den Typ vertraulicher Informationen aus der Liste aus, die Sie ändern möchten, wählen Sie **Bearbeiten**.
2. Sie können andere Muster mit einzigartigen primären und unterstützenden Elementen, Konfidenzniveaus, Zeichenabstand und [**zusätzlichen Prüfungen**](#more-information-on-additional-checks) hinzufügen, oder die bereits vorhandenen bearbeiten/entfernen.

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>Entfernen von benutzerdefinierten Typen für vertrauliche Informationen im Compliance Center 

> [!NOTE]
> Sie können nur benutzerdefinierte Typen für vertrauliche Informationen entfernen; Sie können keine integrierten Typen vertraulicher Informationen entfernen.

> [!IMPORTANT]
> Bevor Sie einen benutzerdefinierten Typ für vertrauliche Informationen entfernen, überprüfen Sie, dass keine DLP-Richtlinien oder Exchange-Nachrichtenflussregeln (auch bezeichnet als Transportregeln) mehr auf den Typ vertraulicher Informationen verweisen.

1. Wechseln Sie im Compliance Center zu **Datenklassifizierung** \> **Typen vertraulicher Informationen** und wählen Sie den Typ vertraulicher Informationen aus der Liste aus, die Sie entfernen möchten.
2. Im Flyout, das geöffnet wird, wählen Sie **Löschen**.

## <a name="copy-and-modify-a-sensitive-information-type"></a>Einen Typ vertraulicher Informationen kopieren und ändern

Verwendung Sie dieses Verfahren, um einen neuen Typ vertraulicher Informationen zu erstellen, der auf einem bereits vorhandenen Typ vertraulicher Informationen basiert. 

1. Wechseln Sie im Compliance Center zu **Datenklassifizierung** \> **Typen vertraulicher Informationen** und wählen Sie den Typ vertraulicher Informationen aus, die Sie kopieren möchten.
2. Wählen Sie im Flyout **Kopieren** aus.
3. Wählen Sie in der Liste der Typen vertraulicher Informationen **Aktualisieren** aus, und suchen Sie nach der Kopie, die Sie gerade erstellt haben. Die Teilzeichenfolge sucht nach Arbeit, daher könnten Sie einfach nach `copy` suchen, und die Suche würde dann alle Typen vertraulicher Informationen mit dem Wort `copy` im Namen zurückgeben. 
4. Füllen Sie die Werte für **Name** und **Beschreibung** aus und wählen Sie **Weiter**.
5. Wählen Sie Ihre Kopie des Typs vertraulicher Informationen aus und wählen Sie **Bearbeiten**. 
6. Geben Sie Ihrem neuen Typ vertraulicher Informationen einen neuen **Namen** und **Beschreibung**.
7. Sie können die vorhandenen Muster bearbeiten und entfernen und neue hinzufügen. Wählen Sie ein Standard-Konfidenzniveau für das neue Muster aus. Die Werte sind **Niedrige Konfidenz**, **Mittlere Konfidenz** und **Hohe Konfidenz**.
8. Wählen Sie und definieren Sie das **Primäre Element**. Das primäre Element kann ein **Regulärer Ausdruck**, eine **Schlüsselwortliste**, ein **Schlüsselwörterbuch**, oder eine der vorkonfigurierten **Funktionen** sein. Lesen Sie [Wonach die DLP-Funktionen suchen](what-the-dlp-functions-look-for.md).
9. Füllen Sie einen Wert für den **Zeichenabstand** aus.
10. (Optional) Wenn Sie **Unterstützende Elemente** oder jede beliebige [**Zusätzliche Prüfungen**](#more-information-on-additional-checks) haben, fügen Sie diese hinzu. Bei Bedarf können Sie Ihre **Unterstützenden Elemente** gruppieren.
11. Wählen Sie **Erstellen**.
12. Wählen Sie **Weiter** aus.
13. Wählen Sie das **empfohlene Konfidenzniveau** für diesen Typ vertraulicher Informationen aus.
14. Überprüfen Sie Ihre Einstellungen, und wählen Sie dann **Absenden** aus.

Sie können auch benutzerdefinierte vertrauliche Informationstypen mithilfe von PowerShell und genauer Datenübereinstimmung erstellen. Weitere Informationen zu diesen Methoden finden Sie unter:
- [Erstellen eines benutzerdefinierten Typs für vertrauliche Informationen in Security & Compliance Center PowerShell](create-a-custom-sensitive-information-type-in-scc-powershell.md)
- [Erstellen eines benutzerdefinierten vertraulichen Informationstyps für DLP mit genauer Datenübereinstimmung (EDM)](create-custom-sensitive-information-types-with-exact-data-match-based-classification.md)

## <a name="more-information-on-additional-checks"></a>Weitere Informationen zu zusätzlichen Prüfungen

Hier sind die Definitionen und einige Beispiele für die verfügbaren zusätzlichen Prüfungen.

**Bestimmte Übereinstimmungen ausschließen**: Mit dieser Prüfung können Sie Schlüsselwörter definieren, die beim Erkennen von Übereinstimmungen für das zu bearbeitende Muster ausgeschlossen werden sollen. Beispielsweise können Sie Testkreditkartennummern wie '4111111111111111' ausschließen, damit sie nicht als gültige Nummer übereinstimmen.

**Beginnt oder beginnt nicht mit Zeichen**: Mit dieser Prüfung können Sie die Zeichen definieren, mit denen die übereinstimmenden Elemente beginnen müssen oder nicht. Wenn Sie beispielsweise möchten, dass das Muster nur Kreditkartennummern erkennt, die mit 41, 42 oder 43 beginnen, wählen Sie **Beginnt mit** und fügen Sie der Liste 41, 42 und 43 hinzu, getrennt durch Kommas. 

**Endet oder endet nicht mit Zeichen**: Mit dieser Prüfung können Sie die Zeichen definieren, mit denen die übereinstimmenden Elemente enden müssen oder nicht. Wenn Ihre Mitarbeiter-ID beispielsweise nicht mit 0 oder 1 enden kann, wählen Sie **Endet nicht mit** und fügen Sie der Liste 0 und 1 hinzu, getrennt durch Kommas.

**Doppelte Zeichen ausschließen**: Mit dieser Prüfung können Sie Übereinstimmungen ignorieren, bei denen alle Ziffern gleich sind. Wenn beispielsweise bei der sechsstelligen Mitarbeiter-ID nicht alle Ziffern identisch sein können, können Sie **Doppelte Zeichen ausschließen** auswählen, um 111111, 222222, 333333, 444444, 555555, 666666, 777777, 888888, 999999 und 000000 aus der Liste der gültigen Übereinstimmungen für die Mitarbeiter-ID auszuschließen.

**Präfixe einschließen oder ausschließen**: Mit dieser Prüfung können Sie die Schlüsselwörter definieren, die unmittelbar vor der übereinstimmenden Entität gefunden werden müssen oder nicht. Abhängig von Ihrer Auswahl werden Entitäten abgeglichen oder nicht abgeglichen, wenn ihnen die hier angegebenen Präfixe vorangestellt sind. Wenn Sie beispielsweise das Präfix **GUID:** **ausschließen**, wird jede Entität, der **GUID:** vorangestellt ist, nicht als Übereinstimmung betrachtet.

**Suffixe einschließen oder ausschließen** Mit dieser Prüfung können Sie die Schlüsselwörter definieren, die unmittelbar nach der übereinstimmenden Entität gefunden werden müssen oder nicht. Abhängig von Ihrer Auswahl werden Entitäten abgeglichen oder nicht abgeglichen, wenn auf sie die Suffixe folgen, die Sie hier einfügen. Wenn Sie beispielsweise das Suffix **:GUID** **ausschließen**, wird der Text, auf den **:GUID** folgt, nicht abgeglichen.


> [!NOTE]
> Microsoft 365 Information Protection unterstützt in der Vorschau Sprachen mit Doppelbyte-Zeichensätzen für:
> - Chinesisch (vereinfacht)
> - Chinesisch (traditionell)
> - Koreanisch
> - Japanisch
>
>Diese Unterstützung ist für vertrauliche Informationstypen verfügbar. Mehr dazu finden Sie in den [Versionshinweisen (Vorschau) zur Unterstützung des Informationsschutzes für Doppelbyte-Zeichensätze](mip-dbcs-relnotes.md).