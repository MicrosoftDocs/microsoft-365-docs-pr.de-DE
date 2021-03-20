---
title: Dokumentfingerabdrücke
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: ITPro
ms.topic: article
search.appverid: MET150
ms.service: exchange-online
ms.collection: M365-security-compliance
localization_priority: Normal
description: Information-Worker in Ihrer Organisation verarbeiten im Lauf eines Arbeitstags viele Arten von vertraulichen Informationen. Dokumentfingerabdrücke erleichtern Ihnen den Schutz dieser Informationen durch Identifikation von Standardformularen, die in Ihrer gesamten Organisation verwendet werden. In diesem Thema werden die Konzepte der Dokumentfingerabdrücke und das Erstellen eines Dokuments mithilfe von PowerShell beschrieben.
ms.openlocfilehash: 1542b956d0a1f662e059ca59ea346a8afc439c83
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918501"
---
# <a name="document-fingerprinting"></a>Dokumentfingerabdrücke

Information-Worker in Ihrer Organisation verarbeiten im Lauf eines Arbeitstags viele Arten von vertraulichen Informationen. Im Security Compliance Center erleichtert Ihnen die Dokumentfingerabdrücke den Schutz dieser Informationen, indem Standardformulare identifiziert werden, die &amp; in Ihrer gesamten Organisation verwendet werden. In diesem Thema werden die Konzepte der Dokumentfingerabdrücke und das Erstellen eines Dokuments mithilfe von PowerShell beschrieben.
  
## <a name="basic-scenario-for-document-fingerprinting"></a>Grundlegendes Szenario für Dokumentfingerabdrücke

Bei der Dokumentfingerabdrücke handelt es sich um ein Feature zur Verhinderung von Datenverlust (Data Loss Prevention, DLP), mit dem ein Standardformular in einen vertraulichen Informationstyp konvertiert wird, den Sie in den Regeln Ihrer DLP-Richtlinien verwenden können. Sie können beispielsweise einen Dokumentfingerabdruck basierend auf einer leeren Patentvorlage erstellen und dann eine DLP-Richtlinie erstellen, die alle ausgehenden Patentvorlagen mit ausgefüllten vertraulichen Inhalten erkennt und blockiert. Optional können Sie Richtlinientipps einrichten, um Absender darüber zu informieren, dass sie möglicherweise vertrauliche Informationen senden, und der Absender sollte überprüfen, ob die Empfänger für den Empfang der Patente qualifiziert sind. [](use-notifications-and-policy-tips.md) Dieser Prozess funktioniert mit allen textbasierten Formularen, die in Ihrer Organisation verwendet werden. Weitere Beispiele für Formulare, die Sie hochladen können, sind:
  
- Regierungsformulare
- HIPAA (Health Insurance Portability and Accountability Act)-kompatible Formulare  
- Formulare mit Mitarbeiterinformationen für die Personalabteilung
- Speziell für Ihre Organisation erstellte benutzerdefinierte Formulare

Ideal wäre es, wenn es in Ihrer Organisation bereits eine etablierte Routine beim Umgang mit der Versendung vertraulicher Informationen gäbe. Nachdem Sie ein leeres Formular hochgeladen haben, das in einen Dokumentfingerabdruck konvertiert werden soll, und eine entsprechende Richtlinie eingerichtet haben, erkennt die DLP alle Dokumente in ausgehenden E-Mails, die mit diesem Fingerabdruck übereinstimmen.

## <a name="how-document-fingerprinting-works"></a>Funktionsweise von Dokumentfingerabdrücken

Wahrscheinlich haben Sie schon erraten, dass sich auf den Dokumenten keine echten Fingerabdrücke befinden - aber der Name erklärt sehr gut die Funktion. Genauso, wie der Fingerabdruck eines Menschen einzigartige Muster hat, haben Dokumente eine einzigartige Wortstruktur. Wenn Sie eine Datei hochladen, identifiziert DLP das eindeutige Wortmuster im Dokument, erstellt einen Dokumentfingerabdruck basierend auf diesem Muster und verwendet diesen Dokumentfingerabdruck, um ausgehende Dokumente zu erkennen, die dasselbe Muster enthalten. Aus diesem Grund werden die effektivsten Dokumentfingerabdrücke durch Hochladen von Formularen oder Vorlagen erstellt. Jede Person, die ein Formular ausfüllt, verwendet denselben Originalsatz von Wörtern und fügt dann ihre eigenen Wörter in das Dokument ein. Solange das ausgehende Dokument nicht kennwortgeschützt ist und den gesamten Text aus dem ursprünglichen Formular enthält, kann DLP bestimmen, ob das Dokument dem Dokumentfingerabdruck entspricht.

