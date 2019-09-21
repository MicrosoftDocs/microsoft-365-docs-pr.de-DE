---
title: Dokumentfingerabdrücke
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Information-Worker in Ihrer Organisation verarbeiten im Lauf eines Arbeitstags viele Arten von vertraulichen Informationen. Dokumentfingerabdrücke erleichtern Ihnen den Schutz dieser Informationen durch Identifikation von Standardformularen, die in Ihrer gesamten Organisation verwendet werden. In diesem Thema werden die Konzepte hinter dem Dokument Fingerabdruck und das Erstellen eines mithilfe von PowerShell beschrieben.
ms.openlocfilehash: 776410ec042e629e32fa6b03a2cb4fe0f2bacd2e
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37070114"
---
# <a name="document-fingerprinting"></a>Dokumentfingerabdrücke

Information-Worker in Ihrer Organisation verarbeiten im Lauf eines Arbeitstags viele Arten von vertraulichen Informationen. Im Security &amp; Compliance Center erleichtert das Dokumentieren von Fingerabdrücken den Schutz dieser Informationen, indem Standardformulare identifiziert werden, die in Ihrer Organisation verwendet werden. In diesem Thema werden die Konzepte hinter dem Dokument Fingerabdruck und das Erstellen eines mithilfe von PowerShell beschrieben.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Grundlegendes Szenario für Dokumentfingerabdrücke

Dokument Fingerabdruck ist eine DLP-Funktion (Data Loss Prevention, Verhinderung von Datenverlust), die ein Standardformular in einen vertraulichen Informationstyp umwandelt, das Sie in den Regeln ihrer DLP-Richtlinien verwenden können. Sie können beispielsweise einen Dokument Fingerabdruck basierend auf einer leeren Patent Vorlage erstellen und anschließend eine DLP-Richtlinie erstellen, mit der alle ausgehenden Patent Vorlagen mit vertraulichen Inhalten erkannt und blockiert werden. Optional können Sie [Richtlinien Tipps](use-notifications-and-policy-tips.md) einrichten, um Absender zu benachrichtigen, dass Sie möglicherweise vertrauliche Informationen senden, und der Absender sollte überprüfen, ob die Empfänger qualifiziert sind, die Patente zu erhalten. Dieser Vorgang funktioniert mit allen textbasierten Formularen, die in Ihrer Organisation verwendet werden. Weitere Beispiele für Formulare, die Sie hochladen können, sind: 
  
- Regierungsformulare
    
- HIPAA (Health Insurance Portability and Accountability Act)-kompatible Formulare
    
- Formulare mit Mitarbeiterinformationen für die Personalabteilung
    
- Speziell für Ihre Organisation erstellte benutzerdefinierte Formulare
    
Ideal wäre es, wenn es in Ihrer Organisation bereits eine etablierte Routine beim Umgang mit der Versendung vertraulicher Informationen gäbe. Nachdem Sie ein leeres Formular hochgeladen haben, um es in einen Fingerabdruck zu konvertieren und eine entsprechende Richtlinie einzurichten, erkennt DLP alle Dokumente in ausgehenden e-Mails, die mit diesem Fingerabdruck übereinstimmen.
  
## <a name="how-document-fingerprinting-works"></a>Funktionsweise von Dokumentfingerabdrücken

Wahrscheinlich haben Sie schon erraten, dass sich auf den Dokumenten keine echten Fingerabdrücke befinden - aber der Name erklärt sehr gut die Funktion. Genauso, wie der Fingerabdruck eines Menschen einzigartige Muster hat, haben Dokumente eine einzigartige Wortstruktur. Wenn Sie eine Datei hochladen, identifiziert DLP das eindeutige Wortmuster im Dokument, erstellt einen Dokument Fingerabdruck basierend auf diesem Muster und verwendet diesen Dokument Fingerabdruck, um ausgehende Dokumente zu erkennen, die dasselbe Muster enthalten. Aus diesem Grund werden die effektivsten Dokumentfingerabdrücke durch Hochladen von Formularen oder Vorlagen erstellt. Jede Person, die ein Formular ausfüllt, verwendet denselben Originalsatz von Wörtern und fügt dann ihre eigenen Wörter in das Dokument ein. Solange das ausgehende Dokument nicht kennwortgeschützt ist und den gesamten Text aus dem ursprünglichen Formular enthält, kann DLP ermitteln, ob das Dokument mit dem Fingerabdruck des Dokuments übereinstimmt.
  
