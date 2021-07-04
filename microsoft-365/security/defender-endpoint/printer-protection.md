---
title: Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz
description: Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz verhindert, dass Benutzer über Nicht-Unternehmensdrucker oder nicht genehmigte USB-Drucker drucken.
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.author: v-lsaldanha
author: lovina-saldanha
ms.reviewer: dansimp
manager: dansimp
audience: ITPro
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 0f089efedef1e4fb6b146692da3f1a630f2bacac
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289691"
---
# <a name="device-control-printer-protection"></a>Druckerschutz für Gerätesteuerung

Microsoft Defender für Endpunkt Gerätesteuerungsdruckerschutz verhindert, dass Benutzer über Nicht-Unternehmensdrucker oder nicht genehmigte USB-Drucker drucken.

## <a name="licensing"></a>Lizenzierung

Bevor Sie mit Printer Protection beginnen, sollten Sie [Ihr Microsoft 365 Abonnement bestätigen.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) Für den Zugriff auf und die Verwendung von Printer Protection benötigen Sie Folgendes:

- Microsoft 365 E3 für die Bereitstellung von Funktionen/Richtlinien
- Microsoft 365 E5 für die Berichterstellung

## <a name="permission"></a>Berechtigung

Für die Richtlinienbereitstellung in Intune muss das Konto zum Bereitstellen von Richtlinien über OMA-URI über Berechtigungen zum Erstellen, Bearbeiten, Aktualisieren oder Löschen von Gerätekonfigurationsprofilen verfügen. Sie können benutzerdefinierte Rollen erstellen oder eine der integrierten Rollen mit diesen Berechtigungen verwenden:

- Rolle "Richtlinien- und Profil-Manager".
- Oder benutzerdefinierte Rolle mit aktivierten Berechtigungen zum Erstellen/Bearbeiten/Aktualisieren/Lesen/Löschen/Anzeigen von Berichten für Gerätekonfigurationsprofile
- Oder globaler Administrator

Um Gerätekonfigurationsberichte anzuzeigen, muss das Konto über Anzeigeberichtsberechtigungen verfügen. Sie können benutzerdefinierte Rollen erstellen oder die integrierten Rollen mit diesen Berechtigungen verwenden:

- Globaler Sicherheitsadministrator
- Sicherheitsadministrator
- Sicherheitsleseberechtigter

## <a name="prepare-your-endpoints"></a>Vorbereiten der Endpunkte

Stellen Sie sicher, dass die Windows 10 Geräte, die Sie für die Bereitstellung von Printer Protection planen, um diese Anforderungen zu erfüllen.

1. Treten Sie dem Insider-Programm bei.