> [!IMPORTANT]
> Derzeit kann DLP die Dokumentfingerabdrücke nur als Erkennungsmethode in Exchange online verwenden.

Im folgenden Beispiel wird gezeigt, was passiert, wenn Sie einen Dokumentfingerabdruck auf Grundlage einer Patentvorlage erstellen. Sie können aber auch jedes andere Formular dafür verwenden.
  
### <a name="example-of-a-patent-document-matching-a-document-fingerprint-of-a-patent-template"></a>Beispiel für ein Patentdokument, das zum Fingerabdruck einer Patentvorlage passt

![Document-Fingerprinting-diagram.png](../media/Document-Fingerprinting-diagram.png)
  
Die Patentvorlage enthält die leeren Felder "Patenttitel", "Inventors" und "Beschreibung" sowie Beschreibungen für jedes dieser Felder– das ist das Wortmuster. Wenn Sie die ursprüngliche Patentvorlage hochladen, wird sie in einem der unterstützten Dateitypen und im Nur-Text-Zustand angezeigt. DLP konvertiert dieses Wortmuster in einen Dokumentfingerabdruck, eine kleine #A0 mit einem eindeutigen Hashwert, der den ursprünglichen Text darstellt, und der Fingerabdruck wird als Datenklassifizierung in Active Directory gespeichert. (Als Sicherheitsmaßnahme wird das ursprüngliche Dokument selbst nicht im Dienst gespeichert; nur der Hashwert wird gespeichert, und das ursprüngliche Dokument kann nicht aus dem Hashwert rekonstruiert werden.) Der Patentfingerabdruck wird dann zu einem vertraulichen Informationstyp, den Sie einer DLP-Richtlinie zuordnen können. Nachdem Sie den Fingerabdruck einer DLP-Richtlinie zugeordnet haben, erkennt DLP ausgehende E-Mails, die Dokumente enthalten, die mit dem Patentfingerabdruck übereinstimmen, und behandelt diese gemäß der Richtlinie Ihrer Organisation. 

Sie können beispielsweise eine DLP-Richtlinie einrichten, die verhindert, dass reguläre Mitarbeiter ausgehende Nachrichten senden, die Patente enthalten. DLP verwendet den Patentfingerabdruck, um Patente zu erkennen und diese E-Mails zu blockieren. Alternativ können Sie Ihrer Rechtsabteilung die Möglichkeit geben, Patente an andere Organisationen zu senden, da sie einen geschäftlichen Bedarf dafür hat. Sie können bestimmten Abteilungen das Senden vertraulicher Informationen erlauben, indem Sie Ausnahmen für diese Abteilungen in Ihrer DLP-Richtlinie erstellen, oder Sie können zulassen, dass sie einen Richtlinientipp mit einer geschäftlichen Begründung außer Kraft setzen.
  
### <a name="supported-file-types"></a>Unterstützte Dateitypen