Im folgenden Beispiel wird gezeigt, was passiert, wenn Sie einen Dokumentfingerabdruck auf Grundlage einer Patentvorlage erstellen. Sie können aber auch jedes andere Formular dafür verwenden.
  
**Beispiel für ein Patentdokument, das zum Fingerabdruck einer Patentvorlage passt**

![Document-Fingerprinting-Diagram. png](media/Document-Fingerprinting-diagram.png)
  
Die Patent Vorlage enthält die leeren Felder "Patent Title", "Inventors" und "Description" sowie Beschreibungen für jedes dieser Felder, also das Wortmuster. Wenn Sie die ursprüngliche Patent Vorlage hochladen, befindet Sie sich in einem der unterstützten Dateitypen und im nur-Text-Format. DLP wandelt dieses Wortmuster in einen Fingerabdruck des Dokuments um, bei dem es sich um eine kleine Unicode-XML-Datei mit einem eindeutigen Hashwert handelt, der den ursprünglichen Text darstellt, und der Fingerabdruck wird als Datenklassifizierung in Active Directory gespeichert. (Als Sicherheitsmaßnahme wird das Originaldokument selbst nicht im Dienst gespeichert; es wird nur der Hashwert gespeichert, und das ursprüngliche Dokument kann nicht aus dem Hashwert rekonstruiert werden.) Der Patent Fingerabdruck wird dann zu einem vertraulichen Informationstyp, den Sie einer DLP-Richtlinie zuordnen können. Nachdem Sie den Fingerabdruck einer DLP-Richtlinie zugeordnet haben, erkennt DLP alle ausgehenden e-Mails mit Dokumenten, die dem Patent Fingerabdruck entsprechen, und behandelt diese entsprechend der Richtlinie Ihrer Organisation. 

Sie möchten beispielsweise eine DLP-Richtlinie einrichten, die verhindert, dass reguläre Mitarbeiter ausgehende Nachrichten mit Patenten senden. DLP verwendet den Patent Fingerabdruck zum Erkennen von Patenten und zum Blockieren dieser e-Mails. Alternativ möchten Sie möglicherweise Ihre Rechtsabteilung in die Lage versetzen, Patente an andere Organisationen zu senden, da dies eine geschäftliche Notwendigkeit dafür hat. Sie können zulassen, dass bestimmte Abteilungen vertrauliche Informationen senden, indem Sie Ausnahmen für diese Abteilungen in ihrer DLP-Richtlinie erstellen, oder Sie können zulassen, dass ein richtlinientipp mit einer geschäftlichen Begründung außer Kraft gesetzt wird.
  
### <a name="supported-file-types"></a>Unterstützte Dateitypen

