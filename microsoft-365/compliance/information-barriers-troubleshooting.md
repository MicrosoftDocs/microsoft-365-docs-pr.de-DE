---
title: Problembehandlung bei Informationsbarrieren
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/08/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: None
description: Verwenden Sie diesen Artikel als Leitfaden für die Problembehandlung von Informationsbarrieren.
ms.openlocfilehash: b4c9bb46bc1e3c13cdc8b46a95733558714a44df
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600592"
---
# <a name="troubleshooting-information-barriers"></a>Problembehandlung bei Informationsbarrieren

[Informationsbarrieren](information-barriers.md) können dazu beitragen, dass Ihre Organisation weiterhin den gesetzlichen Bestimmungen und Branchenvorschriften entspricht. Beispielsweise können Sie mit Informationsbarrieren die Kommunikation zwischen bestimmten Benutzergruppen einschränken, um einen Interessenkonflikt oder andere Probleme zu vermeiden. (Weitere Informationen zum Einrichten von Informationsbarrieren finden Sie unter [define Policies for Information Barriers](information-barriers-policies.md).)

Für den Fall, dass Personen aufgrund von Informationsbarrieren unerwartete Probleme haben, können Sie einige Schritte zur Lösung dieser Probleme durchführen. Verwenden Sie diesen Artikel als Leitfaden.

