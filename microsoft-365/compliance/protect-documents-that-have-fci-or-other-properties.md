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
description: In diesem Artikel erfahren Sie, wie Sie eine DLP-Richtlinie (Data Loss Prevention) zum Schutz von Dokumenten mit Eigenschaften aus einem Drittanbietersystem verwenden.
ms.openlocfilehash: 38177e9ec813c8eb0c36428d3e9f5b6cb0902861
ms.sourcegitcommit: 50526f81ce3f57d58f0a7c0df4fe21685c5a0236
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45434322"
---
# <a name="create-a-dlp-policy-to-protect-documents-with-fci-or-other-properties"></a>Erstellen einer DLP-Richtlinie zum Schützen von Dokumenten mit FCI oder anderen Eigenschaften

In Microsoft 365 können Sie eine DLP-Richtlinie (Data Loss Prevention) verwenden, um vertrauliche Informationen zu identifizieren, zu überwachen und zu schützen. Viele Organisationen verfügen mithilfe der Klassifikationseigenschaften in Windows Dateiklassifizierungsinfrastruktur (FCI, File Classification Infrastructure), der Dokumenteigenschaften in SharePoint oder Dokumenteigenschaften, die von einem Drittanbietersystem angewendet werden, bereits über einen Prozess zum Identifizieren und Klassifizieren vertraulicher Informationen. Wenn dies Ihre Organisation beschreibt, können Sie eine DLP-Richtlinie erstellen, die die Eigenschaften erkennt, die von Windows Server FCI oder einem anderen System auf Dokumente angewendet wurden, sodass die DLP-Richtlinie in Office-Dokumenten mit bestimmten FCI-oder anderen Eigenschaftswerten erzwungen werden kann.

![Diagramm mit Office 365 und externem Klassifikationssystem](../media/59ad0ac1-4146-4919-abd1-c74d8508d25e.png)

Ihre Organisation verwendet z. B. möglicherweise Windows Server FCI zum Identifizieren von Dokumenten mit personenbezogenen Informationen (PII) wie Sozialversicherungsnummern und zum anschließenden Klassifizieren des Dokuments durch Festlegen der Eigenschaft **Personenbezogene Informationen** auf **Hoch**, **Mittel**, **Niedrig**, **Öffentlich** oder **Keine personenbezogenen Informationen** basierend auf dem Typ und der Anzahl von Vorkommen von personenbezogenen Informationen, die im Dokument gefunden werden. In Microsoft 365 können Sie eine DLP-Richtlinie erstellen, die Dokumente identifiziert, für die diese Eigenschaft auf bestimmte Werte festgelegt ist, beispielsweise **hoch** und **Mittel**, und dann eine Aktion wie das Blockieren des Zugriffs auf diese Dateien ausführt. Die gleiche Richtlinie kann eine andere Regel enthalten, die eine andere Aktion ausführt, wenn die Eigenschaft auf **Niedrig** festgelegt ist und z. B. eine E-Mail-Benachrichtigung sendet. Auf diese Weise kann DLP in die Windows Server-FCI integriert werden und zum Schutz von Office-Dokumenten beitragen, die von Windows Server-basierten Dateiservern auf Microsoft 365 hochgeladen oder freigegeben wurden.

Eine DLP-Richtlinie sucht einfach nach einem bestimmten Eigenschafts-Name-Wert-Paar. Eine beliebige Dokumenteigenschaft kann verwendet werden, solange die Eigenschaft über eine entsprechende verwaltete Eigenschaft für die SharePoint-Suche verfügt. Eine SharePoint-Websitesammlung verwendet z. B. möglicherweise einen Inhaltstyp namens **Reisebericht** mit einem erforderlichen Feld namens **Kunde**. Wenn eine Person einen Reisebericht erstellt, muss sie den Namen des Kunden eingeben. Dieses Eigenschafts-Name-Wert-Paar kann auch in einer DLP-Richtlinie verwendet werden – z. B. wenn Sie eine Regel möchten, die den Zugriff auf das Dokument für externe Benutzer sperrt, wenn das Feld **Kunde****Contoso** enthält.

