---
title: Problembehandlung bei Informationsbarrieren
description: Verwenden Sie diesen Artikel als Leitfaden für die Problembehandlung bei Informationsbarrieren.
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
ms.openlocfilehash: 39ac5c2f12b8947bce26d426cac83e57cd4c87ae
ms.sourcegitcommit: c10eb675da725830e9776d2a0566ba3622eb361c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/26/2021
ms.locfileid: "49980038"
---
# <a name="troubleshooting-information-barriers"></a>Problembehandlung bei Informationsbarrieren

[Informationsbarrieren](information-barriers.md) können Dazu beitragen, dass Ihre Organisation den gesetzlichen Anforderungen und Branchenbestimmungen entspricht. Mit Informationsbarrieren können Sie beispielsweise die Kommunikation zwischen bestimmten Benutzergruppen einschränken, um Interessenkonflikte oder andere Probleme zu vermeiden. (Weitere Informationen zum Einrichten von Informationsbarrieren finden Sie unter "Definieren von [Richtlinien für Informationsbarrieren".)](information-barriers-policies.md)

Für den Fall, dass nach dem Auftreten von Informationsbarrieren unerwartete Probleme auftreten, können Sie einige Schritte ausführen, um diese Probleme zu beheben. Verwenden Sie diesen Artikel als Leitfaden.

