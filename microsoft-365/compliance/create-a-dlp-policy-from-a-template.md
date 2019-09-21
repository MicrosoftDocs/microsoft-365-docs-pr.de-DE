---
title: Erstellen einer DLP-Richtlinie aus einer Vorlage
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
description: 'Die einfachste und gängigste Methode für den Einstieg in DLP-Richtlinien ist die Verwendung der in Office 365 enthaltenen Vorlagen. '
ms.openlocfilehash: db32748b25296ef82c56160e95535ac488eb65a5
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080959"
---
# <a name="create-a-dlp-policy-from-a-template"></a>Erstellen einer DLP-Richtlinie aus einer Vorlage

Die einfachste und gängigste Methode für den Einstieg in DLP-Richtlinien ist die Verwendung der in Office 365 enthaltenen Vorlagen. Sie können eine der folgenden Vorlagen verwenden oder die Regeln anpassen, um die spezifischen Compliance-Anforderungen Ihrer Organisation zu erfüllen.
  
Office 365 umfasst mehr als 40 verwendungsbereite Vorlagen, mit denen Sie eine Vielzahl von allgemeinen behördlichen und geschäftlichen Richtlinienanforderungen erfüllen können. Es gibt z. B. DLP-Richtlinienvorlagen für:
  
- Gramm-Leach-Bliley Act (GLBA)
    
- Payment Card Industry Data Security Standard (PCI-DSS)
    
- United States Personally Identifiable Information (U.S. PII)
    
- United States Health Insurance Act (HIPAA)
    
Sie können eine Vorlage anpassen, indem Sie eine vorhandene Regel ändern oder neue hinzufügen. Beispielsweise können Sie neue Arten von vertraulichen Informationen zu einer Regel hinzufügen oder die Anzahl in einer Regel ändern, damit sie leichter oder schwerer ausgelöst wird. Sie können es auch Benutzern ermöglichen, die Aktionen in einer Regel anhand einer geschäftlichen Begründung außer Kraft zu setzen oder ändern, an wen Benachrichtigungen und Schadensberichte gesendet werden. Eine DLP-Richtlinienvorlage ist ein flexibler Ausgangspunkt für viele gängige Compliance-Szenarien.
  
Sie können auch die benutzerdefinierte Vorlage auswählen, die über keine Standardregeln verfügt, und die DLP-Richtlinie von Grund auf neu konfigurieren, um die spezifischen Vorschriften für Ihre Organisation einzuhalten.
  
## <a name="example-identify-sensitive-information-across-all-onedrive-for-business-sites-and-restrict-access-for-people-outside-your-organization"></a>Beispiel: Identifizieren von vertraulichen Informationen auf allen OneDrive für Unternehmen Websites und Einschränken des Zugriffs für Personen außerhalb Ihrer Organisation

OneDrive für Unternehmen Konten erleichtern Personen in Ihrer Organisation die Zusammenarbeit und die gemeinsame Nutzung von Dokumenten. Ein allgemeines Problem für Compliance Officer ist jedoch, dass vertrauliche Informationen, die in OneDrive für Unternehmen Konten gespeichert sind, möglicherweise versehentlich für Personen außerhalb Ihrer Organisation freigegeben werden. Eine DLP-Richtlinie kann dieses Risiko verringern.
  
In diesem Beispiel erstellen Sie eine DLP-Richtlinie, in der die US-PII-Daten identifiziert werden, einschließlich der einzelnen steuerzahl-Identifikationsnummern (ITIN), Sozialversicherungsnummern und US-Passport-Nummern. Sie erhalten zunächst eine Vorlage, und Sie ändern die Vorlage dann entsprechend den Compliance-Anforderungen Ihrer Organisation – insbesondere:
  
- Fügen Sie eine Reihe von vertraulichen Informationen hinzu – U. S. Bank Kontonummern und US-Führerscheinnummern –, damit die DLP-Richtlinie noch mehr vertrauliche Daten schützt.
    
- Machen Sie die Richtlinie vertraulicher, sodass ein einzelnes Vorkommen von vertraulichen Informationen ausreicht, um den Zugriff für externe Benutzer einzuschränken.
    
