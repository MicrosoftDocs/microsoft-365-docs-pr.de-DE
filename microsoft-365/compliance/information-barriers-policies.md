---
title: Definieren von Richtlinien für Informationsbarrieren
description: Erfahren Sie, wie Sie Richtlinien für Informationsbarrieren in Microsoft Teams definieren.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ce387799a2f9e6d6cdffe063d3adf7310d7e7757
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842722"
---
# <a name="define-information-barrier-policies"></a>Definieren von Richtlinien für Informationsbarrieren

Mit Informationsbarrieren können Sie Richtlinien definieren, die bestimmte Benutzersegmente daran hindern sollen, miteinander zu kommunizieren, oder bestimmten Segmenten die Kommunikation nur mit bestimmten anderen Segmenten gestatten. Richtlinien für Informationsbarrieren können Ihrer Organisation helfen, die Einhaltung relevanter Branchenstandards und -vorschriften aufrechtzuerhalten und potenzielle Interessengruppen zu vermeiden. Weitere Informationen finden Sie unter ["Informationsbarrieren".](information-barriers.md)

In diesem Artikel wird beschrieben, wie Richtlinien für Informationsbarrieren geplant, definiert, implementiert und verwaltet werden. Es sind mehrere Schritte beteiligt, und der Arbeitsablauf ist in mehrere Teile unterteilt. Lesen Sie unbedingt die [Voraussetzungen](#prerequisites) und den gesamten Prozess durch, bevor Sie mit dem Definieren (oder Bearbeiten) von Richtlinien für Informationsbarrieren beginnen.

> [!TIP]
> Dieser Artikel enthält ein [Beispielszenario](#example-contosos-departments-segments-and-policies) und eine [herunterladbare Excel Arbeitsmappe,](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) mit der Sie Ihre Richtlinien für Informationsbarrieren planen und definieren können.

## <a name="concepts-of-information-barrier-policies"></a>Ansätze hinter Richtlinien für Informationsbarrieren

Wenn Sie Richtlinien für Informationsbarrieren definieren, arbeiten Sie mit Benutzerkontoattributen, Segmenten, "Blockieren" und/oder "Zulassen"-Richtlinien und Richtlinienanwendung.

- Benutzerkontoattribute sind in Azure Active Directory (oder Exchange Online) definiert. Diese Attribute können Abteilung, Position, Standort, Teamname und andere Auftragsprofildetails umfassen. 
- Segmente sind Benutzergruppen, die im Security & Compliance Center mithilfe eines ausgewählten **Benutzerkontoattributs** definiert sind. (Siehe auch die [Liste der unterstützten Attribute](information-barriers-attributes.md).)
- Mit Richtlinien für Kommunikationsbarrieren werden bestimmte Kommunikationsbeschränkungen festgelegt. Beim Definieren von Richtlinien für Informationsbarrieren können Sie aus zwei Arten von Richtlinien auswählen:
    - "Blockieren"-Richtlinien verhindern, dass ein Segment mit einem anderen Segment kommuniziert.
    - "Zulassen"-Richtlinien ermöglichen es einem Segment, nur mit bestimmten anderen Segmenten zu kommunizieren.
- Die Richtlinienanwendung erfolgt, nachdem alle Richtlinien für Kommunikationsbarrieren definiert wurden und Sie bereit sind, sie in Ihrer Organisation anzuwenden.

## <a name="the-work-flow-at-a-glance"></a>Der Workflow auf einen Blick

| Phase | Was beteiligt ist |
|:--------|:------------------|
| [Stellen Sie sicher, dass die Voraussetzungen erfüllt sind](#prerequisites) | – Stellen Sie sicher, dass Sie über die [erforderlichen Lizenzen und Berechtigungen verfügen.](information-barriers.md#required-licenses-and-permissions)<br/>– Sicherstellen, dass Ihr Verzeichnis Daten zum Segmentieren von Benutzern enthält<br/>– Aktivieren der bereichsbezogenen Verzeichnissuche für Microsoft Teams<br/>– Sicherstellen, dass die Überwachungsprotokollierung aktiviert ist<br/>– Stellen Sie sicher, dass keine Exchange Adressbuchrichtlinien vorhanden sind<br/>– Verwenden von PowerShell (Beispiele werden bereitgestellt)<br/>– Erteilen der Administratorzustimmung für Microsoft Teams (Schritte sind enthalten) |
| [Teil 1: Segmentieren von Benutzern in Ihrer Organisation](#part-1-segment-users) | – Bestimmen, welche Richtlinien erforderlich sind<br/>– Erstellen einer Liste der zu definierenden Segmente<br/>– Identifizieren, welche Attribute verwendet werden sollen<br/>- Definieren von Segmenten im Hinblick auf Richtlinienfilter |
| [Teil 2: Definieren von Richtlinien für Informationsbarrieren](#part-2-define-information-barrier-policies) | – Definieren Sie Ihre Richtlinien (noch nicht anwendbar)<br/>– Aus zwei Arten auswählen (blockieren oder zulassen) |
| [Teil 3: Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies) | – Festlegen von Richtlinien auf den aktiven Status<br/>– Ausführen der Richtlinienanwendung<br/>- Anzeigen des Richtlinienstatus |
| (Nach Bedarf) [Bearbeiten eines Segments oder einer Richtlinie](information-barriers-edit-segments-policies.md) | - Bearbeiten eines Segments<br/>- Bearbeiten oder Entfernen einer Richtlinie<br/>– Erneutes Ausführen der Richtlinienanwendung<br/>- Anzeigen des Richtlinienstatus |
| (Nach Bedarf) [Problembehandlung](information-barriers-troubleshooting.md)| – Maßnahmen ergreifen, wenn dinge nicht wie erwartet funktionieren|

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie zusätzlich zu den [erforderlichen Lizenzen und Berechtigungen](information-barriers.md#required-licenses-and-permissions)sicher, dass die folgenden Anforderungen erfüllt sind:

- Verzeichnisdaten – Stellen Sie sicher, dass die Struktur Ihrer Organisation in Verzeichnisdaten widergespiegelt wird. Um diese Aktion auszuführen, stellen Sie sicher, dass Benutzerkontoattribute wie Gruppenmitgliedschaft, Abteilungsname usw. in Azure Active Directory (oder Exchange Online) richtig ausgefüllt sind. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
  - [Attribute für Richtlinien für Informationsbarrieren](information-barriers-attributes.md)
  - [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Konfigurieren von Eigenschaften eines Benutzerkontos mit Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)

- Bereichsbezogene Verzeichnissuche: Bevor Sie die erste Richtlinie für Informationsbarrieren In Ihrer Organisation definieren, müssen Sie [die Bereichsverzeichnissuche in Microsoft Teams aktivieren.](/MicrosoftTeams/teams-scoped-directory-search) Warten Sie mindestens 24 Stunden, nachdem Sie die bereichsbezogene Verzeichnissuche aktiviert haben, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren.

- EXO-Lizenz : IB-Richtlinien funktionieren nur, wenn den Zielbenutzern eine EXO-Lizenz zugewiesen wurde.

- Überwachungsprotokollierung – Um den Status einer Richtlinienanwendung nachzuschlagen, muss die Überwachungsprotokollierung aktiviert sein. Es wird empfohlen, die Überwachung zu aktivieren, bevor Sie mit der Definition von Segmenten oder Richtlinien beginnen. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md)

- Keine Adressbuchrichtlinien– Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, stellen Sie sicher, dass keine Exchange Adressbuchrichtlinien vorhanden sind. Informationsbarrieren basieren auf der Adressbuchrichtlinien, aber die beiden Arten von Richtlinien sind nicht kompatibel. Wenn Sie über solche Richtlinien verfügen, stellen Sie sicher, dass [Sie ihre Adressbuchrichtlinien](/exchange/address-books/address-book-policies/remove-an-address-book-policy) zuerst entfernen. Sobald Richtlinien für Informationsbarrieren aktiviert sind und Sie hierarchisches Adressbuch aktiviert haben, wird allen ***Benutzern, die nicht*** in einem Informationsbarrierensegment enthalten sind, das hierarchische [Adressbuch](/exchange/address-books/hierarchical-address-books/hierarchical-address-books) in Exchange Online angezeigt.

- PowerShell – Derzeit werden Richtlinien für Informationsbarrieren im Office 365 Security & Compliance Center mithilfe von PowerShell-Cmdlets definiert und verwaltet. Obwohl in diesem Artikel mehrere Beispiele bereitgestellt werden, müssen Sie mit PowerShell-Cmdlets und -Parametern vertraut sein. Sie benötigen auch das Azure PowerShell Modul.
    - [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)
    - [Installieren des Azure PowerShell Moduls](/powershell/azure/install-az-ps?view=azps-2.3.2)

- Administratorzustimmung für Informationsbarrieren in Microsoft Teams – Wenn Ihre IB-Richtlinien vorhanden sind, können sie Nicht-IB-Compliancebenutzer aus Gruppen entfernen (d. h. Teams Kanäle, die auf Gruppen basieren). Diese Konfiguration trägt dazu bei, dass Ihre Organisation weiterhin richtlinien- und regelkonform ist. Verwenden Sie das folgende Verfahren, um zu ermöglichen, dass Richtlinien für Informationsbarrieren in Microsoft Teams wie erwartet funktionieren.

   1. Voraussetzung: Installieren Sie Azure PowerShell von [Install Azure PowerShell.](/powershell/azure/install-az-ps)

   1. Führen Sie die folgenden PowerShell-Cmdlets aus:

      ```powershell
      Connect-AzAccount -Tenant "<yourtenantdomain.com>"  //for example: Connect-AzAccount -Tenant "Contoso.onmicrosoft.com"
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   1. Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto für Office 365 an.

   1. Überprüfen Sie im Dialogfeld **"Angeforderte Berechtigungen"** die Informationen, und wählen Sie dann **"Annehmen"** aus. Die von der App angeforderten Berechtigungen werden unten angegeben.
      
      > [!div class="mx-imgBorder"]
      > ![image](https://user-images.githubusercontent.com/8932063/107690955-b1772300-6c5f-11eb-9527-4235de860b27.png)


Wenn alle Voraussetzungen erfüllt sind, fahren Sie mit dem nächsten Abschnitt fort.

> [!TIP]
> Um Ihnen bei der Vorbereitung Ihres Plans zu helfen, ist ein Beispielszenario in diesem Artikel enthalten. [Weitere Informationen finden Sie in den Abteilungen, Segmenten und Richtlinien von Contoso.](#example-contosos-departments-segments-and-policies)<p>Darüber hinaus steht eine herunterladbare Excel Arbeitsmappe zur Verfügung, mit der Sie Ihre Segmente und Richtlinien planen und definieren können (und Ihre PowerShell-Cmdlets erstellen). [Rufen Sie die Arbeitsmappe](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx)ab.

## <a name="part-1-segment-users"></a>Teil 1: Segmentbenutzer

In dieser Phase bestimmen Sie, welche Richtlinien für Informationsbarrieren erforderlich sind, erstellen eine Liste der zu definierenden Segmente und definieren dann Ihre Segmente.

### <a name="determine-what-policies-are-needed"></a>Bestimmen, welche Richtlinien erforderlich sind

Wer sind die Gruppen in Ihrer Organisation, die Richtlinien für Informationsbarrieren benötigen, wenn Sie rechtliche und branchenspezifische Vorschriften berücksichtigen? Erstellen sie eine Liste. Gibt es Gruppen, die daran gehindert werden sollten, mit einer anderen Gruppe zu kommunizieren? Gibt es Gruppen, die nur mit einer oder zwei anderen Gruppen kommunizieren dürfen? Denken Sie an die Richtlinien, die Sie benötigen, um zu einer von zwei Gruppen zu gehören:

- "Blockieren"-Richtlinien verhindern, dass eine Gruppe mit einer anderen Gruppe kommuniziert.
- Mit "Zulassen"-Richtlinien kann eine Gruppe nur mit bestimmten anderen, bestimmten Gruppen kommunizieren.

Wenn Sie ihre anfängliche Liste von Gruppen und Richtlinien haben, identifizieren Sie die segmente, die Sie benötigen.

### <a name="identify-segments"></a>Identifizieren von Segmenten

Erstellen Sie zusätzlich zu Ihrer anfänglichen Liste von Richtlinien eine Liste der Segmente für Ihre Organisation. Benutzer, die in Richtlinien für Informationsbarrieren einbezogen werden, sollten zu einem Segment gehören. Planen Sie Ihre Segmente sorgfältig, da sich ein Benutzer nur in einem Segment befinden kann. Auf jedes Segment kann nur eine Richtlinie für Informationsbarrieren angewendet werden.

> [!IMPORTANT]
> Ein Benutzer kann nur in einem Segment sein.

Bestimmen Sie, welche Attribute in den Verzeichnisdaten Ihrer Organisation zum Definieren von Segmenten verwendet werden. Sie können *Abteilung,* *MemberOf* oder eines der unterstützten Attribute verwenden. Stellen Sie sicher, dass in dem Attribut, das Sie für Benutzer auswählen, Werte vorhanden sind. [Informationen zu Informationsbarrieren finden Sie in der Liste der unterstützten Attribute.](information-barriers-attributes.md)

> [!IMPORTANT]
> **Bevor Sie mit dem nächsten Abschnitt fortfahren, stellen Sie sicher, dass Ihre Verzeichnisdaten Werte für Attribute aufweisen, die Sie zum Definieren von Segmenten verwenden können.** Wenn Ihre Verzeichnisdaten keine Werte für die Attribute haben, die Sie verwenden möchten, müssen die Benutzerkonten aktualisiert werden, um diese Informationen einzuschließen, bevor Sie mit Informationsbarrieren fortfahren. Hilfe hierzu finden Sie in den folgenden Ressourcen:<br/>- [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md)<br/>- [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definieren von Segmenten mithilfe von PowerShell

Das Definieren von Segmenten wirkt sich nicht auf Benutzer aus. Sie legt lediglich die Phase fest, in der Richtlinien für Informationsbarrieren definiert und dann angewendet werden.

1. Verwenden Sie das Cmdlet **"New-OrganizationSegment"** mit dem **Parameter "UserGroupFilter",** [der](information-barriers-attributes.md) dem attribut entspricht, das Sie verwenden möchten.

    | Syntax | Beispiel |
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In diesem Beispiel wird ein Segment namens *"HR"* mithilfe von *HR* definiert, einem Wert im *Department-Attribut.* Der **"-eq"-Teil** des Cmdlets bezieht sich auf "gleich". (Alternativ können Sie **"-ne"** verwenden, um "ungleich" zu bedeuten. Siehe [Verwenden von "gleich" und "ungleich" in Segmentdefinitionen.)](#using-equals-and-not-equals-in-segment-definitions) |

    Nachdem Sie die einzelnen Cmdlets ausgeführt haben, sollte eine Liste mit Details zum neuen Segment angezeigt werden. Details umfassen den Typ des Segments, die Person, die es erstellt oder zuletzt geändert hat usw. 

2. Wiederholen Sie diesen Vorgang für jedes Segment, das Sie definieren möchten.

    > [!IMPORTANT]
    > **Stellen Sie sicher, dass ihre Segmente nicht überlappen.** Jeder Benutzer, der von Informationsbarrieren betroffen ist, sollte zu einem (und nur einem) Segment gehören. Kein Benutzer sollte zu zwei oder mehr Segmenten gehören. (Siehe Beispiel: Die von Contoso in diesem Artikel [definierten Segmente.)](#contosos-defined-segments)

Nachdem Sie Ihre Segmente definiert haben, fahren Sie mit der Definition von [Richtlinien für Informationsbarrieren](#part-2-define-information-barrier-policies)fort.

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Verwenden von "gleich" und "ungleich" in Segmentdefinitionen

Im folgenden Beispiel definieren wir ein Segment so, dass "Abteilung gleich HR" ist. 

| Beispiel | Hinweis |
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Beachten Sie, dass in diesem Beispiel die Segmentdefinition einen "equals"-Parameter mit der Bezeichnung **-eq** enthält. |

Sie können Segmente auch mithilfe eines Parameters "not equals" definieren, der wie in der folgenden Tabelle dargestellt als **-ne** gekennzeichnet ist:

| Syntax | Beispiel |
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | In diesem Beispiel haben wir ein Segment namens *"NotSales"* definiert, das alle Personen enthält, die nicht im *Vertrieb sind.* Der Teil **"-ne"** des Cmdlets bezieht sich auf "ungleich". |

Zusätzlich zum Definieren von Segmenten mit "equals" oder "not equals" können Sie ein Segment mit den Parametern "equals" und "not equals" definieren. Sie können auch komplexe Gruppenfilter mit logischen *AND-* und *OR-Operatoren* definieren.

| Syntax | Beispiel |
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | In diesem Beispiel haben wir ein Segment namens *LocalFTE* definiert, das Personen enthält, die sich lokal befinden und deren Positionen nicht als *temporär* aufgeführt sind. |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| In diesem Beispiel haben wir ein Segment namens *"Segment1"* definiert, das Personen enthält, die Mitglieder von group1@contoso.com und nicht Mitglieder von group3@contoso.com sind. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In diesem Beispiel haben wir ein Segment namens *Segment2* definiert, das Personen enthält, die Mitglieder von group2@contoso.com und nicht Mitglieder von group3@contoso.com sind. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| In diesem Beispiel haben wir ein Segment namens *"Segment1and2"* definiert, das Personen von group1@contoso.com und group2@contoso.com und keine Mitglieder von group3@contoso.com enthält. |

> [!TIP]
> Verwenden Sie nach Möglichkeit Segmentdefinitionen, die "-eq" oder "-ne" enthalten. Versuchen Sie nicht, komplexe Segmentdefinitionen zu definieren.

## <a name="part-2-define-information-barrier-policies"></a>Teil 2: Definieren von Richtlinien für Informationsbarrieren

Bestimmen Sie, ob Sie die Kommunikation zwischen bestimmten Segmenten verhindern oder die Kommunikation auf bestimmte Segmente beschränken müssen. Im Idealfall verwenden Sie die Mindestanzahl von Richtlinien, um sicherzustellen, dass Ihre Organisation den gesetzlichen und Branchenanforderungen entspricht.

Wählen Sie mit Ihrer Liste der Benutzersegmente und den Richtlinien für Informationsbarrieren, die Sie definieren möchten, ein Szenario aus, und führen Sie dann die Schritte aus.

- [Szenario 1: Blockieren der Kommunikation zwischen Segmenten](#scenario-1-block-communications-between-segments)
- [Szenario 2: Zulassen, dass ein Segment nur mit einem anderen Segment kommuniziert](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Stellen Sie sicher, dass Sie beim Definieren von Richtlinien einem Segment nicht mehr als eine Richtlinie zuweisen.** Wenn Sie beispielsweise eine Richtlinie für ein Segment namens *"Vertrieb"* definieren, definieren Sie keine zusätzliche Richtlinie für *"Vertrieb".*<p> Stellen Sie außerdem beim Definieren von Richtlinien für Informationsbarrieren sicher, dass diese Richtlinien auf den inaktiven Status festgelegt werden, bis Sie bereit sind, sie anzuwenden. Das Definieren (oder Bearbeiten) von Richtlinien wirkt sich erst dann auf Benutzer aus, wenn diese Richtlinien auf den aktiven Status festgelegt und dann angewendet werden.

(Siehe [Beispiel: Die Richtlinien für Informationsbarrieren](#contosos-information-barrier-policies) von Contoso in diesem Artikel.)

### <a name="scenario-1-block-communications-between-segments"></a>Szenario 1: Blockieren der Kommunikation zwischen Segmenten

Wenn Sie verhindern möchten, dass Segmente miteinander kommunizieren, definieren Sie zwei Richtlinien: eine für jede Richtung. Jede Richtlinie blockiert die Kommunikation nur auf eine Weise.

Angenommen, Sie möchten die Kommunikation zwischen Segment A und Segment B blockieren. In diesem Fall definieren Sie eine Richtlinie, die verhindert, dass Segment A mit Segment B kommuniziert, und definieren dann eine zweite Richtlinie, um zu verhindern, dass Segment B mit Segment A kommuniziert.

1. Verwenden Sie zum Definieren Ihrer ersten Sperrrichtlinie das Cmdlet **"New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsBlocked".**

    | Syntax | Beispiel |
    |:--------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie namens *"Sales-Research"* für ein Segment namens *"Sales"* definiert. Wenn diese Richtlinie aktiv und angewendet wird, verhindert diese Richtlinie, dass Personen im *Vertrieb* mit Personen in einem Segment namens *"Forschung"* kommunizieren. |

2. Verwenden Sie zum Definieren ihres zweiten Blockierungssegments erneut das Cmdlet **"New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsBlocked",** dieses Mal mit umgekehrten Segmenten.

    | Beispiel | Hinweis |
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | In diesem Beispiel haben wir eine Richtlinie namens *"Research-Sales"* definiert, um zu verhindern, dass *Research* mit *dem Vertrieb* kommuniziert. |

3. Fahren Sie mit einer der folgenden Aktionen fort:

   - (Falls erforderlich) [Definieren einer Richtlinie, damit ein Segment nur mit einem anderen Segment kommunizieren kann](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Nachdem alle Richtlinien definiert wurden) [Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Szenario 2: Zulassen, dass ein Segment nur mit einem anderen Segment kommuniziert

1. Damit ein Segment nur mit einem anderen Segment kommunizieren kann, verwenden Sie das Cmdlet **"New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsAllowed".**

    | Syntax | Beispiel |
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie namens *Manufacturing-HR* für ein Segment namens *Manufacturing* definiert. Wenn diese Richtlinie aktiv und angewendet wird, können Personen in *der Fertigung* nur mit Personen in einem Segment namens *HR* kommunizieren. (In diesem Fall kann *die Fertigung* nicht mit Benutzern kommunizieren, die nicht Teil der *Personalabteilung* sind.) |

    **Bei Bedarf können Sie mit diesem Cmdlet mehrere Segmente angeben, wie im folgenden Beispiel gezeigt.**

    | Syntax | Beispiel |
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie definiert, die es dem *Segment Forschung* ermöglicht, nur mit *Personalwesen* und *Fertigung* zu kommunizieren. |

    Wiederholen Sie diesen Schritt für jede Richtlinie, die Sie definieren möchten, damit bestimmte Segmente nur mit bestimmten bestimmten Segmenten kommunizieren können.

2. Fahren Sie mit einer der folgenden Aktionen fort:

   - (Falls erforderlich) [Definieren einer Richtlinie zum Blockieren der Kommunikation zwischen Segmenten](#scenario-1-block-communications-between-segments) 
   - (Nachdem alle Richtlinien definiert wurden) [Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Teil 3: Anwenden von Richtlinien für Informationsbarrieren

Richtlinien für Informationsbarrieren sind erst wirksam, wenn Sie sie auf den aktiven Status festlegen und dann die Richtlinien anwenden.

1. Verwenden Sie das Cmdlet **"Get-InformationBarrierPolicy",** um eine Liste der definierten Richtlinien anzuzeigen. Notieren Sie sich den Status und die Identität (GUID) jeder Richtlinie.

    Syntax: `Get-InformationBarrierPolicy`

2. Um eine Richtlinie auf den aktiven Status festzulegen, verwenden Sie das Cmdlet **"Set-InformationBarrierPolicy"** mit einem **Parameter "Identity"** und den Parameter **"State"** auf **"Active".** 

    | Syntax | Beispiel |
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> In diesem Beispiel legen wir eine Richtlinie für Informationsbarrieren mit der GUID *43c37853-ea10-4b90-a23d-ab8c93772471* auf den aktiven Status fest. |

    Wiederholen Sie diesen Schritt nach Bedarf für jede Richtlinie.

3. Wenn Sie die Richtlinien für Informationsbarrieren auf den aktiven Status festgelegt haben, verwenden Sie das Cmdlet **"Start-InformationBarrierPoliciesApplication"** im Security & Compliance Center.

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Lassen Sie nach der Ausführung `Start-InformationBarrierPoliciesApplication` 30 Minuten zu, bis das System mit dem Anwenden der Richtlinien beginnt. Das System wendet richtlinienbenutzerweise an. Das System verarbeitet ca. 5.000 Benutzerkonten pro Stunde.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Anzeigen des Status von Benutzerkonten, Segmenten, Richtlinien oder Richtlinienanwendungen

Mit PowerShell können Sie den Status von Benutzerkonten, Segmenten, Richtlinien und Richtlinienanwendungen anzeigen, wie in der folgenden Tabelle aufgeführt.

| So zeigen Sie diese Informationen an | Führen Sie diese Aktion aus |
|:---------------|:----------|
| Benutzerkonten | Verwenden Sie das Cmdlet **"Get-InformationBarrierRecipientStatus"** mit Identity-Parametern. <p> Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. <p> Beispiel: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel beziehen wir uns auf zwei Benutzerkonten in Office 365: *meganb* für *Megan* und *Alexw* für *Alex*. <p> (Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Dieses Cmdlet gibt Informationen zu Benutzern zurück, z. B. Attributwerte und angewendete Richtlinien für Informationsbarrieren.|
| Segmente | Verwenden Sie das Cmdlet **"Get-OrganizationSegment".**<p> Syntax: `Get-OrganizationSegment` <p> Dieses Cmdlet zeigt eine Liste aller Segmente an, die für Ihre Organisation definiert sind. |
| Richtlinien für Informationsbarrieren | Verwenden Sie das Cmdlet **"Get-InformationBarrierPolicy".** <p> Syntax: `Get-InformationBarrierPolicy` <p> Dieses Cmdlet zeigt eine Liste der Definierten Richtlinien für Informationsbarrieren und deren Status an. |
| Die neueste Anwendung für Richtlinien für Informationsbarrieren | Verwenden Sie das Cmdlet **"Get-InformationBarrierPoliciesApplicationStatus".** <p> Syntax: `Get-InformationBarrierPoliciesApplicationStatus`<p> Dieses Cmdlet zeigt Informationen dazu an, ob die Richtlinienanwendung abgeschlossen wurde, fehlgeschlagen ist oder in Bearbeitung ist. |
| Alle Richtlinienanwendungen für Informationsbarrieren|`Get-InformationBarrierPoliciesApplicationStatus -All` verwenden<p> Dieses Cmdlet zeigt Informationen dazu an, ob die Richtlinienanwendung abgeschlossen wurde, fehlgeschlagen ist oder in Bearbeitung ist.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Was geschieht, wenn ich Richtlinien entfernen oder ändern muss?

Ressourcen stehen zur Verfügung, um Sie bei der Verwaltung Ihrer Richtlinien für Informationsbarrieren zu unterstützen.

- Wenn bei Informationsbarrieren ein Fehler auftritt, lesen Sie die [Informationen zur Problembehandlung.](information-barriers-troubleshooting.md)
- Informationen zum Beenden der Anwendung von Richtlinien finden Sie unter ["Beenden einer Richtlinienanwendung".](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Informationen zum Entfernen einer Richtlinie für Informationsbarrieren finden Sie unter ["Entfernen einer Richtlinie".](information-barriers-edit-segments-policies.md#remove-a-policy)
- Änderungen an Segmenten oder Richtlinien finden Sie unter [Bearbeiten (oder Entfernen) von Richtlinien für Informationsbarrieren.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>Beispiel: Abteilungen, Segmente und Richtlinien von Contoso

Wenn Sie sehen möchten, wie eine Organisation bei der Definition von Segmenten und Richtlinien vorgehen könnte, sehen Sie sich das folgende Beispiel an.

### <a name="contosos-departments-and-plan"></a>Die Abteilungen und der Plan von Contoso

Contoso verfügt über fünf Abteilungen: Personal, Vertrieb, Marketing, Forschung und Fertigung. Um den Branchenvorschriften zu entsprechen, sollten Die Mitarbeiter in einigen Abteilungen nicht mit anderen Abteilungen kommunizieren, wie in der folgenden Tabelle aufgeführt:

| Segment | Kann sprechen mit | Kann nicht sprechen mit |
|:----------|:--------------|:-----------------|
| Personal | Alle | (keine Beschränkungen) |
| Vertrieb | Personalwesen, Marketing, Fertigung | Forschung |
| Marketing | Alle | (keine Beschränkungen) |
| Forschung | Personalwesen, Marketing, Fertigung | Vertrieb |
| Fertigung | Personalwesen, Marketing | Andere Personen als Personalwesen oder Marketing |

Für diese Struktur umfasst der Plan von Contoso drei Richtlinien für Informationsbarrieren:

1. Eine Richtlinie, die verhindern soll, dass Der Vertrieb mit Forschung kommuniziert (und eine andere Richtlinie, um zu verhindern, dass Forschung mit Dem Vertrieb kommuniziert).

2. Eine Richtlinie, die es der Fertigung erlaubt, nur mit Personal und Marketing zu kommunizieren.

Für dieses Szenario ist es nicht erforderlich, Richtlinien für Personalwesen oder Marketing zu definieren.

### <a name="contosos-defined-segments"></a>Die von Contoso definierten Segmente 

Contoso verwendet das Department-Attribut in Azure Active Directory, um Segmente wie folgt zu definieren:

| Abteilung | Segmentdefinition |
|:-------------|:---------------------|
| Personal | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Vertrieb | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Forschung | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Fertigung | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Nachdem die Segmente definiert sind, fährt Contoso mit der Definition von Richtlinien fort.

### <a name="contosos-information-barrier-policies"></a>Contosos Richtlinien für Informationsbarrieren

Contoso definiert drei Richtlinien, wie in der folgenden Tabelle beschrieben:

| Richtlinie | Richtliniendefinition |
|:---------|:--------------------|
| **Richtlinie 1: Unterbindung der Kommunikation von der Abteilung Vertrieb zur Abteilung Forschung** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In diesem Beispiel heißt die Richtlinie zur Informationsbarriere *Vertrieb-Forschung*. Wenn diese Richtlinie aktiv und angewendet ist, verhindert sie, dass Benutzer im Segment Vertrieb Kommunikation an Benutzer im Segment Forschung richten können. Diese Richtlinie ist eine unidirektionale Richtlinie. sie hindert Forschung nicht daran, mit dem Vertrieb zu kommunizieren. Für diesen Fall ist Richtlinie 2 erforderlich. |
| **Richtlinie 2: Unterbindung der Kommunikation von der Abteilung Forschung zur Abteilung Vertrieb** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In diesem Beispiel heißt die Richtlinie zur Informationsbarriere *Forschung-Vertrieb*. Wenn diese Richtlinie aktiv und angewendet ist, verhindert sie, dass Benutzer im Segment Forschung Kommunikation an Benutzer im Segment Vertrieb richten können. |
| **Richtlinie 3: Zulassen, dass die Fertigung nur mit Personal und Marketing kommuniziert** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> In diesem Fall wird die Richtlinie zur Informationsbarriere als *Fertigung-PersonalMarketing* bezeichnet. Wenn diese Richtlinie aktiv und angewendet ist, kann die Fertigung nur mit Personal und Marketing kommunizieren. Personal und Marketing sind nicht auf die Kommunikation mit anderen Segmenten beschränkt. |

Wenn Segmente und Richtlinien definiert sind, wendet Contoso die Richtlinien an, indem das Cmdlet **"Start-InformationBarrierPoliciesApplication"** ausgeführt wird.

Wenn das Cmdlet abgeschlossen ist, erfüllt Contoso die gesetzlichen und Branchenanforderungen.

## <a name="resources"></a>Ressourcen

- [Übersicht über Informationsbarrieren](information-barriers.md)
- [Weitere Informationen zu Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Weitere Informationen zu Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Weitere Informationen zu Informationsbarrieren in OneDrive](/onedrive/information-barriers)