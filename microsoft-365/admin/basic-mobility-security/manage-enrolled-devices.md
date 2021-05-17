---
title: Verwalten von Geräten, die in der Mobile Device Management in Microsoft 365
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
search.appverid:
- MET150
description: Grundlegende Mobilität und Sicherheit können Ihnen dabei helfen, mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 4ff1c43343e00b7eac7aa38b2d266f163f79e2a7
ms.sourcegitcommit: 72795ec56a7c4db863dcaaff5e9f7c41c653fda8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/26/2021
ms.locfileid: "52023881"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Verwalten von Geräten, die in der Mobile Device Management in Microsoft 365

Die integrierte Verwaltung mobiler Geräte für Microsoft 365 hilft Ihnen, die mobilen Geräte Ihrer Benutzer wie iPhones, iPads, Androids und Windows zu sichern und zu verwalten. Der erste Schritt besteht in der Anmeldung bei Microsoft 365 und Einrichten von Basic Mobility and Security. Weitere Informationen finden Sie unter [Set up Basic Mobility and Security](set-up.md).

Nachdem Sie es eingerichtet haben, müssen die Personen in Ihrer Organisation ihre Geräte beim Dienst registrieren. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mithilfe von Basic Mobility and Security](enroll-your-mobile-device.md).Anschließend können Sie grundlegende Mobilität und Sicherheit verwenden, um Geräte in Ihrer Organisation zu verwalten. Beispielsweise können Sie Gerätesicherheitsrichtlinien verwenden, um den E-Mail-Zugriff oder andere Dienste zu beschränken, Geräteberichte anzeigen und ein Gerät remote wischen zu können. Normalerweise wechseln Sie zum Security & Compliance Center, um diese Aufgaben auszuführen. Weitere Informationen finden Sie unter [Microsoft 365 Compliance Center](../../compliance/microsoft-365-compliance-center.md).

## <a name="device-management-tasks"></a>Geräteverwaltungsaufgaben

Führen Sie die folgenden Schritte aus, um zum Geräteverwaltungspanel zu kommen:

1. Wechseln Sie zum [Microsoft 365 Admin Center](../../admin/admin-overview/about-the-admin-center.md).

2. Geben Sie mobile Geräteverwaltung in das Suchfeld ein, und wählen Sie **mobile Geräteverwaltung**   in der Liste der Ergebnisse aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Option für die Verwaltung mobiler Geräte":::

3. Wählen  **Sie Los geht's erste Schritte** aus.

## <a name="manage-mobile-devices"></a>Verwalten mobiler Geräte

Nachdem Sie grundlegende Mobilität und Sicherheit eingerichtet haben, finden Sie hier einige Möglichkeiten, wie Sie die mobilen Geräte in Ihrer Organisation verwalten können.

|**Zweck**|**Aktion...**|
|:----------------|:------------------------------------------------------------------------------|
|Zurücksetzen eines Geräts |Wählen Sie im Bereich Geräteverwaltung den  **** Gerätenamen *aus,* und löschen Sie dann vollständig, um alle Informationen zu löschen, oder selektive Löschung, um nur Organisationsinformationen   auf dem Gerät zu  ****   löschen. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).|
|Blockieren des Zugriffs auf Exchange-E-Mail für nicht unterstützte Geräte unter Verwendung von Exchange ActiveSync |Wählen Sie im Bereich Geräteverwaltung die Option  **Blockieren aus.** |
|Einrichten von Geräterichtlinien wie Kennwortanforderungen und Sicherheitseinstellungen |Wählen Sie im Bereich Geräteverwaltung die Option **Gerätesicherheitsrichtlinien**   >  **Hinzufügen + aus.** Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md).|
|Anzeigen des Liste blockierter Geräte  |Wählen Sie im Bereich Geräteverwaltung unter  **Ansicht auswählen** die Option   Blockiert  **aus.** |
|Entsperren eines nicht kompatiblen oder nicht unterstützten Geräts für einen Benutzer oder eine Benutzergruppe  |Wählen Sie einen der folgenden Optionen aus, um die Blockierung von Geräten zu aufheben:<br/>– Entfernen Sie den Benutzer oder die Benutzer aus der Sicherheitsgruppe, auf die die Richtlinie angewendet wurde. Wechseln Sie zu Microsoft 365 Admin Center > **Gruppen,** und wählen Sie dann Gruppennamen aus. Wählen **Sie Mitglieder und Administratoren bearbeiten aus.**<br/>– Entfernen Sie die Sicherheitsgruppe, in der die Benutzer Mitglied sind, aus der Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security policies** Device   >  **security policies**. Wählen Sie Geräterichtlinienname aus, und wählen Sie dann **Bereitstellung**  >  **bearbeiten aus.**<br/>- Aufheben der Blockierung aller nicht kompatiblen Geräte für eine Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security policies** Device   >  **security policies**. Wählen Sie Geräterichtlinienname aus, und wählen Sie **dann**  >  **Zugriffsanforderungen bearbeiten aus.** Wählen  **Sie Zugriffs- und Berichtsverletzung zulassen aus.**<br/>- Wechseln Sie zum Aufheben der Blockierung eines nicht kompatiblen oder nicht unterstützten Geräts für einen Benutzer oder eine Gruppe von Benutzern zu Security & Compliance Center > **Sicherheitsrichtlinien** Geräteverwaltung Gerätezugriffseinstellungen   >  ****   >  **** verwalten. Fügen Sie eine Sicherheitsgruppe mit den Mitgliedern hinzu, die Sie ausschließen möchten, dass der Zugriff auf das Microsoft 365. Weitere Informationen finden Sie unter [Erstellen, Bearbeiten](../../admin/email/create-edit-or-delete-a-security-group.md)oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center .|
|Entfernen von Benutzern, damit ihre Geräte nicht mehr von Basic Mobility and Security verwaltet werden |Um den Benutzer zu entfernen, bearbeiten Sie die Sicherheitsgruppe mit Geräteverwaltungsrichtlinien für Grundlegende Mobilität und Sicherheit. Weitere Informationen finden Sie unter  [Erstellen, Bearbeiten](../../admin/email/create-edit-or-delete-a-security-group.md)oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center .<br/>Informationen zum Entfernen der grundlegenden Mobilität und Sicherheit von Microsoft 365 Benutzern finden Sie unter [Deaktivieren von Basic Mobility and Security](turn-off.md).|

Live (v14)