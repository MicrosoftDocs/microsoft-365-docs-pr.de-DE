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
recommendations: false
description: Erfahren Sie, wie Sie eine Benennungsrichtlinie für Microsoft 365 erstellen.
ms.openlocfilehash: 5ab5f252e2b81470413b4efea17b131613aabc18
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538171"
---
# <a name="microsoft-365-groups-naming-policy"></a>Microsoft 365 gruppenbenennungsrichtlinie

Sie können eine Gruppenbenennungsrichtlinie verwenden, um eine konsistente Benennungsstrategie für Gruppen zu erzwingen, die von Benutzern in Ihrer Organisation erstellt wurden. Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

Die Benennungsrichtlinie wird auf Gruppen angewendet, die für alle Gruppenworkloads erstellt werden (z. B. Outlook, Microsoft Teams, SharePoint, Planner, Yammer usw.). Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Sie wird auch angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn der Gruppenname, alias, eine Beschreibung oder ein Avatar für eine vorhandene Gruppe bearbeitet wird.

> [!TIP]
> Eine Microsoft 365 gruppenbenennungsrichtlinie gilt nur für Microsoft 365 Gruppen. Sie gilt nicht für in Exchange Online erstellte Verteilergruppen. Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:

- **Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu definieren (z. B. "US \_ My Group \_ Engineering"). Die Präfixe/Suffixe können entweder feste Zeichenfolgen oder Benutzerattribute wie [Abteilung] sein, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.

- **Benutzerdefinierte blockierte** Wörter: Sie können eine Gruppe blockierter Wörter hochladen, die für Ihre Organisation spezifisch sind und in Gruppen blockiert würden, die von Benutzern erstellt wurden. (Beispiel: "CEO Gehaltsabrechnung Personal").

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Die Verwendung der Azure AD-Benennungsrichtlinie für Microsoft 365-Gruppen erfordert, dass Sie eine Azure Active Directory Premium P1-Lizenz oder Azure AD Basic EDU-Lizenz für jeden eindeutigen Benutzer (einschließlich Gäste) besitzen, der Mitglied einer oder mehreren Microsoft 365-Gruppen ist.

Dies ist auch für den Administrator erforderlich, der die Gruppenbenennungsrichtlinie erstellt.

## <a name="prefix-suffix-naming-policy"></a>Prefix-Suffix Namensrichtlinie

Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.

### <a name="fixed-strings"></a>Feste Zeichenfolgen

Sie können kurze Zeichenfolgen verwenden, mit deren Hilfe Sie Gruppen in der GAL und in der linken Navigation der Gruppenworkloads unterscheiden können. Einige der gängigen Präfixsuffixe sind Schlüsselwörter wie "Grp \_ Name", \# "Name", \_ "Name"

### <a name="attributes"></a>Attribute

Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".

Beispiele:

- Richtlinie = "GRP [Gruppenname] [Abteilung]"
- Abteilung des Benutzers = Entwicklung
- Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"

Unterstützte Azure Active Directory (Azure AD)-Attribute sind [Department], [Company], [Office], [StateOrProvince], [CountryOrRegion] und [Title].

- Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen betrachtet, z. B. [postalCode].

- Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.

Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.

### <a name="things-to-look-out-for"></a>Dinge, auf die Sie achten müssen

- Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.

- Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden. Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppenalias nicht zulässig sind, werden sie nur auf den Gruppennamen angewendet. In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.

  > [!NOTE]
  > Ein Zeitraum (.) oder ein Bindestrich (-) ist an einer beliebigen Stelle im Gruppennamen zulässig, außer am Anfang oder Ende des Namens. Ein Unterstrich (_) ist an einer beliebigen Stelle im Gruppennamen zulässig, auch am Anfang oder Ende des Namens.

- Wenn Sie Yammer Office 365 verbundenen Gruppen verwenden, vermeiden Sie die verwendung der folgenden Zeichen in Ihrer Benennungsrichtlinie: @, \# , \[ , , \] \<, and \> . Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.

> [!Tip]
> - Verwenden Sie kurze Zeichenfolgen als Namenszusatz.
> - Verwenden Sie Attribute mit Werten.
> - Seien Sie nicht zu kreativ, die Gesamtnamenlänge beträgt maximal 264 Zeichen.
> - Laden Sie spezifische blockierte Wörter Ihrer Organisation hoch, um die Nutzung einzuschränken.

## <a name="custom-blocked-words"></a>Benutzerdefinierte blockierte Wörter

Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.

Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen.

**Dinge, auf die Sie achten müssen:**

- Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.

- Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.

- Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.

- Es gibt eine Grenze von 5000 Wörtern, die als blockierte Wörter festgelegt werden können.

## <a name="admin-override"></a>Außerkraftsetzung durch Administratoren

Einige Administratoren sind für alle Gruppenarbeitslasten und Endpunkte von diesen Richtlinien ausgenommen, sodass sie Gruppen mit diesen blockierten Wörtern und den gewünschten Benennungskonventionen erstellen können. Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.

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

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](/azure/active-directory/enterprise-users/groups-settings-cmdlets)