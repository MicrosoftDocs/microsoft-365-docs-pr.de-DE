---
title: Verwalten von Apps in Microsoft Managed Desktop
description: Informationen zum Aktualisieren von Branchen-Apps, die auf Microsoft Managed Desktop Geräten bereitgestellt werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: b016d8458b4b4cc9f6b684d3b8a3c0a1e1322fef
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925407"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a>Verwalten von Branchenanwendungen in Microsoft Managed Desktop

<!--Application management -->

Es gibt verschiedene Möglichkeiten zum Verwalten von App-Updates für Apps, die Sie in Microsoft Managed Desktop integriert und auf Ihren Microsoft Managed Desktop Geräten bereitgestellt haben. Sie können App-Updates in Microsoft Managed Desktop Portal oder Intune vornehmen. 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a>Aktualisieren von Branchen-Apps in Microsoft Managed Desktop

**So aktualisieren Sie Ihre Branchen-Apps im Microsoft Managed Desktop Portal**
1. Melden Sie sich bei [Microsoft Managed Desktop Admin-Portal](https://aka.ms/mmdportal)an.
2. Wählen Sie unter **"Inventar"** die Option **"Apps"** aus.  
3. Wählen Sie die App aus, die Sie aktualisieren möchten, und wählen Sie dann **Bearbeiten** aus.
4. Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** aus. 
5. Klicken Sie auf **"App-Paketdatei",** und navigieren Sie dann zum Hochladen einer neuen App-Paketdatei.
6. Wählen Sie **die App-Paketdatei** aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die App-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte App-Paket widerspiegelt. 

Die aktualisierte App wird auf den Geräten Des Benutzers bereitgestellt.

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a>Aktualisieren von Branchen-Apps in Intune

**So aktualisieren Sie Ihre Branchen-Apps in Intune**
1. Melden Sie sich beim [Azure-Portal](https://portal.azure.com)an.
2. Wählen Sie **"Alle Dienste**  >  **Intune"** aus. Intune befindet sich im Abschnitt **"Überwachung + Verwaltung".**
3. Wählen Sie **Client-Apps > Apps** aus.
4. Suchen und wählen Sie Ihre App in der Liste der Apps aus.
5. Wählen Sie im Blatt **"Übersicht"** die Option **"Eigenschaften"** aus.
6. Wählen Sie **die App-Paketdatei** aus.
7. Wählen Sie das Ordnersymbol aus, und navigieren Sie zum Speicherort Ihrer aktualisierten App-Datei. Klicken Sie auf **Öffnen**. Die App-Informationen werden mit den Paketinformationen aktualisiert.
8. Stellen Sie sicher, dass die **App-Version** das aktualisierte App-Paket widerspiegelt.

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a>Zurücksetzen einer App auf eine frühere Version

Wenn beim Bereitstellen einer neuen Version einer App ein Fehler gefunden wird, können Sie ein Rollback auf eine frühere Version ausführen. Der hier beschriebene Prozess gilt für Apps, bei denen der Typ als **Windows MSI-Branchen-App** oder **Windows-App (Win 32)** aufgeführt ist – Vorschau

**So führen Sie ein Rollback einer Branchen-App auf eine frühere Version aus**

1. Melden Sie sich bei [Microsoft Managed Desktop Admin-Portal](https://aka.ms/mmdportal)an.
2. Wählen Sie unter **"Inventar"** die Option **"Apps"** aus.  
3. Wählen Sie die App aus, die Sie zurücksetzen müssen, und wählen Sie dann **Bearbeiten** aus.
4. Wählen Sie unter **"Verwalten"** die Option **"Eigenschaften"** aus. 
    - For **Windows MSI line-of-business app** apps, select App **information,** and then under **Ignore app version**, select **Yes**.
    - For **Windows app (Win 32) - preview** apps, select App **information,** select **Detection rules,** and then select **Add**. 
    Wenn eine MSI-Regel vorhanden ist, überprüfen Sie, ob die **MSI-Produktversionsprüfung** auf **"Nein"** festgelegt ist.
5. [Hochladen eine frühere Version der App-Quelldatei](../get-started/deploy-apps.md) an Microsoft Managed Desktop Verwaltungsportal an.  