1. Die folgenden Windows-Updates sind installiert.
    - For Windows 1809: install Windows Update [KB5003217](https://support.microsoft.com/topic/may-20-2021-kb5003217-os-build-17763-1971-preview-08687c95-0740-421b-a205-54aa2c716b46)
    - For Windows 1909: install Windows Update [KB5003212](https://support.microsoft.com/topic/may-20-2021-kb5003212-os-build-18363-1593-preview-05381524-8380-4b30-b783-e330cad3d4a1)
    - Für Windows 2004 oder höher

1. Wenn Sie die Bereitstellung von Richtlinien über Gruppenrichtlinien planen, muss das Gerät MDATP-mitglied sein. Wenn Sie eine Richtlinie über MEM bereitstellen möchten, muss das Gerät intune-mitglied sein.

## <a name="deploy-device-control-printer-protection-policy"></a>Bereitstellen der Druckerschutzrichtlinie für Gerätesteuerung

Sie können die Richtlinie über gruppenrichtlinien oder Intune bereitstellen.

<br>

****

|Titel|Beschreibung|CSP-Unterstützung | GPO-Unterstützung | Benutzerbasierter Support | Computerbasierter Support |
|---|---|:---:|:---:|:---:|:---:|
|**Aktivieren von Druckeinschränkungen für Gerätesteuerelemente**|Blockieren des Druckens über einen Drucker, der kein Unternehmen ist|Ja|Ja|Ja|Ja|
|**Liste der genehmigten USB-verbundenen Druckgeräte**\*|Zulassen eines bestimmten USB-Druckers|Ja|Ja|Ja|Ja|
|

\* Diese Richtlinie muss zusammen mit **den Druckeinschränkungen** für die Gerätesteuerung verwendet werden.

## <a name="deploy-policy-via-intune"></a>Bereitstellen von Richtlinien über Intune

Für Intune unterstützt der Gerätesteuerungsdruckerschutz derzeit nur OMA-URI.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-intune"></a>Szenario 1: Blockieren des Druckens über einen beliebigen Drucker, der nicht zum Unternehmen gehört, mit Intune

- Anwenden von Richtlinien über Computer:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControl`

- Wenden Sie die Richtlinie über den Benutzer an:

  `./Vendor/MSFT/Policy/Config/Printers/EnableDeviceControlUser`

Die CSP-Unterstützungszeichenfolge `<enabled/>` mit:

:::image type="content" source="../../media/customeditrow.png" alt-text="Benutzerdefinierte Bearbeitungszeile":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-intune"></a>Szenario 2: Zulassen bestimmter genehmigter USB-Drucker mit Intune

- Anwenden von Richtlinien über Computer:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevices`

- Wenden Sie die Richtlinie über den Benutzer an:

  `./Vendor/MSFT/Policy/Config/Printers/ApprovedUsbPrintDevicesUser`

Die CSP-Unterstützungszeichenfolge mit genehmigten USB-Druckern über die Eigenschaft "ApprovedUsbPrintDevices", `<enabled><data id="ApprovedUsbPrintDevices_List" value="03F0/0853,0351/0872">` Beispiel:

:::image type="content" source="../../media/editrow.png" alt-text="Zeile bearbeiten":::

## <a name="deploy-policy-via-group-policy"></a>Bereitstellen von Richtlinien über Gruppenrichtlinien

Wenn das Gerät nicht in Intune eingebunden ist, können Sie die Richtlinie auch über die Gruppenrichtlinie bereitstellen.

### <a name="scenario-1-block-people-from-printing-via-any-non-corporate-printer-using-group-policy"></a>Szenario 1: Blockieren des Druckens über einen beliebigen Nicht-Unternehmensdrucker mithilfe von Gruppenrichtlinien

- Anwenden von Richtlinien über Computer:

  Drucker für administrative Vorlagen für die \> \> Computerkonfiguration: Aktivieren von Druckeinschränkungen für Gerätesteuerelemente

- Wenden Sie die Richtlinie über den Benutzer an:

  Drucker der Systemsteuerung für administrative Vorlagen der \> Benutzerkonfiguration: Aktivieren von \> \> Druckeinschränkungen für Gerätesteuerelemente

:::image type="content" source="../../media/enable-device-ctrl-printing-restrictions.png" alt-text="Aktivieren von Einschränkungen beim Drucken von Geräten":::

### <a name="scenario-2-allow-specific-approved-usb-printers-using-group-policy"></a>Szenario 2: Zulassen bestimmter genehmigter USB-Drucker mithilfe von Gruppenrichtlinien

- Anwenden von Richtlinien über Computer:

  Drucker für administrative Vorlagen für die \> Computerkonfiguration: \> Liste der genehmigten USB-verbundenen Druckgeräte

- Wenden Sie die Richtlinie über den Benutzer an:

  Benutzerkonfiguration \> Administrative Vorlagen \> \> Systemsteuerungsdrucker: Liste der genehmigten USB-verbundenen Druckgeräte

:::image type="content" source="../../media/list-of-approved-connected-print-devices.png" alt-text="Liste der genehmigten usb-verbundenen Druckgeräte":::

## <a name="view-device-control-printer-protection-data-in-microsoft-defender-for-endpoint-portal"></a>Anzeigen von Gerätesteuerungsdrucker-Schutzdaten im Microsoft Defender für Endpunkt-Portal

Das [Microsoft 365 Security Center](https://security.microsoft.com) zeigt das Drucken an, das durch die oben beschriebene Richtlinie für den Gerätesteuerungsdruckerschutz blockiert wurde.

```sql
DeviceEvents

|where ActionType == 'PrintJobBlocked'

| extend parsed=parse_json(AdditionalFields)

| extend PrintedFile=tostring(parsed.JobOrDocumentName)

| extend PrintPortName=tostring(parsed.PortName)

| extend PrinterName=tostring(parsed.PrinterName)

| extend Policy=tostring(parsed.RestrictionReason) 

| project Timestamp, DeviceId, DeviceName, ActionType, InitiatingProcessAccountName,Policy, PrintedFile, PrinterName, PrintPortName, AdditionalFields

| order by Timestamp desc
```

 :::image type="content" source="../../media/device-control-advanced-hunting.png" alt-text="Erweiterte Suche":::
