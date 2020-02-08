---
title: Suche, Schutz und Berichterstellung für die DSGVO in der Office 365-Entwicklungs-/Testumgebung
description: Veranschaulichung von DSGVO-Funktionen in Office 365
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
audience: ITPro
ms.topic: article
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
ms.assetid: c2112ce8-1c4b-424f-b200-59e161db2d21
titleSuffix: Microsoft GDPR
ms.openlocfilehash: f7bf98da5d358f9b76f38372353a1c2a9d0d45d3
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41594089"
---
# <a name="gdpr-discovery-protection-and-reporting-in-the-office-365-devtest-environment"></a>Suche, Schutz und Berichterstellung für die DSGVO in der Office 365-Entwicklungs-/Testumgebung

 **Zusammenfassung:** Veranschaulichung von DSGVO-Funktionen in Office 365 
  
Dieser Artikel beschreibt die Konfiguration und Veranschaulichung von Suche, Schutz und Berichterstellung für personenbezogene Informationen (PII) für die Datenschutz-Grundverordnung (DSGVO) in einer Office 365-Entwicklungs-/Testumgebung.
  
## <a name="phase-1-create-and-configure-your-trial-office-365-subscription"></a>Phase 1: Erstellen und Konfigurieren Ihres Office 365-Testabonnements

