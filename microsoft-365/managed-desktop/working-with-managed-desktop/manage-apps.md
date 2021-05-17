---
title: Verwalten von Apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Business-Apps, die auf Microsoft Managed Desktop-Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600682"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Verwalten von Branchenanwendungen in Microsoft Managed Desktop

<!--Application management -->

Es gibt mehrere Möglichkeiten zum Verwalten von App-Updates für Apps, die Sie in Microsoft Managed Desktop integrierte und auf Ihren Microsoft Managed Desktop-Geräten bereitgestellt haben. Sie können App-Updates im Microsoft Managed Desktop-Portal oder intune erstellen. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aktualisieren von Unternehmensanwendungen in Microsoft Managed Desktop

**So aktualisieren Sie Ihre Business-Apps im Microsoft Managed Desktop-Portal**
1. Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal)
2. Wählen **Sie unter Inventar** die Option **Apps aus.**  
3. Wählen Sie die App aus, die Sie aktualisieren möchten, und wählen Sie dann **Bearbeiten aus.**
4. Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.** 
5. Klicken **Sie auf App-Paketdatei,** und navigieren Sie dann, um eine neue App-Paketdatei hochzuladen.
6. Wählen **Sie App-Paketdatei aus.**
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die App-Informationen werden mit den Paketinformationen aktualisiert.
8. Vergewissern Sie **sich, dass die App-Version** das aktualisierte App-Paket widerspiegelt. 

Die aktualisierte App wird auf den Geräten Ihres Benutzers bereitgestellt.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aktualisieren von Business-Apps in Intune

**So aktualisieren Sie Ihre Business-Apps in Intune**
1. Melden Sie sich beim [Azure-Portal an.](https://portal.azure.com)
2. Wählen **Sie Alle Dienste** Intune  >  **aus.** Intune befindet sich im **Abschnitt Überwachung + Verwaltung.**
3. Wählen **Sie Client-Apps > Apps aus.**
4. Suchen Und wählen Sie Ihre App in der Liste der Apps aus.
5. Wählen Sie **auf dem Blatt** Übersicht eigenschaften **aus.**
6. Wählen **Sie App-Paketdatei aus.**
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die App-Informationen werden mit den Paketinformationen aktualisiert.
8. Vergewissern Sie **sich, dass die App-Version** das aktualisierte App-Paket widerspiegelt.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Rollback einer App auf eine frühere Version

Wenn bei der Bereitstellung einer neuen Version einer App ein Fehler gefunden wird, können Sie ein Rollback auf eine frühere Version starten. Der hier beschriebene Prozess gilt für Apps, bei denen der Typ als **Windows MSI Line-of-Business-App oder Windows-App** **(Win 32) aufgeführt** ist – Vorschau

**So erstellen Sie ein Rollback einer Business-Line-of-Business-App auf eine frühere Version**

1. Melden Sie sich beim [Microsoft Managed Desktop Admin-Portal an.](https://aka.ms/mmdportal)
2. Wählen **Sie unter Inventar** die Option **Apps aus.**  
3. Wählen Sie die App aus, die Sie zum Rollback benötigen, und wählen Sie dann **Bearbeiten aus.**
4. Wählen **Sie unter Verwalten** die Option Eigenschaften **aus.** 
    - Wählen **Sie für Windows MSI-App-Line-of-Business-App-Apps** **App-Informationen** aus, und wählen Sie dann unter **App-Version** ignorieren die Option **Ja aus.**
    - Wählen Sie für Windows-App **(Win 32) die** Vorschau von Apps aus, wählen Sie **App-Informationen** aus, **wählen** Sie Erkennungsregeln aus, und wählen Sie dann Hinzufügen **aus.** 
    Wenn eine MSI-Regel vor ist, überprüfen Sie, ob die Überprüfung der **MSI-Produktversion** auf **Nein festgelegt ist.**
5. [Laden Sie eine frühere Version der App-Quelldatei in](../get-started/deploy-apps.md) das Microsoft Managed Desktop Admin-Portal hoch.  

