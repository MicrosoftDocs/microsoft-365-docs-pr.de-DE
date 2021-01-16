---
title: Verwalten von Geräten, die in Der mobilen Geräteverwaltung in Microsoft 365 registriert sind
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
description: Basic Mobility and Security kann Ihnen helfen, mobile Geräte zu sichern und zu verwalten.
ms.openlocfilehash: 4954da0ff44276d9bd46cabc78bc52c7879e5e26
ms.sourcegitcommit: 8849dd6f80217c29f427c7f008d918f30c792240
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49876960"
---
# <a name="manage-devices-enrolled-in-mobile-device-management-in-microsoft-365"></a>Verwalten von Geräten, die in Der mobilen Geräteverwaltung in Microsoft 365 registriert sind

Die integrierte Verwaltung mobiler Geräte für Microsoft 365 hilft Ihnen, die mobilen Geräte Ihrer Benutzer wie iPhones, iPads, Androids und Windows Phones zu sichern und zu verwalten. Der erste Schritt besteht in der Anmeldung bei Microsoft 365 und dem Einrichten von Basic Mobility and Security. Weitere Informationen finden Sie unter [Einrichten von Basic Mobility and Security](set-up.md).

Nachdem Sie es eingerichtet haben, müssen die Mitarbeiter in Ihrer Organisation ihre Geräte beim Dienst registrieren. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit Basic Mobility and Security](enroll-your-mobile-device.md).Anschließend können Sie basic Mobility and Security verwenden, um Geräte in Ihrer Organisation zu verwalten. Sie können z. B. Gerätesicherheitsrichtlinien verwenden, um den E-Mail-Zugriff oder andere Dienste zu beschränken, Geräteberichte anzeigen und ein Gerät remote zu löschen. Normalerweise wechseln Sie zum Security & Compliance Center, um diese Aufgaben auszuführen. Weitere Informationen finden Sie im [Microsoft 365 Compliance Center.](https://support.microsoft.com/office/7e696a40-b86b-4a20-afcc-559218b7b1b8)

## <a name="device-management-tasks"></a>Geräteverwaltungsaufgaben

Führen Sie die folgenden Schritte aus, um zum Geräteverwaltungspanel zu kommen:

1. Wechseln Sie zum [Microsoft 365 Admin Center.](https://support.microsoft.com/office/758befc4-0888-4009-9f14-0d147402fd23)

2. Geben Sie die Verwaltung mobiler Geräte in das Suchfeld ein, und wählen Sie in der Ergebnisliste die Option **"Mobile**   Geräteverwaltung" aus.

    :::image type="content" source="../../media/basic-mobility-security/bms-6-mobile-device-management-option.png" alt-text="Option für die Verwaltung mobiler Geräte":::

3. Wählen  **Sie "Los geht's" aus.**

## <a name="manage-mobile-devices"></a>Verwalten mobiler Geräte

Nachdem Sie Basic Mobility and Security eingerichtet haben, finden Sie hier einige Möglichkeiten, wie Sie die mobilen Geräte in Ihrer Organisation verwalten können.

|**Zweck**|**Aktion...**|
|:----------------|:------------------------------------------------------------------------------|
|Zurücksetzen eines Geräts |Wählen Sie im Bereich "Geräteverwaltung"  ****  ** den Gerätenamen und dann die vollständige Löschung aus, um alle Informationen zu löschen, oder die selektive Löschung, um nur Organisationsinformationen   auf dem Gerät zu  ****   löschen. Weitere Informationen finden Sie unter [Wipe a mobile device in Basic Mobility and Security](wipe-mobile-device.md).|
|Blockieren des Zugriffs auf Exchange-E-Mail für nicht unterstützte Geräte unter Verwendung von Exchange ActiveSync |Wählen Sie im Bereich "Geräteverwaltung" die Option  **"Blockieren" aus.** |
|Einrichten von Geräterichtlinien wie Kennwortanforderungen und Sicherheitseinstellungen |Wählen Sie im Bereich "Geräteverwaltung" die Option **"Gerätesicherheitsrichtlinien**   >  **hinzufügen+ " aus.** Weitere Informationen finden Sie unter [Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security](create-device-security-policies.md).|
|Anzeigen des Liste blockierter Geräte  |Wählen Sie im Bereich "Geräteverwaltung" unter  **"Ansicht auswählen"**   die Option  **"Blockiert" aus.** |
|Entsperren eines nicht kompatiblen oder nicht unterstützten Geräts für einen Benutzer oder eine Benutzergruppe  |Wählen Sie eine der folgenden Optionen aus, um die Blockierung von Geräten zu aufheben:<br/>– Entfernen Sie die Benutzer aus der Sicherheitsgruppe, auf die die Richtlinie angewendet wurde. Wechseln Sie zu Microsoft 365 Admin Center > **Gruppen,** und wählen Sie dann den Gruppennamen aus. Wählen **Sie "Mitglieder und Administratoren bearbeiten" aus.**<br/>– Entfernen Sie die Sicherheitsgruppe, in der die Benutzer Mitglied sind, aus der Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security policies** Device   >  **security policies**. Wählen Sie den Namen der Geräterichtlinie aus, und wählen Sie dann **"Bereitstellung**  >  **bearbeiten" aus.**<br/>– Aufheben der Blockierung aller nicht kompatiblen Geräte für eine Geräterichtlinie. Wechseln Sie zu Security & Compliance Center > **Security policies** Device   >  **security policies**. Wählen Sie den Namen der Geräterichtlinie und dann **"Zugriffsanforderungen**  >  **bearbeiten" aus.** Wählen Sie  **"Zugriff zulassen" aus, und melden Sie eine Verletzung.**<br/>- To unblock a noncompliant or unsupported device for a user or a group of users, go to Security & Compliance Center > **Security policies Device**   >  **management**   >  **Manage device access settings**. Fügen Sie eine Sicherheitsgruppe mit den Mitgliedern hinzu, die Sie von der Sperrung des Zugriffs auf Microsoft 365 ausschließen möchten. Weitere Informationen finden Sie unter Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im [Microsoft 365 Admin Center.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)|
|Entfernen von Benutzern, damit ihre Geräte nicht mehr von Basic Mobility and Security verwaltet werden |Um den Benutzer zu entfernen, bearbeiten Sie die Sicherheitsgruppe mit Geräteverwaltungsrichtlinien für Basic Mobility and Security. Weitere Informationen finden Sie unter Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im  [Microsoft 365 Admin Center.](https://support.microsoft.com/office/55c96b32-e086-4c9e-948b-a018b44510cb)<br/>Informationen zum Entfernen von Basic Mobility and Security von allen Microsoft 365-Benutzern finden Sie unter ["Deaktivieren von Basic Mobility and Security".](turn-off.md)|

Live (v14)