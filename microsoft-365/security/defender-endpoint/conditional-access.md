---
title: Aktivieren des bedingten Zugriffs zum besseren Schutz von Benutzern, Geräten und Daten
description: Aktivieren Sie bedingten Zugriff, um zu verhindern, dass Anwendungen ausgeführt werden, wenn ein Gerät als gefährdet betrachtet wird und eine Anwendung als nicht kompatibel gilt.
keywords: bedingter Zugriff, Blockieren von Anwendungen, Sicherheitsstufe, Intune,
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 21d17ee789a4757df10e99514f23cfc26b186405
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166197"
---
# <a name="enable-conditional-access-to-better-protect-users-devices-and-data"></a>Aktivieren des bedingten Zugriffs zum besseren Schutz von Benutzern, Geräten und Daten 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-conditionalaccess-abovefoldlink)

Bedingter Zugriff ist eine Funktion, mit der Sie Ihre Benutzer und Unternehmensinformationen besser schützen können, indem sichergestellt wird, dass nur sichere Geräte Zugriff auf Anwendungen haben.

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4byD1]

Mit bedingten Zugriff können Sie den Zugriff auf Unternehmensinformationen basierend auf der Risikostufe eines Geräts steuern. Dadurch können vertrauenswürdige Benutzer auf vertrauenswürdigen Geräten mit vertrauenswürdigen Anwendungen bleiben.

Sie können Sicherheitsbedingungen definieren, unter denen Geräte und Anwendungen ausgeführt werden können und auf Informationen aus Ihrem Netzwerk zugreifen können, indem Sie Richtlinien erzwingen, um die Ausführung von Anwendungen zu verhindern, bis ein Gerät in einen kompatiblen Zustand zurückkehrt. 

Die Implementierung von Bedingter Zugriff in Defender for Endpoint basiert auf Microsoft Intune (Intune)-Geräte-Compliancerichtlinien und Azure Active Directory (Azure AD)-Richtlinien für bedingten Zugriff. 

Die Compliancerichtlinie wird zusammen mit bedingten Zugriff verwendet, um nur Geräten, die eine oder mehrere Richtlinienregeln für die Gerätekonformität erfüllen, den Zugriff auf Anwendungen zu ermöglichen. 

## <a name="understand-the-conditional-access-flow"></a>Verstehen des Bedingten Zugriffsflusses
Bedingter Zugriff wird so installiert, dass der Zugriff auf vertrauliche Inhalte blockiert wird, wenn eine Bedrohung auf einem Gerät angezeigt wird, bis die Bedrohung behoben ist. 

Der Fluss beginnt damit, dass Geräte ein niedriges, mittleres oder hohes Risiko haben. Diese Risikoermittlungen werden dann an Intune gesendet. 

Je nachdem, wie Sie Richtlinien in Intune konfigurieren, kann bedingter Zugriff so eingerichtet werden, dass die Richtlinie angewendet wird, wenn bestimmte Bedingungen erfüllt sind.

Beispielsweise können Sie Intune so konfigurieren, dass bedingter Zugriff auf Geräte mit hohem Risiko angewendet wird.

In Intune wird eine Gerätekonformitätsrichtlinie in Verbindung mit dem bedingten Azure AD-Zugriff verwendet, um den Zugriff auf Anwendungen zu blockieren. Parallel dazu wird ein automatisierter Untersuchungs- und Behebungsprozess gestartet.

 Ein Benutzer kann das Gerät weiterhin verwenden, während die automatisierte Untersuchung und Behebung stattfindet, aber der Zugriff auf Unternehmensdaten wird blockiert, bis die Bedrohung vollständig behoben ist. 

Um das auf einem Gerät gefundene Risiko zu beheben, müssen Sie das Gerät in einen kompatiblen Zustand zurückgeben. Ein Gerät kehrt in einen kompatiblen Zustand zurück, wenn kein Risiko auf dem Gerät besteht. 

Es gibt drei Möglichkeiten, um ein Risiko zu adressieren:
1. Verwenden Sie manuelle oder automatisierte Korrekturen.
2. Lösen Sie aktive Warnungen auf dem Gerät auf. Dadurch wird das Risiko vom Gerät entfernt.
3. Sie können das Gerät aus den aktiven Richtlinien entfernen, und daher wird bedingter Zugriff nicht auf das Gerät angewendet. 

Bei der manuellen Korrektur muss ein Secops-Administrator eine Warnung untersuchen und das auf dem Gerät angezeigte Risiko eingehen. Die automatische Korrektur wird über konfigurationseinstellungen konfiguriert, die im folgenden Abschnitt [Configure Conditional Access bereitgestellt werden.](configure-conditional-access.md)

Wenn das Risiko entweder durch manuelle oder automatisierte Korrekturen entfernt wird, kehrt das Gerät in einen kompatiblen Zustand zurück, und der Zugriff auf Anwendungen wird gewährt.

In der folgenden Beispielsequenz von Ereignissen wird bedingter Zugriff in Aktion erläutert:

1. Ein Benutzer öffnet eine schädliche Datei, und Defender for Endpoint kennzeichnet das Gerät als hohes Risiko.
2. Die Bewertung mit hohem Risiko wird an Intune übergeben. Parallel dazu wird eine automatisierte Untersuchung initiiert, um die identifizierte Bedrohung zu begleichen. Eine manuelle Korrektur kann auch zur Behebung der identifizierten Bedrohung durchgeführt werden.
3. Basierend auf der in Intune erstellten Richtlinie wird das Gerät als nicht kompatibel gekennzeichnet. Die Bewertung wird dann von der Intune-Richtlinie für bedingten Zugriff an Azure AD übermittelt. In Azure AD wird die entsprechende Richtlinie angewendet, um den Zugriff auf Anwendungen zu blockieren.
4. Die manuelle oder automatisierte Untersuchung und Behebung ist abgeschlossen, und die Bedrohung wird entfernt. Defender for Endpoint sieht, dass auf dem Gerät kein Risiko besteht, und Intune bewertet das Gerät als konform. Azure AD wendet die Richtlinie an, die den Zugriff auf Anwendungen zulässt.
5. Benutzer können jetzt auf Anwendungen zugreifen.

 
## <a name="related-topic"></a>Verwandtes Thema
- [Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint](configure-conditional-access.md)
