---
title: Statische Proxyermittlung von Microsoft Defender ATP für Linux
ms.reviewer: ''
description: Beschreibt, wie Sie Microsoft Defender ATP für die statische Proxyermittlung konfigurieren.
keywords: microsoft, defender, atp, linux, installation, proxy
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 93d654773fc73903cbe0c5de289dcfdf9fd34f9f
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51687853"
---
# <a name="configure-microsoft-defender-for-endpoint-on-linux-for-static-proxy-discovery"></a>Konfigurieren von Microsoft Defender for Endpoint unter Linux für die statische Proxyermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

Microsoft Defender ATP kann einen Proxyserver mithilfe der ```HTTPS_PROXY``` Umgebungsvariablen ermitteln. Diese Einstellung muss sowohl **bei** der Installation als auch nach der Installation des Produkts konfiguriert werden.

## <a name="installation-time-configuration"></a>Konfiguration der Installationszeit

Während der Installation muss ```HTTPS_PROXY``` die Umgebungsvariable an den Paket-Manager übergeben werden. Der Paket-Manager kann diese Variable auf eine der folgenden Arten lesen:

- Die ```HTTPS_PROXY``` Variable wird in der folgenden Zeile ```/etc/environment``` definiert:

    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

- Die `HTTPS_PROXY` Variable wird in der globalen Konfiguration des Paket-Managers definiert. In Ubuntu 18.04 können Sie beispielsweise die folgende Zeile `/etc/apt/apt.conf.d/proxy.conf` hinzufügen:
  
    ```bash
    Acquire::https::Proxy "http://proxy.server:port/";
    ```

    > [!CAUTION]
    > Beachten Sie, dass über zwei Methoden den Proxy definieren können, der für andere Anwendungen auf Ihrem System verwendet werden soll. Verwenden Sie diese Methode mit Vorsicht oder nur, wenn dies eine allgemein globale Konfiguration sein soll.
  
- Die Variable wird für die Installations- oder `HTTPS_PROXY` Deinstallationsbefehle vorab verwendet. Verwenden Sie beispielsweise den APT-Paket-Manager, um die Variable beim Installieren von Microsoft Defender for Endpoint wie folgt voran zu verwenden: 

    ```bash  
    HTTPS_PROXY="http://proxy.server:port/" apt install mdatp
    ```

    > [!NOTE]
    > Fügen Sie nicht sudo zwischen der Umgebungsvariablendefinition und apt hinzu, andernfalls wird die Variable nicht verbreitet.

Die `HTTPS_PROXY` Umgebungsvariable kann auch während der Deinstallation definiert werden.

Beachten Sie, dass die Installation und Deinstallation nicht unbedingt fehlschlagen, wenn ein Proxy erforderlich, aber nicht konfiguriert ist. Telemetrie wird jedoch nicht übermittelt, und der Vorgang kann aufgrund von Netzwerktimeouts viel länger dauern.

## <a name="post-installation-configuration"></a>Konfiguration nach der Installation
  
Nach der Installation muss `HTTPS_PROXY` die Umgebungsvariable in der Defender for Endpoint-Dienstdatei definiert werden. Öffnen Sie dazu `/lib/systemd/system/mdatp.service` in einem Texteditor, während Sie als Stammbenutzer ausgeführt werden. Anschließend können Sie die Variable auf zwei Arten an den Dienst weitervermehren:

- Legen Sie die Auskommentierung der Zeile `#Environment="HTTPS_PROXY=http://address:port"` auf, und geben Sie Ihre statische Proxyadresse an.

- Fügen Sie eine Zeile `EnvironmentFile=/path/to/env/file` hinzu. Dieser Pfad kann auf eine oder eine benutzerdefinierte Datei verweisen, die `/etc/environment` die folgende Zeile hinzufügen muss:
  
    ```bash
    HTTPS_PROXY="http://proxy.server:port/"
    ```

Nachdem Sie die `mdatp.service` Datei geändert haben, speichern und schließen Sie sie. Starten Sie den Dienst neu, damit die Änderungen angewendet werden können. In Ubuntu umfasst dies zwei Befehle:  

```bash
systemctl daemon-reload; systemctl restart mdatp
```
