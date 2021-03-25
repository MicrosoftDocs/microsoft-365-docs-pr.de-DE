---
title: Erstellen und Verwalten von Gerätetags
description: Verwenden von Gerätetags zum Gruppieren von Geräten zum Erfassen des Kontexts und Aktivieren der erstellung dynamischer Listen im Rahmen eines Vorfalls
keywords: Tags, Gerätetags, Gerätegruppen, Gruppen, Korrektur, Ebene, Regeln,Ad-Gruppe, Rolle, Zuweisen, Rang
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
ms.openlocfilehash: 4a64d3242a34ec8bf6d5646513170aa35dd3a94c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068888"
---
# <a name="create-and-manage-device-tags"></a>Erstellen und Verwalten von Gerätetags

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Fügen Sie Tags auf Geräten hinzu, um eine logische Gruppenmitgliedschaft zu erstellen. Gerätetags unterstützen die ordnungsgemäße Zuordnung des Netzwerks, sodass Sie verschiedene Tags anfügen können, um Kontext zu erfassen und dynamische Listenerstellung als Teil eines Vorfalls zu ermöglichen. Tags können als Filter **in** der Gerätelistenansicht oder zum Gruppieren von Geräten verwendet werden. Weitere Informationen zur Gerätegruppe finden Sie unter [Create and manage device groups](machine-groups.md).

Sie können Tags auf Geräten mithilfe der folgenden Methoden hinzufügen:

- Verwenden des Portals
- Festlegen eines Registrierungsschlüsselwerts

> [!NOTE]
> Zwischen dem Hinzufügen eines Tags zu einem Gerät und seiner Verfügbarkeit in der Geräteliste und Geräteseite kann eine gewisse Latenz auftreten.  

Informationen zum Hinzufügen von Gerätetags mithilfe der API finden Sie unter [Add or remove device tags API](add-or-remove-machine-tags.md).

## <a name="add-and-manage-device-tags-using-the-portal"></a>Hinzufügen und Verwalten von Gerätetags mithilfe des Portals

1. Wählen Sie das Gerät aus, auf dem Sie Tags verwalten möchten. Sie können ein Gerät aus einer der folgenden Ansichten auswählen oder suchen:

   - **Dashboard für Sicherheitsvorgänge:** Wählen Sie den Gerätenamen im Abschnitt Top devices with active alerts aus.
   - **Warnungswarteschlange** : Wählen Sie den Gerätenamen neben dem Gerätesymbol aus der Benachrichtigungswarteschlange aus.
   - **Geräteliste** – Wählen Sie den Gerätenamen aus der Liste der Geräte aus.
   - **Suchfeld** : Wählen Sie im Dropdownmenü Gerät aus, und geben Sie den Gerätenamen ein.

     Sie können auch über die Datei- und IP-Ansichten zur Warnungsseite gelangen.

2. Wählen **Sie In der** Zeile Reaktionsaktionen die Option Tags verwalten aus.

    ![Abbildung der Schaltfläche "Tags verwalten"](images/manage-tags.png)

3. Geben Sie ein, um Tags zu suchen oder zu erstellen.

    ![Abbildung des Hinzufügens von Tags auf einem Gerät1](images/new-tags.png)

Tags werden der Geräteansicht hinzugefügt und werden  auch in der Gerätelistenansicht angezeigt. Anschließend können Sie den **Filter Tags verwenden,** um die relevante Liste der Geräte zu sehen.

>[!NOTE]
> Die Filterung funktioniert möglicherweise nicht für Tagnamen, die Klammer enthalten.<br>
> Wenn Sie ein neues Tag erstellen, wird eine Liste vorhandener Tags angezeigt. In der Liste werden nur Tags angezeigt, die über das Portal erstellt wurden. Vorhandene Tags, die auf Clientgeräten erstellt wurden, werden nicht angezeigt.

Sie können auch Tags aus dieser Ansicht löschen.

![Abbildung des Hinzufügens von Tags auf einem Gerät2](images/more-manage-tags.png)

## <a name="add-device-tags-by-setting-a-registry-key-value"></a>Hinzufügen von Gerätetags durch Festlegen eines Registrierungsschlüsselwerts

>[!NOTE]
> Gilt nur auf den folgenden Geräten:
>- Windows 10, Version 1709 oder höher
>- Windows Server, Version 1803 oder höher
>- Windows Server 2016
>- Windows Server 2012 R2
>- Windows Server 2008 R2 SP1
>- Windows 8.1
>- Windows 7 SP1

> [!NOTE] 
> Die maximale Anzahl von Zeichen, die in einem Tag festgelegt werden können, ist 200.

Geräte mit ähnlichen Tags können nützlich sein, wenn Sie kontextbezogene Aktionen auf eine bestimmte Liste von Geräten anwenden müssen.

Verwenden Sie den folgenden Registrierungsschlüsseleintrag, um ein Tag auf einem Gerät hinzuzufügen:

- Registrierungsschlüssel: `HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection\DeviceTagging\`
- Registrierungsschlüsselwert (REG_SZ): `Group`
- Registrierungsschlüsseldaten: `Name of the tag you want to set`

>[!NOTE]
>Das Gerätetag ist Teil des Geräteinformationsberichts, der einmal am Tag generiert wird. Alternativ können Sie den Endpunkt neu starten, der einen neuen Geräteinformationsbericht übertragen würde.
> 
> Wenn Sie ein Tag entfernen müssen, das mit dem obigen Registrierungsschlüssel hinzugefügt wurde, löschen Sie den Inhalt der Registrierungsschlüsseldaten, anstatt den Schlüssel "Gruppe" zu entfernen.
