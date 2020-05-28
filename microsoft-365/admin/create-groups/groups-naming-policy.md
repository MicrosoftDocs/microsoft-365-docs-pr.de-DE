---
title: Benennungsrichtlinie für Gruppen
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MST160
- MET150
- MOE150
ms.assetid: 6ceca4d3-cad1-4532-9f0f-d469dfbbb552
description: Hier erfahren Sie, wie Sie eine Benennungsrichtlinie für Microsoft 365-Gruppen erstellen.
ms.openlocfilehash: 38b5bbed0c6e4c12af2f529568a53df329d9a933
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44388005"
---
# <a name="groups-naming-policy"></a>Benennungsrichtlinie für Gruppen

Mithilfe der Gruppenbenennungsrichtlinie können Sie eine konsistente Benennungsstrategie für Gruppen erzwingen, die von Benutzern in Ihrer Organisation erstellt werden. Eine Benennungsrichtlinie kann Ihnen und Ihren Benutzern bei der Identifizierung der Funktion der Gruppe, der Mitgliedschaft, der geografischen Region oder der Person helfen, die die Gruppe erstellt hat. Die Benennungsrichtlinie kann auch hilfreich beim Kategorisieren von Gruppen im Adressbuch sein. Mithilfe der Richtlinie können Sie bestimmte Wörter in Gruppennamen und -aliasen blockieren.

Die Benennungsrichtlinie wird auf Gruppen angewendet, die für alle Gruppen Arbeitsauslastungen erstellt werden (wie Outlook, Microsoft Teams, SharePoint, Planer, jammern usw.). Sie wird sowohl auf den Gruppennamen als auch auf den Gruppenalias angewendet. Außerdem wird sie angewendet, wenn ein Benutzer eine Gruppe erstellt und wenn ein Gruppenname oder -alias bei einer bestehenden Gruppe bearbeitet wird.

> [!TIP]
> Eine Microsoft 365-gruppenbenennungsrichtlinie gilt nur für Microsoft 365-Gruppen. Sie gilt nicht für in Exchange Online erstellte Verteilergruppen. Informationen zum Erstellen einer Benennungsrichtlinie für Verteilergruppen finden Sie unter [Erstellen einer Namensrichtlinie für Verteilergruppen](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-distribution-groups/create-group-naming-policy).

Die Gruppenbenennungsrichtlinie besteht aus den folgenden Features:

- **Präfix-Suffix-Benennungsrichtlinie**: Sie können Präfixe oder Suffixe verwenden, um die Benennungskonvention von Gruppen zu definieren (beispielsweise "US \_ My Group \_ Engineering"). Bei den Präfixen/Suffixen kann es sich entweder um feste Zeichenfolgen oder Benutzerattribute wie [Department] handeln, die basierend auf dem Benutzer ersetzt werden, der die Gruppe erstellt.

- **Benutzerdefinierte blockierte Wörter**: Sie können eine Gruppe blockierter Wörter für Ihre Organisation hochladen, die in von Benutzern erstellten Gruppen blockiert werden. (Beispiel: "CEO, Abrechnung, HR").

## <a name="licensing-requirements"></a>Lizenzierungsanforderungen

Wenn Sie Azure AD Benennungsrichtlinie für Microsoft 365-Gruppen verwenden, müssen Sie für jeden eindeutigen Benutzer (einschließlich Gäste), der Mitglied einer oder mehrerer Microsoft 365-Gruppen ist, eine Azure Active Directory Premium P1-Lizenz oder Azure AD Basic edu-Lizenz besitzen, jedoch nicht unbedingt zuweisen.

Dies gilt auch für den Administrator, der die Benennungsrichtlinie für Gruppen erstellt.

## <a name="prefix-suffix-naming-policy"></a>Präfix Suffix-Benennungsrichtlinie

Bei Präfixen und Suffixen kann es sich entweder um feste Zeichenfolgen oder um Benutzerattribute handeln.

### <a name="fixed-strings"></a>Feste Zeichenfolgen

Sie können kurze Zeichenfolgen verwenden, mit denen Sie Gruppen in der GAL und der linken Navigation der Gruppen Arbeitsauslastungen unterscheiden können. Einige der gängigen Präfix Suffixe sind Schlüsselwörter wie "GRP \_ Name", " \# Name", " \_ Name".

### <a name="attributes"></a>Attribute

Sie können Attribute verwenden, anhand derer Sie feststellen können, wer eine Gruppe erstellt hat, z. B. "[Abteilung]", und wo sie erstellt wurde "[Land]".

|||
|:-----|:-----|
|**Beispiele**|Richtlinie = "GRP [Gruppenname] [Abteilung]"|
||Abteilung des Benutzers = Entwicklung|
||Erstellter Gruppenname = "GRP Meine Gruppe Entwicklung"|

Die unterstützten Azure Active Directory (Azure AD)-Attribute sind [Department], [Firma], [Office], [StateOrProvince], [CountryOrRegion] und [title].

- Nicht unterstützte Benutzerattribute werden als feste Zeichenfolgen angesehen. Z. B. "[Postleitzahl]"

- Erweiterungsattribute und benutzerdefinierte Attribute werden nicht unterstützt.

