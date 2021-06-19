---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt
f1.keywords:
- NOCSH
keywords: Integration, Microsoft Defender, Microsoft Defender für Endpunkt
ms.author: deniseb
author: denisebmsft
manager: dansimp
ms.date: 06/10/2021
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: Verwenden Sie Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt, um detailliertere Informationen zu Bedrohungen für Ihre Geräte und E-Mail-Inhalte zu erhalten.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1d54e4ec40c636b8b3ea319e79cbad5005850952
ms.sourcegitcommit: c70067b4ef9c6f8f04aca68c35bb5141857c4e4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53029263"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender für Endpunkt

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Verwendung mit [Microsoft Defender für Endpunkt](/windows/security/threat-protection)konfiguriert werden.

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt kann Ihrem Sicherheitsteam helfen, die Überwachung und schnelle Maßnahmen zu ergreifen, wenn die Geräte der Benutzer gefährdet sind. Sobald die Integration beispielsweise aktiviert ist, kann Ihr Sicherheitsteam die Geräte sehen, die möglicherweise von einer erkannten E-Mail-Nachricht betroffen sind, sowie wie viele aktuelle Warnungen für diese Geräte in Microsoft Defender für Endpunkt generiert wurden.

Die folgende Abbildung zeigt, wie die Registerkarte **"Geräte"** aussieht, wenn Die Integration von Microsoft Defender für Endpunkt aktiviert ist:

![Wenn Microsoft Defender für Endpunkt aktiviert ist, sehen Sie eine Liste der Geräte mit Warnungen.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In diesem Beispiel können Sie sehen, dass die Empfänger der erkannten E-Mail-Nachricht über vier Geräte verfügen und eines über eine Warnung verfügt. Durch Klicken auf den Link für ein Gerät wird die Seite in [Microsoft 365 Defender](../defender-endpoint/microsoft-defender-security-center.md) (früher Microsoft Defender Security Center) geöffnet.

> [!TIP]
> Das Microsoft 365 Defender-Portal ersetzt die Microsoft Defender Security Center. Siehe [Microsoft Defender für Endpunkt in Microsoft 365 Defender](../defender/microsoft-365-security-center-mde.md).

## <a name="requirements"></a>Anforderungen

- Ihre Organisation benötigt Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpunkt.

- Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) in Microsoft 365 zugewiesen haben. Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender Portal.](permissions-microsoft-365-security-center.md)

- Sie müssen Zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md)haben.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt ist sowohl in Defender für Endpunkt als auch in Defender für Office 365 eingerichtet.

1. Als globaler Administrator oder <https://security.microsoft.com/threatexplorer> Sicherheitsadministrator.

2. Wählen Sie im Navigationsbereich **E-Mail &** Zusammenarbeits-Explorer \> aus.

3. Klicken Sie auf der **Explorer-Seite** in der oberen rechten Ecke des Bildschirms auf **MDE Einstellungen**.

4. Aktivieren Sie im angezeigten **Microsoft Defender für Endpunkt-Verbindungs-Flyout** **Verbinden zu Microsoft Defender für Endpunkt** ( ![ Einschalten ](../../media/scc-toggle-on.png) ) und klicken Sie dann auf schließen ![ ](../../media/m365-cc-sc-close-icon.png) .

    :::image type="content" source="../../media/explorer-mdeconnection-dialognew.png" alt-text="MDE-Verbindung":::

5. Wählen Sie im Navigationsbereich **Einstellungen** aus. Wählen Sie auf der **Seite Einstellungen** **Endpunkte aus.**

6. Wählen Sie auf der seite **"Endpunkte",** die geöffnet wird, die Option **"Erweiterte Features" aus.**

7. Scrollen Sie nach unten zu **Office 365 Threat Intelligence-Verbindung,** und aktivieren Sie sie ( ![ Umschalten ](../../media/scc-toggle-on.png) ).

   Wenn Sie fertig sind, klicken Sie auf **"Einstellungen speichern".**

## <a name="related-articles"></a>Verwandte Artikel

[Funktionen zur Untersuchung und Reaktion auf Bedrohungen in Office 365](office-365-ti.md)

[Microsoft Defender für Office 365](defender-for-office-365.md)

[Microsoft Defender für Endpunkt](/windows/security/threat-protection)