- Sie ermöglichen Benutzern, die Aktionen anhand einer geschäftlichen Begründung oder der Meldung eines falsch positiven Ergebnisses außer Kraft zu setzen. Auf diese Weise hindert ihre DLP-Richtlinie nicht, dass Personen in Ihrer Organisation ihre Arbeit erledigen, vorausgesetzt, Sie verfügen über einen gültigen geschäftlichen Grund für die Freigabe vertraulicher Informationen.
    
### <a name="create-a-dlp-policy-from-a-template"></a>Erstellen einer DLP-Richtlinie aus einer Vorlage

1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an. Sie befinden sich jetzt im Office 365 Security &amp; Compliance Center.
    
3. Im &amp; Security \> Compliance Center Links Navigations \> **Richtlinie** \> zur **Verhinderung** \> von Datenverlust und **Erstellen einer Richtlinie**.
    
    ![Erstellen einer Richtlinien Schaltfläche](media/b1e48a08-92e2-47ca-abdc-4341694ddc7c.png)
  
4. Wählen Sie die DLP-Richtlinienvorlage aus, die die Typen von vertraulichen \> Informationen schützt, die Sie **als nächstes**benötigen.
    
    In diesem Beispiel wählen Sie Daten **Schutz** \> - **US-Daten für personenbezogene Informationen (PII)** aus, da Sie bereits die meisten Arten von vertraulichen Informationen enthält, die Sie schützen möchten – Sie fügen später ein paar hinzu. 
    
    Wenn Sie eine Vorlage auswählen, können Sie die Beschreibung auf der rechten Seite lesen, um zu erfahren, welche Arten von vertraulichen Informationen die Vorlage schützt.
    
    ![Seite zum Auswählen einer DLP-Richtlinienvorlage](media/775266f6-ad87-4080-8d7c-97f2e7403b30.png)
  
5. Nennen Sie die \> Richtlinie **als nächstes**.
    
6. Führen Sie einen der folgenden Schritte aus, um die Speicherorte auszuwählen, die von der DLP-Richtlinie geschützt werden sollen:
    
  - Wählen Sie **in Office 365** \> **Next**alle Standorte aus.
    
  - Wählen Sie **Let Me Choose specific Locations** \> **Next**aus. Wählen Sie in diesem Beispiel diese aus.
    
    Wenn Sie einen gesamten Standort wie alle Exchange-e-Mails oder alle OneDrive-Konten einschließen oder ausschließen möchten, wechseln Sie den **Status** dieser Position ein oder aus. 
    
    Um nur bestimmte SharePoint-Websites oder OneDrive für Unternehmen Konten einzuschließen, wechseln Sie den **Status** auf ein, und klicken Sie dann auf die Links unter **einschließen** , um bestimmte Websites oder Konten auszuwählen. Wenn Sie eine Richtlinie auf eine Website anwenden, werden die in dieser Richtlinie konfigurierten Regeln automatisch auf alle Unterwebsites dieser Website angewendet. 
    
    ![Optionen für Standorte, an denen eine DLP-Richtlinie angewendet werden kann](media/ee50a61a-e867-4571-a150-3eec8d83650f.png)
  
    Wenn Sie in diesem Beispiel vertrauliche Informationen schützen möchten, die in allen OneDrive für Unternehmen Konten gespeichert sind, deaktivieren Sie den **Status** für **Exchange-e-Mails** und **SharePoint-Websites**, und belassen Sie den **Status** für **OneDrive-Konten**.
    
7. Wählen Sie \> **weiter** **Erweiterte Einstellungen verwenden** aus.
    
