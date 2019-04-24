---
title: Verwalten von apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: ce2765ef2ab176dc5d9a1d41db7e26549b007d79
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32285945"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Verwalten von Branchen-apps in Microsoft Managed Desktop

<!--Application management -->

Es gibt verschiedene Möglichkeiten, APP-Updates für apps zu verwalten, die Sie auf Microsoft Managed Desktop und auf Ihren von Microsoft verwalteten Desktop-Geräten bereitgestellt haben. Sie können APP-Updates in Microsoft Managed Desktop Portal oder InTune vornehmen. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aktualisieren von Branchen-apps in Microsoft Managed Desktop

**So aktualisieren Sie Ihre Branchen-apps in Microsoft Managed Desktop Portal**
1. Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.
2. Wählen Sie unter **Inventar**die Option **apps**aus.  
3. Wählen Sie die APP aus, die Sie aktualisieren möchten, und klicken Sie dann auf **Bearbeiten**.
4. Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus. 
5. Klicken Sie auf **App-Paketdatei**, und navigieren Sie, um eine neue APP-Paketdatei hochzuladen.
6. Wählen Sie **App-Paketdatei**aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die APP-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt. 

Die aktualisierte APP wird auf den Geräten der Benutzer bereitgestellt.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aktualisieren von Branchen-apps in InTune

**So aktualisieren Sie Ihre Branchen-apps in InTune**
1. Melden Sie sich beim [Azure-Portal](https://azure.portal.com)an.
2. Wählen Sie **alle Dienste** > **InTune**aus. InTune befindet sich im Abschnitt **Monitoring + Management** .
3. Wählen Sie **Client apps _GT_ apps**aus.
4. Suchen und wählen Sie Ihre APP in der Liste der Apps aus.
5. Wählen Sie im Blatt **Übersicht** die Option **Eigenschaften**aus.
6. Wählen Sie **App-Paketdatei**aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort der aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die APP-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte APP-Paket widerspiegelt.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Zurücksetzen einer APP auf eine frühere Version

Wenn bei der Bereitstellung einer neuen Version einer APP ein Fehler gefunden wird, können Sie einen Rollback zu einer früheren Version ausführen. Der hier beschriebene Prozess gilt für apps, bei denen der Typ als **Windows-MSI** -Branchen-APP oder **Windows-app (Win 32)-Vorschau** angezeigt wird.

**So führen Sie ein Rollback für eine Branchen-App auf eine frühere Version aus**

1. Melden Sie sich beim [Microsoft Managed Desktop Admin Portal](http://aka.ms/mmdportal)an.
2. Wählen Sie unter **Inventar**die Option **apps**aus.  
3. Wählen Sie die APP aus, die Sie zurücksetzen müssen, und wählen Sie dann **Bearbeiten**aus.
4. Wählen Sie unter **Verwalten**die Option **Eigenschaften**aus. 
    - Wählen Sie **app-Informationen**für **Windows-MSI-App-** Apps aus, und wählen Sie dann unter **App-Version ignorieren**die Option **Ja**aus.
    - Wählen Sie für **Windows-app (Win 32)-Vorschau** Apps die Option **app-Informationen**aus, wählen Sie **Erkennungsregeln**aus, und wählen Sie dann **Hinzufügen**aus. 
    Wenn eine MSI-Regel vorhanden ist, stellen Sie sicher, dass die **MSI-Produkt Versionsüberprüfung** auf **Nein**festgelegt ist.
5. [Laden Sie eine frühere Version der APP-Quelldatei in das](../get-started/deploy-apps.md) Microsoft Managed Desktop Admin Portal hoch.  

