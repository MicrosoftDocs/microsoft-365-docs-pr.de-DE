---
title: Verwalten von apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 425ba674ca9911e4c93bda4fc9ad61cec7fb85b7
ms.sourcegitcommit: 3d37043c0447359c952dc99026c219dd69f6fb8d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/06/2019
ms.locfileid: "38012410"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Verwalten von Branchenanwendungen in Microsoft Managed Desktop

<!--Application management -->

Es gibt verschiedene Möglichkeiten, APP-Updates für apps zu verwalten, die Sie auf dem Microsoft Managed Desktop installiert und auf Ihren verwalteten Microsoft-Desktop-Geräten bereitgestellt haben. Sie können APP-Updates in Microsoft Managed Desktop Portal oder InTune vornehmen. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aktualisieren von Branchenanwendungen in Microsoft Managed Desktop

**So aktualisieren Sie Ihre Branchen-apps im Microsoft Managed Desktop Portal**
1. Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.
2. Wählen Sie unter **Inventar**die Option **apps**aus.  
3. Wählen Sie die APP aus, die Sie aktualisieren möchten, und klicken Sie dann auf **Bearbeiten**.
4. Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus. 
5. Klicken Sie auf **App-Paketdatei**und dann auf Durchsuchen, um eine neue APP-Paketdatei hochzuladen.
6. Wählen Sie **App-Paketdatei**aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die APP-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt. 

Die aktualisierte APP wird auf den Geräten Ihrer Benutzer bereitgestellt.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aktualisieren von Branchenanwendungen in InTune

**So aktualisieren Sie Ihre Branchen-apps in InTune**
1. Melden Sie sich beim [Azure-Portal](https://azure.portal.com)an.
2. Wählen Sie **alle Dienste** > **InTune**aus. InTune befindet sich im Abschnitt **Überwachung + Verwaltung** .
3. Wählen Sie **Client apps #a0 apps**aus.
4. Suchen Sie Ihre APP in der Liste der apps, und wählen Sie Sie aus.
5. Wählen Sie im Blatt **Übersicht** die Option **Eigenschaften**aus.
6. Wählen Sie **App-Paketdatei**aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die APP-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Wiederherstellen einer APP auf eine frühere Version

Wenn beim Bereitstelleneiner neuen Version einer APP ein Fehler festgestellt wurde, können Sie auf eine frühere Version zurücksetzen. Der hier dargestellte Vorgang gilt für apps, bei denen Type als **Windows-MSI** -Branchen-APP oder **Windows-app (Win 32) – Vorschau** angezeigt wird.

**So setzen Sie eine Branchen-App auf eine frühere Version zurück**

1. Melden Sie sich beim [Microsoft Managed Desktop-Verwaltungsportal](https://aka.ms/mmdportal)an.
2. Wählen Sie unter **Inventar**die Option **apps**aus.  
3. Wählen Sie die APP aus, die Sie für ein Rollback ausführen möchten, und wählen Sie dann **Bearbeiten**aus.
4. Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus. 
    - Wählen Sie für **Windows-MSI-App-** Apps die Option **app-Informationen**aus, und wählen Sie dann unter APP- **Version ignorieren**die Option **Ja**aus.
    - Für **Windows-app (Win 32) – Vorschau** von apps, wählen Sie **app-Informationen**aus, wählen Sie **Erkennungsregeln**aus, und wählen Sie dann **Hinzufügen**aus. 
    Wenn eine MSI-Regel vorhanden ist, stellen Sie sicher, dass die **MSI-Produkt Versionsüberprüfung** auf **Nein**festgelegt ist.
5. [Laden Sie eine frühere Version der APP-Quelldatei in das](../get-started/deploy-apps.md) Verwaltungsportal von Microsoft Managed Desktop hoch.  

