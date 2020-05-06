---
title: DSGVO für lokale Dateifreigaben
description: Erfahren Sie, wie Sie mit Anforderungen der Datenschutz-Grundverordnung (DSGVO) in lokalen Windows Server-Dateifreigaben umgehen.
f1.keywords:
- NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
titleSuffix: Microsoft GDPR
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: e9d45c86b2838acef9966b10806e589d1bb42ff9
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44036248"
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

Weitere Informationen über die Verwendung des Azure Information Protection-Scanners zum Suchen und Beschriften von personenbezogenen Daten finden Sie im Microsoft GDPR Data Discovery Toolkit unter [https://aka.ms/gdprpartners](<https://aka.ms/gdprpartners>).

Informationen über die Konfiguration des Scanners für Bedingungen und die Verwendung der vertraulichen Datentypen für die Verhinderung von Datenverlust in Office 365 finden Sie unter [So konfigurieren Sie Bedingungen für die automatische und empfohlene Klassifizierung von Azure Information Protection](https://docs.microsoft.com/information-protection/deploy-use/configure-policy-classification). Beachten Sie, dass neue vertrauliche Datentypen in Office 365 nicht sofort für die Verwendung mit dem Scanner zur Verfügung stehen und dass benutzerdefinierte vertrauliche Datentypen nicht mit dem Scanner verwendet werden können.
