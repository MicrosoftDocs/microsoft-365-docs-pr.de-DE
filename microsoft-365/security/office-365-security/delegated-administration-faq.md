---
title: Häufig gestellte Fragen zur delegierten Verwaltung
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: d6a87ce8-2c22-433a-b430-5eab14f6afdc
ms.custom:
- seo-marvel-apr2020
description: Dieses Thema enthält FAQs und Antworten für Microsoft-Partner und-Händler, die Delegierte Microsoft 365-Verwaltungsaufgaben durchführen möchten.
ms.openlocfilehash: d1522973292b290fd9f66f534ca23aeaa55ee756
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44209523"
---
# <a name="delegated-administration-faq"></a>Häufig gestellte Fragen zur delegierten Verwaltung

Dieses Thema enthält häufig gestellte Fragen und Antworten für Microsoft-Partner und-Händler, die Delegierte Verwaltungsaufgaben durchführen möchten, einschließlich der Möglichkeit, Exchange Online Schutz für andere Mandanten (Unternehmen) zu verwalten (EoP).

## <a name="im-a-reseller-and-i-need-to-manage-my-customers-tenants-how-does-this-work"></a>Ich bin Händler und muss die Mandanten meines Kunden verwalten. Wie funktioniert das?

Wenn Sie ein Microsoft-Partner oder-Wiederverkäufer sind und sich als Microsoft Advisor angemeldet haben, können Sie die Berechtigung zum Verwalten des Mandanten im Admin Center anfordern. Dies wird als Delegierte Verwaltung bezeichnet und ermöglicht es Ihnen, Ihren Microsoft 365-Mandanten (einschließlich EoP-Einstellungen) zu verwalten, als wären Sie ein Administrator in Ihrer Organisation. Die Schritte für die delegierte Verwaltung sind wie folgt:

1. Registrieren Sie sich als [Microsoft Office 365 Advisor](https://aka.ms/cloudbenefits).

2. Registrieren Sie sich für die delegierte Verwaltung. Bevor Sie mit der Verwaltung eines Kundenkontos beginnen können, muss der Kunde Sie als delegierten Administrator autorisieren. Um die Genehmigung des Kunden einzuholen, [senden Sie ihm zuerst ein Angebot für die delegierte Verwaltung](https://support.microsoft.com/office/26530dc0-ebba-415b-86b1-b55bc06b073e). (Sie können Ihrem Kunden die delegierte Verwaltung auch später anbieten.)

3. Erstellen Sie das Delegierte Administratorkonto mithilfe der Schritte unter [hinzufügen, ändern oder Löschen eines Subscription Advisor-Partners](https://docs.microsoft.com/office365/admin/misc/add-partner).

Visit [Partners: Erstellen Sie Ihr Unternehmen, und verwalten Sie das Partner Abonnement](https://support.office.com/article/30dd1681-47e0-4cbc-abfe-a222cd111319) , um weitere Informationen zum Einrichten der Delegierten Verwaltung zu erhalten.

## <a name="im-a-customer-not-a-reseller-how-can-set-up-delegated-administrator-for-my-sub-tenants"></a>Ich bin Kunde, kein Wiederverkäufer, wie kann ich einen delegierten Administrator für meine unter Mandanten einrichten?

Die delegierte Verwaltung ist derzeit nur für Wiederverkäufer und Partner verfügbar. Wir haben jedoch ein Beispielskript für Windows PowerShell bereitgestellt, mit dessen Hilfe Sie Richtlinie auf Ihre Untermandanten (Unternehmen) anwenden können. Weitere Informationen finden Sie unter [Beispielskript für das Anwenden von EOP-Einstellungen für mehrere Mandanten](sample-script-for-applying-eop-settings-to-multiple-tenants.md).

## <a name="can-i-prevent-my-sub-tenant-admin-from-modifying-my-policy"></a>Kann ich verhindern, dass mein unter mandantenadministrator meine Richtlinie ändert?

Microsoft 365 verfügt derzeit nicht über diese Funktion.

## <a name="can-i-get-consolidated-reporting-across-all-of-my-sub-tenants"></a>Kann ich einen konsolidierten Bericht über alle meine unter Mandanten erhalten?

Die konsolidierte Berichterstellung über die Unternehmen, die Sie verwalten, steht derzeit nicht für die Microsoft 365 Admin Center-Berichte zur Verfügung. Sie können dies jedoch mithilfe von [Microsoft Graph](https://docs.microsoft.com/graph/overview)tun.