Führen Sie zunächst die Schritte in [Phase 2 des Artikels „Office 365-Entwicklungs-/Testumgebung“](https://docs.microsoft.com/Office365/Enterprise/office-365-dev-test-environment#phase-2-create-an-office-365-trial-subscription) aus.

Konfigurieren Sie dann mit den folgenden Schritte den eDiscovery-Manager:

1. Melden Sie sich mit Ihrem globalen Administratorkonto bei Ihrem Office 365-Testmandanten an.
2. Klicken Sie auf der Office 365-Startseite auf **Sicherheit und Compliance**.
3. Klicken Sie auf der neuen Registerkarte „Sicherheit und Compliance“ auf **Berechtigungen** > **eDiscovery-Manager**.
4. Klicken Sie für eDiscovery-Manager auf **Bearbeiten**, und klicken Sie dann auf **eDiscovery-Manager auswählen**.
5. Klicken Sie auf **+ Hinzufügen**, suchen Sie nach dem Namen Ihres globalen Administratorkontos, und fügen Sie dieses als eDiscovery-Manager hinzu.
6. Klicken Sie auf **Fertig** > **Speichern** > **Schließen**.
  
## <a name="phase-2-add-personally-identifiable-information-to-your-tenant"></a>Phase 2: Hinzufügen von personenbezogenen Informationen zu Ihrem Mandanten

In dieser Phase erstellen Sie ein Dokument mit PII für eine Reihe von Beispielen für internationale Kontonummern (International Banking Account Numbers, IBANs) und speichern es auf einer SharePoint Online-Website in Ihrer Office 365-Entwicklungs-/Testumgebung.

1. Öffnen Sie Microsoft Word auf dem lokalen Computer.
2. Fügen Sie die folgende Tabelle in die Word-Datei ein, und speichern Sie sie als „IBANs.docx“ auf dem lokalen Computer.
    
    Nummer  |Land  |Code |IBAN  |
    |---------|---------|---------|---------|
    |1     |  Österreich SEPA      | AT            |AT611904300234573201       |
    |2     |  Bulgarien SEPA       |BG    |BG80BNBG96611020345678      |
    |3     |  Dänemark SEPA      |   DK      |DK5000400440116243      |
    |4     |  Finnland SEPA      |   FI      |FI2112345600000785         |
    |5     |  Frankreich SEPA       |   FR      |FR1420041010050500013M02606         |
    |6     |  Deutschland SEPA      |   DE      |DE89370400440532013000         |
    |7     |  Griechenland SEPA       |   GR      |GR1601101250000000012300695         |
    |8     |  Italien SEPA       |    IT     |GR1601101250000000012300695         |
    |9     |  Niederlande SEPA      |   NL      |    NL91ABNA0417164300     |
    |10     | Polen SEPA       |  PL       | PL27114020040000300201355387        |

Hinweis: Dieser Beispieldatensatz wird von öffentlich verfügbaren Informationen abgeleitet und soll nur für Testzwecke verwendet werden.

3. Geben Sie auf einer neuen Browserregisterkarte die folgende Adresse ein: **https://**\<NameIhresMandanten\>**.sharepoint.com**
4. Klicken Sie auf **Dokumente**, um die Dokumentbibliothek für diese Website zu öffnen. Wenn Sie zu einer Tour über neue Listen aufgefordert werden, klicken Sie auf **Weiter**, bis sie abgeschlossen ist.
5.  Klicken Sie auf **Hochladen** > **Dateien**, und wählen Sie die Datei „IBANs.docx“ aus, die Sie in Schritt 2 erstellt haben.

  
## <a name="phase-3-demonstrate-data-discovery"></a>Phase 3: Veranschaulichen der Datenermittlung

In dieser Phase veranschaulichen Sie die Suche nach dem in Schritt 2 erstellten und gespeicherten Dokument basierend auf dessen Inhalt (IBANs).

1. Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ auf **Start**, und klicken Sie dann auf **Suche und Untersuchung** > **Inhaltssuche**.
2. Erstellen Sie ein neues Suchelement, indem Sie auf **+** klicken.
3. Geben Sie in einem neuen Fenster die folgenden Informationen an:  
    a. Name: IBAN-Suche  
    b. Wo sollen wir suchen?: **Wählen Sie die zu durchsuchenden Websites** (klicken Sie auf **+**), und geben Sie dann die URL der Website ein: **https://** \< NameIhresMandanten\>**.sharepoint.com/**  
    c. Klicken Sie auf **Hinzufügen** und dann auf **OK**. Wenn eine Warnung angezeigt wird, klicken Sie auf **OK**.  
    d. Klicken Sie in einem **neuen Suchfenster** auf **Weiter**.  
    e. Geben Sie für **Wonach sollen wir suchen?**: **SensitiveType: „International Banking Account Number (IBAN)“** ein, und klicken Sie dann auf **Suchen**.

4. Stellen Sie sicher, dass mindestens ein Element in den **IBAN-Suchergebnissen** aufgeführt ist.


## <a name="phase-4-create-a-custom-sensitive-information-type-via-powershell"></a>Phase 4: Erstellen eines benutzerdefinierten vertraulichen Informationstyps über PowerShell

In dieser Phase erstellen Sie einen benutzerdefinierten vertraulichen Informationstyp für die fiktive Contoso Corporation mithilfe von Microsoft PowerShell. Contoso verwendet einer Contoso-Kundennummer (Contoso Customer Number, CCN) zur Identifizierung der einzelnen Kunden in seiner Kundendatenbank. Eine CCN weist die folgende Struktur auf:
- Zwei Ziffern, die für das Jahr stehen, in dem der Datensatz erstellt wurde
    - Contoso wurde 2002 gegründet, daher wäre der früheste mögliche Wert „02“. 
- Drei Ziffern, die für die Partneragentur stehen, die den Datensatz erstellt hat
    - Mögliche Agenturwerte liegen zwischen 000 bis 999. 
- Ein alphabetisches Zeichen, das für die Branche steht
    - Mögliche Werte sind a-z, Groß- und Kleinschreibung soll nicht berücksichtigt werden.
- Eine vierstellige Seriennummer 
    - Mögliche Werte für Seriennummern liegen zwischen 0000 und 9999.   

Contoso verwendet immer eine CCN beim Verweisen auf Kunden in der internen Korrespondenz, externen Korrespondenz, in Dokumenten und andere Formularen. Contoso benötigt einen benutzerdefinierten vertraulichen Informationstyp, um die Verwendung von CCNs in Office 365-Inhalt zu ermitteln, um einen möglichen Schutz für die Verwendung dieser personenbezogenen Informationen anzuwenden.

1. Folgen Sie den Anweisungen in [Verbinden mit Security & Compliance Center PowerShell über Multi-Factor Authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell?view=exchange-ps) und stellen Sie mit dem UPN Ihres globalen Administratorkontos eine Verbindung mit Security & Compliance Center her.
2. Führen Sie die folgenden PowerShell-Befehle aus:

     ```
    #Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName#Create & start search for sample data
    $searchName = "Sample Customer Information Search"
    $searchQuery = "15080P9562 OR 14040O1119 OR 15020J8317 OR 14050E2330 OR 16050E2166 OR 17040O1118"
    New-ComplianceSearch -Name $searchName -SharePointLocation All -ExchangeLocation All -ContentMatchQuery $searchQuery
    Start-ComplianceSearch -Identity $searchName
    ```
3. Führen Sie die folgenden PowerShell-Befehle aus, und kopieren Sie die generierten GUIDs in der Reihenfolge, in der sie aufgelistet sind, in eine offene Instanz von Editor auf Ihrem Computer.
    ```
    #Generate three unique GUIDs
    Write-Host "GUID1 = "([guid]::NewGuid().Guid)
    Write-Host "GUID2 = "([guid]::NewGuid().Guid)
    Write-Host "GUID3 = "([guid]::NewGuid().Guid)
    ```
4. Öffnen Sie auf dem lokalen Computer eine weitere Instanz von Editor, und fügen Sie den folgenden Inhalt ein:

    ```
    <?xml version="1.0" encoding="utf-8"?>
    <RulePackage xmlns="https://schemas.microsoft.com/office/2011/mce"> 
    <RulePack id="GUID1">
    <Version major="1" minor="0" build="0" revision="0" />
    <Publisher id="GUID2" />
    <Details defaultLangCode="en"> 
    <LocalizedDetails langcode="en"> 
    <PublisherName>Contoso Ltd.</PublisherName> 
    <Name>Contoso Rule Package</Name> 
    <Description>Defines Contoso's custom set of classification rules</Description>
    </LocalizedDetails>
    </Details>
    </RulePack>
    <Rules>
    <!-- Contoso Customer Number (CCN) -->
    <Entity id="GUID3" patternsProximity="300" recommendedConfidence="85">
    <Pattern confidenceLevel="85">
    <IdMatch idRef="Regex_contoso_ccn" />
    <Match idRef="Keyword_contoso_ccn" />
    <Match idRef="Regex_eu_date" />
    </Pattern>
    </Entity>
    <Regex id="Regex_contoso_ccn">[0-1][0-9][0-9]{3}[A-Za-z][0-9]{4}</Regex>
    <Keyword id="Keyword_contoso_ccn">
    <Group matchStyle="word">
    <Term caseSensitive="false">customer number</Term>
    <Term caseSensitive="false">customer no</Term>
    <Term caseSensitive="false">customer #</Term>
    <Term caseSensitive="false">customer#</Term>
    <Term caseSensitive="false">Contoso customer</Term>
    </Group>
    </Keyword>
    <Regex id="Regex_eu_date"> (0?[1-9]|[12][0-9]|3[0-1])[\/-](0?[1-9]|1[0-2]|j\x00e4n(uar)?|jan(uary|uari|uar|eiro|vier|v)?|ene(ro)?|genn(aio)? |feb(ruary|ruari|rero|braio|ruar|br)?|f\x00e9vr(ier)?|fev(ereiro)?|mar(zo|o|ch|s)?|m\x00e4rz|maart|apr(ile|il)?|abr(il)?|avril |may(o)?|magg(io)?|mai|mei|mai(o)?|jun(io|i|e|ho)?|giugno|juin|jul(y|io|i|ho)?|lu(glio)?|juil(let)?|ag(o|osto)?|aug(ustus|ust)?|ao\x00fbt|sep|sept(ember|iembre|embre)?|sett(embre)?|set(embro)?|oct(ober|ubre|obre)?|ott(obre)?|okt(ober)?|out(ubro)? |nov(ember|iembre|embre|embro)?|dec(ember)?|dic(iembre|embre)?|dez(ember|embro)?|d\x00e9c(embre)?)[ \/-](19|20)?[0-9]{2}</Regex>
    <LocalizedStrings>
    <Resource idRef="GUID3">
    <Name default="true" langcode="en-us">Contoso Customer Number (CCN)</Name>
    <Description default="true" langcode="en-us">Contoso Customer Number (CCN) that looks for additional keywords and EU formatted date</Description>
    </Resource>
    </LocalizedStrings>
    </Rules>
    </RulePackage>
    ```
5. Ersetzen Sie die Werte von GUID1, GUID2 und GUID3 im XML-Text von Schritt 4 durch deren Werte aus Schritt 3, und speichern Sie dann die Inhalte mit dem Namen „ContosoCCN.xml“ auf dem lokalen Computer.
6. Geben Sie den Pfad zur Datei „ContosoCCN.xml“ ein, und führen Sie die folgenden Befehle aus.
    ```
    #Create new Sensitive Information Type
    $path="<path to the ContosoCCN.xml file, such as C:\Scripts\ContosoCCN.xml>"
    New-DlpSensitiveInformationTypeRulePackage -FileData (Get-Content -Path $path -Encoding Byte -ReadCount 0)
    ```
7. Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ auf **Klassifizierungen** > **Typen vertraulicher Informationen**. Die Contoso-Kundennummer (CCN) sollte in der Liste angezeigt werden.

## <a name="phase-5-demonstrate-data-protection"></a>Phase 5: Veranschaulichen des Datenschutzes

Schutz von personenbezogenen Informationen in Office 365 umfasst Funktionen, um Datenverlust zu vermeiden.  Mit DLP-Richtlinien können Sie automatisch in Office 365 vertrauliche Informationen schützen.

Es gibt mehrere Methoden zum Anwenden des Schutzes. Die Aufklärung und Bewusstseinsbildung in Bezug auf Daten von EU-Bürgern, die in Ihrer Umgebung gespeichert werden, sowie den Umgang von Mitarbeitern mit diesen stellen eine Ebene des Informationsschutzes unter Verwendung von DLP von Office 365 dar.

In dieser Phase erstellen Sie eine neue DLP-Richtlinie und veranschaulichen, wie sie auf die Datei „IBANs.docx“ angewendet wird, die Sie in Phase 2 in SharePoint Online gespeichert haben, und wie sie angewendet wird, wenn Sie versuchen, eine E-Mail mit IBANs zu versenden.

1. Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ im Browser auf **Start**.
2. Klicken Sie auf **Verhinderung von Datenverlust** > **Richtlinie**.
3. Klicken Sie auf **+ Erstellen einer Richtlinie**.
4. Klicken Sie in **Mit einer Vorlage beginnen oder eine benutzerdefinierte Richtlinie erstellen** auf **Benutzerdefiniert** > **Benutzerdefinierte Richtlinie** > **Weiter**.
5. Geben Sie in **Richtlinie benennen** die folgenden Details an, und klicken Sie dann auf **Weiter**: a. Name: **PII-Richtlinie für EU-Bürger** b. Beschreibung: **Schützen der personenbezogenen Informationen von EU-Bürgern**
6. Wählen Sie in **Speicherorte auswählen** die Option **Alle Speicherorte in Office 365** aus. Dies beinhaltet Inhalt in Exchange-E-Mail- sowie OneDrive- und SharePoint-Dokumenten. Klicken Sie dann auf **Weiter**.
7. Klicken Sie in **Anpassen des zu schützenden Inhaltstyps** auf **Nach Inhalten suchen, die Folgendes enthalten:**, und klicken Sie dann auf **Bearbeiten**.
8. Klicken Sie in **Auswählen des zu schützenden Inhaltstyps** auf **Hinzufügen** > **Typen vertraulicher Informationen**.
9. Klicken Sie in **Typen vertraulicher Informationen** auf **+ Hinzufügen**.
10. Suchen Sie in **Typen vertraulicher Informationen** nach **IBAN**, aktivieren Sie das Kontrollkästchen für **International Banking Account Number (IBAN)**, und klicken Sie auf **Hinzufügen**.
11. Vergewissern Sie sich, dass **International Banking Account Number (IBAN)** als Typ vertraulicher hinzugefügt wurde, und klicken Sie dann auf **Fertig**.
12. Vergewissern Sie sich in **Inhalt enthält**, dass die Typen vertraulicher Informationen hinzugefügt wurden, und klicken Sie dann auf **Speichern**.
13. Stellen Sie in **Anpassen des zu schützenden Inhaltstyps** sicher, dass **Nach Inhalten suchen, die Folgendes enthalten:** die **internationale Bankkontonummer (IBAN)** enthält, und klicken Sie dann auf **Weiter**.
14. Ändern Sie in **Erkennen, wenn Inhalte, die freigegeben werden, Folgendes enthalten:** den Wert von **10** in **1**, und klicken Sie dann auf **Weiter**.
15. Wählen Sie in **Möchten Sie die Richtlinie aktivieren oder sie zuerst ausprobieren?** die folgenden Einstellungen aus, und klicken Sie dann auf **Weiter**.  
    a. Wählen Sie die Option für **Ich möchte sie zuerst testen** aus.  
    b. Aktivieren Sie das Kontrollkästchen für **Anzeigen von Richtlinientipps im Testmodus**. 
16. Klicken Sie in **Überprüfen Sie Ihre Einstellungen** auf **Erstellen**, nachdem Sie die Einstellungen überprüft haben. HINWEIS: Nach dem Erstellen einer neuen DLP-Richtlinie dauert es eine Weile, bis diese wirksam wird.
17. Öffnen Sie auf dem lokalen Computer eine private Instanz des Browsers.
18. Geben Sie in der Adressleiste **https://**\<NameIhresMandanten\>**. sharepoint.com** ein, und melden Sie sich mit Ihrem globalen Administratorkonto an.
19. Klicken Sie auf **Dokumente**.
20. Klicken Sie auf die Datei mit dem Namen „IBANs.docx“. „Richtlinientipp für IBANs.docx“ sollte angezeigt werden. Die Datei „IBANs.docx“ wurde an externe Empfänger versendet, was gegen die DLP-Richtlinie verstößt. 
21. Geben Sie in der Adressleiste Folgendes ein: `https://outlook.office365.com`
22. Klicken Sie auf **Neu** - **E-Mail-Nachricht**, und geben Sie Folgendes an:  
    - **An:** \< eine persönliche E-Mail-Adresse\>  
    - **Betreff:** DSGVO-Test  
    - **Text:** Kopieren Sie die unten gezeigte Tabelle mit Werten, und fügen Sie sie ein.
  
        |Nummer  |Land  |Code |IBAN  |
        |---------|---------|---------|---------|
        |1     |  Österreich SEPA      | AT            |AT611904300234573201       |
        |2     |  Bulgarien SEPA       |BG    |BG80BNBG96611020345678      |
        |3     |  Dänemark SEPA      |   DK      |DK5000400440116243      |
        |4     |  Finnland SEPA      |   FI      |FI2112345600000785         |
        |5     |  Frankreich SEPA       |   FR      |FR1420041010050500013M02606         |
        |6     |  Deutschland SEPA      |   DE      |DE89370400440532013000         |
        |7     |  Griechenland SEPA       |   GR      |GR1601101250000000012300695         |
        |8     |  Italien SEPA       |    IT     |GR1601101250000000012300695         |
        |9     |  Niederlande SEPA      |   NL      |   NL91ABNA0417164300      |
        |10     | Polen SEPA       |  PL       | PL27114020040000300201355387        |

Hinweis: Dieser Beispieldatensatz wird von öffentlich verfügbaren Informationen abgeleitet und soll nur für Testzwecke verwendet werden.

23. Sie sehen, dass die DLP-Richtlinie erkannt hat, dass der Text der E-Mail IBANs enthält und Ihnen am oberen Rand des Nachrichtenfensters den Richtlinientipp bereitstellt.
24. Schließen Sie die private Instanz des Browsers.


## <a name="phase-6-demonstrate-reporting"></a>Phase 6: Veranschaulichen der Berichterstellung
 
In dieser Phase veranschaulichen Sie die Office 365-Berichterstellung basierend auf der in Phase 5 konfigurierten DLP-Richtlinie.

   1. Klicken Sie auf der Registerkarte „Sicherheit und Compliance“ im Browser auf **Start**.
   2. Klicken Sie auf **Berichte** > **Dashboard** > **DLP-Richtlinienübereinstimmungen**.
   3. Ihre DLP-Richtlinie trägt zum Identifizieren und Schützen vertraulicher Informationen der Organisation bei. Beispielsweise sehen Sie im Bericht, dass die Richtlinie das Dokuments identifiziert hat, das in SharePoint Online gespeicherte IBANs enthält.
  
## <a name="see-also"></a>Siehe auch

[Schutz von Informationen in Office 365 für die DSGVO](office-365-information-protection-for-gdpr.md)

[DSGVO für Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/gdpr?toc=/microsoft-365/enterprise/toc.json)