8. Eine DLP-Richtlinienvorlage enthält vordefinierte Regeln mit Bedingungen und Aktionen, die bestimmte Arten von vertraulichen Informationen erkennen und entsprechende Aktionen ausführen. Sie können eine der vorhandenen Regeln bearbeiten, löschen oder deaktivieren oder neue Regeln hinzufügen. Klicken Sie nach Abschluss des Vorganges auf **weiter**.
    
    ![In der US-PII-Richtlinienvorlage Erweiterte Regeln](media/3bc9f1b6-f8ad-4334-863a-24448bb87687.png)
  
    In diesem Beispiel enthält die US-PII-Datenvorlage zwei vordefinierte Regeln:
    
  - **Geringe Menge an Inhalten, die in US-PII erkannt** wurden Diese Regel sucht nach Dateien, die zwischen 1 und 10 Vorkommen von jeweils drei Arten von vertraulichen Informationen enthalten (ITIN, SSN und US-Passport-Nummern), wobei die Dateien für Personen außerhalb der Organisation freigegeben werden. Wenn die Regel gefunden wird, sendet Sie eine e-Mail-Benachrichtigung an den primären Websitesammlungsadministrator, den Dokumentbesitzer und die Person, die das Dokument zuletzt geändert hat. 
    
  - **Hohes Volumen an Inhalten, die in US-PII erkannt** wurden Diese Regel sucht nach Dateien, die 10 oder mehr Vorkommen jedes der drei Typen vertraulicher Informationen enthalten, wobei die Dateien für Personen außerhalb der Organisation freigegeben werden. Wenn diese Aktion gefunden wird, wird auch eine e-Mail-Benachrichtigung gesendet, und der Zugriff auf die Datei wird eingeschränkt. Für Inhalte in einem OneDrive für Unternehmen-Konto bedeutet dies, dass Berechtigungen für das Dokument für alle Benutzer mit Ausnahme des primären Websitesammlungsadministrators, des Dokumentbesitzers und der Person, die das Dokument zuletzt geändert hat, eingeschränkt sind. 
    
    Um die spezifischen Anforderungen Ihrer Organisation zu erfüllen, sollten Sie die Regeln möglicherweise einfacher auslösen, sodass ein einzelnes Vorkommen vertraulicher Informationen ausreicht, um den Zugriff für externe Benutzer zu blockieren. Nachdem Sie sich diese Regeln angesehen haben, wissen Sie, dass Sie keine Regeln für niedrige und hohe Anzahl benötigen – Sie benötigen nur eine einzige Regel, die den Zugriff blockiert, wenn ein Vorkommen vertraulicher Informationen gefunden wird.
    
    Erweitern Sie daher die Regel mit dem Namen " **Low Volume of Content detected U.S. PII** \> **Delete Rule**".
    
    ![Schaltfläche "Regel löschen"](media/bc36f7d2-0fae-4af1-92e8-95ba51077b12.png)
  
9. In diesem Beispiel müssen Sie nun zwei vertrauliche Informationstypen hinzufügen (US-Bank Kontonummern und US-Führerscheinnummern), Benutzern das außer Kraft setzen einer Regel ermöglichen und die Anzahl in jedes Vorkommen ändern. Sie können dies alles tun, indem Sie eine Regel bearbeiten, daher wählen Sie **hohe Anzahl von Inhalten, die in der US-PII** \> - **Bearbeitungsregel**erkannt wurden.
    
    ![Schaltfläche ' Regel bearbeiten '](media/eaf54067-4945-4c98-8dd6-fb2c5d6de075.png)
  
10. Zum Hinzufügen eines Typs für vertrauliche Informationen **** im Abschnitt \> Bedingungen **Hinzufügen oder Ändern von Typen**. Wählen Sie dann unter **Hinzufügen oder ändern Typen** \> die **** \> Option Select **US Bank Account Number** und **u.s. Driver es License Number** \> **Add** \> **done**aus.
    
    ![Option zum Hinzufügen oder Ändern von Typen](media/c6c3ae86-f7db-40a8-a6e4-db11692024be.png)
  
    ![Bereich "Typen hinzufügen oder ändern"](media/fdbb96af-b914-4a6c-a97b-bbd014689965.png)
  
11. Wenn Sie die Anzahl der Instanzen von vertraulichen Informationen ändern möchten, die zum Auslösen der Regel erforderlich sind, wählen Sie unter **** **Instanz count** \> den Wert Min \> für jeden Typ 1 aus. Die minimale Anzahl darf nicht leer sein. Die maximale Anzahl kann leer sein; ein leerer **Max** -Wert, der in **any**konvertiert werden soll.
    
    Nach Abschluss des Vorgangs sollte die minimale Anzahl für alle Typen vertraulicher Informationen **1** sein, und die maximale Anzahl sollte **beliebig**sein. Mit anderen Worten: jedes Vorkommen dieses Typs vertraulicher Informationen erfüllt diese Bedingung.
    
    ![Instanzenanzahl für Typen vertraulicher Informationen](media/5c6e08cb-59a9-4558-b54b-d899836d4737.png)
  
