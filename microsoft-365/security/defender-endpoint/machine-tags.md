---
title: Erstellen und Verwalten von Gerätekategorien
description: Verwenden von Gerätetags zum Gruppieren von Geräten zum Erfassen von Kontext und Aktivieren der dynamischen Listenerstellung als Teil eines Vorfalls
keywords: Tags, Gerätetags, Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln, AAD-Gruppe, Rolle, zuweisen, Rangfolge
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 83dd2483b93b2f4fe520973ce05346f59baf2f28
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453585"
---
# <a name="create-and-manage-device-tags"></a>Erstellen und Verwalten von Gerätekategorien

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Fügen Sie Kategorien auf Geräten hinzu, um eine logische Gruppenzugehörigkeit zu erstellen. Gerätekategorien unterstützen die ordnungsgemäße Zuordnung des Netzwerks, sodass Sie verschiedene Kategorien anfügen können, um den Kontext zu erfassen und die dynamische Listenerstellung als Teil eines Vorfalls zu ermöglichen. Tags können als Filter in der **Gerätelistenansicht** oder zum Gruppieren von Geräten verwendet werden. Weitere Informationen zur Gerätegruppierung finden Sie unter [Erstellen und Verwalten von Gerätegruppen.](machine-groups.md)

Sie können Tags auf Geräten auf folgende Weise hinzufügen:

- Das Portal verwenden
- Einen Registrierungsschlüsselwert festlegen

> [!NOTE]
> Zwischen dem Hinzufügen eines Tags zu einem Gerät und dessen Verfügbarkeit in der Geräteliste und auf der Geräteseite kann eine gewisse Latenz auftreten.  

Informationen zum Hinzufügen von Gerätekategorien mithilfe der API finden Sie unter [Hinzufügen oder Entfernen von Gerätekategorien-API](add-or-remove-machine-tags.md).

## <a name="add-and-manage-device-tags-using-the-portal"></a>Hinzufügen und Verwalten von Gerätekategorien über das Portal

1. Wählen Sie das Gerät aus, auf dem Sie Kategorien verwalten möchten. Sie können ein Gerät aus einer der folgenden Ansichten auswählen oder danach suchen:

   - **Dashboard für Sicherheitsvorgänge** – Wählen Sie den Gerätenamen im Abschnitt "Top devices with active alerts" aus.
   - **Benachrichtigungswarteschlange** – Wählen Sie den Gerätenamen neben dem Gerätesymbol aus der Benachrichtigungswarteschlange aus.
   - **Geräteliste** – Wählen Sie den Gerätenamen aus der Geräteliste aus.
   - **Suchfeld** – Wählen Sie im Dropdownmenü "Gerät" aus und geben Sie den Gerätenamen ein.

     Sie können die Benachrichtigungsseite auch über die Datei- und IP-Ansichten öffnen.

2. Wählen Sie **Kategorien verwalten** aus der Zeile "Antwortaktionen" aus.

    :::image type="content" alt-text="Abbildung der Schaltfläche &quot;Tags verwalten&quot;." source="images/manage-tags-option.png":::

3. Typ zum Suchen oder Erstellen von Tags

    :::image type="content" alt-text="Abbildung des Hinzufügens von Tags auf einem Gerät1." source="images/create-new-tag.png":::

Tags werden der Geräteansicht hinzugefügt und werden auch in der **Gerätelistenansicht** angezeigt. Anschließend können Sie den **Tags-Filter** verwenden, um die relevante Liste der Geräte anzuzeigen.

>[!NOTE]
> Das Filtern funktioniert möglicherweise nicht für Tagnamen, die Klammern enthalten.<br>
> Wenn Sie ein neues Tag erstellen, wird eine Liste vorhandener Tags angezeigt. In der Liste werden nur Tags angezeigt, die über das Portal erstellt wurden. Vorhandene Tags, die von Clientgeräten erstellt wurden, werden nicht angezeigt.

Sie können tags auch aus dieser Ansicht löschen.

:::image type="content" alt-text="Abbildung des Hinzufügens von Tags auf einem Gerät2." source="images/new-tag-label-display.png":::

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts

>[!NOTE]
> Gilt nur für die folgenden Geräte:
>- Windows 10, Version 1709 oder höher
>- Windows Server, Version 1803 oder höher
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> Die maximale Anzahl von Zeichen, die in einem Tag festgelegt werden können, beträgt 200.

Geräte mit ähnlichen Tags können nützlich sein, wenn Sie kontextbezogene Aktionen auf eine bestimmte Liste von Geräten anwenden müssen.

Verwenden Sie den folgenden Registrierungsschlüsseleintrag, um ein Tag auf einem Gerät hinzuzufügen:

- Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Registrierungsschlüsselwert (REG_SZ): `Group`
- Registrierungsschlüsseldaten: `Name of the tag you want to set`

>[!NOTE]
>Das Gerätetag ist Teil des Geräteinformationsberichts, der einmal täglich generiert wird. Alternativ können Sie den Endpunkt neu starten, der einen neuen Geräteinformationsbericht übertragen würde.
> 
> Wenn Sie ein Tag entfernen müssen, das mit dem oben genannten Registrierungsschlüssel hinzugefügt wurde, löschen Sie den Inhalt der Registrierungsschlüsseldaten, anstatt den Schlüssel "Gruppe" zu entfernen.