Es empfiehlt sich, Attribute mit ausgefüllten Werten für alle Benutzer in Ihrer Organisation zu verwenden und Attribute mit längeren Werten zu vermeiden.

### <a name="things-to-look-out-for"></a>Worauf Sie achten sollten

- Während der Erstellung der Richtlinie ist die Gesamtlänge der Zeichenfolgen für Präfixe und Suffixe auf 53 Zeichen eingeschränkt.

- Präfixe und Suffixe können Sonderzeichen enthalten, die in Gruppennamen und Gruppenaliasen unterstützt werden. Wenn die Präfixe und Suffixe Sonderzeichen enthalten, die im Gruppen Alias nicht zulässig sind, werden Sie nur auf den Gruppennamen angewendet. In diesem Fall würden sich also die auf den Gruppennamen angewendeten Präfixe und Suffixe von den auf den Gruppennamen angewendeten unterscheiden.

- Wenn Sie Microsoft 365-verbundene Gruppen mit jammern verwenden, vermeiden Sie die Verwendung der folgenden Zeichen in ihrer Benennungsrichtlinie: @, \# , \[ , \] , \<, and \> . Wenn die Benennungsrichtlinie eines dieser Zeichen enthält, können normale Yammer-Benutzer keine Gruppen erstellen.

## <a name="custom-blocked-words"></a>Benutzerdefinierte blockierte Wörter

Sie können eine durch Trennzeichen getrennte Liste der blockierten Wörter eingeben, die in Gruppennamen und -aliasen blockiert werden.

Es erfolgt keine Suche nach Teilzeichenfolgen, d. h. es muss eine genaue Übereinstimmung zwischen dem vom Benutzer eingegebenen Namen und den benutzerdefinierten blockierten Wörtern bestehen, um eine Ablehnung auszulösen. Es erfolgt keine Suche nach Teilzeichenfolgen, sodass Benutzer ein Wort wie 'Klarschiff' verwenden können, obwohl 'Arsch' ein blockiertes Wort ist.

**Dinge, die Sie beachten**sollten:

- Bei blockierten Wörtern wird die Groß-/Kleinschreibung nicht berücksichtigt.

- Wenn ein Benutzer ein blockiertes Wort eingibt, zeigt der Gruppenclient eine Fehlermeldung mit dem gesperrten Wort an.

- Es bestehen keine Zeichenbeschränkungen für die verwendeten blockierten Wörter.

- Es gibt ein Limit von 5000 Wörtern, die als blockierte Wörter festgelegt werden können.

## <a name="admin-override"></a>Außerkraftsetzung durch Administratoren

Ausgewählte Administratoren sind übergreifend über alle Workloads und Endpunkte von diesen Richtlinien ausgenommen, sodass sie Gruppen mit den blockierten Wörtern und Benennungskonventionen nach eigenen Wünschen erstellen können. Es folgt eine Liste der Administratorrollen, die von der Gruppenbenennungsrichtlinie ausgenommen sind.

- Globaler Administrator

- Partnersupport der Ebene 1

- Partnersupport der Ebene 2

- Administrator für Benutzerkonten

- Verzeichnisautoren

## <a name="how-to-set-up-the-naming-policy"></a>Vorgehensweise zum Einrichten der Benennungsrichtlinie

So richten Sie eine Benennungsrichtlinie ein:

1. Klicken Sie in [Azure Active Directory](https://aad.portal.azure.com) unter **Verwalten** auf **Gruppen**.
2. Klicken Sie unter **Einstellungen** auf **Benennungsrichtlinie**.
3. Wählen Sie die Registerkarte **Gruppenbenennungsrichtlinie** aus.
4. Wählen Sie unter **Aktuelle Richtlinie** aus, ob ein Präfix oder ein Suffix oder beides benötigt wird, und aktivieren Sie die entsprechenden Kontrollkästchen.
5. Wählen Sie zwischen **Attribut** und **Zeichenfolge** für jede Zeile aus, und geben Sie dann das Attribut oder die Zeichenfolge an.
6. Wenn Sie die benötigten Präfixe und Suffixe hinzugefügt haben, klicken Sie auf **Speichern**.

![Screenshot der Einstellungen für Benennungsrichtlinien für Gruppen in Azure Active Directory](../../media/groups-naming-policy-azure.png)

> [!NOTE]
> StaffHub Teams bezieht sich nicht auf die Benennungsrichtlinie, die zugrunde liegende Microsoft 365-Gruppe wird jedoch nicht befolgt. Der StaffHub-Teamname wendet die Präfixe und Suffixe nicht an und wird nicht auf benutzerdefinierte blockierte Wörter überprüft. StaffHub jedoch wendet die Präfixe und Suffixe an und entfernt blockierte Wörter aus der zugrunde liegenden Microsoft 365-Gruppe.

## <a name="more-articles-on-naming-policy"></a>Weitere Artikel zur Benennungsrichtlinie

[Erzwingen einer Benennungsrichtlinie für Microsoft 365-Gruppen in Azure Active Directory](https://go.microsoft.com/fwlink/?linkid=868340)

[Azure Active Directory-Cmdlets für die Konfiguration von Gruppeneinstellungen](https://go.microsoft.com/fwlink/?linkid=868341)