12. Für die abschließende Anpassung möchten Sie nicht, dass ihre DLP-Richtlinien Personen daran hindern, ihre Arbeit zu tätigen, wenn Sie eine gültige geschäftliche Begründung haben oder ein falsch positives Ergebnis auftreten, sodass die Benutzerbenachrichtigung Optionen zum außer Kraft setzen der Blockierungsaktion enthalten soll.
    
    Im Abschnitt **Benutzer Benachrichtigungen** können Sie sehen, dass e-Mail-Benachrichtigungen und Richtlinien Tipps standardmäßig für diese Regel in der Vorlage aktiviert sind. 
    
    Im Abschnitt **User Overrides** können Sie sehen, dass Außerkraftsetzungen für eine geschäftliche Begründung aktiviert sind, aber Außerkraftsetzungen, um falsch positive Ergebnisse zu melden. Wählen Sie **die Regel automatisch außer Kraft setzen aus, wenn Sie Sie als falsch positives Ergebnis melden**.
    
    ![Abschnitt "User Notifications" und "User Overrides"](media/62720e7a-a939-4c03-b414-67748f3d64a0.png)
  
13. Ändern Sie oben im Regel-Editor den Namen dieser Regel von der standardmäßigen **hohen Menge an Inhalten** , die von US-PII erkannt wurden, in **alle mit US-PII erfassten Inhalte** , da diese nun durch alle Vorkommen Ihrer vertraulichen Informationstypen ausgelöst werden. 
    
14. Am unteren Rand des Regel-Editors \> **Speichern**.
    
15. Überprüfen Sie die Bedingungen und Aktionen für \> diese Regel **als nächstes**.
    
    Beachten Sie auf der rechten Seite die **Status** Option für die Regel. Wenn Sie eine gesamte Richtlinie deaktivieren, werden auch alle in der Richtlinie enthaltenen Regeln deaktiviert. Hier können Sie jedoch eine bestimmte Regel deaktivieren, ohne die gesamte Richtlinie zu deaktivieren. Dies kann hilfreich sein, wenn Sie eine Regel untersuchen müssen, die eine große Anzahl falsch positiver Ergebnisse generiert. 
    
16. Lesen und verstehen Sie auf \> **der nächsten Seite**die folgenden Informationen, und wählen Sie dann aus, ob die Regel aktiviert oder zuerst getestet werden soll.
    
     Bevor Sie DLP-Richtlinien erstellen, sollten Sie sie erst einmal nach und nach bereitstellen, um die Auswirkungen beurteilen und ihre Effektivität testen zu können, bevor Sie sie vollständig durchsetzen. Sie möchten beispielsweise nicht, dass eine neue DLP-Richtlinie versehentlich den Zugriff auf Tausende von Dokumenten blockiert, die für Personen erforderlich sind, damit Sie Ihre Arbeit erledigen können. 
    
    Wenn Sie DLP-Richtlinien mit einer großen potenziellen Auswirkung erstellen, wird empfohlen, diese Sequenz zu folgen:
    
17. Beginnen Sie im Testmodus ohne Richtlinientipps, und werten Sie die Auswirkungen dann anhand der DLP-Berichte aus. In den DLP-Berichten werden die Anzahl von Richtlinienübereinstimmungen, der Ort des Vorkommens, der Typ und der Schweregrad aufgeführt. Auf Grundlage der Ergebnisse können Sie die Regeln nach Bedarf genauer anpassen. Im Testmodus haben DLP-Richtlinien keinen Einfluss auf die Produktivität der Mitarbeiter in Ihrer Organisation. 
    
18. Fahren Sie im Testmodus mit Benachrichtigungen und Richtlinientipps fort, sodass Sie die Benutzer über die Einhaltungsrichtlinien in Kenntnis setzen und auf die Anwendung der Regeln vorbereiten können. In dieser Phase können Sie die Benutzer auch bitte, Sie über falsche Positivmeldungen zu benachrichtigen, damit Sie die Regeln noch besser abstimmen können.
    
19. Aktivieren Sie die Richtlinien, damit die Regeln erzwungen werden und der Inhalt geschützt ist. Überwachen Sie weiterhin die DLP-Berichte und alle Schadensberichte oder Benachrichtigungen, um sicherzustellen, dass die von Ihnen gewünschten Ergebnisse erzielt werden. 
    
    ![Optionen für die Verwendung des Testmodus und das Aktivieren der Richtlinie](media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)
  
20. Überprüfen Sie die Einstellungen für \> diese Richtlinie **Create**.
    
