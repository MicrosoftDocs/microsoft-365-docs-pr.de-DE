---
title: Erstellen einer DLP-Richtlinie aus einer Vorlage
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 6/29/2018
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
description: In diesem Artikel erfahren Sie, wie Sie DLP-Richtlinien mithilfe einer der vorlagen erstellen, die in der Office 365.
ms.openlocfilehash: 0088381698b47b2451f52fde32716a2436e8c073
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52113967"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Erstellen einer DLP-Richtlinie aus einer Vorlage

Die einfachste und gängigste Methode zum Einstieg in DLP-Richtlinien (Data Loss Prevention, Verhinderung von Datenverlust) ist die Verwendung einer der in Office 365 enthaltenen Vorlagen. Sie können eine dieser Vorlagen wie folgt verwenden oder die Regeln anpassen, um die spezifischen Complianceanforderungen Ihrer Organisation zu erfüllen.
  
Microsoft 365 umfasst mehr als 40 einsatzbereite Vorlagen, mit deren Hilfe Sie eine Vielzahl gängiger behördlicher und geschäftlicher Richtlinienanforderungen erfüllen können. Es gibt z. B. DLP-Richtlinienvorlagen für:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Payment Card Industry Data Security Standard (PCI-DSS)
    
- United States Personally Identifiable Information (U.S. PII)
    
- United States Health Insurance Act (HIPAA)
    
Sie können eine Vorlage anpassen, indem Sie eine vorhandene Regel ändern oder neue hinzufügen. Beispielsweise können Sie neue Arten von vertraulichen Informationen zu einer Regel hinzufügen oder die Anzahl in einer Regel ändern, damit sie leichter oder schwerer ausgelöst wird. Sie können es auch Benutzern ermöglichen, die Aktionen in einer Regel anhand einer geschäftlichen Begründung außer Kraft zu setzen oder ändern, an wen Benachrichtigungen und Schadensberichte gesendet werden. Eine DLP-Richtlinienvorlage ist ein flexibler Ausgangspunkt für viele gängige Compliance-Szenarien.
  
Sie können auch die benutzerdefinierte Vorlage auswählen, die über keine Standardregeln verfügt, und die DLP-Richtlinie von Grund auf neu konfigurieren, um die spezifischen Vorschriften für Ihre Organisation einzuhalten.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Beispiel: Identifizieren von vertraulichen Informationen auf OneDrive for Business Websites und Einschränken des Zugriffs für Personen außerhalb Ihrer Organisation

OneDrive for Business Konten machen es Personen in Ihrer Organisation einfach, zusammenzuarbeiten und Dokumente zu teilen. Ein allgemeines Problem für Compliance officers ist jedoch, dass vertrauliche Informationen, die in OneDrive for Business gespeichert sind, versehentlich an Personen außerhalb Ihrer Organisation weitergegeben werden. Eine DLP-Richtlinie kann dieses Risiko verringern.
  
In diesem Beispiel erstellen Sie eine DLP-Richtlinie, die US-PII-Daten identifiziert, die itIN (Individual Taxpayer Identification Numbers), Sozialversicherungsnummern und US-Reisepassnummern enthält. Sie beginnen mit einer Vorlage und ändern dann die Vorlage, um die Complianceanforderungen Ihrer Organisation zu erfüllen– insbesondere:
  
- Fügen Sie mehrere Typen vertraulicher Informationen hinzu , z. B. US-Bankkontonummern und Führerscheinnummern der USA, damit die DLP-Richtlinie noch mehr Ihrer vertraulichen Daten schützt.
    
- Machen Sie die Richtlinie vertraulicher, sodass ein einzelnes Vorkommen vertraulicher Informationen ausreicht, um den Zugriff für externe Benutzer einzuschränken.
    
