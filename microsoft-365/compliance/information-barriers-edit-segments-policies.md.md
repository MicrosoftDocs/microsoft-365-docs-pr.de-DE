---
title: Bearbeiten von Richtlinien für Informationsbarrieren
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
description: Hier erfahren Sie, wie Sie Richtlinien für Informationsbarrieren bearbeiten oder entfernen.
ms.openlocfilehash: 20a1dd62fa80469a7a31db9b5541064ae16b4e02
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080642"
---
# <a name="edit-or-remove-information-barrier-policies"></a>Bearbeiten (oder entfernen) von Richtlinien für Informationsbarrieren

Nachdem Sie [Richtlinien für Informationsbarrieren definiert](information-barriers-policies.md)haben, müssen Sie möglicherweise im Rahmen der [Problembehandlung](information-barriers-troubleshooting.md) oder als regelmäßige Wartung Änderungen an diesen Richtlinien oder an Ihren Benutzersegmenten vornehmen. Verwenden Sie diesen Artikel als Leitfaden.

## <a name="what-do-you-want-to-do"></a>Was möchten Sie machen?

|Aktion  |Beschreibung |
|---------|---------|
|[Bearbeiten von Benutzerkonto Attributen](#edit-user-account-attributes)     |Geben Sie Attribute in Azure Active Directory ein, die zum Definieren von Segmenten verwendet werden können.<br/>Bearbeiten Sie benutzerkontoattribute, wenn Benutzer nicht in den Segmenten enthalten sind, die Sie sein sollten, um zu ändern, in welchen Segmenten Benutzer sich befinden, oder um Segmente mit unterschiedlichen Attributen zu definieren.         |
|[Bearbeiten eines Segments](#edit-a-segment)     |Bearbeiten Sie Segmente, wenn Sie ändern möchten, wie ein Segment definiert wird. <br/>Sie haben beispielsweise ursprünglich Segmente mithilfe von *Department* definiert und möchten nun ein anderes Attribut verwenden *, wie Beispiels*Weise "" ".         |
|[Bearbeiten einer Richtlinie](#edit-a-policy)     |Bearbeiten Sie eine Richtlinie für Informationsbarrieren, wenn Sie die Funktionsweise einer Richtlinie ändern möchten.<br/>Anstatt die Kommunikation zwischen zwei Segmenten zu blockieren, können Sie beispielsweise festlegen, dass die Kommunikation nur zwischen bestimmten Segmenten erfolgen soll.         |
|[Festlegen einer Richtlinie auf inaktiver Status](#set-a-policy-to-inactive-status)     |Legen Sie eine Richtlinie auf inaktiven Status fest, wenn Sie Änderungen an einer Richtlinie vornehmen möchten oder wenn Sie nicht möchten, dass eine Richtlinie wirksam ist.         |
|[Entfernen einer Richtlinie](#remove-a-policy)     |Entfernen einer Richtlinie für Informationsbarrieren, wenn Sie eine bestimmte Richtlinie nicht mehr an Ort und Stelle benötigen.         |
|[Beenden einer Richtlinienanwendung](#stop-a-policy-application)     |Tun Sie dies, wenn Sie den Prozess der Anwendung von Richtlinien für Informationsbarrieren beenden möchten.<br/>Beachten Sie, dass das Beenden einer Richtlinienanwendung nicht sofort erfolgt und keine Richtlinien rückgängig gemacht wird, die bereits auf Benutzer angewendet wurden.         |
|[Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)     |Definieren Sie eine Richtlinie für Informationsbarrieren, wenn noch keine solchen Richtlinien vorhanden sind, und Sie müssen die Kommunikation zwischen bestimmten Benutzergruppen einschränken oder einschränken.         |
|[Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md)     |Lesen Sie diesen Artikel, wenn Sie unerwartete Probleme mit Informationsbarrieren ausführen.         |

> [!IMPORTANT]
> Um die in diesem Artikel beschriebenen Aufgaben ausführen zu können, muss Ihnen eine entsprechende Rolle zugewiesen sein, beispielsweise eine der folgenden:<br/>-Microsoft 365 Enterprise-Global-Administrator<br/>-Office 365 globaler Administrator<br/>-Compliance-Administrator<br/>-IB-Compliance-Management (Dies ist eine neue Rolle!)<p>Weitere Informationen zu den Voraussetzungen für Informationsbarrieren finden Sie unter [Prerequisites (for Information Barrier Policies)](information-barriers-policies.md#prerequisites).<p>Stellen Sie sicher, dass Sie [eine Verbindung mit Office 365 Security #a0 Compliance Center PowerShell herstellen](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell?view=exchange-ps).

## <a name="edit-user-account-attributes"></a>Bearbeiten von Benutzerkonto Attributen

Verwenden Sie dieses Verfahren zum Bearbeiten von Attributen, die für die Segmentierung von Benutzern verwendet werden. 

Wenn Sie beispielsweise ein Department-Attribut verwenden und für ein oder mehrere Benutzerkonten derzeit keine Werte für die Abteilung aufgeführt sind, müssen Sie diese Benutzerkonten bearbeiten, um Abteilungsinformationen einzubeziehen. 

Benutzerkontoattribute werden für die Definition von Segmenten verwendet, sodass Richtlinien für Informationsbarrieren zugewiesen werden können.

1. Verwenden Sie zum Anzeigen von Details für ein bestimmtes Benutzerkonto, wie Attributwerte und zugewiesene Segmente, das Cmdlet **Get-InformationBarrierRecipientStatus** mit Identitäts Parametern. 

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Get-InformationBarrierRecipientStatus -Identity <value> -Identity2 <value>` <p>   Sie können einen beliebigen Wert verwenden, der jeden Benutzer eindeutig identifiziert, beispielsweise Name, Alias, Distinguished Name, kanonischer Domänenname, e-Mail-Adresse oder GUID. <p>   (Sie können dieses Cmdlet auch für einen einzelnen Benutzer verwenden: `Get-InformationBarrierRecipientStatus -Identity <value>`)      |`Get-InformationBarrierRecipientStatus -Identity meganb -Identity2 alexw`  <p>   In diesem Beispiel wird auf zwei Benutzerkonten in Office 365 verwiesen: *meganb* für *Megan*und *alexw* für *Alex*.         |

2. Bestimmen Sie, welches Attribut Sie für Ihr Benutzerkontoprofil (en) bearbeiten möchten. Weitere Informationen finden Sie unter [Attribute for Information Barrier Policies](information-barriers-attributes.md) . 

3. Bearbeiten Sie ein oder mehrere Benutzerkonten, um Werte für das Attribut einzuschließen, das Sie im vorherigen Schritt ausgewählt haben. Verwenden Sie dazu eines der folgenden Verfahren:

    - Informationen zum Bearbeiten eines einzelnen Kontos finden Sie unter [Hinzufügen oder Aktualisieren der Profilinformationen eines Benutzers mithilfe von Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).

    - Informationen zum Bearbeiten mehrerer Konten (oder zum Bearbeiten eines einzelnen Kontos mithilfe von PowerShell) finden Sie unter [Konfigurieren von Benutzerkontoeigenschaften mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/configure-user-account-properties-with-office-365-powershell).

## <a name="edit-a-segment"></a>Bearbeiten eines Segments

Verwenden Sie dieses Verfahren bearbeiten der Definition eines Benutzersegments. Beispielsweise können Sie den Namen eines Segments oder den Filter ändern, der verwendet wird, um zu bestimmen, wer im Segment enthalten ist.

1. Verwenden Sie das Cmdlet **Get-OrganizationSegment** , um alle vorhandenen Segmente anzuzeigen.
    
    Syntax`Get-OrganizationSegment`

    Es wird eine Liste mit Segmenten und Details für jede, wie Segmenttyp, den UserGroupFilter-Wert, der erstellt oder zuletzt geändert, Guid, und so weiter angezeigt.

    > [!TIP]
    > Drucken oder speichern Sie die Liste der Segmente als Referenz später. Wenn Sie beispielsweise ein Segment bearbeiten möchten, müssen Sie dessen Namen oder den Wert ermitteln (dieser wird mit dem Parameter Identity verwendet).

2. Verwenden Sie zum Bearbeiten eines Segments das Cmdlet " **OrganizationSegment** " mit dem Parameter " **Identity** " und den relevanten Details. 

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Set-OrganizationSegment -Identity GUID -UserGroupFilter "attribute -eq 'attributevalue'"`     |`Set-OrganizationSegment -Identity c96e0837-c232-4a8a-841e-ef45787d8fcd -UserGroupFilter "Department -eq 'HRDept'"` <p>In diesem Beispiel haben wir für das Segment mit dem GUID- *c96e0837-C232-4a8a-841e-ef45787d8fcd*den Namen der Abteilung in "HRDept" geändert.         |

Wenn Sie die Bearbeitung von Segmenten für Ihre Organisation abgeschlossen haben, können Sie die Richtlinien für Informationsbarrieren entweder [definieren](information-barriers-policies.md#part-2-define-information-barrier-policies) oder [Bearbeiten](#edit-a-policy) .

## <a name="edit-a-policy"></a>Bearbeiten einer Richtlinie

1. Verwenden Sie das Cmdlet **Get-InformationBarrierPolicy** , um eine Liste der aktuellen Information Barrier-Richtlinien anzuzeigen.

    Syntax`Get-InformationBarrierPolicy`

    Identifizieren Sie in der Ergebnisliste die Richtlinie, die Sie ändern möchten. Beachten Sie die GUID und den Namen der Richtlinie.

2. Verwenden Sie das Cmdlet "InformationBarrierPolicy" mit einem **Identity** **-** Parameter, und geben Sie die Änderungen an, die Sie vornehmen möchten.

    Beispiel: angenommen, eine Richtlinie wurde definiert, um zu verhindern, dass das *Forschungs* Segment mit den *Vertriebs* -und *Marketing* Segmenten kommuniziert. Die Richtlinie wurde mithilfe dieses Cmdlets definiert:`New-InformationBarrierPolicy -Name "Research-SalesMarketing" -AssignedSegment "Research" -SegmentsBlocked "Sales","Marketing"`
    
    Angenommen, wir möchten diese ändern, damit Personen im *Forschungs* Segment nur mit Personen im *HR* -Segment kommunizieren können. Um diese Änderung vorzunehmen, verwenden wir dieses Cmdlet:`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471 -SegmentsAllowed "HR"`

    In diesem Beispiel haben wir "SegmentsBlocked" in "SegmentsAllowed" geändert und das *HR* -Segment angegeben.

3. Wenn Sie die Bearbeitung einer Richtlinie abgeschlossen haben, sollten Sie Ihre Änderungen übernehmen. (Weitere Informationen finden Sie unter [Apply Information Barrier Policies](information-barriers-policies.md#part-3-apply-information-barrier-policies).)

## <a name="set-a-policy-to-inactive-status"></a>Festlegen einer Richtlinie auf inaktiver Status

1. Verwenden Sie das Cmdlet **Get-InformationBarrierPolicy** , um eine Liste der aktuellen Information Barrier-Richtlinien anzuzeigen.

    Syntax`Get-InformationBarrierPolicy`

    Identifizieren Sie in der Ergebnisliste die Richtlinie, die Sie ändern möchten (oder entfernen). Beachten Sie die GUID und den Namen der Richtlinie.

2. Um den Status der Richtlinie auf inaktiv festzulegen, verwenden Sie das Cmdlet "InformationBarrierPolicy" mit einem Identity-Parameter und dem State **-** Parameter auf "inaktiv" festgelegt.

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Set-InformationBarrierPolicy -Identity GUID -State Inactive`     |`Set-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c9377247 -State Inactive` <p>In diesem Beispiel wird eine Richtlinie für Informationsbarrieren festgelegt, die GUID *43c37853-EA10-4b90-a23d-ab8c9377247* in einen inaktiven Status hat.         |

3. Verwenden Sie das Cmdlet **Start-InformationBarrierPoliciesApplication** , um die Änderungen zu übernehmen.

    Syntax`Start-InformationBarrierPoliciesApplication`

    Änderungen werden angewendet, Benutzer nach Benutzer, für Ihre Organisation. Wenn Ihre Organisation groß ist, kann es 24 Stunden (oder mehr) dauern, bis dieser Prozess abgeschlossen ist. (Als allgemeine Richtlinie dauert es etwa eine Stunde, 5.000-Benutzerkonten zu verarbeiten.)

Zu diesem Zeitpunkt werden mindestens eine Richtlinie für Informationsbarrieren auf inaktiver Status festgelegt. Von hier aus können Sie einen der folgenden Schritte ausführen:
- Beibehalten (eine auf inaktiven Status festgelegte Richtlinie hat keine Auswirkungen auf die Benutzer)
- [Bearbeiten einer Richtlinie](#edit-a-policy) 
- [Entfernen einer Richtlinie](#remove-a-policy)

## <a name="remove-a-policy"></a>Entfernen einer Richtlinie

1. Verwenden Sie das Cmdlet **Get-InformationBarrierPolicy** , um eine Liste der aktuellen Information Barrier-Richtlinien anzuzeigen.

    Syntax`Get-InformationBarrierPolicy`

    Identifizieren Sie in der Ergebnisliste die Richtlinie, die Sie entfernen möchten. Beachten Sie die GUID und den Namen der Richtlinie. Stellen Sie sicher, dass die Richtlinie auf inaktiver Status festgelegt ist.

2. Verwenden Sie das Cmdlet **Remove-InformationBarrierPolicy** mit einem Identity-Parameter.

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Remove-InformationBarrierPolicy -Identity GUID`     |`Remove-InformationBarrierPolicy -Identity 43c37853-ea10-4b90-a23d-ab8c93772471` <p>In diesem Beispiel wird die Richtlinie mit GUID- *43c37853-EA10-4b90-a23d-ab8c93772471*entfernt.          |

    Bestätigen Sie die Änderung, wenn Sie dazu aufgefordert werden.

3. Wiederholen Sie die Schritte 1-2 für jede Richtlinie, die Sie entfernen möchten.

4. Wenn Sie das Entfernen von Richtlinien abgeschlossen haben, wenden Sie die Änderungen an. Verwenden Sie dazu das Cmdlet **Start-InformationBarrierPoliciesApplication** .

    Syntax`Start-InformationBarrierPoliciesApplication`

    Änderungen werden angewendet, Benutzer nach Benutzer, für Ihre Organisation. Wenn Ihre Organisation groß ist, kann es 24 Stunden (oder mehr) dauern, bis dieser Prozess abgeschlossen ist.

## <a name="stop-a-policy-application"></a>Beenden einer Richtlinienanwendung

Wenn Sie die Anwendung von Richtlinien für Informationsbarrieren gestartet haben und diese Richtlinien nicht mehr angewendet werden sollen, verwenden Sie das folgende Verfahren. Denken Sie daran, dass es ungefähr 30-35 Minuten dauern wird, bis der Prozess beginnt.

1. Verwenden Sie das Cmdlet **Get-InformationBarrierPoliciesApplicationStatus** , um den Status der neuesten Informations Barriere-Richtlinienanwendung anzuzeigen.

    Syntax`Get-InformationBarrierPoliciesApplicationStatus`

    Beachten Sie die GUID der Anwendung.

2. Verwenden Sie das Cmdlet **Stop-InformationBarrierPoliciesApplication** mit einem Identity-Parameter.

    |Syntax  |Beispiel  |
    |---------|---------|
    |`Stop-InformationBarrierPoliciesApplication -Identity GUID`     |`Stop-InformationBarrierPoliciesApplication -Identity 46237888-12ca-42e3-a541-3fcb7b5231d1` <p>In diesem Beispiel wird das Anwenden von Richtlinien für Informationsbarrieren angehalten.         |

## <a name="related-articles"></a>Verwandte Artikel

[Hier erhalten Sie einen Überblick über Informationsbarrieren](information-barriers.md)

[Definieren von Richtlinien für Informationsbarrieren](information-barriers-policies.md)

[Weitere Informationen zu Informationsbarrieren in Microsoft Teams](https://docs.microsoft.com/MicrosoftTeams/information-barriers-in-teams)

[Attribute für Richtlinien für Informationsbarrieren](information-barriers-attributes.md)

[Problembehandlung bei Informationsbarrieren](information-barriers-troubleshooting.md)
