---
title: Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI oder anderen Eigenschaften
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.UnifiedDLPRuleContentPropertyContainsWords
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) verwenden, um Dokumente mit Eigenschaften aus einem Drittanbietersystem zu schützen.
ms.openlocfilehash: cf026e447ad1f0da3486a36dd5e36c52c09998cb
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288228"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI oder anderen Eigenschaften

Microsoft 365-Richtlinien zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) können Klassifizierungseigenschaften oder Elementeigenschaften verwenden, um vertrauliche Elemente zu identifizieren. Sie können z. B. folgende Informationen verwenden:

- Eigenschaften der Windows Server File Classification Infrastructure (FCI)
- SharePoint-Dokumenteigenschaften
- Systemdokumenteigenschaften von Drittanbietern

![Diagramm mit Office 365 und externem Klassifizierungssystem](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Beispielsweise kann Ihre Organisation Windows Server FCI verwenden, um Elemente mit personenbezogenen Daten zu identifizieren, z. B. Sozialversicherungsnummern, und dann das Dokument zu klassifizieren, indem die Eigenschaft "Personenbezogene Informationen" auf **"Hoch",** **"Mittel",**  **"Niedrig",**"Öffentlich" oder **"Nicht PII"** basierend auf dem Typ und der Anzahl der vorkommenden personenbezogenen Daten im Dokument festlegen. 

In Microsoft 365 können Sie eine DLP-Richtlinie erstellen, die Dokumente identifiziert, für die diese Eigenschaft auf bestimmte Werte festgelegt ist, z. B. "Hoch" und **"Mittel",** und dann eine Aktion wie das Blockieren des Zugriffs auf diese Dateien ergreifen.  Die gleiche Richtlinie kann eine andere Regel enthalten, die eine andere Aktion ausführt, wenn die Eigenschaft auf **Niedrig** festgelegt ist und z. B. eine E-Mail-Benachrichtigung sendet. Auf diese Weise wird DLP in Windows Server FCI integriert und kann zum Schutz von Office-Dokumenten beitragen, die von Windows Server-basierten Dateiservern hochgeladen oder auf Microsoft 365 freigegeben wurden.

Eine DLP-Richtlinie sucht einfach nach einem bestimmten Eigenschafts-Name-Wert-Paar. Eine beliebige Dokumenteigenschaft kann verwendet werden, solange die Eigenschaft über eine entsprechende verwaltete Eigenschaft für die SharePoint-Suche verfügt. Eine SharePoint-Websitesammlung verwendet z. B. möglicherweise einen Inhaltstyp namens **Reisebericht** mit einem erforderlichen Feld namens **Kunde**. Wenn eine Person einen Reisebericht erstellt, muss sie den Namen des Kunden eingeben. Dieses Eigenschaftennamen-Wert-Paar kann auch in einer DLP-Richtlinie verwendet werden, z. B. wenn  Sie eine Regel wünschen, die den Zugriff auf das Dokument für Gäste blockiert, wenn das Feld "Kunde" **Contoso enthält.**

Wenn Sie Ihre DLP-Richtlinie auf Inhalte mit bestimmten Microsoft 365-Bezeichnungen anwenden möchten, sollten Sie die hier gezeigten Schritte nicht ausführen. Erfahren Sie stattdessen, wie [Sie eine Aufbewahrungsbezeichnung als Bedingung in einer DLP-Richtlinie verwenden.](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy)

## <a name="before-you-create-the-dlp-policy"></a>Bevor Sie die DLP-Richtlinie erstellen

Bevor Sie eine Windows Server FCI-Eigenschaft oder eine andere Eigenschaft in einer DLP-Richtlinie verwenden können, müssen Sie im SharePoint Admin Center eine verwaltete Eigenschaft erstellen. Dies ist der Grund.

Beispiele

> [!NOTE]
> Achten Sie darauf, beim Erstellen von DLP-Regeln, die die Bedingung verwenden, nicht den Namen einer durchforsteten Eigenschaft zu `ContentPropertyContainsWords` verwenden.

Dies ist wichtig, da DLP den Suchcrawler verwendet, um vertrauliche Informationen auf Ihren Websites zu identifizieren und zu klassifizieren und diese vertraulichen Informationen dann in einem sicheren Teil des Suchindex zu speichern. Wenn Sie ein Dokument in Office 365 hochladen, erstellt SharePoint automatisch durchforstete Eigenschaften auf Grundlage der Dokumenteigenschaften. Um aber eine FCI- oder eine andere Eigenschaft in einer DLP-Richtlinie zu verwenden, muss die durchforstete Eigenschaft einer verwalteten Eigenschaft zugeordnet werden, damit Inhalt mit dieser Eigenschaft im Index gespeichert wird.

Weitere Informationen zur Suche und zu verwalteten Eigenschaften finden Sie unter ["Verwalten des Suchschemas in SharePoint Online".](https://go.microsoft.com/fwlink/p/?LinkID=627454)

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Schritt 1: Hochladen eines Dokuments mit der erforderlichen Eigenschaft in Office 365

Sie müssen zuerst ein Dokument mit der Eigenschaft hochladen, auf die Sie in der DLP-Richtlinie verweisen möchten. Microsoft 365 erkennt die Eigenschaft und erstellt automatisch eine durchforstungsbenutzerdefinierte Eigenschaft. Im nächsten Schritt erstellen Sie eine verwaltete Eigenschaft und ordnen die verwaltete Eigenschaft dieser durchforsteten Eigenschaft zu.

### <a name="step-2-create-a-managed-property"></a>Schritt 2: Erstellen einer verwalteten Eigenschaft

1. Melden Sie sich beim Microsoft 365 Admin Center an.

2. Wählen Sie im linken Navigationsbereich Admin **Center** \> **SharePoint aus.** Sie befinden sich jetzt im SharePoint Admin Center.

3. Wählen Sie im linken Navigationsbereich auf **der** \> Suchverwaltungsseite "Suchschema **verwalten"** \> **die Option "Suche" aus.**

   ![Seite "Suchverwaltung" im SharePoint Admin Center](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. Neue **verwaltete Eigenschaft auf** der \> **Seite "Verwaltete Eigenschaften"**

   ![Seite "Verwaltete Eigenschaften" mit hervorgehobener Schaltfläche "Neue verwaltete Eigenschaft"](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Geben Sie einen Namen und eine Beschreibung für die Eigenschaft ein. Dieser Name wird in den DLP-Richtlinien angezeigt.

6. Wählen Sie für **Typ****Text**.

7. Wählen Sie unter **Haupteigenschaften****Abfragbar** und **Abrufbar**.

8. Fügen **Sie unter Zuordnungen zu durchforsteten Eigenschaften** eine Zuordnung \> **hinzu.**

9. Suchen Sie **im** Auswahldialogfeld für durchforste Eigenschaften die durchforstungsrespondierte Eigenschaft, die der Windows Server-FCI-Eigenschaft oder einer anderen Eigenschaft entspricht, die Sie in Ihrer DLP-Richtlinie OK verwenden werden, und wählen Sie \> \> **sie aus.**

   ![Auswahldialogfeld für durchforste Eigenschaften](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. Am unteren Rand der Seite \> **OK**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Erstellen einer DLP-Richtlinie, die eine FCI-Eigenschaft oder eine andere Eigenschaft verwendet

In diesem Beispiel verwendet eine Organisation FCI auf ihren Windows Server-basierten Dateiservern. Insbesondere verwenden sie die FCI-Klassifizierungseigenschaft namens **"Personenbezogene** Informationen" mit den möglichen Werten **"Hoch",** **"Mittel",** **"Niedrig",** **"Öffentlich"** und **"Nicht PII".** Jetzt möchten sie ihre vorhandene FCI-Klassifizierung in ihren DLP-Richtlinien in Office 365 verwenden.

Zunächst führen sie die oben beschriebenen Schritte zum Erstellen einer verwalteten Eigenschaft in SharePoint Online aus, die der durchforsteten Eigenschaft zugeordnet wird, die automatisch aus der FCI-Eigenschaft erstellt wurde.

Als Nächstes erstellen sie eine DLP-Richtlinie mit zwei Regeln, die beide die Bedingung **"Document"-Eigenschaften verwenden, die einen der folgenden Werte enthalten:**

- **FCI PII content - High, Moderate** Die erste Regel schränkt den Zugriff auf  das Dokument ein, wenn die Eigenschaft "Personenbezogene Informationen" der Eigenschaft "Personenbezogene Informationen" **"Hoch"** oder **"Mittel"** entspricht und das Dokument für Personen außerhalb der Organisation freigegeben wird.

- **FCI PII content - Low** Die zweite Regel sendet eine Benachrichtigung an den  Dokumentbesitzer, wenn die Eigenschaft "Personenbezogene Informationen" der Eigenschaft "Personenbezogene Informationen" **"Niedrig"** entspricht und das Dokument für Personen außerhalb der Organisation freigegeben wird.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Erstellen der DLP-Richtlinie mithilfe von PowerShell

Die Eigenschaften **des** Bedingungsdokuments enthalten einen dieser Werte sind vorübergehend nicht auf der Benutzeroberfläche des Security Compliance Center verfügbar, Aber Sie können diese Bedingung weiterhin mithilfe von &amp; PowerShell verwenden. Sie können die Cmdlets verwenden, um mit einer DLP-Richtlinie zu arbeiten, und die Cmdlets mit dem Parameter verwenden, um die Bedingung hinzuzufügen, dass Dokumenteigenschaften einen dieser `New\Set\Get-DlpCompliancePolicy` `New\Set\Get-DlpComplianceRule` Werte `ContentPropertyContainsWords` **enthalten.**

Weitere Informationen zu diesen Cmdlets finden Sie unter [Security &amp; Compliance Center-Cmdlets.](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409)

1. [Herstellen einer Verbindung mit dem Security &amp; Compliance Center mithilfe der Remote-PowerShell](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. Erstellen Sie die Richtlinie mithilfe  `New-DlpCompliancePolicy` von .

Diese PowerShell erstellt eine DLP-Richtlinie, die für alle Speicherorte gilt.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Erstellen Sie die beiden oben beschriebenen Regeln mithilfe von , wobei eine Regel für den Wert "Niedrig" und eine andere für die Werte `New-DlpComplianceRule` **"Hoch"** und **"Mittel"** gilt. 

   Hier ist ein PowerShell-Beispiel, in dem diese beiden Regeln erstellt werden. Die Eigenschaftennamen-Wert-Paare sind in Anführungszeichen eingeschlossen, und ein Eigenschaftsname kann mehrere Werte durch Kommas getrennt ohne Leerzeichen angeben, wie  `"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Windows Server FCI enthält viele integrierte Eigenschaften, einschließlich **personenbezogener Informationen,** die in diesem Beispiel verwendet werden. Die möglichen Werte für jede Eigenschaft können für jede Organisation unterschiedlich sein. Die **hier verwendeten** **Werte "Hoch", "Mittel"** und **"Niedrig"** sind nur ein Beispiel. Für Ihre Organisation können Sie die Windows Server-FCI-Klassifizierungseigenschaften mit ihren möglichen Werten im Datei-Serverressourcen-Manager auf dem Windows Server-basierten Dateiserver anzeigen. Weitere Informationen finden Sie unter [Erstellen einer Klassifizierungseigenschaft.](https://go.microsoft.com/fwlink/p/?LinkID=627456)

Wenn Sie fertig sind, sollte ihre Richtlinie zwei neue Regeln aufweisen, die beide die Dokumenteigenschaften verwenden, **eine dieser Werte enthalten.** Diese Bedingung wird nicht auf der Benutzeroberfläche angezeigt, obwohl die anderen Bedingungen, Aktionen und Einstellungen angezeigt werden.

Eine Regel sperrt den Zugriff auf Inhalte, bei denen die Eigenschaft **Personenbezogene Informationen** den Wert **Hoch** oder **Mittel** aufweist. Eine zweite Regel sendet eine Benachrichtigung über Inhalte, bei denen die Eigenschaft **Personenbezogene Informationen** den Wert **Niedrig** aufweist.

![Dialogfeld "Neue DLP-Richtlinie" mit zwei gerade erstellten Regeln](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Nachdem Sie die DLP-Richtlinie erstellt haben

Wenn Sie die Schritte in den vorherigen Abschnitten ausführen, wird eine DLP-Richtlinie erstellt, mit der Inhalte mit dieser Eigenschaft schnell erkannt werden, jedoch nur, wenn dieser Inhalt neu hochgeladen wird (sodass der Inhalt indiziert wird), oder wenn dieser Inhalt alt ist, aber gerade bearbeitet wurde (sodass der Inhalt neu indiziert wird).

Um überall Inhalte mit dieser Eigenschaft zu ermitteln, sollten Sie manuell anfordern, dass die Bibliothek, Website oder Websitesammlung neu indiziert werden, damit die DLP-Richtlinie alle Inhalte mit dieser Eigenschaft kennt. In SharePoint Online werden Inhalte basierend auf einem definierten Durchforstungszeitplan automatisch durchforstet. Der Crawler ruft Inhalte ab, die seit der letzten Durchforstung geändert wurden, und aktualisiert den Index. Wenn Ihre DLP-Richtlinie Inhalte vor der nächsten geplanten Durchforstung schützen soll, können Sie diese Schritte ausführen.

> [!CAUTION]
> Erneute Indizierung einer Website kann das Suchsystem massiv belasten. Indizieren Sie Ihre Website nur dann neu, wenn dies in Ihrem Szenario unbedingt erforderlich ist.

Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizierens einer Website, Bibliothek oder Liste](https://go.microsoft.com/fwlink/p/?LinkID=627457).

### <a name="reindex-a-site-optional"></a>Neuindizierung einer Website (optional)

1. Wählen Sie auf der Website **"Einstellungen"** (Zahnradsymbol in der oberen rechten Ecke) \> **"Websiteeinstellungen" aus.**

2. Wählen Sie unter Suche die Website  **Suchen und** \> **Offlineverfügbarkeit Neuindex aus.**

## <a name="more-information"></a>Weitere Informationen

- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)

- [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md)

- [Senden von Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)

- [Bestandteile von DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md)

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
