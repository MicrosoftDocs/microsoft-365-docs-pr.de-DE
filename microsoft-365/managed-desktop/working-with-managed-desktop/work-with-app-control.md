---
title: Arbeiten mit dem App-Steuerelement
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9efe6ba6704b0e1633973d157c38827221316bbd
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430447"
---
# <a name="work-with-app-control"></a>Arbeiten mit dem App-Steuerelement

Sobald die APP-Steuerung in Ihrer Umgebung bereitgestellt wurde, haben sowohl Sie als auch Microsoft Managed Desktop-Vorgänge fortlaufende Aufgaben. Beispielsweise können Sie eine neue app in der Umgebung hinzufügen oder einen vertrauenswürdigen Signaturer hinzufügen (oder entfernen). Um die Sicherheit zu verbessern, sollten alle apps Code signiert sein, bevor Sie Sie an Endbenutzer freigeben. Die Herausgeber Details einer App enthalten Informationen zur signiererin.


## <a name="add-a-new-app"></a>Hinzufügen einer neuen App

Führen Sie die folgenden Schritte aus, um eine neue APP hinzuzufügen:

1. Fügen Sie die APP zu [Microsoft InTune](https://docs.microsoft.com/mem/intune/apps/apps-win32-app-management)hinzu.
2. Stellen Sie die APP auf einem beliebigen Gerät im Test-Ring bereit. 
3. Testen Sie Ihre APP gemäß ihren Standardgeschäftsprozessen. 
4. Überprüfen Sie die Ereignisanzeige unter **Application and Services Logs\Microsoft\Windows\AppLocker**, und suchen Sie nach **8003** -oder **8006** -Ereignissen. Diese Ereignisse deuten darauf hin, dass die APP blockiert würde. Weitere Informationen zu allen APP locker-Ereignissen und deren Bedeutung finden Sie unter [Verwenden der Ereignisanzeige mit AppLocker](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Wenn Sie eines der folgenden Ereignisse finden, öffnen Sie eine Signaturer-Anforderung mit Microsoft Managed Desktop Operations.

## <a name="add-or-remove-a-trusted-signer"></a>Hinzufügen (oder entfernen) einer vertrauenswürdigen signierenden

Wenn Sie eine Signaturgeber Anforderung öffnen, müssen Sie zuerst einige wichtige Publisher-Details angeben. Führen Sie dann die folgenden Schritte aus:

1. [Sammeln Sie Herausgeber Details](#gather-publisher-details).
2. Öffnen Sie ein Ticket mit Microsoft Managed Desktop Operations, um die Signaturer-Regel anzufordern, und schließen Sie die folgenden Details ein:  
    - Anwendungsname 
    - Anwendungsversion 
    - Beschreibung 
    - Change Type ("hinzufügen" oder "entfernen")  
    - Publisher-Details (Beispiel: "O = <publisher name> , L = <location> , S = State, C = Country") 

> [!NOTE]
> Wenn Sie die Vertrauensstellung für eine APP entfernen möchten, führen Sie die gleichen Schritte aus, legen Sie jedoch **Change Type** auf *Remove*fest.

Durch Vorgänge werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt, die auf diesen Zeitplan folgen:


|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 2       |
|Allgemein     | Enforced        |  Tag 3       |


Sie können die Bereitstellung jederzeit während des Rollouts anhalten oder ein Rollback ausführen. Öffnen Sie dazu eine andere Dienstanforderung mit Vorgängen.

> [!NOTE]
> Wenn Sie die Veröffentlichung einer Signaturregel anhalten, muss die Regel entweder zurückgesetzt oder abgeschlossen werden, bevor ein anderes Rollout gestartet werden kann.

## <a name="gather-publisher-details"></a>Sammeln von Herausgeber Details

Führen Sie die folgenden Schritte aus, um auf die Herausgeberdaten für eine APP zuzugreifen:

1. Suchen Sie ein Microsoft Managed Desktop-Gerät im testring, auf dem eine Überwachungsmodus-Richtlinie angewendet wurde. 
2. Versuchen Sie, die APP auf dem Gerät zu installieren.
3. Öffnen Sie die Ereignisanzeige auf dem Gerät. 
4. Navigieren Sie in der Ereignisanzeige zu **Anwendungs-und Dienst Logs\Microsoft\Windows**, und wählen Sie dann **AppLocker**aus. 
5. Suchen Sie nach einem beliebigen **8003** -oder **8006** -Ereignis, und kopieren Sie dann Informationen aus dem Ereignis: 
    - Anwendungsname 
    - Anwendungsversion 
    - Beschreibung 
    - Publisher-Details (Beispiel: "O = <publisher name> , L = <location> , S = State, C = Country") 