> [!IMPORTANT]
> Zum Ausführen der in diesem Artikel beschriebenen Aufgaben muss Ihnen eine entsprechende Rolle zugewiesen werden, z. B. eine der folgenden:<br/>– Globaler Microsoft 365 Enterprise-Administrator<br/>– globaler Administrator<br/>– Complianceadministrator<br/>- IB Compliance Management (dies ist eine neue Rolle!)<p>Weitere Informationen zu voraussetzungen für Informationsbarrieren finden Sie unter [Voraussetzungen (für Richtlinien für Informationsbarrieren)](information-barriers-policies.md#prerequisites).<p>Stellen Sie sicher, [dass Sie eine Verbindung mit Security & Compliance Center PowerShell herstellen.](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problem: Benutzer werden unerwarteterweise an der Kommunikation mit anderen in Microsoft Teams blockiert. 

In diesem Fall melden Personen unerwartete Probleme bei der Kommunikation mit anderen in Microsoft Teams. Einige Beispiele:

- Ein Benutzer sucht nach einem anderen Benutzer in Microsoft Teams, kann ihn aber nicht finden.
- Ein Benutzer kann einen anderen Benutzer in Microsoft Teams finden, aber nicht auswählen.
- Ein Benutzer kann einen anderen Benutzer sehen, aber keine Nachrichten an diesen anderen Benutzer in Microsoft Teams senden.

### <a name="what-to-do"></a>Vorgehensweise

Bestimmen Sie, ob die Benutzer von einer Richtlinie für Informationsbarrieren betroffen sind. Je nachdem, wie Richtlinien konfiguriert sind, funktionieren Informationsbarrieren möglicherweise wie erwartet. Oder Sie müssen die Richtlinien Ihrer Organisation verfeinern.

1. Verwenden Sie **das Cmdlet "Get-InformationBarrierRecipientStatus"** mit dem Parameter "Identity". 

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p> Sie können einen beliebigen Identitätswert verwenden, der jeden Empfänger eindeutig identifiziert, z. B. Name, Alias, DN (Distinguished Name), kanonischer DN, E-Mail-Adresse oder GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb` <p> In diesem Beispiel verwenden wir einen Alias (*meganb*) für den Parameter "Identity". Dieses Cmdlet gibt Informationen zurück, die angeben, ob der Benutzer von einer Richtlinie für Informationsbarrieren betroffen ist. (Suchen Sie nach *ExoPolicyId: \<GUID> .) |

    **Wenn die Benutzer nicht in den Richtlinien für Informationsbarrieren enthalten sind, wenden Sie sich an den Support.** Führen Sie andernfalls die nächste Aktion aus.

2. Erfahren Sie, welche Segmente in einer Richtlinie für Informationsbarrieren enthalten sind. Verwenden Sie dazu das `Get-InformationBarrierPolicy` Cmdlet mit dem Parameter "Identity". 

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierPolicy` <p> Verwenden Sie Details, z. B. die Richtlinien-GUID (ExoPolicyId), die Sie im vorherigen Schritt erhalten haben, als Identitätswert. | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p> In diesem Beispiel erhalten wir detaillierte Informationen zur Richtlinie für Informationsbarrieren, die exoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f hat.* |

    Suchen Sie nach dem Ausführen des Cmdlets in den Ergebnissen nach **AssignedSegment-,** **SegmentsAllowed-** und **SegmentsBlocked-Werten.**

    Beispielsweise haben wir nach dem Ausführen des `Get-InformationBarrierPolicy` Cmdlets Folgendes in der Ergebnisliste gesehen:

    ```powershell
    AssignedSegment : Sales
    SegmentsAllowed : {}
    SegmentsBlocked : {Research}
    ```

    In diesem Fall sehen wir, dass eine Richtlinie für Informationsbarrieren Personen betrifft, die sich in den Segmenten Vertrieb und Forschung befinden. In diesem Fall wird verhindert, dass Personen im Vertrieb mit Personen in der Forschung kommunizieren.

    Wenn dies korrekt erscheint, funktionieren Informationsbarrieren wie erwartet. Wenn nicht, fahren Sie mit dem nächsten Schritt fort.

3. Stellen Sie sicher, dass Ihre Segmente richtig definiert sind. Verwenden Sie dazu das `Get-OrganizationSegment` Cmdlet, und überprüfen Sie die Liste der Ergebnisse.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-OrganizationSegment`<p> Verwenden Sie dieses Cmdlet mit einem Identity-Parameter. | `Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p> In diesem Beispiel erhalten wir Informationen über das Segment mit der GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd*. |

    Überprüfen Sie die Details für das Segment. Bearbeiten Sie [bei Bedarf ein Segment,](information-barriers-edit-segments-policies.md#edit-a-segment)und verwenden Sie dann das `Start-InformationBarrierPoliciesApplication` Cmdlet erneut.

    Wenn weiterhin Probleme mit ihrer Richtlinie für **Informationsbarrieren auftreten, wenden Sie sich an den Support.**

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problem: Die Kommunikation zwischen Benutzern, die in Microsoft Teams blockiert werden sollen, ist zulässig.

In diesem Fall können, obwohl Informationsbarrieren definiert, aktiv und angewendet werden, Personen, die daran gehindert werden sollten, miteinander zu kommunizieren, in Microsoft Teams miteinander chatten und sich anrufen.

### <a name="what-to-do"></a>Vorgehensweise

Stellen Sie sicher, dass die benutzer in einer Richtlinie für Informationsbarrieren enthalten sind. 

1. Verwenden Sie **das Cmdlet "Get-InformationBarrierRecipientStatus"** mit Identitätsparametern.

    |**Syntax** _|_ *Example**|
    |:----------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel beziehen wir uns auf zwei Benutzerkonten in Office 365: *Meganb* für *Megan* und *alexw* für *Alex*. |

    > [!TIP]
    > Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>`

2. Überprüfen Sie die Ergebnisse. Das **Cmdlet "Get-InformationBarrierRecipientStatus"** gibt Informationen zu Benutzern zurück, z. B. Attributwerte und angewendete Richtlinien für Informationsbarrieren.

    Überprüfen Sie die Ergebnisse, und führen Sie dann die nächsten Schritte aus, wie in der folgenden Tabelle beschrieben:

    |**Ergebnisse**|**Nächste Schritte**|
    |:----------|:------------------|
    | Es werden keine Segmente für die ausgewählten Benutzer aufgelistet. | Führen Sie einen der folgenden Schritte aus:<br/>– Weisen Sie Benutzern ein vorhandenes Segment zu, indem Sie ihre Benutzerprofile in Azure Active Directory bearbeiten. (Siehe [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell.)](https://docs.microsoft.com/microsoft-365/enterprise/configure-user-account-properties-with-microsoft-365-powershell)<br/>- Definieren Sie ein Segment mithilfe eines [unterstützten Attributs für Informationsbarrieren.](information-barriers-attributes.md) Definieren Sie dann entweder [eine neue Richtlinie,](information-barriers-policies.md#part-2-define-information-barrier-policies) oder bearbeiten Sie eine [vorhandene Richtlinie,](information-barriers-edit-segments-policies.md#edit-a-policy) um dieses Segment zu enthalten. |
    | Segmente werden aufgelistet, aber diesen Segmenten werden keine Richtlinien für Informationsbarrieren zugewiesen. | Führen Sie einen der folgenden Schritte aus:<br/>- [Definieren einer neuen Richtlinie für Informationsbarrieren](information-barriers-policies.md#part-2-define-information-barrier-policies) für jedes segment in Frage <br/>- [Bearbeiten einer vorhandenen Richtlinie für Informationsbarrieren,](information-barriers-edit-segments-policies.md#edit-a-policy) um sie dem richtigen Segment zuzuordnen |
    | Segmente werden aufgelistet und sind jeweils in einer Richtlinie für Informationsbarrieren enthalten. | – Führen Sie das `Get-InformationBarrierPolicy` Cmdlet aus, um zu überprüfen, ob Richtlinien für Informationsbarrieren aktiv sind<br/>– Führen Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet aus, um zu bestätigen, dass die Richtlinien angewendet wurden.<br/>– Führen Sie das `Start-InformationBarrierPoliciesApplication` Cmdlet aus, um alle Richtlinien für aktive Informationsbarrieren anzuwenden |

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problem: Ich muss einen einzelnen Benutzer aus einer Richtlinie für Informationsbarrieren entfernen

In diesem Fall sind Richtlinien für Informationsbarrieren in Kraft, und ein oder mehrere Benutzer werden unerwartet von der Kommunikation mit anderen in Microsoft Teams blockiert. Anstatt Richtlinien für Informationsbarrieren vollständig zu entfernen, können Sie einen oder mehrere einzelne Benutzer aus Richtlinien für Informationsbarrieren entfernen.

### <a name="what-to-do"></a>Vorgehensweise

Richtlinien für Informationsbarrieren werden Segmenten von Benutzern zugewiesen. Segmente werden mithilfe bestimmter [Attribute in Benutzerkontenprofilen definiert.](information-barriers-attributes.md) Wenn Sie eine Richtlinie von einem einzelnen Benutzer entfernen müssen, sollten Sie das Profil dieses Benutzers in Azure Active Directory so bearbeiten, dass der Benutzer nicht mehr in einem Segment enthalten ist, das von Informationsbarrieren betroffen ist.

1. Verwenden Sie **das Cmdlet "Get-InformationBarrierRecipientStatus"** mit Identitätsparametern. Dieses Cmdlet gibt Informationen zu Benutzern zurück, z. B. Attributwerte und richtlinien für Informationsbarrieren, die angewendet werden.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. | `Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel beziehen wir uns auf zwei Benutzerkonten in Office 365: *Meganb* für *Megan* und *alexw* für *Alex*.          |
    | `Get-InformationBarrierRecipientStatus -Identity <value>` <p> Sie können einen beliebigen Wert verwenden, der den Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p> In diesem Beispiel beziehen wir uns auf ein einzelnes Konto in Office 365: *".* |

2. Überprüfen Sie die Ergebnisse, um zu sehen, ob Richtlinien für Informationsbarrieren zugewiesen sind und zu welchen Segmenten die Benutzer gehören.

3. Um einen Benutzer aus einem Segment zu entfernen, das von Informationsbarrieren betroffen ist, aktualisieren Sie die Profilinformationen des Benutzers [in Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)

4. Warten Sie etwa 30 Minuten, bis FwdSync auftritt. Oder führen Sie das `Start-InformationBarrierPoliciesApplication` Cmdlet aus, um alle Richtlinien für aktive Informationsbarrieren anzuwenden.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problem: Der Anwendungsprozess für Informationsbarrieren nimmt zu viel Zeit in Die Anwendung

Nach dem Ausführen **des Cmdlets "Start-InformationBarrierPoliciesApplication"** nimmt der Vorgang sehr viel Zeit ins Spiel.

### <a name="what-to-do"></a>Vorgehensweise

Beachten Sie, dass beim Ausführen des Richtlinienanwendungs-Cmdlets Richtlinien für Informationsbarrieren für alle Konten in Ihrer Organisation von Benutzer zu Benutzer angewendet (oder entfernt) werden. Wenn sie viele Benutzer haben, dauert dies eine Weile. (Allgemein gilt, dass es ungefähr eine Stunde dauert, bis 5.000 Benutzerkonten verwendet werden.)

1. Verwenden Sie **das Cmdlet "Get-InformationBarrierPoliciesApplicationStatus",** um den Status der neuesten Richtlinienanwendung zu überprüfen.

    |**So zeigen Sie die neueste Richtlinienanwendung an**|**So zeigen Sie den Status aller Richtlinienanwendungen an**|
    |:---------------------------------------------|:---------------------------------------------|
    | `Get-InformationBarrierPoliciesApplicationStatus` | `Get-InformationBarrierPoliciesApplicationStatus -All $true` |

    Dadurch werden Informationen darüber angezeigt, ob die Richtlinienanwendung abgeschlossen wurde, fehlgeschlagen ist oder ausgeführt wird.

2. Führen Sie je nach den Ergebnissen des vorherigen Schritts einen der folgenden Schritte aus:
  
    |**Status**|**Nächster Schritt**|
    |:---------|:------------|
    | **Nicht gestartet** | If it has been more than 45 minutes since the **Start-InformationBarrierPoliciesApplication** cmdlet has been run, review your audit log to see if there are any errors in policy definitions, or some other reason why the application has not started. |
    | **Fehlgeschlagen** | Wenn die Anwendung fehlgeschlagen ist, überprüfen Sie Das Überwachungsprotokoll. Überprüfen Sie auch Ihre Segmente und Richtlinien. Sind Benutzer mehreren Segmenten zugewiesen? Werden Segmenten mehr als eine Poliicie zugewiesen? Bearbeiten Sie bei Bedarf [Segmente](information-barriers-edit-segments-policies.md#edit-a-segment) [und/oder](information-barriers-edit-segments-policies.md#edit-a-policy)Richtlinien, und führen Sie dann das Cmdlet **"Start-InformationBarrierPoliciesApplication"** erneut aus. |
    | **In Bearbeitung** | Wenn die Anwendung noch ausgeführt wird, lassen Sie mehr Zeit, bis sie abgeschlossen ist. Wenn es mehrere Tage gezeit ist, sammeln Sie Ihre Überwachungsprotokolle, und wenden Sie sich dann an den Support. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problem: Richtlinien für Informationsbarrieren werden überhaupt nicht angewendet

In diesem Fall haben Sie Segmente definiert, Richtlinien für Informationsbarrieren definiert und versucht, diese Richtlinien anzuwenden. Wenn Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet jedoch ausführen, können Sie sehen, dass die Richtlinienanwendung fehlgeschlagen ist.

### <a name="what-to-do"></a>Vorgehensweise

Stellen Sie sicher, dass in Ihrer Organisation keine Richtlinien [für das Exchange-Adressbuch](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) verwendet werden. Solche Richtlinien verhindern, dass Richtlinien für Informationsbarrieren angewendet werden.

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) her.

2. Führen Sie [das Cmdlet "Get-AddressBookPolicy"](https://docs.microsoft.com/powershell/module/exchange/get-addressbookpolicy) aus, und überprüfen Sie die Ergebnisse.

    |**Ergebnisse**|**Nächster Schritt**|
    |:----------|:------------|
    | Richtlinien für das Exchange-Adressbuch sind aufgeführt | [Adressbuchrichtlinien entfernen](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy) |
    | Es sind keine Adressbuchrichtlinien vorhanden |Überprüfen Der Überwachungsprotokolle, um herauszufinden, warum die Richtlinienanwendung einen Fehler meldet |

3. [Anzeigen des Status von Benutzerkonten, Segmenten, Richtlinien oder Richtlinienanwendung.](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application)

## <a name="issue-information-barrier-policy-not-applied-to-all-designated-users"></a>Problem: Richtlinie für Informationsbarrieren wird nicht auf alle festgelegten Benutzer angewendet

Nachdem Sie Segmente definiert, Richtlinien für Informationsbarrieren definiert und versucht haben, diese Richtlinien anzuwenden, können Sie feststellen, dass die Richtlinie auf einige Empfänger angewendet wird, jedoch nicht auf andere.
Wenn Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet ausführen, durchsuchen Sie die Ausgabe nach Text wie diesem.

> Identität: `<application guid>`
>
> Gesamtzahl der Empfänger: 81527
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

2. Überprüfen Sie die detaillierte Ausgabe aus dem Überwachungsprotokoll auf die Werte der `"UserId"` Felder `"ErrorDetails"` und Felder. Dies gibt Ihnen den Grund für den Fehler an. Sie können diesen PowerShell-Code kopieren und für Ihre Variablen ändern.

```powershell
   $DetailedLogs[1] |fl
```

Beispiel:

> "UserId": Benutzer1
>
>"ErrorDetails":"Status: IBPolicyConflict. Fehler: Das SEGMENT "segment id1" und das SEGMENT "segment id2" des SEGMENT "IB" haben einen Konflikt und können dem Empfänger nicht zugewiesen werden.

3. In der Regel werden Sie feststellen, dass ein Benutzer in mehr als einem Segment enthalten ist. Sie können dieses Problem beheben, indem Sie den `-UserGroupFilter` Wert in `OrganizationSegments` aktualisieren.

4. Wenden Sie Richtlinien für Informationsbarrieren mithilfe dieser Verfahren für Informationsbarrierenrichtlinien [erneut an.](information-barriers-policies.md#part-3-apply-information-barrier-policies)

## <a name="resources"></a>Ressourcen

- [Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)
- [Informationsbarrieren](information-barriers.md)