Nachdem Sie eine DLP-Richtlinie erstellt und aktiviert haben, wird Sie in allen darin enthaltenen Inhaltsquellen bereitgestellt, beispielsweise SharePoint Online Websites oder OneDrive für Unternehmen Konten, bei denen die Richtlinie automatisch mit der Durchsetzung der Regeln für diese Inhalte beginnt.
  
## <a name="view-the-status-of-a-dlp-policy"></a>Anzeigen des Status einer DLP-Richtlinie

Sie können den Status Ihrer DLP-Richtlinien jederzeit auf der Seite **Richtlinie** im Abschnitt **Verhinderung von Datenverlust** im Security &amp; Compliance Center anzeigen. Hier finden Sie wichtige Informationen, beispielsweise ob eine Richtlinie erfolgreich aktiviert oder deaktiviert wurde oder ob die Richtlinie im Testmodus ausgeführt wird. 
  
Nachfolgend werden die verschiedenen Statuswerte und deren Bedeutung beschrieben.
  
|**Status**|**Erläuterung**|
|:-----|:-----|
|**Aktivieren von...** <br/> |Die Richtlinie wird gerade für die Inhaltsquellen, die sie umfasst, bereitgestellt. Die Richtlinie wird noch nicht bei allen Quellen erzwungen.  <br/> |
|**Testen, mit Benachrichtigungen** <br/> |Die Richtlinie ist im Testmodus. Die Aktionen in einer Regel werden nicht angewendet, aber Richtlinienübereinstimmungen werden mithilfe der DLP-Berichte zusammengestellt und angezeigt. Benachrichtigungen über Richtlinienübereinstimmungen werden an die angegebenen Empfänger gesendet.  <br/> |
|**Testen, ohne Benachrichtigungen** <br/> |Die Richtlinie ist im Testmodus. Die Aktionen in einer Regel werden nicht angewendet, aber Richtlinienübereinstimmungen werden mithilfe der DLP-Berichte zusammengestellt und angezeigt. Benachrichtigungen über Richtlinienübereinstimmungen werden nicht an die angegebenen Empfänger gesendet.  <br/> |
|**On** <br/> |Die Richtlinie ist aktiv und wird erzwungen. Die Richtlinie wurde erfolgreich für alle zugehörigen Inhaltsquellen bereitgestellt.  <br/> |
|**Wird deaktiviert...** <br/> |Die Richtlinie wird gerade aus den Inhaltsquellen, die sie umfasst, entfernt. Die Richtlinie kann noch bei einigen Quellen aktiv sein und erzwungen werden. Das Deaktivieren einer Richtlinie kann bis zu 45 Minuten dauern.  <br/> |
|**Off** <br/> |Die Richtlinie ist nicht aktiv und wird nicht erzwungen. Die Einstellungen für die Richtlinie (Quellen, Schlüsselwörter, Dauer usw.) werden gespeichert.  <br/> |
|**Löschen...** <br/> |Die Richtlinie wird gerade gelöscht. Die Richtlinie ist nicht aktiv und wird nicht erzwungen.  <br/> |
   
## <a name="turn-off-a-dlp-policy"></a>Deaktivieren einer DLP-Richtlinie

Sie können eine DLP-Richtlinie jederzeit bearbeiten oder deaktivieren. Durch das Deaktivieren einer Richtlinie werden alle Regeln in der Richtlinie deaktiviert.
  
Zum Bearbeiten oder Deaktivieren einer DLP-Richtlinie wählen Sie auf der \> Seite \> **Richtlinie** die Richtlinien **Bearbeitungs Richtlinie**aus.
  
![Schaltfläche ' Richtlinie bearbeiten '](media/ce319e92-0519-44fe-9507-45a409eaefe4.png)
  
Darüber hinaus können Sie jede Regel einzeln deaktivieren, indem Sie die Richtlinie bearbeiten und dann den **Status** dieser Regel umschalten, wie oben beschrieben. 
  
## <a name="more-information"></a>Weitere Informationen

- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)
    
- [Senden von Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)
    
- [Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI oder anderen Eigenschaften](protect-documents-that-have-fci-or-other-properties.md)
    
- [Inhalt der DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md)
    
- [Verfügbare Arten von vertraulichen Informationen](what-the-sensitive-information-types-look-for.md)
    

