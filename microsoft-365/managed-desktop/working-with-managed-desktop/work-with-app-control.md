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
ms.openlocfilehash: 31cc897fe28f557a65cba9c99e5dcecbf7c2b0e5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917640"
---
# <a name="work-with-app-control"></a>Arbeiten mit dem App-Steuerelement

Sobald die App-Steuerung in Ihrer Umgebung bereitgestellt wurde, sind sowohl Sie als auch Microsoft Managed Desktop Vorgänge fortlaufend verantwortlich. Sie können beispielsweise eine neue App in der Umgebung hinzufügen oder einen vertrauenswürdigen Signer hinzufügen (oder entfernen). Zur Verbesserung der Sicherheit sollten alle Apps vor der Veröffentlichung für Benutzer mit Code signiert werden. Die Herausgeberdetails einer App enthalten Informationen zum Signier.


## <a name="add-a-new-app"></a>Hinzufügen einer neuen App

Führen Sie die folgenden Schritte aus, um eine neue App hinzuzufügen:

1. Fügen Sie die App zu [Microsoft Intune](/mem/intune/apps/apps-win32-app-management).
2. Stellen Sie die App auf einem beliebigen Gerät im Testring aus. 
3. Testen Sie Ihre App gemäß Ihren Standardgeschäftsprozessen. 
4. Überprüfen Sie die Ereignisanzeige unter Anwendungs- und **Dienstprotokolle\Microsoft\Windows\AppLocker,** und suchen Sie nach **8003-** oder **8006-Ereignissen.** Diese Ereignisse deuten darauf hin, dass die App blockiert wird. Weitere Informationen zu allen App Locker-Ereignissen und deren Bedeutung finden Sie unter [Using Event Viewer with AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/using-event-viewer-with-applocker).
5. Wenn Sie eines dieser Ereignisse finden, öffnen Sie eine Signieranforderung mit Microsoft Managed Desktop Vorgänge.

## <a name="add-or-remove-a-trusted-signer"></a>Hinzufügen (oder Entfernen) eines vertrauenswürdigen Signers

Wenn Sie eine Signieranforderung öffnen, müssen Sie zunächst einige wichtige Herausgeberdetails bereitstellen. Führen Sie dann die folgenden Schritte aus:

1. [Sammeln von Herausgeberdetails](#gather-publisher-details).
2. Öffnen Sie ein Ticket mit Microsoft Managed Desktop Vorgängen, um die Signierregel an fordern und die folgenden Details enthalten:  
    - Name der Anwendung 
    - Anwendungsversion 
    - Beschreibung 
    - Änderungstyp ("hinzufügen" oder "entfernen")  
    - Publisher (z. B.: "O= <publisher name> ,L= <location> ,S=State,C=Country") 

> [!NOTE]
> Führen Sie die gleichen Schritte aus, um die Vertrauensstellung für eine App zu entfernen, legen Sie **jedoch Den Änderungstyp** auf *entfernen festgelegt.*

Im Anschluss an diesen Zeitplan werden schrittweise Richtlinien für Bereitstellungsgruppen bereitgestellt:


|Bereitstellungsgruppe  |Richtlinientyp  |Timing  |
|---------|---------|---------|
|Testen     |  Überwachung       |  Tag 0       |
|Erster     | Enforced        | Tag 1        |
|Schnell     | Enforced        |  Tag 2       |
|Allgemein     | Enforced        |  Tag 3       |


Sie können die Bereitstellung während des Rollouts jederzeit anhalten oder ein Rollback vornehmen. Öffnen Sie dazu eine weitere Dienstanforderung mit Vorgängen.

> [!NOTE]
> Wenn Sie die Veröffentlichung einer Signierregel anhalten, muss diese Regel entweder zurückgesetzt oder abgeschlossen werden, bevor ein weiteres Rollout gestartet werden kann.

## <a name="gather-publisher-details"></a>Sammeln von Herausgeberdetails

Führen Sie die folgenden Schritte aus, um auf die Herausgeberdaten für eine App zu zugreifen:

1. Suchen Sie Microsoft Managed Desktop Gerät im Testring, auf das eine Überwachungsmodusrichtlinie angewendet wurde. 
2. Versuchen Sie, die App auf dem Gerät zu installieren.
3. Öffnen Sie die Ereignisanzeige auf diesem Gerät. 
4. Navigieren Sie in der Ereignisanzeige zu Anwendungs- und **Dienstprotokolle\Microsoft\Windows**, und wählen Sie **dann AppLocker aus.** 
5. Suchen Sie **nach einem 8003-** oder **8006-Ereignis,** und kopieren Sie dann Informationen aus dem Ereignis: 
    - Name der Anwendung 
    - Anwendungsversion 
    - Beschreibung 
    - Publisher (z. B. "O= <publisher name> , L= <location> , S=State, C=Country")