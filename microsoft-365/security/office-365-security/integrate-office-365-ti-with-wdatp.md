---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt
f1.keywords:
- NOCSH
keywords: integration, Microsoft Defender, ATP
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 01/21/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Verwenden Sie Microsoft Defender für Office 365 zusammen mit Microsoft Defender for Endpoint, um detailliertere Informationen zu Bedrohungen gegen Ihre Geräte und E-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 24b81bb4c445c44d7c0228fa1c4440faff642816
ms.sourcegitcommit: ba830e85899f247e5a1e117d63e09e4d5b8a8020
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49939332"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365 kann für](office-365-atp.md) die Verwendung mit [Microsoft Defender for Endpoint konfiguriert werden.](https://docs.microsoft.com/windows/security/threat-protection)

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender for Endpoint kann Ihrem Sicherheitsteam dabei helfen, die Geräte der Benutzer zu überwachen und schnell maßnahmen zu ergreifen. Wenn beispielsweise die Integration aktiviert ist, kann Ihr Sicherheitsteam die Geräte anzeigen, die potenziell von einer erkannten E-Mail-Nachricht betroffen sind, sowie die Vielen kürzlich generierten Warnungen für diese Geräte in Microsoft Defender for Endpoint.

Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Microsoft Defender für Endpunkt integration aktiviert ist:

![Wenn Microsoft Defender für Endpunkt aktiviert ist, können Sie eine Liste der Geräte mit Warnungen anzeigen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte und eines über eine Warnung verfügen. Wenn Sie auf den Link für ein Gerät klicken, wird seine Seite im Microsoft Defender Security Center ( <https://securitycenter.windows.com> ) geöffnet.

> [!TIP]
> **[Erfahren Sie mehr über das Microsoft Defender Security Center](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender für Endpunktportal bezeichnet).

## <a name="requirements"></a>Anforderungen

- Ihre Organisation muss über Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender for Endpoint verfügen.

- Sie müssen ein globaler Administrator sein oder über eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) im [Security & Compliance Center verfügen.](https://protection.office.com) (Siehe [Berechtigungen im Security & Compliance Center)](permissions-in-the-security-and-compliance-center.md)

- Sie müssen zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md) im Security & Compliance Center und im Microsoft Defender Security Center haben.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender for Endpoint

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender for Endpoint wird mithilfe des Security & Compliance Center und des Microsoft Defender Security Center eingerichtet.

1. Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und <https://protection.office.com> melden Sie sich an. (Dies führt Sie zum Office 365 Security & Compliance Center.)

2. Wählen Sie im Navigationsbereich den **Bedrohungsverwaltungs-Explorer** \> **aus.**

   ![Explorer im Menü "Bedrohungsverwaltung"](../../media/ThreatMgmt-Explorer-nav.png)

3. Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender für Endpunkteinstellungen (MDE-Einstellungen) aus.**

4. Aktivieren Sie im Dialogfeld "Verbindung mit Microsoft Defender für Endpunkt" die Verbindung **mit Microsoft Defender für Endpunkt.**

   ![Microsoft Defender für Endpunktverbindung](../../media/Explorer-WDATPConnection-dialog.png)

5. Wechseln Sie zum Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).

6. Wählen Sie in der Navigationsleiste Einstellungen **aus.** Wählen Sie dann unter **"Allgemein"** die Option **"Erweiterte Features" aus.**

7. Scrollen Sie nach unten **zur Office 365 Threat** Intelligence-Verbindung, und aktivieren Sie die Verbindung.

   ![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Verwandte Artikel

[Untersuchungs- und Reaktionsfunktionen für Bedrohungen in Office 365](office-365-ti.md)

[Microsoft Defender für Office 365](office-365-atp.md)

[Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection)