> [!IMPORTANT]
> Um die in diesem Artikel beschriebenen Aufgaben ausführen zu können, muss Ihnen eine entsprechende Rolle zugewiesen sein, beispielsweise eine der folgenden:<br/>-Microsoft 365 Enterprise-Global-Administrator<br/>-Office 365 globaler Administrator<br/>-Compliance-Administrator<br/>-IB-Compliance-Management (Dies ist eine neue Rolle!)<p>Weitere Informationen zu den Voraussetzungen für Informationsbarrieren finden Sie unter [Prerequisites (for Information Barrier Policies)](information-barriers-policies.md#prerequisites).<p>Stellen Sie sicher, dass Sie [eine Verbindung mit Office 365 Security #a0 Compliance Center PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="issue-users-are-unexpectedly-blocked-from-communicating-with-others-in-microsoft-teams"></a>Problem: Benutzer werden unerwartet für die Kommunikation mit anderen Personen in Microsoft Teams blockiert. 

In diesem Fall melden Personen unerwartete Probleme, die mit anderen in Microsoft Teams kommunizieren. Beispiele:
- Ein Benutzer sucht nach, kann ihn jedoch nicht finden, sondern einen anderen Benutzer in Microsoft Teams.
- Ein Benutzer kann einen anderen Benutzer in Microsoft Teams finden, aber nicht auswählen.
- Ein Benutzer kann einen anderen Benutzer sehen, aber keine Nachrichten an diesen anderen Benutzer in Microsoft Teams senden.

### <a name="what-to-do"></a>Nächste Schritte

Bestimmen Sie, ob die Benutzer von einer Informations Sperrrichtlinie betroffen sind. Je nachdem, wie Richtlinien konfiguriert sind, funktionieren Informationsbarrieren möglicherweise wie erwartet. Oder Sie müssen die Richtlinien Ihrer Organisation möglicherweise verfeinern.

1. Verwenden Sie das Cmdlet **Get-InformationBarrierRecipientStatus** mit dem Parameter Identity. 

    |Syntax  |Beispiel  |
    |---------|---------|
    | `Get-InformationBarrierRecipientStatus -Identity` <p>Sie können jeden Identitätswert verwenden, der jeden Empfänger eindeutig identifiziert, beispielsweise Name, Alias, DN (Distinguished Name), kanonischer DN, e-Mail-Adresse oder GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb` <p>In diesem Beispiel wird ein Alias (*meganb*) für den Parameter Identity verwendet. Dieses Cmdlet gibt Informationen zurück, die angeben, ob der Benutzer von einer Richtlinie für Informationsbarrieren betroffen ist. (Suchen Sie nach * ExoPolicyId \<: GUID>.)         |

    **Wenn die Benutzer nicht in Richtlinien für Informationsbarrieren enthalten sind, wenden Sie sich an den Support**. Führen Sie andernfalls die nächste Aktion aus.

2. Finden Sie heraus, welche Segmente in einer Informations Sperrrichtlinie enthalten sind. Verwenden Sie dazu das `Get-InformationBarrierPolicy` Cmdlet mit dem Parameter Identity. 

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Get-InformationBarrierPolicy` <p>Verwenden Sie Details wie die Richtlinien-GUID (ExoPolicyId), die Sie während des vorherigen Schritts erhalten haben, als Identitätswert.     | `Get-InformationBarrierPolicy -Identity b42c3d0f-49e9-4506-a0a5-bf2853b5df6f` <p>In diesem Beispiel werden detaillierte Informationen zur Richtlinie mit Informationsbarrieren abgerufen, die ExoPolicyId *b42c3d0f-49e9-4506-a0a5-bf2853b5df6f*enthält.         |

    Suchen Sie nach dem Ausführen des Cmdlets in den Ergebnissen nach **AssignedSegment**-, **SegmentsAllowed**-und **SegmentsBlocked** -Werten.

    Beispielsweise haben wir nach dem `Get-InformationBarrierPolicy` Ausführen des Cmdlets in der Ergebnisliste Folgendes gesehen:

    ```powershell
        AssignedSegment      : Sales
        SegmentsAllowed      : {}
        SegmentsBlocked      : {Research}
    ```
    In diesem Fall können wir sehen, dass eine Informations Barriere-Richtlinie Personen betrifft, die sich in den Segmenten Vertrieb und Forschung befinden. In diesem Fall werden Personen im Vertrieb daran gehindert, mit Personen in der Forschung zu kommunizieren. 
    
    Wenn dies richtig erscheint, funktionieren Informationsbarrieren wie erwartet. Wenn dies nicht der Fall ist, fahren Sie mit dem nächsten Schritt fort.

4. Stellen Sie sicher, dass ihre Segmente ordnungsgemäß definiert sind. Verwenden Sie dazu das `Get-OrganizationSegment` Cmdlet, und überprüfen Sie die Ergebnisliste. 

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Get-OrganizationSegment`<p>Verwenden Sie dieses Cmdlet mit einem Identity-Parameter.     |`Get-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd` <p>In diesem Beispiel werden Informationen zu dem Segment abgerufen, das über GUID- *c96e0837-C232-4a8a-841e-ef45787d8fcd*verfügt.         |

    Überprüfen Sie die Details für das Segment. Bearbeiten Sie bei Bedarf [ein Segment](information-barriers-edit-segments-policies.md#edit-a-segment), und verwenden Sie dann das `Start-InformationBarrierPoliciesApplication` Cmdlet erneut.

    **Wenn Sie weiterhin Probleme mit ihrer Richtlinie zu Informationsbarrieren haben, wenden Sie sich an den Support**.

## <a name="issue-communications-are-allowed-between-users-who-should-be-blocked-in-microsoft-teams"></a>Problem: Kommunikationen zwischen Benutzern, die in Microsoft Teams blockiert werden sollten, sind zulässig.

In diesem Fall sind zwar Informationsbarrieren definiert, aktiv und angewendet, aber Personen, die nicht miteinander kommunizieren sollten, können mit Microsoft Teams chatten und sich gegenseitig anrufen.

### <a name="what-to-do"></a>Nächste Schritte

Stellen Sie sicher, dass die fraglichen Benutzer in einer Informations Sperrrichtlinie enthalten sind. 

1. Verwenden Sie das Cmdlet **Get-InformationBarrierRecipientStatus** mit Identitäts Parametern.

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, beispielsweise Name, Alias, Distinguished Name, kanonischer Domänenname, e-Mail-Adresse oder GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In diesem Beispiel wird auf zwei Benutzerkonten in Office 365 verwiesen: *meganb* für *Megan*und *alexw* für *Alex*.          |

    
    > [!TIP]
    > Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden:`Get-InformationBarrierRecipientStatus -Identity <value>`
    
2. Überprüfen Sie die Ergebnisse. Das Cmdlet **Get-InformationBarrierRecipientStatus** gibt Informationen zu Benutzern zurück, beispielsweise Attributwerte und alle Richtlinien für Informationsbarrieren, die angewendet werden. 

    Überprüfen Sie die Ergebnisse, und führen Sie dann die nächsten Schritte aus, wie in der folgenden Tabelle beschrieben:
    
    |Ergebnisse  |Nächste Schritte  |
    |---------|---------|
    |Für die ausgewählten Benutzer werden keine Segmente aufgeführt.     |Führen Sie einen der folgenden Schritte aus:<br/>– Zuweisen von Benutzern zu einem vorhandenen Segment durch Bearbeiten der Benutzerprofile in Azure Active Directory. (Weitere Informationen finden Sie unter [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).)<br/>-Definieren eines Segments mithilfe eines [unterstützten Attributs für Informationsbarrieren](information-barriers-attributes.md). Definieren Sie dann entweder [eine neue Richtlinie](information-barriers-policies.md#part-2-define-information-barrier-policies) , oder [Bearbeiten Sie eine vorhandene Richtlinie](information-barriers-edit-segments-policies.md#edit-a-policy) , um dieses Segment einzubeziehen.  |
    |Segmente werden aufgelistet, aber diesen Segmenten werden keine Richtlinien für Informationsbarrieren zugewiesen.     |Führen Sie einen der folgenden Schritte aus:<br/>- [Definieren einer neuen Informations Sperrrichtlinie](information-barriers-policies.md#part-2-define-information-barrier-policies) für jedes betreffende Segment<br/>- [Bearbeiten einer vorhandenen Richtlinie für Informationsbarrieren](information-barriers-edit-segments-policies.md#edit-a-policy) , um Sie dem richtigen Segment zuzuweisen         |
    |Segmente werden aufgelistet, und jede Richtlinie enthält eine Informations Barriere.     |-Führen Sie `Get-InformationBarrierPolicy` das Cmdlet aus, um sicherzustellen, dass Richtlinien für Informationsbarrieren aktiv sind.<br/>-Führen Sie `Get-InformationBarrierPoliciesApplicationStatus` das Cmdlet aus, um zu bestätigen, dass die Richtlinien angewendet werden<br/>-Ausführen des `Start-InformationBarrierPoliciesApplication` Cmdlets zum Anwenden aller Active Information Barrier-Richtlinien          |
    

## <a name="issue-i-need-to-remove-a-single-user-from-an-information-barrier-policy"></a>Problem: Ich muss einen einzelnen Benutzer aus einer Informations Sperrrichtlinie entfernen.

In diesem Fall sind Richtlinien für Informationsbarrieren wirksam, und ein oder mehrere Benutzer werden unerwartet für die Kommunikation mit anderen Personen in Microsoft Teams blockiert. Anstatt Richtlinien für Informationsbarrieren gänzlich zu entfernen, können Sie einen oder mehrere einzelne Benutzer aus Informations Sperrrichtlinien entfernen. 

### <a name="what-to-do"></a>Nächste Schritte

Richtlinien für Informationsbarrieren werden Segmenten von Benutzern zugewiesen. Segmente werden mithilfe bestimmter [Attribute in Benutzerkonto Profilen](information-barriers-attributes.md)definiert. Wenn Sie eine Richtlinie von einem einzelnen Benutzer entfernen müssen, sollten Sie das Profil des Benutzers in Azure bearbeiten Active Directory so, dass der Benutzer nicht mehr in einem Segment enthalten ist, das von Informationsbarrieren betroffen ist.

1. Verwenden Sie das Cmdlet **Get-InformationBarrierRecipientStatus** mit Identitäts Parametern. Dieses Cmdlet gibt Informationen zu Benutzern zurück, beispielsweise Attributwerte und alle angewendeten Richtlinien für Informationsbarrieren.

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>`<p>Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, beispielsweise Name, Alias, Distinguished Name, kanonischer Domänenname, e-Mail-Adresse oder GUID.     |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p>In diesem Beispiel wird auf zwei Benutzerkonten in Office 365 verwiesen: *meganb* für *Megan*und *alexw* für *Alex*.          |
    |`Get-InformationBarrierRecipientStatus -Identity <value>` <p>Sie können einen beliebigen Wert verwenden, der den Benutzer eindeutig identifiziert, beispielsweise Name, Alias, Distinguished Name, kanonischer Domänenname, e-Mail-Adresse oder GUID.|`Get-InformationBarrierRecipientStatus -Identity jeanp`<p>In diesem Beispiel wird auf ein einzelnes Konto in Office 365 verwiesen: *jeanp*. |

2. Überprüfen Sie die Ergebnisse, um festzustellen, ob Richtlinien für Informationsbarrieren zugewiesen sind und zu welchem Segment (n) die Benutzer gehören. 

3. Wenn Sie einen Benutzer aus einem Segment entfernen möchten, das von Informationsbarrieren betroffen ist, [Aktualisieren Sie die Profilinformationen des Benutzers in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

4. Warten Sie etwa 30 Minuten, bis FwdSync ausgeführt wird. Oder führen Sie das `Start-InformationBarrierPoliciesApplication` Cmdlet aus, um alle Active Information Barrier-Richtlinien anzuwenden.

## <a name="issue-the-information-barrier-application-process-is-taking-too-long"></a>Problem: der Anwendungsprozess für Informationsbarrieren dauert zu lange.

Nach dem Ausführen des Cmdlets **Start-InformationBarrierPoliciesApplication** dauert es sehr lange, bis der Vorgang abgeschlossen ist.

### <a name="what-to-do"></a>Nächste Schritte

Beachten Sie, dass beim Ausführen des Cmdlets für die Richtlinienanwendung für alle Konten in Ihrer Organisation Richtlinien für Informationsbarrieren angewendet (oder entfernt) werden, Benutzer nach Benutzer. Wenn Sie viele Benutzer haben, dauert es eine Weile, bis Sie verarbeitet werden. (Als allgemeine Richtlinie dauert es etwa eine Stunde, 5.000-Benutzerkonten zu verarbeiten.)

1. Verwenden Sie das Cmdlet **Get-InformationBarrierPoliciesApplicationStatus** , um den Status der neuesten Richtlinienanwendung zu überprüfen.

    |So zeigen Sie die neueste Richtlinienanwendung an  |So zeigen Sie den Status für alle Richtlinien Anwendungen an  |
    |---------|---------|
    |`Get-InformationBarrierPoliciesApplicationStatus`     |`Get-InformationBarrierPoliciesApplicationStatus -All $true`         |


    Dadurch werden Informationen darüber angezeigt, ob die Richtlinienanwendung abgeschlossen, ein Fehler aufgetreten ist oder ausgeführt wird.

2. Führen Sie je nach den Ergebnissen des vorherigen Schritts einen der folgenden Schritte aus:
  
    |Status  |Nächster Schritt  |
    |---------|---------|
    |**Nicht gestartet**     |Wenn es mehr als 45 Minuten seit dem **Start-InformationBarrierPoliciesApplication-** Cmdlet ausgeführt wurde, überprüfen Sie Ihr Überwachungsprotokoll, um zu sehen, ob es Fehler in Richtlinien Definitionen gibt, oder aus einem anderen Grund, warum die Anwendung noch nicht gestartet wurde. |
    |**Fehlgeschlagen**     |Wenn die Anwendung fehlgeschlagen ist, überprüfen Sie Ihr Überwachungsprotokoll. Überprüfen Sie auch ihre Segmente und Richtlinien. Sind alle Benutzer mehr als einem Segment zugeordnet? Sind Segmente mit mehr als einem poliicy zugeordnet? Bearbeiten Sie gegebenenfalls [Segmente](information-barriers-edit-segments-policies.md#edit-a-segment) und/oder [Bearbeiten Sie Richtlinien](information-barriers-edit-segments-policies.md#edit-a-policy), und führen Sie dann das Cmdlet **Start-InformationBarrierPoliciesApplication** erneut aus.  |
    |**In Bearbeitung**     |Wenn die Anwendung noch ausgeführt wird, lassen Sie mehr Zeit für ihre Ausführung zu. Wenn es sich um mehrere Tage handelt, erfassen Sie die Überwachungsprotokolle, und wenden Sie sich an den Support. |

## <a name="issue-information-barrier-policies-are-not-being-applied-at-all"></a>Problem: Richtlinien für Informationsbarrieren werden nicht angewendet.

In diesem Fall haben Sie Segmente definiert, Richtlinien für Informationsbarrieren definiert und versucht, diese Richtlinien anzuwenden. Wenn Sie das `Get-InformationBarrierPoliciesApplicationStatus` Cmdlet ausführen, können Sie jedoch sehen, dass die Richtlinienanwendung fehlgeschlagen ist.

### <a name="what-to-do"></a>Nächste Schritte

Stellen Sie sicher, dass in Ihrer Organisation keine [Exchange-adressbuchrichtlinien](https://docs.microsoft.com/exchange/address-books/address-book-policies/address-book-policies) vorhanden sind. Solche Richtlinien verhindern, dass Richtlinien für Informationsbarrieren angewendet werden.

1. Stellen Sie eine Verbindung mit [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps) her. 

2. Führen Sie das Cmdlet [Get-AddressBookPolicy](https://docs.microsoft.com/powershell/module/exchange/email-addresses-and-address-books/get-addressbookpolicy?view=exchange-ps) aus, und überprüfen Sie die Ergebnisse.

    |Ergebnisse  |Nächster Schritt  |
    |---------|---------|
    |Exchange-adressbuchrichtlinien werden aufgelistet     |[Adressbuchrichtlinien entfernen](https://docs.microsoft.com/exchange/address-books/address-book-policies/remove-an-address-book-policy)         |
    |Es sind keine adressbuchrichtlinien vorhanden. |Überprüfen der Überwachungsprotokolle, um herauszufinden, warum die Richtlinienanwendung fehlschlägt |

3. [Anzeigen des Status von Benutzerkonten, Segmenten, Richtlinien oder Richtlinienanwendung](information-barriers-policies.md#view-status-of-user-accounts-segments-policies-or-policy-application).

## <a name="related-topics"></a>Verwandte Themen

[Definieren von Richtlinien für Informationsbarrieren in Microsoft Teams](information-barriers-policies.md)

[Informationsbarrieren](information-barriers.md)



