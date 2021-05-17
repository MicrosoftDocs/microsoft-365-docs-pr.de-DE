---
title: Standortdienst für Windows 10
description: So können Sie Windows Standortdienste für Ihre Geräte aktiviert haben
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
# <a name="windows-10-location-service"></a>Standortdienst für Windows 10

Geräte in Microsoft Managed Desktop werden mithilfe von autopilot Windows registriert. Bei diesem Prozess können wir sie mit Azure Active Directory und Microsoft Intune. Standardmäßig ist Windows 10 Standortdienst deaktiviert, wenn ein Gerät zum ersten Mal aktiviert ist, es sei denn, dieses Feature ist während der "out-of-box"-Erfahrung in den Datenschutzeinstellungen aktiviert. Diese Einstellungen werden während der Autopilot-Registrierung in Microsoft Managed Desktop. Weitere Informationen zum Einrichten von Autopilot finden Sie unter [First-run experience with Autopilot und the Enrollment Status Page](esp-first-run.md).

Aus diesem Grund Microsoft Managed Desktop Geräte ihren Gerätespeicherort nicht abrufen, was die Funktionalität mehrerer Windows, z. B. Zeitzonen, einschränkt. Weitere Informationen zum Standortdienst Windows 10 finden Sie [unter Windows 10 Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).

Sie müssen den Standortdienst nicht verwenden, um an Microsoft Managed Desktop teilzunehmen, aber die Benutzeroberfläche wird eingeschränkt. Beispielsweise können Geräte nicht automatisch die Zeitzone bestimmen, in der sie sich befinden, wenn Ihre Benutzer in einer anderen Zeitzone arbeiten.

## <a name="enable-the-location-service"></a>Aktivieren des Standortdiensts

Sie können sich entweder für die Verwendung des Standortdiensts entscheiden, wenn Sie Geräte beim Microsoft Managed Desktop registrieren, oder Sie können den Dienst nach der Registrierung aktivieren oder deaktivieren.

### <a name="opt-in-during-enrollment"></a>Anmeldung während der Registrierung

Sie können den Microsoft Managed Desktop Standortdienst aktivieren lassen. Während der Registrierungssequenz werden Sie aufgefordert, auszuwählen, ob Sie zulassen möchten, dass Windows 10 Standortdienst auf Geräten aktiviert wird.

### <a name="control-the-location-service-after-enrollment"></a>Steuern des Standortdiensts nach der Registrierung

Sie können den Standortdienst jederzeit aktiviert (oder deaktiviert) [](../working-with-managed-desktop/admin-support.md) haben, indem Sie eine Supportanfrage über das [Administratorportal übermitteln.](access-admin-portal.md)

## <a name="how-microsoft-managed-desktop-configures-the-windows-10-location-service"></a>Konfigurieren Microsoft Managed Desktop standortdiensts Windows 10

Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, verwenden wir die erforderlichen Mindesteinstellungen, ohne den Datenschutz der Benutzer zu beeinträchtigen. Weitere Informationen finden Sie unter [Windows 10 Standortdienst und Datenschutz](https://support.microsoft.com/windows/windows-10-location-service-and-privacy-3a8eee0a-5b0b-dc07-eede-2a5ca1c49088).

Microsoft Managed Desktop aktiviert die Einstellung **Standortdatenschutz** in **den Windows,** um den Zugriff auf den Standort **auf diesem Gerät zu ermöglichen.** Die Benutzeroberfläche sieht wie dies aus:

 :::image type="content" source="../../media/MMD-location-services-UI.png" alt-text="Standorteinstellungen in Windows Einstellungen":::

> [!NOTE]
> Wenn Sie sich für die Verwendung des Standortdiensts entscheiden, gilt dies nur für Windows Betriebssystem selbst. Apps dürfen keine Standortdienste verwenden. Jeder Benutzer kann auswählen, ob Apps auf seinen Standort zugreifen dürfen.