---
title: DSGVO für lokale Dateifreigaben
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
description: Erfahren Sie, wie Sie mit DSGVO-Anforderungen bei lokalen Windows Server-Dateifreigaben umgehen.
ms.openlocfilehash: b5d5023ec8a052dc51575fa01f9cb77c4bf001c4
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37080693"
---
# <a name="gdpr-for-on-premises-windows-server-file-shares"></a>DSGVO für lokale Windows Server-Dateifreigaben

Folgende grundlegende Vorgehensweise wird für Dateifreigaben empfohlen:

-   Verwenden Sie Azure Information Protection, um vertrauliche Daten zu beschriften.

-   Verwenden Sie den Azure Information Protection-Scanner, um Daten zu finden.

Die empfohlene Vorgehensweise für  Dateifreigaben umfasst die folgenden Schritte:

1.  **Installieren und konfigurieren Sie den Azure Information Protection-Scanner.**

    -   Entscheiden Sie, welche vertraulichen Datentypen Sie verwenden möchten.

    -   Geben Sie die lokalen Ordner und Netzwerkfreigaben an, die Sie verwenden möchten.

2.  **Führen Sie einen Suchzyklus durch.**

    -   Führen Sie den Scanner im Suchmodus aus und überprüfen Sie die Ergebnisse.

    -   Falls erforderlich, optimieren Sie die Bedingungen und vertraulichen Datentypen.

    -   Bewerten Sie die erwarteten Auswirkungen einer automatischen Anwendung von Beschriftungen.

3.  **Führen Sie den Azure Information Protection-Scanner aus, um Beschriftungen für berechtigende Dokumente anzuwenden**.

4.  **Zum Schutz:**

    -   Konfigurieren Sie Regeln zum Schutz vor Datenverlust in Exchange, um Dokumente mit der gewünschten Beschriftung zu schützen.

    -   Beschränken Sie mithilfe von Berechtigungen, wer auf Dateien zugreifen kann.

5.  **Integrieren Sie zur Überwachung Windows Server-Protokolle mit einem SIEM-Tool.**

    -   Verwenden Sie den Azure Information Protection-Scanner, um personenbezogene Daten für Anfragen von betroffenen Personen zu finden. Sie können auch eine SharePoint Server-Suche konfigurieren, um Dateifreigaben zu durchsuchen.

Weitere Informationen über die Verwendung des Azure Information Protection-Scanners zum Suchen und Beschriften von personenbezogenen Daten finden Sie im Microsoft GDPR Data Discovery Toolkit unter [http://aka.ms/gdprpartners](<http://aka.ms/gdprpartners>).

Informationen über die Konfiguration des Scanners für Bedingungen und die Verwendung der vertraulichen Datentypen für die Verhinderung von Datenverlust in Office 365 finden Sie unter [So konfigurieren Sie Bedingungen für die automatische und empfohlene Klassifizierung von Azure Information Protection](https://docs.microsoft.com/de-DE/information-protection/deploy-use/configure-policy-classification). Beachten Sie, dass neue vertrauliche Datentypen in Office 365 nicht sofort für die Verwendung mit dem Scanner zur Verfügung stehen und dass benutzerdefinierte vertrauliche Datentypen nicht mit dem Scanner verwendet werden können.
