---
title: Zuweisen von Geräten zu einer Bereitstellungsgruppe
description: Angeben der Bereitstellungsgruppe, in der sich Geräte befinden sollen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 19465d2d2f077859490c106b9c01f08beb6e3906
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985575"
---
# <a name="assign-devices-to-a-deployment-group"></a>Zuweisen von Geräten zu einer Bereitstellungsgruppe

Microsoft Managed Desktop den verschiedenen Bereitstellungsgruppen Geräte zuweisen. Sie können jedoch mithilfe des Verwaltungsportals festlegen oder ändern, dass ein Gerät einem Gerät zugewiesen ist. Sie ändern die Zuweisung, nachdem ein Gerät registriert wurde oder nachdem ein Benutzer registriert wurde.

> [!IMPORTANT]
> Wenn Sie die Zuweisung ändern, werden richtlinien, die für diese Gruppe spezifisch sind, auf das Gerät angewendet. Die Änderung kann die neueste Version von Windows 10 installieren (einschließlich aller neuen Features oder Qualitätsupdates). Es empfiehlt sich, zunächst nur einige Geräte zu verschieben und dann die resultierende Benutzererfahrung zu überprüfen. Beachten Sie, dass bestimmte Updates das Gerät neu starten. Überprüfen Sie, ob Sie die richtigen Geräte ausgewählt haben, die Sie zuweisen möchten. Es kann bis zu 24 Stunden dauern, bis die Zuordnung wirksam wird.

Führen Sie die folgenden Schritte aus, um einer Bereitstellungsgruppe Geräte zuzuweisen. Wenn Sie separate Geräte in verschiedene Gruppen verschieben möchten, wiederholen Sie diese Schritte für jede Gruppe.

1. Wählen Sie in Microsoft Endpoint Manager im linken Bereich **"Geräte"** aus. **Wählen** Sie im Abschnitt **Microsoft Managed Desktop** Geräte aus.
2. Wählen Sie die Geräte aus, die Sie zuweisen möchten. Alle ausgewählten Geräte werden der von Ihnen angegebenen Gruppe zugewiesen.
3. Wählen Sie im Menü **Geräteaktionen** aus.
4. Wählen Sie **"Gerät zu Gruppe zuweisen"** aus. Ein Fly-In wird geöffnet.
5. Verwenden Sie das Dropdownmenü, um die Gruppe auszuwählen, in die Geräte verschoben werden sollen, und wählen Sie dann **"Speichern"** aus. Die **von zugewiesene Gruppe** wird in **"Ausstehend"** geändert.

Wenn die Zuweisung abgeschlossen ist, ändert sich die **Gruppe, die von zugewiesen wurde,** zu **"Administrator"** (sie hat angegeben, dass Sie die Änderung vorgenommen haben), und in der **Spalte "Gruppe"** wird die neue Gruppenzuweisung angezeigt.

> [!NOTE]
> Sie können Geräte nicht in andere Gruppen verschieben, wenn sie sich im Registrierungsstatus "Fehler" oder "Ausstehend" befinden.
>
>Wenn ein Gerät nicht ordnungsgemäß entfernt wurde, könnte der Status "bereit" angezeigt werden. Wenn Sie ein solches Gerät verschieben, ist es möglich, dass die Verschiebung nicht abgeschlossen wird. Wenn in Schritt 5 keine **Gruppe durch** Änderung an **"Ausstehend"** zugewiesen wird, überprüfen Sie, ob das Gerät verfügbar ist, indem Sie in Intune danach suchen. Weitere Informationen finden Sie unter [Anzeigen von Gerätedetails in Intune](/mem/intune/remote-actions/device-inventory).