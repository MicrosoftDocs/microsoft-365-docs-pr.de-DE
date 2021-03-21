---
title: Problembehandlung bei Informationsbarrieren
description: Verwenden Sie diesen Artikel als Leitfaden zur Problembehandlung bei Informationsbarrieren.
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: de415ba7b68df786ead038bb72465c445a86ba5a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50928005"
---
# <a name="troubleshooting-information-barriers"></a>Problembehandlung bei Informationsbarrieren

[Informationsbarrieren](information-barriers.md) können Dazu beitragen, dass Ihre Organisation den gesetzlichen Anforderungen und Branchenbestimmungen entspricht. Mit Informationsbarrieren können Sie beispielsweise die Kommunikation zwischen bestimmten Benutzergruppen einschränken, um einen Interessenkonflikt oder andere Probleme zu vermeiden. (Weitere Informationen zum Einrichten von Informationsbarrieren finden Sie unter [Define policies for information barriers](information-barriers-policies.md).)

Für den Fall, dass personen unerwartete Probleme auftreten, nachdem Informationsbarrieren in Kraft sind, gibt es einige Schritte, die Sie zur Lösung dieser Probleme ausführen können. Verwenden Sie diesen Artikel als Leitfaden.

> [!IMPORTANT]
> Zum Ausführen der in diesem Artikel beschriebenen Aufgaben muss Ihnen eine entsprechende Rolle zugewiesen werden, z. B. eine der folgenden:<br/>– Microsoft 365 Enterprise Global Administrator<br/>– globaler Administrator<br/>- Complianceadministrator<br/>- IB Compliance Management (dies ist eine neue Rolle!)<p>Weitere Informationen zu voraussetzungen für Informationsbarrieren finden Sie unter [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).<p>Stellen Sie sicher, dass Sie eine [Verbindung mit Security & Compliance Center PowerShell herstellen.](/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problem: Benutzern wird unerwartet die Kommunikation mit anderen Benutzern in Microsoft Teams blockiert. 

In diesem Fall melden Personen unerwartete Probleme bei der Kommunikation mit anderen Personen in Microsoft Teams. Einige Beispiele:

- Ein Benutzer sucht nach einem anderen Benutzer in Microsoft Teams, kann ihn aber nicht finden.
- Ein Benutzer kann einen anderen Benutzer in Microsoft Teams finden, aber nicht auswählen.
- Ein Benutzer kann einen anderen Benutzer sehen, aber keine Nachrichten an diesen anderen Benutzer in Microsoft Teams senden.

### <a name="what-to-do"></a>Vorgehensweise

Bestimmen Sie, ob die Benutzer von einer Richtlinie für Informationsbarrieren betroffen sind. Je nachdem, wie Richtlinien konfiguriert werden, funktionieren Informationsbarrieren möglicherweise wie erwartet. Oder Sie müssen die Richtlinien Ihrer Organisation verfeinern.

1. Verwenden Sie **das Cmdlet Get-InformationBarrierRecipientStatus** mit dem Parameter Identity. 

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> Sie können einen beliebigen Identitätswert verwenden, der jeden Empfänger eindeutig identifiziert, z. B. Name, Alias, Distinguished Name (DN), kanonischer DN, E-Mail-Adresse oder GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> In diesem Beispiel verwenden wir einen Alias (*meganb*) für den Identity-Parameter. Dieses Cmdlet gibt Informationen zurück, die angeben, ob der Benutzer von einer Richtlinie für Informationsbarrieren betroffen ist. (Suchen Sie nach *ExoPolicyId: \<GUID> .) |

    **Wenn die Benutzer nicht in Informationsbarriererichtlinien enthalten sind, wenden Sie sich an den Support.** Führen Sie andernfalls die nächste Aktion aus.

2. Erfahren Sie, welche Segmente in einer Richtlinie für Informationsbarrieren enthalten sind. Verwenden Sie dazu das `Get-InformationBarrierPolicy` Cmdlet mit dem Parameter Identity. 

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Verwenden Sie Details, z. B. die Richtlinien-GUID (ExoPolicyId), die Sie im vorherigen Schritt erhalten haben, als Identitätswert. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> In diesem Beispiel erhalten wir detaillierte Informationen zur Richtlinie für Informationsbarrieren mit ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*. |

    Suchen Sie nach dem Ausführen des Cmdlets in den Ergebnissen nach **AssignedSegment-,** **SegmentsAllowed-** und **SegmentsBlocked-Werten.**

    Nach dem Ausführen des Cmdlets wurde z. B. `Get-InformationBarrierPolicy` Folgendes in der Ergebnisliste angezeigt:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    In diesem Fall können wir sehen, dass eine Richtlinie zur Informationsbarriere Personen betrifft, die sich in den Segmenten Vertrieb und Forschung befinden. In diesem Fall wird verhindert, dass Personen im Vertrieb mit Personen in Research kommunizieren.

    Wenn dies richtig scheint, funktionieren Informationsbarrieren wie erwartet. Wenn nicht, fahren Sie mit dem nächsten Schritt fort.

3. Stellen Sie sicher, dass Ihre Segmente richtig definiert sind. Verwenden Sie dazu das `Get-OrganizationSegment` Cmdlet, und überprüfen Sie die Ergebnisliste.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Verwenden Sie dieses Cmdlet mit einem Identity-Parameter. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> In diesem Beispiel erhalten wir Informationen zum Segment mit guiD *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Überprüfen Sie die Details für das Segment. Bearbeiten Sie [bei Bedarf ein Segment,](information-barriers-edit-segments-policies.md#edit-a-segment)und verwenden Sie dann das `Start-InformationBarrierPoliciesApplication` Cmdlet erneut.

    Wenn Weiterhin Probleme mit Ihrer Richtlinie für **Informationsbarrieren auftreten, wenden Sie sich an den Support.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problem: Die Kommunikation zwischen Benutzern, die in Microsoft Teams blockiert werden sollten, ist zulässig.

In diesem Fall sind zwar Informationsbarrieren definiert, aktiv und angewendet, aber Personen, die an der Kommunikation miteinander gehindert werden sollten, können sich in Microsoft Teams gegenseitig chatten und anrufen.

### <a name="what-to-do"></a>Vorgehensweise

Stellen Sie sicher, dass die benutzer in einer Richtlinie für Informationsbarrieren enthalten sind. 

1. Verwenden Sie **das Cmdlet Get-InformationBarrierRecipientStatus** mit Identity-Parametern.

    |**Syntax** _|_ *Example**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel verweisen wir auf zwei Benutzerkonten in Office 365: *meganb* für *Megan* und *alexw* für *Alex*. |

    > [!TIP]
    > Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Überprüfen Sie die Ergebnisse. Das **Cmdlet Get-InformationBarrierRecipientStatus** gibt Informationen zu Benutzern zurück, z. B. Attributwerte und angewendete Richtlinien für Informationsbarrieren.

    Überprüfen Sie die Ergebnisse, und führen Sie dann die nächsten Schritte aus, wie in der folgenden Tabelle beschrieben:

    |**Ergebnisse**|**Weitere Schritte**|
    |:----------|:------------------|
    | Für die ausgewählten Benutzer werden keine Segmente aufgelistet. | Führen Sie einen der folgenden Schritte aus:<br/>– Weisen Sie einem vorhandenen Segment Benutzer zu, indem Sie ihre Benutzerprofile in Azure Active Directory bearbeiten. (Siehe [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).)<br/>- Definieren eines Segments mithilfe eines [unterstützten Attributs für Informationsbarrieren](information-barriers-attributes.md). Definieren Sie dann [entweder eine neue Richtlinie,](information-barriers-policies.md#part-2-define-information-barrier-policies) oder bearbeiten Sie eine [vorhandene Richtlinie,](information-barriers-edit-segments-policies.md#edit-a-policy) um dieses Segment zu enthalten. |
    | Segmente werden aufgelistet, aber diesen Segmenten werden keine Richtlinien für Informationsbarrieren zugewiesen. | Führen Sie einen der folgenden Schritte aus:<br/>- [Definieren einer neuen Richtlinie für Informationsbarrieren](information-barriers-policies.md#part-2-define-information-barrier-policies) für jedes in Frage gestellte Segment <br/>- [Bearbeiten einer vorhandenen Richtlinie für Informationsbarrieren,](information-barriers-edit-segments-policies.md#edit-a-policy) um sie dem richtigen Segment zuzuordnen |
    | Segmente werden aufgelistet und sind jeweils in einer Richtlinie für Informationsbarrieren enthalten. | – Führen Sie das `Get-InformationBarrierPolicy` Cmdlet aus, um zu überprüfen, ob Richtlinien für Informationsbarrieren aktiv sind<br/>– Führen Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet aus, um zu bestätigen, dass die Richtlinien angewendet wurden<br/>– Führen Sie das `Start-InformationBarrierPoliciesApplication` Cmdlet aus, um alle aktiven Richtlinien für Informationsbarrieren anzuwenden |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problem: Ich muss einen einzelnen Benutzer aus einer Richtlinie für Informationsbarrieren entfernen.

In diesem Fall sind Richtlinien für Informationsbarrieren wirksam, und ein oder mehrere Benutzer werden unerwartet an der Kommunikation mit anderen Benutzern in Microsoft Teams blockiert. Anstatt Richtlinien für Informationsbarrieren vollständig zu entfernen, können Sie einen oder mehrere einzelne Benutzer aus Richtlinien für Informationsbarrieren entfernen.

### <a name="what-to-do"></a>Vorgehensweise

Richtlinien für Informationsbarrieren werden Segmenten von Benutzern zugewiesen. Segmente werden mithilfe bestimmter [Attribute in Benutzerkontenprofilen definiert.](information-barriers-attributes.md) Wenn Sie eine Richtlinie aus einem einzelnen Benutzer entfernen müssen, sollten Sie das Profil dieses Benutzers in Azure Active Directory so bearbeiten, dass der Benutzer nicht mehr in einem Segment enthalten ist, das von Informationsbarrieren betroffen ist.

1. Verwenden Sie **das Cmdlet Get-InformationBarrierRecipientStatus** mit Identity-Parametern. Dieses Cmdlet gibt Informationen zu Benutzern zurück, z. B. Attributwerte und angewendete Richtlinien für Informationsbarrieren.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel verweisen wir auf zwei Benutzerkonten in Office 365: *meganb* für *Megan* und *alexw* für *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> Sie können einen beliebigen Wert verwenden, der den Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> In diesem Beispiel beziehen wir uns auf ein einzelnes Konto in Office 365: *jeanp*. |

2. Überprüfen Sie die Ergebnisse, um zu sehen, ob Richtlinien für Informationsbarrieren zugewiesen sind und zu welchen Segmenten die Benutzer gehören.

3. Aktualisieren Sie die Profilinformationen des Benutzers [in Azure Active Directory,](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)um einen Benutzer aus einem Segment zu entfernen, das von Informationsbarrieren betroffen ist.

4. Warten Sie etwa 30 Minuten, bis FwdSync auftritt. Führen Sie das `Start-InformationBarrierPoliciesApplication` Cmdlet auch aus, um alle aktiven Richtlinien für Informationsbarrieren anzuwenden.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problem: Der Anwendungsprozess für informationsbarrieren wird zu lange dauern

Nach dem **Ausführen des Cmdlets Start-InformationBarrierPoliciesApplication** wird der Prozess sehr lange dauern.

### <a name="what-to-do"></a>Vorgehensweise

Beachten Sie, dass beim Ausführen des Cmdlets für Richtlinienanwendung Richtlinien für Informationsbarrieren für alle Konten in Ihrer Organisation angewendet (oder entfernt) werden, Benutzer für Benutzer. Wenn Sie über eine große Anzahl von Benutzern verfügen, dauert es eine Weile, bis sie verarbeiten. (Als allgemeine Richtlinie dauert es etwa eine Stunde, bis 5.000 Benutzerkonten verarbeiten werden.)

1. Verwenden Sie **das Cmdlet Get-InformationBarrierPoliciesApplicationStatus,** um den Status der neuesten Richtlinienanwendung zu überprüfen.

    |**So zeigen Sie die neueste Richtlinienanwendung an**|**So zeigen Sie den Status für alle Richtlinienanwendungen an**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Dadurch werden Informationen darüber angezeigt, ob die Richtlinienanwendung abgeschlossen, fehlgeschlagen ist oder ausgeführt wird.

2. Führen Sie in Abhängigkeit von den Ergebnissen des vorherigen Schritts einen der folgenden Schritte aus:
  
    |**Status**|**Nächster Schritt**|
    |:---------|:------------|
    | **Nicht gestartet** | Wenn das **Cmdlet Start-InformationBarrierPoliciesApplication** seit mehr als 45 Minuten ausgeführt wurde, überprüfen Sie das Überwachungsprotokoll, um zu prüfen, ob Fehler in Richtliniendefinitionen oder ein anderer Grund für den Nichtstart der Anwendung vor liegt. |
    | **Fehlgeschlagen** | Wenn die Anwendung fehlgeschlagen ist, überprüfen Sie das Überwachungsprotokoll. Überprüfen Sie auch Ihre Segmente und Richtlinien. Sind Benutzer mehreren Segmenten zugewiesen? Werden Segmenten mehr als eine Poliicy zugewiesen? Bearbeiten Sie bei Bedarf [Segmente](information-barriers-edit-segments-policies.md#edit-a-segment) [und/oder](information-barriers-edit-segments-policies.md#edit-a-policy)Bearbeitungsrichtlinien, und führen Sie dann das Cmdlet **Start-InformationBarrierPoliciesApplication** erneut aus. |
    | **In Bearbeitung** | Wenn die Anwendung noch ausgeführt wird, lassen Sie mehr Zeit, bis sie abgeschlossen ist. Wenn es mehrere Tage war, sammeln Sie Ihre Überwachungsprotokolle, und wenden Sie sich dann an den Support. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problem: Richtlinien für Informationsbarrieren werden überhaupt nicht angewendet

In diesem Fall haben Sie Segmente definiert, Richtlinien für Informationsbarrieren definiert und versucht, diese Richtlinien anzuwenden. Wenn Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet jedoch ausführen, können Sie sehen, dass die Richtlinienanwendung fehlgeschlagen ist.

### <a name="what-to-do"></a>Vorgehensweise

Stellen Sie sicher, dass in Ihrer Organisation keine [Exchange-Adressbuchrichtlinien](/exchange/address-books/address-book-policies/address-book-policies) verwendet werden. Solche Richtlinien verhindern, dass Richtlinien für Informationsbarrieren angewendet werden.

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie [das Cmdlet Get-AddressBookPolicy](/powershell/module/exchange/get-addressbookpolicy) aus, und überprüfen Sie die Ergebnisse.

    |**Ergebnisse**|**Nächster Schritt**|
    |:----------|:------------|
    | Exchange-Adressbuchrichtlinien werden aufgelistet | [Adressbuchrichtlinien entfernen](/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Keine Adressbuchrichtlinien vorhanden |Überprüfen Der Überwachungsprotokolle, um herauszufinden, warum die Richtlinienanwendung ausfehlt |

3. [Anzeigen des Status von Benutzerkonten, Segmenten, Richtlinien oder Richtlinienanwendung](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problem: Richtlinie zur Informationsbarriere nicht auf alle benannten Benutzer angewendet

Nachdem Sie Segmente definiert, Richtlinien für Informationsbarrieren definiert und versucht haben, diese Richtlinien anzuwenden, können Sie feststellen, dass die Richtlinie auf einige Empfänger angewendet wird, aber nicht auf andere.
Wenn Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet ausführen, suchen Sie in der Ausgabe nach Text wie diesem.

> Identität: `<application guid>`
>
> Gesamtempfänger: 81527
>
> Fehlgeschlagene Empfänger: 2
>
> Fehlerkategorie: Keine
>
> Status: Abgeschlossen

### <a name="what-to-do"></a>Vorgehensweise

1. Suchen Sie im Überwachungsprotokoll nach `<application guid>` . Sie können diesen PowerShell-Code kopieren und für Ihre Variablen ändern.

```powershell
$DetailedLogs = Search-UnifiedAuditLog -EndDate <yyyy-mm-ddThh:mm:ss>  -StartDate <yyyy-mm-ddThh:mm:ss> -RecordType InformationBarrierPolicyApplication -ResultSize 1000 |?{$_.AuditData.Contains(<application guid>)} 
```

2. Überprüfen Sie die detaillierte Ausgabe aus dem Überwachungsprotokoll auf die Werte der `"UserId"` Felder `"ErrorDetails"` und. Dies gibt Ihnen den Grund für den Fehler. Sie können diesen PowerShell-Code kopieren und für Ihre Variablen ändern.

```powershell
   $DetailedLogs[1] |fl
```

Beispiel:

> "UserId": User1
>
>"ErrorDetails":"Status: IBPolicyConflict. Fehler: DAS SEGMENT "segment id1" und das SEGMENT "segment id2" haben Konflikte und können dem Empfänger nicht zugewiesen werden.

3. In der Regel werden Sie feststellen, dass ein Benutzer in mehreren Segmenten enthalten ist. Sie können dies beheben, indem Sie den `-UserGroupFilter` Wert in `OrganizationSegments` aktualisieren.

4. Wenden Sie Richtlinien für Informationsbarrieren mithilfe dieser Verfahren für [Informationsbarrieren erneut an.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Ressourcen

- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Informationsbarrieren](information-barriers.md)