- Sie ermöglichen Benutzern, die Aktionen anhand einer geschäftlichen Begründung oder der Meldung eines falsch positiven Ergebnisses außer Kraft zu setzen. Auf diese Weise verhindert Ihre DLP-Richtlinie nicht, dass Personen in Ihrer Organisation ihre Arbeit erledigen, sofern sie einen gültigen geschäftlichen Grund für die Freigabe der vertraulichen Informationen haben.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Erstellen einer DLP-Richtlinie aus einer Vorlage

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto an. Sie sind jetzt im Security &amp; Compliance Center.
    
3. In the Security &amp; Compliance Center left navigation Data loss \> \> **prevention** \> **Policy** \> **+ Create a policy**.
    
    ![Erstellen einer Richtlinienschaltfläche](../media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Wählen Sie die DLP-Richtlinienvorlage aus, die die Typen vertraulicher Informationen schützt, die Sie als \> **Nächstes benötigen.**
    
    In diesem Beispiel wählen  Sie Daten der personenbezogenen Daten \> **(Privacy U.S. Personally Identifiable Information, PII)** aus, da sie bereits die meisten Typen vertraulicher Informationen enthalten, die Sie schützen möchten– Sie fügen später ein paar hinzu. 
    
    Wenn Sie eine Vorlage auswählen, können Sie die Beschreibung auf der rechten Seite lesen, um zu erfahren, welche Arten vertraulicher Informationen die Vorlage schützt.
    
    ![Seite zum Auswählen einer DLP-Richtlinienvorlage](../media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nennen Sie die \> **Richtlinie Weiter**.
    
6. Gehen Sie wie folgt vor, um die Speicherorte zu wählen, die die DLP-Richtlinie schützen soll:
    
  - Wählen **Sie Alle Speicherorte in Office 365** Weiter \> **aus.**
    
  - Wählen **Sie Let me choose specific locations** Next \> **aus.** Wählen Sie in diesem Beispiel diese Option aus.
    
    Um einen gesamten Speicherort wie alle E-Mail-Exchange oder alle OneDrive-Konten ein- oder auszuschließen, deaktivieren Sie den **Status** dieses Speicherorts. 
    
    Um nur bestimmte SharePoint websites oder OneDrive for Business zu verwenden, wechseln Sie zu **Status,** und  klicken Sie dann unter Include auf die Links, um bestimmte Websites oder Konten zu wählen. Wenn Sie eine Richtlinie auf eine Website anwenden, werden die in dieser Richtlinie konfigurierten Regeln automatisch auf alle Unterwebsites dieser Website angewendet. 
    
    ![Optionen für Orte, auf die eine DLP-Richtlinie angewendet werden kann](../media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    Deaktivieren Sie in diesem Beispiel den Status für Exchange-E-Mails und **SharePoint-Websites,** um vertrauliche Informationen zu schützen, die in allen **OneDrive for Business-Konten** gespeichert sind, und lassen Sie den **Status** für **OneDrive-Konten.** 
    
7. Wählen **Sie Erweiterte Einstellungen verwenden** Weiter \> **aus.**
    
8. Eine DLP-Richtlinienvorlage enthält vordefinierte Regeln mit Bedingungen und Aktionen, die bestimmte Arten von vertraulichen Informationen erkennen und entsprechende Aktionen ausführen. Sie können vorhandene Regeln bearbeiten, löschen oder deaktivieren oder neue hinzufügen. Klicken Sie nach getaner Arbeit auf **Weiter**.
    
    ![Regeln, die in der Richtlinienvorlage "US PII" erweitert wurden](../media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    In diesem Beispiel enthält die VORLAGE FÜR PII-Daten in den USA zwei vordefinierte Regeln:
    
  - **Geringes Inhaltsvolumen erkannte US-PII** Diese Regel sucht nach Dateien mit 1 bis 10 Vorkommen jeder der drei Arten vertraulicher Informationen (ITIN, SSN und US-Reisepassnummern), in denen die Dateien für Personen außerhalb der Organisation freigegeben werden. Wenn gefunden, sendet die Regel eine E-Mail-Benachrichtigung an den primären Websitesammlungsadministrator, den Dokumentbesitzer und die Person, die das Dokument zuletzt geändert hat. 
    
  - **Hohe Menge von Inhalten, die in den USA piI erkannt wurden** Diese Regel sucht nach Dateien mit 10 oder mehr Vorkommen der drei gleichen typen vertraulichen Informationen, in denen die Dateien für Personen außerhalb der Organisation freigegeben werden. Wenn diese Aktion gefunden wird, sendet sie auch eine E-Mail-Benachrichtigung und schränkt den Zugriff auf die Datei ein. Für Inhalte in einem OneDrive for Business bedeutet dies, dass die Berechtigungen für das Dokument für alle Personen eingeschränkt sind, mit Ausnahme des primären Websitesammlungsadministrators, des Dokumentbesitzers und der Person, die das Dokument zuletzt geändert hat. 
    
    Um die spezifischen Anforderungen Ihrer Organisation zu erfüllen, sollten Sie die Auslösung der Regeln vereinfachen, damit ein einzelnes Vorkommen vertraulicher Informationen ausreicht, um den Zugriff für externe Benutzer zu blockieren. Nachdem Sie sich diese Regeln anschaut, wissen Sie, dass Sie keine Regeln mit niedriger und hoher Anzahl benötigen– Sie benötigen nur eine einzelne Regel, die den Zugriff blockiert, wenn ein Vorkommen vertraulicher Informationen gefunden wird.
    
    Daher erweitern Sie die Regel namens **Low volume of content detected U.S. PII** Delete \> **rule**.
    
    ![Regelschaltfläche löschen](../media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. In diesem Beispiel müssen Sie nun zwei Typen vertraulicher Informationen hinzufügen (US-Bankkontonummern und Führerscheinnummern der USA), Personen das Außerkraft setzen und die Anzahl in ein beliebiges Vorkommen ändern. Sie können all dies tun, indem Sie eine Regel bearbeiten, wählen Sie also Hohe Menge von erkannten **Inhalten in** den USA PII \> **Edit-Regel aus.**
    
    ![Schaltfläche "Regel bearbeiten"](../media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Um einen vertraulichen Informationstyp hinzuzufügen, fügen Sie im Abschnitt **Bedingungen** Typen hinzufügen \> **oder ändern hinzu.** Wählen Sie dann unter **Add or change types** die Option Hinzufügen die Option \>  \> **Us.S. Bankkontonummer** und **U.S.** Führerscheinnummer \> **Hinzufügen Fertig** \> **aus.**
    
    ![Option zum Hinzufügen oder Ändern von Typen](../media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Hinzufügen oder Ändern des Bereichs "Typen"](../media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Um die Anzahl zu ändern (die Anzahl der Instanzen vertraulicher Informationen, die zum Auslösen der Regel erforderlich sind), wählen Sie unter **Instanzanzahl** den Min-Wert für jeden Typ \>  \> 1 aus. Die Mindestanzahl darf nicht leer sein. Die maximale Anzahl kann leer sein. Ein leerer **maximaler** Wert wird in **eine beliebige konvertiert.**
    
    Wenn Sie fertig sind, sollte die Min.-Anzahl für alle Typen vertraulicher Informationen **1** sein, und die maximale Anzahl sollte alle **sein.** Anders ausgedrückt: Jedes Vorkommen dieser Art vertraulicher Informationen erfüllt diese Bedingung.
    
    ![Instanzanzahl für Typen vertraulicher Informationen](../media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Für die endgültige Anpassung möchten Sie nicht, dass Ihre DLP-Richtlinien Personen an ihrer Arbeit blockieren, wenn sie über eine gültige Geschäftliche Begründung verfügen oder eine falsch positive Einstellung haben. Sie möchten daher, dass die Benutzerbenachrichtigung Optionen enthält, um die Blockierende Aktion außer Kraft zu setzen.
    
    Im Abschnitt **Benutzerbenachrichtigungen** sehen Sie, dass E-Mail-Benachrichtigungen und Richtlinientipps für diese Regel in der Vorlage standardmäßig aktiviert sind. 
    
    Im  Abschnitt Benutzerüberschreibungen sehen Sie, dass Außerkraftsetzungen für eine Geschäftliche Begründung aktiviert sind, Außerkraftsetzungen zum Melden falsch positiver Ergebnisse jedoch nicht. Wählen Sie Die Regel automatisch außer Kraft **setzen aus, wenn sie als falsch positiv angezeigt wird.**
    
    ![Abschnitt "Benutzerbenachrichtigungen" und "Benutzerüberschreibungen"](../media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Ändern Sie oben im Regel-Editor den Namen dieser Regel von dem standardmäßigen High Volume of **content detected U.S. PII** in **Any content detected with U.S. PII,** da sie jetzt durch alle Vorkommen der typen vertraulicher Informationen ausgelöst wird. 
    
14. Unten im Regel-Editor \> **Speichern**.
    
15. Überprüfen Sie die Bedingungen und Aktionen für diese Regel \> **Weiter**.
    
    Beachten Sie auf der rechten Seite die **Option Status** für die Regel. Wenn Sie eine gesamte Richtlinie deaktivieren, werden auch alle in der Richtlinie enthaltenen Regeln deaktiviert. Hier können Sie jedoch eine bestimmte Regel deaktivieren, ohne die gesamte Richtlinie zu deaktivieren. Dies kann hilfreich sein, wenn Sie eine Regel untersuchen müssen, die eine große Anzahl falsch positiver Ergebnisse generiert. 
    
16. Lesen Und verstehen Sie auf der nächsten Seite Folgendes, und wählen Sie dann aus, ob sie die Regel aktivieren oder zuerst \> **testen möchten Weiter**.
    
     Bevor Sie DLP-Richtlinien erstellen, sollten Sie sie erst einmal nach und nach bereitstellen, um die Auswirkungen beurteilen und ihre Effektivität testen zu können, bevor Sie sie vollständig durchsetzen. Sie möchten beispielsweise nicht, dass eine neue DLP-Richtlinie versehentlich den Zugriff auf Tausende von Dokumenten blockiert, die Personen benötigen, um ihre Arbeit erledigen zu können. 
    
    Wenn Sie DLP-Richtlinien erstellen, die potenziell weitreichende Auswirkungen haben können, empfehlen wir, in der folgenden Reihenfolge vorzugehen:
    
17. Beginnen Sie im Testmodus ohne Richtlinientipps, und werten Sie die Auswirkungen dann anhand der DLP-Berichte aus. In den DLP-Berichten werden die Anzahl von Richtlinienübereinstimmungen, der Ort des Vorkommens, der Typ und der Schweregrad aufgeführt. Auf Grundlage der Ergebnisse können Sie die Regeln nach Bedarf genauer anpassen. Im Testmodus haben DLP-Richtlinien keinen Einfluss auf die Produktivität der Mitarbeiter in Ihrer Organisation. 
    
18. Fahren Sie im Testmodus mit Benachrichtigungen und Richtlinientipps fort, sodass Sie die Benutzer über die Einhaltungsrichtlinien in Kenntnis setzen und auf die Anwendung der Regeln vorbereiten können. In dieser Phase können Sie die Benutzer auch bitte, Sie über falsche Positivmeldungen zu benachrichtigen, damit Sie die Regeln noch besser abstimmen können.
    
19. Aktivieren Sie die Richtlinien, damit die Regeln erzwungen und der Inhalt geschützt wird. Überwachen Sie weiterhin die DLP-Berichte und alle Schadensberichte oder Benachrichtigungen, um sicherzustellen, dass die von Ihnen gewünschten Ergebnisse erzielt werden. 
    
    ![Optionen zum Verwenden des Testmodus und zum Aktivieren der Richtlinie](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Überprüfen Sie Ihre Einstellungen für diese Richtlinie, wählen \> Sie **Erstellen aus.**
    
Nachdem Sie eine DLP-Richtlinie erstellt und aktiviert haben, wird sie für alle Inhaltsquellen bereitgestellt, die sie enthält, z. B. SharePoint Onlinewebsites oder OneDrive for Business-Konten, in denen die Richtlinie beginnt, ihre Regeln für diesen Inhalt automatisch zu erzwingen.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Anzeigen des Status einer DLP-Richtlinie

Sie können jederzeit den Status Ihrer DLP-Richtlinien auf der  Seite **Richtlinie** im Abschnitt Verhinderung von Datenverlust im Security &amp; Compliance Center anzeigen. Hier finden Sie wichtige Informationen, z. B. ob eine Richtlinie erfolgreich aktiviert oder deaktiviert wurde oder ob sich die Richtlinie im Testmodus befindet. 
  
Nachfolgend werden die verschiedenen Statuswerte und deren Bedeutung beschrieben.
  
|**Status**|**Erläuterung**|
|:-----|:-----|
|**Aktivieren von...** <br/> |Die Richtlinie wird gerade für die Inhaltsquellen, die sie umfasst, bereitgestellt. Die Richtlinie wird noch nicht bei allen Quellen erzwungen.  <br/> |
|**Testen, mit Benachrichtigungen** <br/> |Die Richtlinie ist im Testmodus. Die Aktionen in einer Regel werden nicht angewendet, aber Richtlinienübereinstimmungen werden mithilfe der DLP-Berichte zusammengestellt und angezeigt. Benachrichtigungen über Richtlinienübereinstimmungen werden an die angegebenen Empfänger gesendet.  <br/> |
|**Testen, ohne Benachrichtigungen** <br/> |Die Richtlinie ist im Testmodus. Die Aktionen in einer Regel werden nicht angewendet, aber Richtlinienübereinstimmungen werden mithilfe der DLP-Berichte zusammengestellt und angezeigt. Benachrichtigungen über Richtlinienübereinstimmungen werden nicht an die angegebenen Empfänger gesendet.  <br/> |
|**On** <br/> |Die Richtlinie ist aktiv und wird erzwungen. Die Richtlinie wurde erfolgreich für alle zugehörigen Inhaltsquellen bereitgestellt.  <br/> |
|**Wird deaktiviert...** <br/> |Die Richtlinie wird gerade aus den Inhaltsquellen, die sie umfasst, entfernt. Die Richtlinie kann noch bei einigen Quellen aktiv sein und erzwungen werden. Das Deaktivieren einer Richtlinie kann bis zu 45 Minuten dauern.  <br/> |
|**Off** <br/> |Die Richtlinie ist nicht aktiv und wird nicht erzwungen. Die Einstellungen für die Richtlinie (Quellen, Schlüsselwörter, Dauer usw.) werden gespeichert.  <br/> |
|**Löschen...** <br/> |Die Richtlinie wird gerade gelöscht. Die Richtlinie ist nicht aktiv und wird nicht erzwungen. Das Delet einer Richtlinie dauert normalerweise eine Stunde. <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Deaktivieren einer DLP-Richtlinie

Sie können eine DLP-Richtlinie jederzeit bearbeiten oder deaktivieren. Wenn Sie eine Richtlinie deaktivieren, werden alle Regeln in der Richtlinie deaktiviert.
  
Um eine DLP-Richtlinie zu bearbeiten oder zu deaktivieren, wählen Sie auf der Seite **Richtlinie** \> die Richtlinie Bearbeiten richtlinie \> **aus.**
  
![Schaltfläche "Richtlinie bearbeiten"](../media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Darüber hinaus können Sie jede Regel einzeln deaktivieren, indem Sie die Richtlinie bearbeiten und dann wie oben beschrieben den **Status** dieser Regel deaktivieren. 
  
## <a name="more-information"></a>Weitere Informationen

- [Informationen zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md)
- [Senden von Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)
- [Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI- oder anderen Eigenschaften](protect-documents-that-have-fci-or-other-properties.md)
- [Bestandteile von DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