Dokumentfingerabdrücke unterstützen dieselben Dateitypen, die in Nachrichtenflussregeln unterstützt werden (auch als Transportregeln bekannt). Eine Liste der unterstützten Dateitypen finden Sie unter [Supported file types for mail flow rule content inspection](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments#supported-file-types-for-mail-flow-rule-content-inspection). Eine kurze Anmerkung zu Dateitypen: Weder Nachrichtenflussregeln noch Dokumentfingerabdrücke unterstützen den .dotx-Dateityp, was verwirrend sein kann, da es sich um eine Vorlagendatei in Word geht. Der Begriff "Vorlage" in diesem und anderen Themen zum Dokumentfingerabdruck bezieht sich auf ein Dokument, das Sie als Standardformular eingerichtet haben, nicht auf den Dateityp "Vorlage".
  
#### <a name="limitations-of-document-fingerprinting"></a>Einschränkungen der Funktion "Dokumentfingerabdruck"

Dokumentfingerabdrücke erkennen in den folgenden Fällen keine vertraulichen Informationen:
  
- Kennwortgeschützte Dateien
- Dateien, die nur Bilder enthalten
- Dokumente, die nicht den gesamten Text aus dem Originalformular enthalten, aus dem der Dokumentfingerabdruck erstellt wurde

## <a name="use-powershell-to-create-a-classification-rule-package-based-on-document-fingerprinting"></a>Verwenden von PowerShell zum Erstellen eines Klassifizierungsregelpakets auf der Grundlage von Dokumentfingerabdrücken

Beachten Sie, dass Sie derzeit einen Dokumentfingerabdruck nur mithilfe von PowerShell im Security &amp; Compliance Center erstellen können. Informationen zum Herstellen einer Verbindung finden Sie [unter Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).

DLP verwendet Klassifizierungsregelpakete, um vertrauliche Inhalte zu erkennen. Verwenden Sie die **Cmdlets New-DlpFingerprint** und **New-DlpSensitiveInformationType,** um ein Klassifizierungsregelpaket basierend auf einem Dokumentfingerabdruck zu erstellen. Da die Ergebnisse von **New-DlpFingerprint** nicht außerhalb der Datenklassifizierungsregel gespeichert werden, führen Sie **New-DlpFingerprint** und **New-DlpSensitiveInformationType** oder **Set-DlpSensitiveInformationType** immer in derselben PowerShell-Sitzung aus. Im folgenden Beispiel wird ein neuer Dokumentfingerabdruck basierend auf der Datei "C:\Eigene Dateien\Contoso Employee Template.docx" erstellt. Sie speichern den neuen Fingerabdruck als Variable, damit Sie ihn mit dem Cmdlet **New-DlpSensitiveInformationType** in derselben PowerShell-Sitzung verwenden können.
  
```powershell
$Employee_Template = Get-Content "C:\My Documents\Contoso Employee Template.docx" -Encoding byte -ReadCount 0
$Employee_Fingerprint = New-DlpFingerprint -FileData $Employee_Template -Description "Contoso Employee Template"
```

Lassen Sie uns nun eine neue Datenklassifizierungsregel namens "Contoso Employee Confidential" erstellen, die den Dokumentfingerabdruck auf der Datei "C:\Eigene Dateien\Contoso Customer Information Form.docx" verwendet.
  
```powershell
$Customer_Form = Get-Content "C:\My Documents\Contoso Customer Information Form.docx" -Encoding byte -ReadCount 0
$Customer_Fingerprint = New-DlpFingerprint -FileData $Customer_Form -Description "Contoso Customer Information Form"
New-DlpSensitiveInformationType -Name "Contoso Customer Confidential" -Fingerprints $Customer_Fingerprint -Description "Message contains Contoso customer information." 
```

Sie können nun das **Cmdlet Get-DlpSensitiveInformationType** verwenden, um alle DLP-Datenklassifizierungsregelpakete zu finden, und in diesem Beispiel ist "Contoso Customer Confidential" Teil der Datenklassifizierungsregelpaketliste. 
  
Fügen Sie schließlich das Datenklassifizierungsregelpaket "Contoso Customer Confidential" einer DLP-Richtlinie im Security &amp; Compliance Center hinzu. In diesem Beispiel wird einer vorhandenen DLP-Richtlinie mit dem Namen "ConfidentialPolicy" eine Regel hinzufügt.

```powershell
New-DlpComplianceRule -Name "ContosoConfidentialRule" -Policy "ConfidentialPolicy" -ContentContainsSensitiveInformation @{Name="Contoso Customer Confidential"} -BlockAccess $True
```

Sie können das Datenklassifizierungsregelpaket auch in Nachrichtenflussregeln in Exchange Online verwenden, wie im folgenden Beispiel gezeigt. Zum Ausführen dieses Befehls müssen Sie zunächst eine Verbindung [mit Exchange Online PowerShell herstellen.](/powershell/exchange/connect-to-exchange-online-powershell) Beachten Sie außerdem, dass die Synchronisierung des Regelpakets vom Security Compliance Center mit dem &amp; Exchange Admin Center dauert.
  
```powershell
New-TransportRule -Name "Notify :External Recipient Contoso confidential" -NotifySender NotifyOnly -Mode Enforce -SentToScope NotInOrganization -MessageContainsDataClassification @{Name=" Contoso Customer Confidential"}
```

DLP erkennt nun Dokumente, die dem Contoso Customer-Form.docx entsprechen.
  
Informationen zu Syntax und Parametern finden Sie unter:

- [New-DlpFingerprint](/powershell/module/exchange/New-DlpFingerprint)
- [New-DlpSensitiveInformationType](/powershell/module/exchange/New-DlpSensitiveInformationType)
- [Remove-DlpSensitiveInformationType](/powershell/module/exchange/Remove-DlpSensitiveInformationType)
- [Set-DlpSensitiveInformationType](/powershell/module/exchange/Set-DlpSensitiveInformationType)
- [Get-DlpSensitiveInformationType](/powershell/module/exchange/Get-DlpSensitiveInformationType)