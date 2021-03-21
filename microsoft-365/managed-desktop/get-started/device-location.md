---
title: Windows 10-Standortdienst
description: So haben Sie die Windows-Standortdienste für Ihre Geräte aktiviert?
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 210356dd21b36efbb27d8faa4f8616145584159c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929499"
---
# <a name="windows-10-location-service"></a>Windows 10-Standortdienst

Geräte in Microsoft Managed Desktop werden mithilfe von Windows Autopilot registriert. Bei diesem Prozess können wir sie mit Azure Active Directory und Microsoft Intune verwalten. Standardmäßig ist der Windows 10-Standortdienst deaktiviert, wenn ein Gerät zum ersten Mal aktiviert ist, es sei denn, dieses Feature ist während der "out-of-box"-Erfahrung in den Datenschutzeinstellungen aktiviert. Diese Einstellungen werden während der Autopilot-Registrierung in Microsoft Managed Desktop ausgeblendet. Weitere Informationen zum Einrichten von Autopilot finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](esp-first-run.md).

Aus diesem Grund können Microsoft Managed Desktop-Geräte ihren Gerätespeicherort nicht abrufen, was die Funktionalität mehrerer Windows-Features, z. B. Zeitzonen, einschränkt. Weitere Informationen zum Windows 10-Standortdienst finden Sie unter [Windows 10-Standortdienst und Datenschutz.](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088)

Sie müssen den Standortdienst nicht verwenden, um an Microsoft Managed Desktop teilzunehmen, aber die Benutzeroberfläche wird eingeschränkt. Beispielsweise können Geräte nicht automatisch die Zeitzone bestimmen, in der sie sich befinden, wenn Ihre Benutzer in einer anderen Zeitzone arbeiten.

## <a name="enable-the-location-service"></a>Aktivieren des Standortdiensts

Sie können sich entweder für die Verwendung des Standortdiensts entscheiden, wenn Sie Geräte beim Microsoft Managed Desktop-Dienst registrieren, oder Sie können den Dienst nach der Registrierung aktivieren oder deaktivieren.

### <a name="opt-in-during-enrollment"></a>Anmeldung während der Registrierung

Der Microsoft Managed Desktop-Dienst kann den Speicherortdienst aktivieren. Während der Registrierungssequenz werden Sie aufgefordert, auszuwählen, ob Sie zulassen möchten, dass der Windows 10-Standortdienst auf Geräten aktiviert wird.

### <a name="control-the-location-service-after-enrollment"></a>Steuern des Standortdiensts nach der Registrierung

Sie können den Standortdienst jederzeit aktiviert (oder deaktiviert) [](../working-with-managed-desktop/admin-support.md) haben, indem Sie eine Supportanfrage über das [Administratorportal übermitteln.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>So konfiguriert Microsoft Managed Desktop den Windows 10-Standortdienst

Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, verwenden wir die erforderlichen Mindesteinstellungen, ohne den Datenschutz der Benutzer zu beeinträchtigen. Weitere Informationen finden Sie unter [Windows 10-Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).

Microsoft Managed Desktop aktiviert die **Einstellung Standortdatenschutz** in **den Windows-Einstellungen,** um den Zugriff auf den Speicherort auf diesem Gerät zu **ermöglichen.** Die Benutzeroberfläche sieht wie dies aus:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Standorteinstellungen in Den Windows-Einstellungen":::

> [!NOTE]
> Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, gilt dies nur für das Windows-Betriebssystem selbst. Apps dürfen keine Standortdienste verwenden. Jeder Benutzer kann auswählen, ob Apps auf seinen Standort zugreifen dürfen.