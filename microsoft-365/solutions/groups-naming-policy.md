---
title: Microsoft 365 gruppenbenennungsrichtlinie
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Hier erfahren Sie, wie Sie eine Benennungsrichtlinie für Microsoft 365-Gruppen erstellen.
ms.openlocfilehash: 9bc0a4c7e1ae6ad532c97b442a2bc50880a942fc
ms.sourcegitcommit: 884ac262443c50362d0c3ded961d36d6b15d8b73
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49698675"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 gruppenbenennungsrichtlinie

Sie können eine gruppenbenennungsrichtlinie verwenden, um eine konsistente Benennungsstrategie für Gruppen zu erzwingen, die von Benutzern in Ihrer Organisation erstellt wurden. Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

Die Benennungsrichtlinie wird auf Gruppen angewendet, die für alle Gruppen Arbeitsauslastungen erstellt werden (wie Outlook, Microsoft Teams, SharePoint, Planer, jammern usw.). Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.

> [!TIP]
> Eine Microsoft 365-gruppenbenennungsrichtlinie gilt nur für Microsoft 365-Gruppen. Sie gilt nicht für in Exchange Online erstellte Verteilergruppen. Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:

- **Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu definieren (beispielsweise "US \_ My Group \_ Engineering"). Bei den Präfixen/Suffixen kann es sich entweder um feste Zeichenfolgen oder Benutzerattribute wie [Department] handeln, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.

- **Benutzerdefinierte blockierte Wörter**: Sie können eine Gruppe blockierter Wörter für Ihre Organisation hochladen, die in von Benutzern erstellten Gruppen blockiert werden. (Beispiel: "CEO, Abrechnung, HR").

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Wenn Sie Azure AD Benennungsrichtlinie für Microsoft 365-Gruppen verwenden, müssen Sie für jeden eindeutigen Benutzer (einschließlich Gäste), der Mitglied einer oder mehrerer Microsoft 365-Gruppen ist, eine Azure Active Directory Premium P1-Lizenz oder Azure AD Basic edu-Lizenz besitzen, jedoch nicht unbedingt zuweisen.

Dies ist auch für den Administrator erforderlich, der die Benennungsrichtlinie für Gruppen erstellt.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix Benennungsrichtlinie

Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.

### <a name="fixed-strings"></a>Feste Zeichenfolgen

Sie können kurze Zeichenfolgen verwenden, mit denen Sie Gruppen in der GAL und der linken Navigation der Gruppen Arbeitsauslastungen unterscheiden können. Einige der gängigen Präfix Suffixe sind Schlüsselwörter wie "GRP \_ Name", " \# Name", " \_ Name".

### <a name="attributes"></a>Attribute

Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".

Beispiele:

- Richtlinie = "GRP [Gruppenname] [Abteilung]"
- Abteilung des Benutzers = Entwicklung
- Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"

Die unterstützten Azure Active Directory (Azure AD)-Attribute sind [Department], [Firma], [Office], [StateOrProvince], [CountryOrRegion] und [title].

- Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen betrachtet, beispielsweise [PostalCode].

- Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.

Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.

### <a name="things-to-look-out-for"></a>Worauf Sie achten sollten

- Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.

- Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden. Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppen Alias nicht zulässig sind, werden Sie nur auf den Gruppennamen angewendet. In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.

  > [!NOTE]
  > Ein Punkt (.) oder ein Bindestrich (-) ist an beliebiger Stelle im Gruppennamen zulässig, außer am Anfang oder Ende des Namens. Ein Unterstrich (_) ist an beliebiger Stelle im Gruppennamen zulässig, einschließlich am Anfang oder Ende des Namens.

- Wenn Sie jammern Office 365 verbundene Gruppen verwenden, vermeiden Sie die Verwendung der folgenden Zeichen in ihrer Benennungsrichtlinie: @, \# , \[ , \] , \<, and \> . Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.

> [!Tip]
> - Verwenden Sie kurze Zeichenfolgen als Namenszusatz.
> - Verwenden Sie Attribute mit Werten.
> - Lassen Sie sich nicht zu kreativ sein, die gesamte Name-Länge hat maximal 264 Zeichen.
> - Laden Sie spezifische blockierte Wörter Ihrer Organisation hoch, um die Nutzung einzuschränken.

## <a name="custom-blocked-words"></a>Benutzerdefinierte blockierte Wörter

Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.

Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen.

**Dinge, die Sie beachten** sollten:

- Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.

- Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.

- Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.

- Es gibt ein Limit von 5000 Wörtern, die als blockierte Wörter festgelegt werden können.

## <a name="admin-override"></a>Außerkraftsetzung durch Administratoren

Einige Administratoren sind von diesen Richtlinien für alle Gruppen Arbeitslasten und-Endpunkte ausgenommen, sodass Sie Gruppen mit diesen blockierten Wörtern und mit Ihren gewünschten Benennungskonventionen erstellen können. Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.

- Globaler Administrator

- Partnersupport der Ebene 1

- Partnersupport der Ebene 2

- Administrator für Benutzerkonten

## <a name="how-to-set-up-the-naming-policy"></a>Vorgehensweise zum Einrichten der Benennungsrichtlinie

So richten Sie eine Benennungsrichtlinie ein:

1. Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com) unter **Verwalten** auf **Gruppen**.
2. Klicken Sie unter **Einstellungen** auf **Benennungsrichtlinie**.
3. Wählen Sie die Registerkarte **Gruppenbenennungsrichtlinie** aus.
4. Wählen Sie unter **Aktuelle Richtlinie** aus, ob ein Präfix oder ein Suffix oder beides benötigt wird, und aktivieren Sie die entsprechenden Kontrollkästchen.
5. Wählen Sie zwischen **Attribut** und **Zeichenfolge** für jede Zeile aus, und geben Sie dann das Attribut oder die Zeichenfolge an.
6. Wenn Sie die benötigten Präfixe und Suffixe hinzugefügt haben, klicken Sie auf **Speichern**.

![Screenshot der Einstellungen für Benennungsrichtlinien für Gruppen in Azure Active Directory](../media/groups-naming-policy-azure.png)

## <a name="related-topics"></a>Verwandte Themen

[Planung der Collaboration-Steuerung Schritt für Schritt](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Steuerungsplans für die Zusammenarbeit](collaboration-governance-first.md)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?linkid=868341)
