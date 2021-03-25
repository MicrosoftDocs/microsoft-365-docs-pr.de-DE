---
title: Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender for Endpoint
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
ms.openlocfilehash: c2e7a3eeb9576b53723a786de85f0c4bece679b4
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51204246"
---
# <a name="use-microsoft-defender-for-office-365-together-with-microsoft-defender-for-endpoint"></a>Verwenden von Microsoft Defender für Office 365 zusammen mit Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365](defender-for-office-365.md) kann für die Zusammenarbeit mit [Microsoft Defender for Endpoint konfiguriert werden.](/windows/security/threat-protection)

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender for Endpoint kann Ihr Sicherheitsbetriebsteam bei der Überwachung und schnellen Maßnahmen unterstützen, wenn die Geräte der Benutzer gefährdet sind. Wenn beispielsweise die Integration aktiviert ist, kann Ihr Sicherheitsteam die Geräte anzeigen, die potenziell von einer erkannten E-Mail-Nachricht betroffen sind, sowie die Vielen kürzlich generierten Warnungen für diese Geräte in Microsoft Defender for Endpoint.

Die folgende Abbildung zeigt, wie die Registerkarte **Geräte** aussieht, wenn Die Integration von Microsoft Defender for Endpoint aktiviert ist:

![Wenn Microsoft Defender for Endpoint aktiviert ist, wird eine Liste der Geräte mit Warnungen angezeigt.](../../media/fec928ea-8f0c-44d7-80b9-a2e0a8cd4e89.PNG)

In diesem Beispiel sehen Sie, dass die Empfänger der erkannten E-Mail-Nachricht vier Geräte und eines über eine Warnung verfügen. Wenn Sie auf den Link für ein Gerät klicken, wird die Seite im Microsoft Defender Security Center ( <https://securitycenter.windows.com> ) geöffnet.

> [!TIP]
> **[Erfahren Sie mehr über das Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/use)** (auch als Microsoft Defender for Endpoint-Portal bezeichnet).

## <a name="requirements"></a>Anforderungen

- Ihre Organisation muss über Microsoft Defender für Office 365 (oder Office 365 E5) und Microsoft Defender für Endpoint verfügen.

- Sie müssen ein globaler Administrator sein oder eine Sicherheitsadministratorrolle (z. B. Sicherheitsadministrator) im [Security & Compliance Center zugewiesen haben.](https://protection.office.com) (Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md))

- Sie müssen zugriff auf [Explorer (oder Echtzeiterkennungen)](threat-explorer.md) im Security & Compliance Center und im Microsoft Defender Security Center haben.

## <a name="to-integrate-microsoft-defender-for-office-365-with-microsoft-defender-for-endpoint"></a>So integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender for Endpoint

Die Integration von Microsoft Defender für Office 365 in Microsoft Defender for Endpoint wird mithilfe des Security & Compliance Center und des Microsoft Defender Security Center eingerichtet.

1. Wechseln Sie als globaler Administrator oder Sicherheitsadministrator zu und <https://protection.office.com> melden Sie sich an. (Dies führt Sie zum Office 365 Security & Compliance Center.)

2. Wählen Sie im Navigationsbereich Den **Bedrohungsverwaltungs-Explorer** \> **aus.**

   ![Explorer im Menü Bedrohungsverwaltung](../../media/ThreatMgmt-Explorer-nav.png)

3. Wählen Sie in der oberen rechten Ecke des Bildschirms **Defender für Endpunkteinstellungen (MDE-Einstellungen) aus.**

4. Aktivieren Sie im Dialogfeld Microsoft Defender for Endpoint-Verbindung die Verbindung **mit Microsoft Defender for Endpoint verbinden.**

   ![Microsoft Defender for Endpoint-Verbindung](../../media/Explorer-WDATPConnection-dialog.png)

5. Wechseln Sie zum Microsoft Defender Security Center ( <https://securitycenter.windows.com> ).

6. Wählen Sie in der Navigationsleiste **Einstellungen aus.** Wählen Sie dann unter **Allgemein** die Option **Erweiterte Features aus.**

7. Scrollen Sie nach unten **zu Office 365 Threat Intelligence-Verbindung,** und schalten Sie die Verbindung ein.

   ![Office 365 Threat Intelligence-Verbindung](../../media/mdatp-oatptoggle.png)

## <a name="related-articles"></a>Verwandte Artikel

[Untersuchungs- und Reaktionsfunktionen für Bedrohungen in Office 365](office-365-ti.md)

[Microsoft Defender für Office 365](defender-for-office-365.md)

[Microsoft Defender für Endpunkt](/windows/security/threat-protection)