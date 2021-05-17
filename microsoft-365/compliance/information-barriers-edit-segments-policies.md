---
title: Verwalten von Richtlinien für Informationsbarrieren
description: Erfahren Sie, wie Sie Richtlinien für Informationsbarrieren bearbeiten oder entfernen.
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
ms.openlocfilehash: 668ca8e26371d80f068c2723357ce3ee407db03a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925551"
---
# <a name="manage-information-barrier-policies"></a>Verwalten von Richtlinien für Informationsbarrieren

Nachdem Sie [Richtlinien für Informationsbarrieren](information-barriers-policies.md)definiert haben, müssen Sie möglicherweise Änderungen an diesen Richtlinien oder an Ihren Benutzersegmenten vornehmen, als Teil der Problembehandlung [oder](information-barriers-troubleshooting.md) als regelmäßige Wartung. Verwenden Sie diesen Artikel als Leitfaden.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie machen?

|**Aktion**|**Beschreibung**|
|:---------|:--------------|
| [Bearbeiten von Benutzerkontoattributen](#edit-user-account-attributes) | Füllen Sie Attribute in Azure Active Directory, die zum Definieren von Segmenten verwendet werden können.<br/>Bearbeiten Sie Benutzerkontoattribute, wenn Benutzer in bestimmten Segmenten, in denen sie enthalten sein sollten, nicht enthalten sind, um zu ändern, in welchen Segmenten Benutzer enthalten sind oder um Segmente mit unterschiedlichen Attributen zu definieren. |
| [Bearbeiten eines Segments](#edit-a-segment) | Bearbeiten Sie Segmente, wenn Sie ändern möchten, wie ein Segment definiert ist. <br/>Sie können beispielsweise ursprünglich Segmente mit *Department* definiert haben und nun ein anderes Attribut verwenden, z. B. *MemberOf*. |
| [Bearbeiten einer Richtlinie ](#edit-a-policy) | Bearbeiten Sie eine Richtlinie für Informationsbarrieren, wenn Sie ändern möchten, wie eine Richtlinie funktioniert.<br/>Anstatt beispielsweise die Kommunikation zwischen zwei Segmenten zu blockieren, können Sie die Kommunikation nur zwischen bestimmten Segmenten zulassen. |
| [Festlegen einer Richtlinie auf inaktiven Status](#set-a-policy-to-inactive-status) |Legen Sie eine Richtlinie auf inaktiven Status, wenn Sie Änderungen an einer Richtlinie vornehmen möchten oder wenn Sie nicht möchten, dass eine Richtlinie wirksam wird. |
| [Entfernen einer Richtlinie](#remove-a-policy) | Entfernen Sie eine Richtlinie für Informationsbarrieren, wenn Sie keine bestimmte Richtlinie mehr benötigen. |
| [Beenden einer Richtlinienanwendung](#stop-a-policy-application) | Ergreifen Sie diese Aktion, wenn Sie das Anwenden von Richtlinien für Informationsbarrieren beenden möchten.<br/> Das Beenden einer Richtlinienanwendung ist nicht sofort und führt nicht zum Rückgängig machen von Richtlinien, die bereits auf Benutzer angewendet wurden. |
| [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md) | Definieren Sie eine Richtlinie für Informationsbarrieren, wenn sie noch nicht vorhanden ist und Sie die Kommunikation zwischen bestimmten Benutzergruppen einschränken oder einschränken müssen. |
| [Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md) | Lesen Sie diesen Artikel, wenn unerwartete Probleme mit Informationsbarrieren auftreten. |

> [!IMPORTANT]
> Zum Ausführen der in diesem Artikel beschriebenen Aufgaben muss Ihnen eine entsprechende Rolle zugewiesen werden, z. B. eine der folgenden:<br/>– Microsoft 365 Enterprise globaler Administrator<br/>– Globaler Administrator<br/>- Complianceadministrator<br/>- IB Compliance Management (dies ist eine neue Rolle!)<br><br>Weitere Informationen zu voraussetzungen für Informationsbarrieren finden Sie unter [Prerequisites (for information barrier policies)](information-barriers-policies.md#prerequisites).<br><br> Stellen Sie sicher, dass Sie eine Verbindung mit [dem Security & Compliance Center PowerShell herstellen.](/powershell/exchange/connect-to-scc-powershell)

## <a name="edit-user-account-attributes"></a>Bearbeiten von Benutzerkontoattributen

Verwenden Sie dieses Verfahren, um Attribute zu bearbeiten, die für die Segmentierung von Benutzern verwendet werden. Wenn Sie z. B. ein Department-Attribut verwenden und mindestens ein Benutzerkonto derzeit keine Werte für Department enthält, müssen Sie diese Benutzerkonten so bearbeiten, dass sie Abteilungsinformationen enthalten. Benutzerkontenattribute werden zum Definieren von Segmenten verwendet, damit Richtlinien für Informationsbarrieren zugewiesen werden können.

1. Verwenden Sie zum Anzeigen von Details für ein bestimmtes Benutzerkonto, z. B. Attributwerte und zugewiesene Segmente, das **Cmdlet Get-InformationBarrierRecipientStatus** mit Identity-Parametern.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p> Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, z. B. Name, Alias, Distinguished Name, kanonischer Domänenname, E-Mail-Adresse oder GUID. <p> (Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>` ) |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw` <p> In diesem Beispiel verweisen wir auf zwei Benutzerkonten in Office 365: *meganb* für *Megan* und *alexw* für *Alex*. |

2. Bestimmen Sie, welches Attribut Sie für Ihre Benutzerkontenprofile bearbeiten möchten. Weitere Informationen finden Sie unter [Attributes for information barrier policies](information-barriers-attributes.md). 

3. Bearbeiten Sie ein oder mehrere Benutzerkonten, um Werte für das attribut zu enthalten, das Sie im vorherigen Schritt ausgewählt haben. Verwenden Sie eines der folgenden Verfahren, um diese Aktion zu ergreifen:

    - Informationen zum Bearbeiten eines einzelnen Kontos finden Sie unter Hinzufügen oder Aktualisieren der Profilinformationen eines [Benutzers mithilfe Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Informationen zum Bearbeiten mehrerer Konten (oder zum Bearbeiten eines einzelnen Kontos mithilfe von PowerShell) finden Sie unter [Configure user account properties with Office 365 PowerShell](../enterprise/configure-user-account-properties-with-microsoft-365-powershell.md).

## <a name="edit-a-segment"></a>Bearbeiten eines Segments

Verwenden Sie dieses Verfahren bearbeiten Sie die Definition eines Benutzersegments. Sie können z. B. den Namen eines Abschnitts oder den Filter ändern, der verwendet wird, um zu bestimmen, wer im Segment enthalten ist.

1. Verwenden Sie zum Anzeigen aller vorhandenen Segmente das **Cmdlet Get-OrganizationSegment.**

    Syntax: `Get-OrganizationSegment`

    Es wird eine Liste der Segmente und Details für jedes Segment angezeigt, z. B. Segmenttyp, UserGroupFilter-Wert, der sie erstellt oder zuletzt geändert hat, GUID und so weiter.

    > [!TIP]
    > Drucken oder speichern Sie die Liste der Segmente später zur Referenz. Wenn Sie z. B. ein Segment bearbeiten möchten, müssen Sie den Namen oder Denkwert kennen (dies wird mit dem Parameter Identity verwendet).

2. Verwenden Sie zum Bearbeiten eines Abschnitts das **Cmdlet Set-OrganizationSegment** mit dem **Parameter Identity** und den relevanten Details.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"` |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p> In diesem Beispiel wurde für das Segment mit der GUID *c96e0837-c232-4a8a-841e-ef45787d8fcd* der Abteilungsname auf "HRDept" aktualisiert. |

Wenn Sie die Bearbeitung von Segmenten [](information-barriers-policies.md#part-2-define-information-barrier-policies) für Ihre Organisation abgeschlossen haben, können Sie Richtlinien für Informationsbarrieren definieren [oder](#edit-a-policy) bearbeiten.

## <a name="edit-a-policy"></a>Bearbeiten einer Richtlinie 

1. Verwenden Sie zum Anzeigen einer Liste der aktuellen Richtlinien für Informationsbarrieren das **Cmdlet Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifizieren Sie in der Liste der Ergebnisse die Richtlinie, die Sie ändern möchten. Notieren Sie sich die GUID und den Namen der Richtlinie.

2. Verwenden Sie **das Cmdlet Set-InformationBarrierPolicy** mit einem **Identity-Parameter,** und geben Sie die Änderungen an, die Sie vornehmen möchten.

    Beispiel: Angenommen, eine Richtlinie wurde definiert, um zu blockieren, dass das *Segment Research* mit den *Vertriebs-* und *Marketingsegmenten kommuniziert.* Die Richtlinie wurde mithilfe dieses Cmdlets definiert: `New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`

    Angenommen, wir möchten sie so ändern, dass Personen im Segment *Forschung* nur mit Personen im Personalbereich *kommunizieren* können. Um diese Änderung zu ändern, verwenden wir dieses Cmdlet: `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    In diesem Beispiel haben wir "SegmentsBlocked" in "SegmentsAllowed" geändert und das *Personalabteilungssegment* angegeben.

3. Wenn Sie mit der Bearbeitung einer Richtlinie fertig sind, müssen Sie die Änderungen anwenden. (Siehe [Anwenden von Richtlinien für Informationsbarrieren](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Festlegen einer Richtlinie auf inaktiven Status

1. Verwenden Sie zum Anzeigen einer Liste der aktuellen Richtlinien für Informationsbarrieren das **Cmdlet Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifizieren Sie in der Liste der Ergebnisse die Richtlinie, die Sie ändern (oder entfernen möchten). Notieren Sie sich die GUID und den Namen der Richtlinie.

2. Um den Status der Richtlinie auf inaktiv zu setzen, verwenden Sie das **Cmdlet Set-InformationBarrierPolicy** mit einem Identity-Parameter und den State-Parameter auf Inaktiv.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Set-InformationBarrierPolicy -Identity GUID -State Inactive` | `Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p> In diesem Beispiel legen wir eine Richtlinie für Informationsbarrieren mit guiD *43c37853-ea10-4b90-a23d-ab8c9377247* auf einen inaktiven Status fest. |

3. Verwenden Sie zum Anwenden der Änderungen das **Cmdlet Start-InformationBarrierPoliciesApplication.**

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Änderungen werden von Benutzer zu Benutzer für Ihre Organisation angewendet. Wenn Ihre Organisation groß ist, kann es 24 Stunden (oder mehr) dauern, bis dieser Prozess abgeschlossen ist. (Als allgemeine Richtlinie dauert es etwa eine Stunde, bis 5.000 Benutzerkonten verarbeiten werden.)

An diesem Punkt wird eine oder mehrere Richtlinien für Informationsbarrieren auf den inaktiven Status festgelegt. Von hier aus können Sie eine der folgenden Aktionen ausführen:

- Behalten Sie es bei (eine auf inaktive Richtlinie festgelegte Richtlinie hat keine Auswirkungen auf Benutzer)
- [Bearbeiten einer Richtlinie](#edit-a-policy) 
- [Entfernen einer Richtlinie](#remove-a-policy)

## <a name="remove-a-policy"></a>Entfernen einer Richtlinie

1. Verwenden Sie zum Anzeigen einer Liste der aktuellen Richtlinien für Informationsbarrieren das **Cmdlet Get-InformationBarrierPolicy.**

    Syntax: `Get-InformationBarrierPolicy`

    Identifizieren Sie in der Liste der Ergebnisse die Richtlinie, die Sie entfernen möchten. Notieren Sie sich die GUID und den Namen der Richtlinie. Stellen Sie sicher, dass die Richtlinie auf den inaktiven Status festgelegt ist.

2. Verwenden Sie **das Cmdlet Remove-InformationBarrierPolicy** mit einem Identity-Parameter.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Remove-InformationBarrierPolicy -Identity GUID` | `Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p> In diesem Beispiel entfernen wir die Richtlinie mit guiD *43c37853-ea10-4b90-a23d-ab8c93772471*. |

    Bestätigen Sie die Änderung, wenn Sie dazu aufgefordert werden.

3. Wiederholen Sie die Schritte 1 bis 2 für jede Richtlinie, die Sie entfernen möchten.

4. Wenn Sie mit dem Entfernen von Richtlinien fertig sind, wenden Sie die Änderungen an. Verwenden Sie dazu das **Cmdlet Start-InformationBarrierPoliciesApplication.**

    Syntax: `Start-InformationBarrierPoliciesApplication`

    Änderungen werden von Benutzer zu Benutzer für Ihre Organisation angewendet. Wenn Ihre Organisation groß ist, kann es 24 Stunden (oder mehr) dauern, bis dieser Prozess abgeschlossen ist.

## <a name="stop-a-policy-application"></a>Beenden einer Richtlinienanwendung

Nachdem Sie mit der Anwendung von Richtlinien für Informationsbarrieren begonnen haben, verwenden Sie das folgende Verfahren, wenn Sie die Anwendung dieser Richtlinien verhindern möchten. Es dauert ungefähr 30 bis 35 Minuten, bis der Prozess beginnt.

1. Verwenden Sie zum Anzeigen des Status der neuesten Richtlinie für Informationsbarrieren das **Cmdlet Get-InformationBarrierPoliciesApplicationStatus.**

    Syntax: `Get-InformationBarrierPoliciesApplicationStatus`

    Notieren Sie sich die GUID der Anwendung.

2. Verwenden Sie **das Cmdlet Stop-InformationBarrierPoliciesApplication** mit einem Identity-Parameter.

    |**Syntax**|**Beispiel**|
    |:---------|:----------|
    | `Stop-InformationBarrierPoliciesApplication -Identity GUID` | `Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p> In diesem Beispiel wird die Anwendung von Richtlinien für Informationsbarrieren beendet. |

## <a name="resources"></a>Ressourcen

- [Übersicht über Informationsbarrieren](information-barriers.md)
- [Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)
- [Erfahren Sie mehr über Informationsbarrieren in Microsoft Teams](/MicrosoftTeams/information-barriers-in-teams)
- [Erfahren Sie mehr über Informationsbarrieren in SharePoint Online](/sharepoint/information-barriers)
- [Erfahren Sie mehr über Informationsbarrieren in OneDrive](/onedrive/information-barriers)
- [Attribute für Richtlinien für Informationsbarrieren](information-barriers-attributes.md)
- [Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md)