Beachten Sie, dass Sie die hier beschriebenen Schritte nicht ausführen sollten, wenn Sie Ihre DLP-Richtlinie auf Inhalte mit bestimmten Microsoft 365-Bezeichnungen anwenden möchten. Erfahren Sie stattdessen, wie Sie [eine Aufbewahrungs Bezeichnung als Bedingung in einer DLP-Richtlinie verwenden](data-loss-prevention-policies.md#using-a-retention-label-as-a-condition-in-a-dlp-policy).

## <a name="before-you-create-the-dlp-policy"></a>Bevor Sie die DLP-Richtlinie erstellen

Bevor Sie eine Windows Server FCI-Eigenschaft oder eine andere Eigenschaft in einer DLP-Richtlinie verwenden können, müssen Sie im SharePoint Admin Center eine verwaltete Eigenschaft erstellen. Hier ist der Grund.

Beispiele

Dies ist wichtig, da DLP mithilfe des suchcrawlers vertrauliche Informationen auf ihren Websites identifiziert und klassifiziert und diese vertraulichen Informationen dann in einem sicheren Teil des Suchindex speichert. Wenn Sie ein Dokument in Office 365 hochladen, erstellt SharePoint automatisch durchforstete Eigenschaften auf Grundlage der Dokumenteigenschaften. Um aber eine FCI- oder eine andere Eigenschaft in einer DLP-Richtlinie zu verwenden, muss die durchforstete Eigenschaft einer verwalteten Eigenschaft zugeordnet werden, damit Inhalt mit dieser Eigenschaft im Index gespeichert wird.

Weitere Informationen zu Such-und verwalteten Eigenschaften finden Sie unter [Verwalten des Suchschemas in SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkID=627454).

### <a name="step-1-upload-a-document-with-the-needed-property-to-office-365"></a>Schritt 1: Hochladen eines Dokuments mit der erforderlichen Eigenschaft in Office 365

Sie müssen zuerst ein Dokument mit der Eigenschaft hochladen, auf die Sie in der DLP-Richtlinie verweisen möchten. Microsoft 365 erkennt die Eigenschaft und erstellt automatisch eine durchforstete Eigenschaft daraus. Im nächsten Schritt erstellen Sie eine verwaltete Eigenschaft und ordnen dann die verwaltete Eigenschaft dieser durchforstete Eigenschaft zu.

### <a name="step-2-create-a-managed-property"></a>Schritt 2: Erstellen einer verwalteten Eigenschaft

1. Melden Sie sich beim Microsoft 365 Admin Center an.

2. Wählen Sie im linken Navigationsbereich **Admin Centers** \> **SharePoint**aus. Sie befinden sich jetzt im SharePoint Admin Center.

3. Klicken Sie im linken Navigationsbereich **search** \> auf der Seite **Suchverwaltung** auf Suche verwalten, um das \> **Such Schema zu verwalten**.

   ![Seite "Suchverwaltung" im SharePoint Admin Center](../media/6bcd3aec-d11a-4f8c-9987-8f35da14d80b.png)

4. Klicken Sie auf der Seite **verwaltete Eigenschaften** auf \> **neue verwaltete Eigenschaft**.

   ![Seite "verwaltete Eigenschaften" mit hervorgehobener Schaltfläche "verwaltete Eigenschaft"](../media/b161c764-414c-4037-83ed-503a49fb4410.png)

5. Geben Sie einen Namen und eine Beschreibung für die Eigenschaft ein. Dieser Name wird in den DLP-Richtlinien angezeigt.

6. Wählen Sie für **Typ****Text**.

7. Wählen Sie unter **Haupteigenschaften****Abfragbar** und **Abrufbar**.

8. Fügen Sie unter **Zuordnungen zu durchforstete Eigenschaften** \> **eine Zuordnung hinzu**.

9. Suchen und wählen Sie im Dialogfeld durch **forstete Eigenschaften Auswahl** \> die durchforstete Eigenschaft aus, die der Eigenschaft Windows Server-FCI oder einer anderen Eigenschaft entspricht, die Sie in ihrer DLP-Richtlinie verwenden werden, \> **OK**.

   ![Dialogfeld "durchforstete Eigenschaften Auswahl"](../media/aeda1dce-1342-48bf-9594-a8e4f230e8aa.png)

10. Klicken Sie unten auf der Seite auf \> **OK**.

## <a name="create-a-dlp-policy-that-uses-an-fci-property-or-other-property"></a>Erstellen einer DLP-Richtlinie, die eine FCI-Eigenschaft oder eine andere Eigenschaft verwendet

In diesem Beispiel verwendet eine Organisation FCI auf Ihren Windows Server-basierten Dateiservern; insbesondere verwenden Sie die FCI-Klassifizierungseigenschaft mit dem Namen " **personenbezogene Informationen** " mit möglichen Werten **hoch**, **moderat**, **niedrig**, **öffentlich**und **nicht PII**. Nun möchten Sie Ihre vorhandene FCI-Klassifizierung in ihren DLP-Richtlinien in Office 365 nutzen.

Zunächst führen sie die oben beschriebenen Schritte zum Erstellen einer verwalteten Eigenschaft in SharePoint Online aus, die der durchforsteten Eigenschaft zugeordnet wird, die automatisch aus der FCI-Eigenschaft erstellt wurde.

Als Nächstes erstellen Sie eine DLP-Richtlinie mit zwei Regeln, die beide die Bedingung **Dokumenteigenschaften enthalten einen der folgenden Werte**verwenden:

- **FCI-PII-Inhalte – hoch, moderat** Die erste Regel schränkt den Zugriff auf das Dokument ein, wenn die FCI-Klassifizierungseigenschaft **persönlich identifizierbare Informationen** **hoch** oder **moderat** entspricht und das Dokument für Personen außerhalb der Organisation freigegeben wird.

- **FCI-PII-Inhalte – niedrig** Die zweite Regel sendet eine Benachrichtigung an den Dokumentbesitzer, wenn die FCI-Klassifizierungseigenschaft **persönlich identifizierbare Informationen** **niedrig** ist und das Dokument für Personen außerhalb der Organisation freigegeben wird.

### <a name="create-the-dlp-policy-by-using-powershell"></a>Erstellen der DLP-Richtlinie mithilfe von PowerShell

Beachten Sie, dass die Bedingungs **Dokumenteigenschaften einen dieser Werte enthalten** , die in der Benutzeroberfläche des Security &amp; Compliance Centers vorübergehend nicht verfügbar sind, Sie können diese Bedingung jedoch weiterhin mithilfe von PowerShell verwenden. Sie können die `New\Set\Get-DlpCompliancePolicy` Cmdlets verwenden, um mit einer DLP-Richtlinie zu arbeiten, und die `New\Set\Get-DlpComplianceRule` Cmdlets mit dem Parameter verwenden, `ContentPropertyContainsWords` um die Bedingung **Dokumenteigenschaften enthalten einen dieser Werte**hinzufügen.

Weitere Informationen zu diesen Cmdlets finden Sie unter [Security &amp; Compliance Center-Cmdlets](https://go.microsoft.com/fwlink/?LinkID=799772&amp;clcid=0x409).

1. [Herstellen einer Verbindung mit dem Security &amp; Compliance Center mithilfe von Remote-PowerShell](https://go.microsoft.com/fwlink/?LinkID=799771&amp;clcid=0x409)

2. Erstellen Sie die Richtlinie mithilfe von `New-DlpCompliancePolicy` .

   Hier ist ein PowerShell-Beispiel, das eine DLP-Richtlinie erstellt, die für alle Standorte gilt.

   ```powershell
   New-DlpCompliancePolicy -Name FCI_PII_policy -ExchangeLocation All -SharePointLocation All -OneDriveLocation All -Mode Enable
   ```

3. Erstellen Sie die beiden oben beschriebenen Regeln mithilfe von `New-DlpComplianceRule` , wobei eine Regel für den **niedrigen** Wert steht, und eine andere Regel für die **hohen** und **moderaten** Werte.

   Es folgt ein PowerShell-Beispiel, in dem diese beiden Regeln erstellt werden. Beachten Sie, dass die Eigenschaften Name/Wert-Paare in Anführungszeichen eingeschlossen sind, und ein Eigenschaftsname möglicherweise mehrere Werte durch Kommas ohne Leerzeichengetrennt angibt, wie`"<Property1>:<Value1>,<Value2>","<Property2>:<Value3>,<Value4>"....`

   ```powershell
   New-DlpComplianceRule -Name FCI_PII_content-High,Moderate -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $true -ContentPropertyContainsWords "Personally Identifiable Information:High,Moderate" -Disabled $falseNew-DlpComplianceRule -Name FCI_PII_content-Low -Policy FCI_PII_policy -AccessScope NotInOrganization -BlockAccess $false -ContentPropertyContainsWords "Personally Identifiable Information:Low" -Disabled $false -NotifyUser Owner
   ```

   Beachten Sie, dass Windows Server FCI viele integrierte Eigenschaften enthält, einschließlich **personenbezogener Informationen** , die in diesem Beispiel verwendet werden. Die möglichen Werte für jede Eigenschaft können für jede Organisation unterschiedlich sein. Die hier verwendeten **hohen**, **moderaten**und **niedrigen** Werte sind nur ein Beispiel. Für Ihre Organisation können Sie die Eigenschaften der Windows Server-FCI-Klassifizierung mit ihren möglichen Werten im Ressourcen-Manager für Dateiserver auf dem Windows Server-basierten Dateiserver anzeigen. Weitere Informationen finden Sie unter [Erstellen einer Klassifizierungseigenschaft](https://go.microsoft.com/fwlink/p/?LinkID=627456).

Wenn Sie fertig sind, sollte Ihre Richtlinie zwei neue Regeln haben, in denen beide die **Dokumenteigenschaften mit einer dieser Werte Bedingung enthalten** . Beachten Sie, dass diese Bedingung nicht auf der Benutzeroberfläche angezeigt wird, obwohl die anderen Bedingungen, Aktionen und Einstellungen angezeigt werden.

Eine Regel sperrt den Zugriff auf Inhalte, bei denen die Eigenschaft **Personenbezogene Informationen** den Wert **Hoch** oder **Mittel** aufweist. Eine zweite Regel sendet eine Benachrichtigung über Inhalte, bei denen die Eigenschaft **Personenbezogene Informationen** den Wert **Niedrig** aufweist.

![Dialogfeld "neue DLP-Richtlinie" mit zwei soeben erstellten Regeln](../media/5c56c13b-62a5-4f25-8eb7-ce83a844bb12.png)

## <a name="after-you-create-the-dlp-policy"></a>Nachdem Sie die DLP-Richtlinie erstellt haben

Durch Ausführen der Schritte in den vorherigen Abschnitten wird eine DLP-Richtlinie erstellt, mit der Inhalte schnell mit dieser Eigenschaft erkannt werden, jedoch nur, wenn dieser Inhalt neu hochgeladen wird (damit der Inhalt indiziert ist) oder wenn dieser Inhalt alt, aber nur bearbeitet ist (damit der Inhalt erneut indiziert wird).

Um überall Inhalte mit dieser Eigenschaft zu ermitteln, sollten Sie manuell anfordern, dass die Bibliothek, Website oder Websitesammlung neu indiziert werden, damit die DLP-Richtlinie alle Inhalte mit dieser Eigenschaft kennt. In SharePoint Online werden Inhalte basierend auf einem definierten Durchforstungszeitplan automatisch durchforstet. Der Crawler ruft Inhalte ab, die seit der letzten Durchforstung geändert wurden, und aktualisiert den Index. Wenn Ihre DLP-Richtlinie Inhalte vor der nächsten geplanten Durchforstung schützen soll, können Sie diese Schritte ausführen.

> [!CAUTION]
> Erneute Indizierung einer Website kann das Suchsystem massiv belasten. Indizieren Sie Ihre Website nicht neu, es sei denn, Ihr Szenario erfordert dies unbedingt.

Weitere Informationen finden Sie unter [Manuelles Anfordern des Durchforstens und des erneuten Indizierens einer Website, Bibliothek oder Liste](https://go.microsoft.com/fwlink/p/?LinkID=627457).

### <a name="re-index-a-site-optional"></a>Erneute Indizierung einer Website (optional)

1. Wählen Sie auf der Website **Einstellungen** (Zahnradsymbol in der oberen rechten) \> **Websiteeinstellungen**aus.

2. Wählen Sie unter **Suchen**die Option **Such-und Offline Verfügbarkeits** \> **REINDEX Website**aus.

## <a name="more-information"></a>Weitere Informationen

- [Übersicht über die Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md)

- [Erstellen einer DLP-Richtlinie aus einer Vorlage](create-a-dlp-policy-from-a-template.md)

- [Senden von Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)

- [Bestandteile von DLP-Richtlinienvorlagen](what-the-dlp-policy-templates-include.md)

- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)