Die Dokument Fingerabdruckunterstützung unterstützt die gleichen Dateitypen, die in Nachrichtenfluss Regeln (auch bekannt als Transportregeln) unterstützt werden. Eine Liste der unterstützten Dateitypen finden Sie unter [Unterstützte Dateitypen für die Inhaltsüberprüfung von Nachrichtenfluss Regeln](https://docs.microsoft.com/en-us/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Ein kurzer Hinweis zu Dateitypen: weder Nachrichtenfluss Regeln noch Dokument Fingerabdruck unterstützen den DOTX-Dateityp, was verwirrend sein kann, da es sich um eine Vorlagendatei in Word handelt. Der Begriff "Vorlage" in diesem und anderen Themen zum Dokumentfingerabdruck bezieht sich auf ein Dokument, das Sie als Standardformular eingerichtet haben, nicht auf den Dateityp "Vorlage".
  
#### <a name="limitations-of-document-fingerprinting"></a>Einschränkungen der Funktion "Dokumentfingerabdruck"

Das Dokumentieren von Fingerabdrücken erkennt in den folgenden Fällen keine vertraulichen Informationen:
  
- Kennwortgeschützte Dateien
    
- Dateien, die nur Bilder enthalten
    
- Dokumente, die nicht den gesamten Text aus dem Originalformular enthalten, aus dem der Dokumentfingerabdruck erstellt wurde
    
## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Verwenden von PowerShell zum Erstellen eines Klassifizierungsregel Pakets basierend auf dem Dokument Fingerabdruck

Beachten Sie, dass Sie derzeit nur mithilfe von PowerShell im Security &amp; Compliance Center einen Dokument Fingerabdruck erstellen können. Informationen zum Herstellen einer Verbindung finden Sie unter [Connect to Security #a0 Compliance Center PowerShell](https://docs.microsoft.com/en-us/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).

DLP verwendet Klassifizierungsregel Pakete, um vertrauliche Inhalte zu erkennen. Zum Erstellen eines Klassifizierungsregel Pakets basierend auf einem Dokument Fingerabdruck verwenden Sie die Cmdlets **New-DlpFingerprint** und **New-DlpSensitiveInformationType** . Da die Ergebnisse von **New-DlpFingerprint** nicht außerhalb der Daten Klassifizierungsregel gespeichert werden, führen Sie immer **New-DlpFingerprint** und **New-DlpSensitiveInformationType** oder **festlegen-DlpSensitiveInformationType** in derselben PowerShell-Sitzung. Im folgenden Beispiel wird ein neuer Dokumentfingerabdruck basierend auf der Datei "C:\Eigene Dateien\Contoso Employee Template.docx" erstellt. Sie speichern den neuen Fingerabdruck als Variable, damit Sie ihn mit dem Cmdlet **New-DlpSensitiveInformationType** in derselben PowerShell-Sitzung verwenden können. 
  
```
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Lassen Sie uns nun eine neue Datenklassifizierungsregel namens "Contoso Employee Confidential" erstellen, die den Dokumentfingerabdruck auf der Datei "C:\Eigene Dateien\Contoso Customer Information Form.docx" verwendet.
  
```
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Sie können jetzt das Cmdlet **Get-DlpSensitiveInformationType** verwenden, um nach allen DLP-Daten Klassifizierungsregel Paketen zu suchen, und in diesem Beispiel ist "Contoso-Kunde vertraulich" Teil der Liste der Daten Klassifizierungsregel Pakete. 
  
Fügen Sie abschließend das Daten Klassifizierungsregel Paket "Contoso Customer Confidential" zu einer DLP-Richtlinie &amp; im Security Compliance Center hinzu. In diesem Beispiel wird einer vorhandenen DLP-Richtlinie mit dem Namen "ConfidentialPolicy" eine Regel hinzugefügt.

```
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

Sie können das Daten Klassifizierungsregel Paket auch in Nachrichtenfluss Regeln in Exchange Online verwenden, wie im folgenden Beispiel dargestellt. Zum Ausführen dieses Befehls müssen Sie zunächst [eine Verbindung mit Exchange Online PowerShell herstellen](https://docs.microsoft.com/en-us/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Beachten Sie auch, dass es Zeit dauert, bis das Regelpaket vom Security &amp; Compliance Center mit dem Exchange Admin Center synchronisiert wird.
  
```
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}

```

DLP erkennt jetzt Dokumente, die dem Fingerabdruck des Dokuments "Contoso Customer Form. docx" entsprechen.
  
Informationen zu Syntax und Parametern finden Sie unter:

- [New-DlpFingerprint](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Remove-DlpSensitiveInformationType)
- [Gruppe-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-dlp/Get-DlpSensitiveInformationType)
