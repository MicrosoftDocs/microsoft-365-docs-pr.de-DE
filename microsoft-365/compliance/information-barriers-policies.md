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
ms.openlocfilehash: 80123674644b47c76becb92fa08c21f4668614b2
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980057"
---
# <a name="define-information-barrier-policies"></a>Definieren von Richtlinien für Informationsbarrieren

Mit Informationsbarrieren können Sie Richtlinien definieren, die verhindern, dass bestimmte Benutzersegmente miteinander kommunizieren, oder bestimmten Segmenten die Kommunikation nur mit bestimmten anderen Segmenten ermöglichen. Richtlinien für Informationsbarrieren können Ihrer Organisation dabei helfen, die Einhaltung relevanter Branchenstandards und -vorschriften zu gewährleisten und potenzielle Interessenkonflikte zu vermeiden. Weitere Informationen finden Sie unter [Informationsbarrieren.](information-barriers.md)

In diesem Artikel wird beschrieben, wie Richtlinien für Informationsbarrieren geplant, definiert, implementiert und verwaltet werden. Es sind mehrere Schritte erforderlich, und der Arbeitsablauf ist in mehrere Teile unterteilt. Lesen Sie unbedingt die [Voraussetzungen](#prerequisites) und den gesamten Prozess durch, bevor Sie mit dem Definieren (oder Bearbeiten) von Richtlinien für Informationsbarrieren beginnen.

> [!TIP]
> Dieser Artikel enthält ein [Beispielszenario](#example-contosos-departments-segments-and-policies) und eine [herunterladbare](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx) Excel-Arbeitsmappe, mit der Sie Richtlinien für Informationsbarrieren planen und definieren können.

## <a name="concepts-of-information-barrier-policies"></a>Ansätze hinter Richtlinien für Informationsbarrieren

Wenn Sie Richtlinien für Informationsbarrieren definieren, arbeiten Sie mit Benutzerkontoattributen, Segmenten, "Blockieren" und/oder "Zulassen"-Richtlinien und Richtlinienanwendung.

- Benutzerkontoattribute sind in Azure Active Directory (oder Exchange Online) definiert. Diese Attribute können Abteilung, Position, Standort, Teamname und andere Auftragsprofildetails umfassen. 
- Segmente sind Benutzergruppen, die im Security & Compliance Center mithilfe eines ausgewählten **Benutzerkontoattributs definiert sind.** (Siehe auch die [Liste der unterstützten Attribute](information-barriers-attributes.md).)
- Mit Richtlinien für Kommunikationsbarrieren werden bestimmte Kommunikationsbeschränkungen festgelegt. Beim Definieren von Richtlinien für Informationsbarrieren können Sie aus zwei Arten von Richtlinien auswählen:
    - "Blockieren"-Richtlinien verhindern, dass ein Segment mit einem anderen Segment kommuniziert.
    - Mit "Zulassen"-Richtlinien kann ein Segment nur mit bestimmten anderen Segmenten kommunizieren.
- Die Richtlinienanwendung erfolgt, nachdem alle Richtlinien für Kommunikationsbarrieren definiert wurden und Sie bereit sind, sie in Ihrer Organisation anzuwenden.

## <a name="the-work-flow-at-a-glance"></a>Der Workflow auf einen Blick

|**Phase**|**Was beteiligt ist**|
|:--------|:------------------|
| [Sicherstellen, dass die Voraussetzungen erfüllt sind](#prerequisites) | – Stellen Sie sicher, dass Sie über [die erforderlichen Lizenzen und Berechtigungen verfügen](information-barriers.md#required-licenses-and-permissions)<br/>– Stellen Sie sicher, dass Ihr Verzeichnis Daten für die Segmentierung von Benutzern enthält<br/>– Aktivieren der Bereichsverzeichnissuche für Microsoft Teams<br/>– Stellen Sie sicher, dass die Überwachungsprotokollierung aktiviert ist<br/>– Sicherstellen, dass keine Richtlinien für das Exchange-Adressbuch verwendet werden<br/>- Verwenden von PowerShell (Beispiele werden bereitgestellt)<br/>- Bereitstellen der Administrator zustimmung für Microsoft Teams (Schritte sind enthalten) |
| [Teil 1: Segmentieren von Benutzern in Ihrer Organisation](#part-1-segment-users) | – Bestimmen, welche Richtlinien erforderlich sind<br/>– Erstellen einer Liste der zu definierende Segmente<br/>– Identifizieren der zu verwendende Attribute<br/>– Definieren von Segmenten in Bezug auf Richtlinienfilter |
| [Teil 2: Definieren von Richtlinien für Informationsbarrieren](#part-2-define-information-barrier-policies) | – Definieren Sie Ihre Richtlinien (gelten noch nicht)<br/>- Choose from two kinds (block or allow) |
| [Teil 3: Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies) | – Festlegen von Richtlinien auf den aktiven Status<br/>– Ausführen der Richtlinienanwendung<br/>– Anzeigen des Richtlinienstatus |
| (Nach Bedarf) [Bearbeiten eines Segments oder einer Richtlinie](information-barriers-edit-segments-policies.md) | – Bearbeiten eines Segments<br/>– Bearbeiten oder Entfernen einer Richtlinie<br/>– Erneutes Ausführen der Richtlinienanwendung<br/>– Anzeigen des Richtlinienstatus |
| (Nach Bedarf) [Problembehandlung](information-barriers-troubleshooting.md)| – Ergreifen Sie Maßnahmen, wenn die Dinge nicht wie erwartet funktionieren|

## <a name="prerequisites"></a>Voraussetzungen

Stellen Sie zusätzlich zu den [erforderlichen Lizenzen und Berechtigungen](information-barriers.md#required-licenses-and-permissions)sicher, dass die folgenden Anforderungen erfüllt sind:

- Verzeichnisdaten – Stellen Sie sicher, dass die Struktur Ihrer Organisation in Verzeichnisdaten widergespiegelt wird. Um diese Aktion zu ergreifen, stellen Sie sicher, dass Benutzerkontoattribute, z. B. Gruppenmitgliedschaft, Abteilungsname usw., in Azure Active Directory (oder Exchange Online) ordnungsgemäß aufgefüllt werden. Weitere Informationen hierzu finden Sie in den folgenden Ressourcen:
  - [Attribute für Richtlinien für Informationsbarrieren](information-barriers-attributes.md)
  - [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)
  - [Konfigurieren von Eigenschaften eines Benutzerkontos mit Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)

- Bereichsverzeichnissuche : Bevor Sie die erste Richtlinie für Informationsbarrieren in Ihrer Organisation definieren, müssen Sie [die Bereichsverzeichnissuche in Microsoft Teams aktivieren.](https://docs.microsoft.com/MicrosoftTeams/teams-scoped-directory-search) Warten Sie nach dem Aktivieren der Bereichsverzeichnissuche mindestens 24 Stunden, bevor Sie Richtlinien für Informationsbarrieren einrichten oder definieren.

- EXO-Lizenz : RICHTLINIEN für DIE A/A-Richtlinien funktionieren nur, wenn den Zielbenutzern eine EXO-Lizenz zugewiesen wurde.

- Überwachungsprotokollierung: Um den Status einer Richtlinienanwendung nach suchen zu können, muss die Überwachungsprotokollierung aktiviert sein. Es wird empfohlen, die Überwachung zu aktivieren, bevor Sie mit der Definition von Segmenten oder Richtlinien beginnen. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](turn-audit-log-search-on-or-off.md)

- Keine Adressbuchrichtlinien: Bevor Sie Richtlinien für Informationsbarrieren definieren und anwenden, stellen Sie sicher, dass keine Richtlinien für das Exchange-Adressbuch gelten. Informationsbarrieren basieren auf der Adressbuchrichtlinien, aber die beiden Arten von Richtlinien sind nicht kompatibel. Wenn Sie über solche Richtlinien verfügen, müssen Sie zuerst ihre [Adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) entfernen. Sobald Richtlinien für Informationsbarrieren aktiviert sind und Sie ein hierarchisches Adressbuch aktiviert haben, wird allen Benutzern *_*,_* die nicht in einem Segment für Informationsbarrieren enthalten sind, das hierarchische Adressbuch [in](https://docs.microsoft.com/exchange/address-books/hierarchical-address-books/hierarchical-address-books) Exchange Online zu sehen sein.

- PowerShell – Derzeit werden Richtlinien für Informationsbarrieren im Office 365 Security & Compliance Center mithilfe von PowerShell-Cmdlets definiert und verwaltet. Obwohl in diesem Artikel mehrere Beispiele bereitgestellt werden, müssen Sie mit den Cmdlets und Parametern von PowerShell vertraut sein. Sie benötigen auch das Azure PowerShell-Modul.
    - [Herstellen einer Verbindung mit Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)
    - [Installieren des Azure PowerShell-Moduls](https://docs.microsoft.com/powershell/azure/install-az-ps?view=azps-2.3.2)

- Administratorgewilligung für Informationsbarrieren in Microsoft Teams: Wenn Ihre Richtlinien verfügbar sind, können Informationsbarrieren Personen aus Chatsitzungen entfernen, in denen sie sich nicht befinden sollen. Diese Konfiguration trägt dazu bei, dass Ihre Organisation den Richtlinien und Vorschriften entspricht. Verwenden Sie das folgende Verfahren, damit Richtlinien für Informationsbarrieren in Microsoft Teams wie erwartet funktionieren.

   1. Führen Sie die folgenden PowerShell-Cmdlets aus:

      ```powershell
      Connect-AzureAD 
      $appId="bcf62038-e005-436d-b970-2a472f8c1982" 
      $sp=Get-AzADServicePrincipal -ServicePrincipalName $appId
      if ($sp -eq $null) { New-AzADServicePrincipal -ApplicationId $appId }
      Start-Process  "https://login.microsoftonline.com/common/adminconsent?client_id=$appId"
      ```

   2. Wenn Sie dazu aufgefordert werden, melden Sie sich mit Ihrem Geschäfts-, Schul- oder Schulkonto für Office 365 an.

   3. Überprüfen Sie im Dialogfeld _ *Angeforderte* Berechtigungen * die Informationen, und wählen Sie dann **"Akzeptieren" aus.**

Wenn alle Voraussetzungen erfüllt sind, fahren Sie mit dem nächsten Abschnitt fort.

> [!TIP]
> Um Ihnen bei der Vorbereitung Ihres Plans zu helfen, ist ein Beispielszenario in diesem Artikel enthalten. [Weitere Informationen finden Sie in den Abteilungen, Segmenten und Richtlinien von Contoso.](#example-contosos-departments-segments-and-policies)<p>Darüber hinaus steht eine herunterladbare Excel-Arbeitsmappe zur Verfügung, die Sie beim Planen und Definieren Ihrer Segmente und Richtlinien (und beim Erstellen Ihrer PowerShell-Cmdlets) unterstützt. [Die Arbeitsmappe erhalten](https://github.com/MicrosoftDocs/OfficeDocs-O365SecComp/raw/public/SecurityCompliance/media/InfoBarriers-PowerShellGenerator.xlsx).

## <a name="part-1-segment-users"></a>Teil 1: Segmentieren von Benutzern

In dieser Phase bestimmen Sie, welche Richtlinien für Informationsbarrieren erforderlich sind, erstellen eine Liste der zu definierende Segmente und definieren dann Ihre Segmente.

### <a name="determine-what-policies-are-needed"></a>Bestimmen, welche Richtlinien erforderlich sind

Wer sind die Gruppen in Ihrer Organisation, die Richtlinien für Informationsbarrieren benötigen, wenn rechtliche und branchen rechtliche Vorschriften in Betracht ziehen? Erstellen sie eine Liste. Gibt es Gruppen, die an der Kommunikation mit einer anderen Gruppe gehindert werden sollten? Gibt es Gruppen, die nur mit einer oder zwei anderen Gruppen kommunizieren dürfen? Denken Sie an die Richtlinien, die Sie als Zugehörigkeit zu einer von zwei Gruppen benötigen:

- "Blockieren"-Richtlinien verhindern, dass eine Gruppe mit einer anderen Gruppe kommuniziert.
- Mit "Zulassen"-Richtlinien kann eine Gruppe nur mit bestimmten anderen, bestimmten Gruppen kommunizieren.

Wenn Sie ihre anfängliche Liste von Gruppen und Richtlinien haben, identifizieren Sie die benötigten Segmente.

### <a name="identify-segments"></a>Identifizieren von Segmenten

Erstellen Sie zusätzlich zur ursprünglichen Liste der Richtlinien eine Liste der Segmente für Ihre Organisation. Benutzer, die in Richtlinien für Informationsbarrieren einbezogen werden, sollten zu einem Segment gehören. Planen Sie Ihre Segmente sorgfältig, da ein Benutzer nur in einem Segment enthalten sein kann. Auf jedes Segment kann nur eine Richtlinie für Informationsbarrieren angewendet werden.

> [!IMPORTANT]
> Ein Benutzer kann nur in einem Segment sein.

Bestimmen Sie, welche Attribute in den Verzeichnisdaten Ihrer Organisation Zum Definieren von Segmenten verwendet werden. Sie können *Department*, *MemberOf* oder eines der unterstützten Attribute verwenden. Stellen Sie sicher, dass das attribut, das Sie für Benutzer auswählen, Werte enthält. [Weitere Informationen finden Sie in der Liste der unterstützten Attribute für Informationsbarrieren.](information-barriers-attributes.md)

> [!IMPORTANT]
> Bevor Sie mit dem nächsten Abschnitt fortfahren, stellen Sie sicher, dass Ihre Verzeichnisdaten Werte für Attribute aufweisen, die Sie zum Definieren von **Segmenten verwenden können.** Wenn Ihre Verzeichnisdaten keine Werte für die attribute aufweisen, die Sie verwenden möchten, müssen die Benutzerkonten aktualisiert werden, damit sie diese Informationen enthalten, bevor Sie mit Informationsbarrieren fortfahren. Hilfe dazu finden Sie in den folgenden Ressourcen:<br/>- [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

### <a name="define-segments-using-powershell"></a>Definieren von Segmenten mithilfe von PowerShell

Das Definieren von Segmenten wirkt sich nicht auf Benutzer aus. Sie legt lediglich die Phase fest, in der Richtlinien für Informationsbarrieren definiert und dann angewendet werden.

1. Verwenden Sie **das Cmdlet "New-OrganizationSegment"** mit dem **Parameter "UserGroupFilter",** der dem attribut [entspricht,](information-barriers-attributes.md) das Sie verwenden möchten.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `New-OrganizationSegment -Name "segmentname" -UserGroupFilter "attribute -eq 'attributevalue'"` |`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` <p>In diesem Beispiel wird ein Segment mit dem Namen *"HR"* mithilfe von *HR* definiert, einem Wert im *Attribut "Department".* Der **Teil "-eq"** des Cmdlets bezieht sich auf "gleich". (Alternativ können Sie **"-ne"** verwenden, um "nicht gleich" zu bedeuten. Siehe [Verwenden von "gleich" und "nicht gleich" in Segmentdefinitionen.)](#using-equals-and-not-equals-in-segment-definitions) |

    Nachdem Sie die einzelnen Cmdlets ausgeführt haben, sollte eine Liste mit Details zum neuen Segment angezeigt werden. Zu den Details gehören der Typ des Segments, wer ihn erstellt oder zuletzt geändert hat, und so weiter. 

2. Wiederholen Sie diesen Vorgang für jedes Segment, das Sie definieren möchten.

    > [!IMPORTANT]
    > **Stellen Sie sicher, dass die Segmente nicht überlappen.** Jeder Benutzer, der von Informationsbarrieren betroffen ist, sollte zu einem (und nur einem) Segment gehören. Kein Benutzer sollte zu zwei oder mehr Segmenten gehören. (Siehe [Beispiel: Contosos definierte Segmente](#contosos-defined-segments) in diesem Artikel.)

Nachdem Sie Ihre Segmente definiert haben, fahren Sie mit der [Definition von Richtlinien für Informationsbarrieren fort.](#part-2-define-information-barrier-policies)

### <a name="using-equals-and-not-equals-in-segment-definitions"></a>Verwenden von "gleich" und "nicht gleich" in Segmentdefinitionen

Im folgenden Beispiel definieren wir ein Segment so, dass "Abteilung gleich Personal" ist. 

|**Beispiel**|**Hinweis**|
|:----------|:-------|
|`New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` | Beachten Sie, dass die Segmentdefinition in diesem Beispiel einen "equals"-Parameter enthält, der als **-eq bezeichnet wird.** |

Sie können Segmente auch mithilfe eines Parameters "not equals" definieren, der als **-ne** bezeichnet wird, wie in der folgenden Tabelle dargestellt:

|**Syntax**|**Beispiel**|
|:---------|:----------|
| `New-OrganizationSegment -Name "NotSales" -UserGroupFilter "Department -ne 'Sales'"` | In diesem Beispiel haben wir ein Segment mit dem Namen *"NotSales"* definiert, das alle Personen enthält, die nicht in *Sales enthalten sind.* Der **-ne-Teil** des Cmdlets bezieht sich auf "nicht gleich". |

Zusätzlich zum Definieren von Segmenten mit "gleich" oder "nicht gleich" können Sie ein Segment mit den Parametern "equals" und "not equals" definieren. Sie können auch komplexe Gruppenfilter mit logischen *AND-* und *OR-Operatoren* definieren.

|**Syntax**|**Beispiel**|
|:---------|:----------|
| `New-OrganizationSegment -Name "LocalFTE" -UserGroupFilter "Location -eq 'Local'" -and "Position -ne 'Temporary'"` | In diesem Beispiel haben wir ein Segment mit dem Namen *LocalFTE* definiert, das Personen enthält, die sich lokal befinden und deren Positionen nicht als Temporär *aufgeführt sind.* |
| `New-OrganizationSegment -Name "Segment1" -UserGroupFilter "MemberOf -eq 'group1@contoso.com'' -and MemberOf -ne 'group3@contoso.com'"`| In diesem Beispiel haben wir ein Segment namens *"Segment1"* definiert, das Personen enthält, die Mitglieder von group1@contoso.com und keine Mitglieder der group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment2" -UserGroupFilter "MemberOf -eq 'group2@contoso.com' -or MemberOf -ne 'group3@contoso.com'"` | In diesem Beispiel haben wir ein Segment namens *"Segment2"* definiert, das Personen enthält, die Mitglieder von group2@contoso.com und keine Mitglieder der group3@contoso.com. |
| `New-OrganizationSegment -Name "Segment1and2" -UserGroupFilter "(MemberOf -eq 'group1@contoso.com' -or MemberOf -eq 'group2@contoso.com') -and MemberOf -ne 'group3@contoso.com'"`| In diesem Beispiel haben wir ein Segment namens *"Segment1and2"* definiert, das Personenmitglieder von group1@contoso.com und group2@contoso.com und keine Mitglieder von group3@contoso.com. |

> [!TIP]
> Verwenden Sie nach Möglichkeit Segmentdefinitionen, die "-eq" oder "-ne" enthalten. Versuchen Sie nicht, komplexe Segmentdefinitionen zu definieren.

## <a name="part-2-define-information-barrier-policies"></a>Teil 2: Definieren von Richtlinien für Informationsbarrieren

Bestimmen Sie, ob Sie die Kommunikation zwischen bestimmten Segmenten verhindern oder die Kommunikation auf bestimmte Segmente beschränken müssen. Im Idealfall verwenden Sie die Mindestanzahl von Richtlinien, um sicherzustellen, dass Ihre Organisation rechtliche und branchenkonforme Anforderungen erfüllt.

Wählen Sie mit der Liste der Benutzersegmente und den Richtlinien für Informationsbarrieren, die Sie definieren möchten, ein Szenario aus, und führen Sie dann die Schritte aus.

- [Szenario 1: Blockieren der Kommunikation zwischen Segmenten](#scenario-1-block-communications-between-segments)
- [Szenario 2: Zulassen, dass ein Segment nur mit einem anderen Segment kommuniziert](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment)

> [!IMPORTANT]
> **Stellen Sie sicher, dass** Sie beim Definieren von Richtlinien einem Segment nicht mehr als eine Richtlinie zuweisen. Wenn Sie beispielsweise eine Richtlinie für ein Segment namens *"Sales"* definieren, definieren Sie keine zusätzliche Richtlinie für *"Sales".*<p> Stellen Sie außerdem beim Definieren von Richtlinien für Informationsbarrieren sicher, dass diese Richtlinien auf den inaktiven Status festgelegt werden, bis Sie bereit sind, sie anzuwenden. Das Definieren (oder Bearbeiten) von Richtlinien wirkt sich erst auf Benutzer aus, wenn diese Richtlinien auf den aktiven Status festgelegt und dann angewendet werden.

(Siehe [Beispiel: Contosos Richtlinien für Informationsbarrieren](#contosos-information-barrier-policies) in diesem Artikel.)

### <a name="scenario-1-block-communications-between-segments"></a>Szenario 1: Blockieren der Kommunikation zwischen Segmenten

Wenn Sie die Kommunikation zwischen Segmenten blockieren möchten, definieren Sie zwei Richtlinien: eine für jede Richtung. Jede Richtlinie blockiert die Kommunikation nur in eine Andere.

Angenommen, Sie möchten die Kommunikation zwischen Segment A und Segment B blockieren. In diesem Fall definieren Sie eine Richtlinie, die verhindert, dass Segment A mit Segment B kommuniziert, und definieren dann eine zweite Richtlinie, um zu verhindern, dass Segment B mit Segment A kommuniziert.

1. Verwenden Sie zum Definieren der ersten Blockierungsrichtlinie das **Cmdlet "New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsBlocked".**

    |**Syntax** | **Beispiel**| |**--------|:----------| |`New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsBlocked "segment2name"` | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie namens *"Sales-Research"* für ein Segment namens *"Sales" definiert.* Wenn diese Richtlinie aktiv und angewendet wird, hindert sie Personen *im* Vertrieb an der Kommunikation mit Personen in einem Segment namens *"Research".* |

2. Um Das zweite blockierende Segment zu definieren, verwenden Sie erneut das **Cmdlet "New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsBlocked",** dieses Mal mit umgekehrten Segmenten.

    |**Beispiel**|**Hinweis**|
    |:----------|:-------|
    |`New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` | In diesem Beispiel haben wir eine Richtlinie namens *"Research-Sales"* definiert, um zu verhindern, dass *Research* mit Sales *kommuniziert.* |

3. Fahren Sie mit einer der folgenden Aktionen fort:

   - (Falls erforderlich) [Definieren einer Richtlinie, damit ein Segment nur mit einem anderen Segment kommunizieren kann](#scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment) 
   - (Nachdem alle Richtlinien definiert wurden) [Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies)

### <a name="scenario-2-allow-a-segment-to-communicate-only-with-one-other-segment"></a>Szenario 2: Zulassen, dass ein Segment nur mit einem anderen Segment kommuniziert

1. Damit ein Segment nur mit einem anderen Segment kommunizieren kann, verwenden Sie das **Cmdlet "New-InformationBarrierPolicy"** mit dem Parameter **"SegmentsAllowed".**

    |**Syntax**|**Beispiel**|
    |:----------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name","segment1name"` | `New-InformationBarrierPolicy -Name "Manufacturing-HR" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Manufacturing" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie namens *Manufacturing-HR* für ein Segment namens *Manufacturing definiert.* Wenn diese Richtlinie aktiv ist und angewendet wird, können Personen in *der* Fertigung nur mit Personen in einem Segment namens *PERSONAL kommunizieren.* (In diesem Fall kann *die Fertigung* nicht mit Benutzern kommunizieren, die nicht Teil der *Personalabteilung sind.)* |

    **Bei Bedarf können Sie mit diesem Cmdlet mehrere Segmente angeben, wie im folgenden Beispiel dargestellt.**

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `New-InformationBarrierPolicy -Name "policyname" -AssignedSegment "segment1name" -SegmentsAllowed "segment2name", "segment3name","segment1name"` | `New-InformationBarrierPolicy -Name "Research-HRManufacturing" -AssignedSegment "Research" -SegmentsAllowed "HR","Manufacturing","Research" -State Inactive` <p> In diesem Beispiel haben wir eine Richtlinie definiert, die es dem Segment *"Research"* ermöglicht, nur mit *Personal* und Fertigung zu *kommunizieren.* |

    Wiederholen Sie diesen Schritt für jede Richtlinie, die Sie definieren möchten, damit bestimmte Segmente nur mit bestimmten bestimmten Segmenten kommunizieren können.

2. Fahren Sie mit einer der folgenden Aktionen fort:

   - (Falls erforderlich) [Definieren einer Richtlinie zum Blockieren der Kommunikation zwischen Segmenten](#scenario-1-block-communications-between-segments) 
   - (Nachdem alle Richtlinien definiert wurden) [Anwenden von Richtlinien für Informationsbarrieren](#part-3-apply-information-barrier-policies)

## <a name="part-3-apply-information-barrier-policies"></a>Teil 3: Anwenden von Richtlinien für Informationsbarrieren

Richtlinien für Informationsbarrieren werden erst wirksam, wenn Sie sie auf den aktiven Status festlegen und dann die Richtlinien anwenden.

1. Verwenden Sie **das Cmdlet "Get-InformationBarrierPolicy",** um eine Liste der definierten Richtlinien zu erhalten. Notieren Sie sich den Status und die Identität (GUID) jeder Richtlinie.

    Syntax: `Get-InformationBarrierPolicy`

2. Um eine Richtlinie auf den aktiven Status zu setzen, verwenden Sie das **Cmdlet "Set-InformationBarrierPolicy"** mit einem Parameter **"Identity"** und den Parameter **"State"** auf **"Active".** 

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Active` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -State Active` <p> In diesem Beispiel legen wir eine Richtlinie für Informationsbarrieren mit der GUID *43c37853-ea10-4b90-a23d-ab8c93772471* auf den aktiven Status fest. |

    Wiederholen Sie diesen Schritt je nach Richtlinie.

3. Wenn Sie die Richtlinien für Informationsbarrieren auf den aktiven Status festlegen, verwenden Sie das Cmdlet **"Start-InformationBarrierPoliciesApplication"** im Security & Compliance Center.

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Nachdem Sie die Ausführung `Start-InformationBarrierPoliciesApplication` ausgeführt haben, lassen Sie 30 Minuten, bis das System mit der Anwendung der Richtlinien beginnt. Das System wendet Benutzerrichtlinien nach Benutzer an. Das System verarbeitet ca. 5.000 Benutzerkonten pro Stunde.

## <a name="view-status-of-user-accounts-segments-policies-or-policy-application"></a>Anzeigen des Status von Benutzerkonten, Segmenten, Richtlinien oder Richtlinienanwendung

Mit PowerShell können Sie den Status von Benutzerkonten, Segmenten, Richtlinien und Richtlinien anzeigen, wie in der folgenden Tabelle aufgeführt.

|**So zeigen Sie diese Informationen an**|**Diese Aktion**|
|:---------------|:----------|
| Benutzerkonten | Verwenden Sie **das Cmdlet "Get-InformationBarrierRecipientStatus"** mit Identitätsparametern. <p> Syntax: `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. <p> Beispiel: `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel beziehen wir uns auf zwei Benutzerkonten in Office 365: *Meganb* für *Megan* und *alexw* für *Alex*. <p> (Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>` ) <p> Dieses Cmdlet gibt Informationen zu Benutzern zurück, z. B. Attributwerte und richtlinien für Informationsbarrieren, die angewendet werden.|
| Segmente | Verwenden Sie **das Cmdlet "Get-OrganizationSegment".**<p> Syntax: `Get-OrganizationSegment` <p> Dieses Cmdlet zeigt eine Liste aller Segmente an, die für Ihre Organisation definiert sind. |
| Richtlinien für Informationsbarrieren | Verwenden Sie **das Cmdlet "Get-InformationBarrierPolicy".** <p> Syntax: `Get-InformationBarrierPolicy` <p> Dieses Cmdlet zeigt eine Liste der definierten Richtlinien für Informationsbarrieren und deren Status an. |
| Die neueste Richtlinienanwendung für Informationsbarrieren | Verwenden Sie **das Cmdlet "Get-InformationBarrierPoliciesApplicationStatus".** <p> Syntax: `Get-InformationBarrierPoliciesApplicationStatus`<p> Dieses Cmdlet zeigt Informationen darüber an, ob die Richtlinienanwendung abgeschlossen wurde, fehlgeschlagen ist oder ausgeführt wird. |
| Alle Richtlinienanwendungen für Informationsbarrieren|`Get-InformationBarrierPoliciesApplicationStatus -All` verwenden<p> Dieses Cmdlet zeigt Informationen darüber an, ob die Richtlinienanwendung abgeschlossen wurde, fehlgeschlagen ist oder ausgeführt wird.|

<!-- IN the " The most recent information barrier policy application, add link to troubleshooting topic -->

## <a name="what-if-i-need-to-remove-or-change-policies"></a>Was passiert, wenn ich Richtlinien entfernen oder ändern muss?

Es stehen Ressourcen zur Verfügung, mit deren Hilfe Sie Ihre Richtlinien für Informationsbarrieren verwalten können.

- Wenn bei Informationsbarrieren etwas schief geht, finden Sie [weitere Informationen unter Problembehandlung bei Informationsbarrieren.](information-barriers-troubleshooting.md)
- Informationen zum Anhalten der Anwendung von Richtlinien finden Sie [unter "Beenden einer Richtlinienanwendung".](information-barriers-edit-segments-policies.md#stop-a-policy-application)
- Informationen zum Entfernen einer Richtlinie für Informationsbarrieren finden Sie unter ["Entfernen einer Richtlinie".](information-barriers-edit-segments-policies.md#remove-a-policy)
- Informationen zum Vornehmen von Änderungen an Segmenten oder Richtlinien finden Sie unter [Bearbeiten (oder Entfernen) von Richtlinien für Informationsbarrieren.](information-barriers-edit-segments-policies.md)

## <a name="example-contosos-departments-segments-and-policies"></a>Beispiel: Abteilungen, Segmente und Richtlinien von Contoso

Wenn Sie sehen möchten, wie eine Organisation bei der Definition von Segmenten und Richtlinien vorgehen könnte, sehen Sie sich das folgende Beispiel an.

### <a name="contosos-departments-and-plan"></a>Die Abteilungen und der Plan von Contoso

Contoso verfügt über fünf Abteilungen: Personal, Vertrieb, Marketing, Forschung und Fertigung. Um branchenkonforme Vorschriften einzuhalten, sollten Mitarbeiter in einigen Abteilungen nicht mit anderen Abteilungen kommunizieren, wie in der folgenden Tabelle aufgeführt:

|**Segment**|**Kann sprechen mit**|**Kann nicht sprechen mit**|
|:----------|:--------------|:-----------------|
| HR | Alle | (keine Beschränkungen) |
| Vertrieb | PERSONAL, Marketing, Fertigung | Forschung |
| Marketing | Alle | (keine Beschränkungen) |
| Forschung | PERSONAL, Marketing, Fertigung | Vertrieb |
| Fertigung | HR, Marketing | Andere Personen als Personalwesen oder Marketing |

Für diese Struktur umfasst contosos Plan drei Richtlinien für Informationsbarrieren:

1. Eine Richtlinie, mit der verhindert werden soll, dass der Vertrieb mit der Forschung kommuniziert (und eine weitere Richtlinie, um zu verhindern, dass Die Forschung mit dem Vertrieb kommuniziert).
2. Eine Richtlinie, die der Fertigung die Kommunikation nur mit Personal und Marketing erlaubt.

In diesem Szenario ist es nicht erforderlich, Richtlinien für Personalwesen oder Marketing zu definieren.

### <a name="contosos-defined-segments"></a>Die von Contoso definierten Segmente 

Contoso verwendet das Attribut "Department" in Azure Active Directory, um Segmente wie folgt zu definieren:

|**Department**|**Segmentdefinition**|
|:-------------|:---------------------|
| Personal | `New-OrganizationSegment -Name "HR" -UserGroupFilter "Department -eq 'HR'"` |
| Vertrieb | `New-OrganizationSegment -Name "Sales" -UserGroupFilter "Department -eq 'Sales'"` |
| Marketing | `New-OrganizationSegment -Name "Marketing" -UserGroupFilter "Department -eq 'Marketing'"` |
| Forschung | `New-OrganizationSegment -Name "Research" -UserGroupFilter "Department -eq 'Research'"` |
| Fertigung | `New-OrganizationSegment -Name "Manufacturing" -UserGroupFilter "Department -eq 'Manufacturing'"` |

Nachdem die Segmente definiert sind, fährt Contoso mit der Definition von Richtlinien fort.

### <a name="contosos-information-barrier-policies"></a>Contosos Richtlinien für Informationsbarrieren

Contoso definiert drei Richtlinien, wie in der folgenden Tabelle beschrieben:

|**Policy**|**Richtliniendefinition**|
|:---------|:--------------------|
| **Richtlinie 1: Unterbindung der Kommunikation von der Abteilung Vertrieb zur Abteilung Forschung** | `New-InformationBarrierPolicy -Name "Sales-Research" -AssignedSegment "Sales" -SegmentsBlocked "Research" -State Inactive` <p> In diesem Beispiel heißt die Richtlinie zur Informationsbarriere *Vertrieb-Forschung*. Wenn diese Richtlinie aktiv und angewendet ist, verhindert sie, dass Benutzer im Segment Vertrieb Kommunikation an Benutzer im Segment Forschung richten können. Diese Richtlinie ist eine one-way-Richtlinie; Sie verhindert nicht, dass Research mit "Sales" kommuniziert. Für diesen Fall ist Richtlinie 2 erforderlich. |
| **Richtlinie 2: Unterbindung der Kommunikation von der Abteilung Forschung zur Abteilung Vertrieb** | `New-InformationBarrierPolicy -Name "Research-Sales" -AssignedSegment "Research" -SegmentsBlocked "Sales" -State Inactive` <p> In diesem Beispiel heißt die Richtlinie zur Informationsbarriere *Forschung-Vertrieb*. Wenn diese Richtlinie aktiv und angewendet ist, verhindert sie, dass Benutzer im Segment Forschung Kommunikation an Benutzer im Segment Vertrieb richten können. |
| **Richtlinie 3: Zulassen der Kommunikation zwischen Fertigung und Personal und Marketing** | `New-InformationBarrierPolicy -Name "Manufacturing-HRMarketing" -AssignedSegment "Manufacturing" -SegmentsAllowed "HR","Marketing","Manufacturing" -State Inactive` <p> In diesem Fall wird die Richtlinie zur Informationsbarriere als *Fertigung-PersonalMarketing* bezeichnet. Wenn diese Richtlinie aktiv und angewendet ist, kann die Fertigung nur mit Personal und Marketing kommunizieren. Personalwesen und Marketing sind nicht auf die Kommunikation mit anderen Segmenten beschränkt. |

Mit definierten Segmenten und Richtlinien wendet Contoso die Richtlinien an, indem das Cmdlet **"Start-InformationBarrierPoliciesApplication"** ausgeführt wird.

Wenn das Cmdlet abgeschlossen ist, erfüllt Contoso rechtliche und branchenkonforme Anforderungen.

## <a name="resources"></a>Ressourcen

- [Übersicht über Informationsbarrieren](information-barriers.md)
- [Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)
