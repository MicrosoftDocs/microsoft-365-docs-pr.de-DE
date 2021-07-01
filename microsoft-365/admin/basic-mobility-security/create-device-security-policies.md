---
title: Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security
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
description: Verwenden Sie Basic Mobility and Security, um Geräterichtlinien zu erstellen, die Ihre Unternehmensinformationen schützen.
ms.openlocfilehash: 62dc2eef87d413a9cb62a01541126860620eec3f
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53228255"
---
# <a name="create-device-security-policies-in-basic-mobility-and-security"></a>Erstellen von Gerätesicherheitsrichtlinien in Basic Mobility and Security

Sie können Basic Mobility and Security verwenden, um Geräterichtlinien zu erstellen, die Ihre Unternehmensinformationen auf Microsoft 365 vor unbefugtem Zugriff schützen. Sie können Richtlinien auf jedes mobile Gerät in Ihrer Organisation anwenden, auf dem der Benutzer des Geräts über eine zutreffende Microsoft 365 Lizenz verfügt und das Gerät bei Basic Mobility and Security registriert hat.

## <a name="before-you-begin"></a>Bevor Sie beginnen

> [!IMPORTANT]
> Bevor Sie eine Richtlinie für mobile Geräte erstellen können, müssen Sie grundlegende Mobilität und Sicherheit aktivieren und einrichten. Weitere Informationen finden Sie unter "Übersicht über grundlegende Mobilität und Sicherheit".

- Erfahren Sie mehr über die Geräte, Apps für mobile Geräte und Sicherheitseinstellungen, die Von Basic Mobility und Security unterstützt werden. Siehe ["Funktionen der grundlegenden Mobilität und Sicherheit".](capabilities.md)
- Erstellen Sie Sicherheitsgruppen, die Microsoft 365 Benutzer enthalten, für die Sie Richtlinien bereitstellen möchten, und für Benutzer, die Sie möglicherweise ausschließen möchten, dass der Zugriff auf Microsoft 365 blockiert wird. Vor der Bereitstellung einer neuen Richtlinie für Ihre Organisation sollten Sie die Richtlinie testen, indem Sie diese für eine geringe Benutzeranzahl bereitstellen. Sie können eine Sicherheitsgruppe erstellen und verwenden, die nur sich selbst oder eine kleine Anzahl Microsoft 365 Benutzer enthält, die die Richtlinie für Sie testen können. Weitere Informationen zu Sicherheitsgruppen finden Sie unter [Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe.](../email/create-edit-or-delete-a-security-group.md)
- Um grundlegende Mobilitäts- und Sicherheitsrichtlinien in Microsoft 365 zu erstellen und bereitzustellen, müssen Sie ein Microsoft 365 globaler Administrator sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center.](../../security/office-365-security/permissions-in-the-security-and-compliance-center.md)
- Informieren Sie Ihre Organisation vor der Bereitstellung von Richtlinien über die potenziellen Auswirkungen der Registrierung eines Geräts in Basic Mobility and Security. Je nachdem, wie Sie die Richtlinien einrichten, können nicht konforme Geräte am Zugriff auf Microsoft 365 und Daten gehindert werden, einschließlich installierter Anwendungen, Fotos und persönlicher Informationen auf einem registrierten Gerät, und Daten können gelöscht werden.

> [!NOTE]
> Richtlinien und Zugriffsregeln, die in Basic Mobility and Security für Microsoft 365 Business Standard erstellt wurden, setzen Exchange ActiveSync Postfachrichtlinien und Gerätezugriffsregeln außer Kraft, die im Exchange Admin Center erstellt wurden. Nachdem ein Gerät in Basic Mobility and Security for Microsoft 365 Business Standard registriert wurde, werden alle Exchange ActiveSync Postfachrichtlinie oder Gerätezugriffsregel für mobile Geräte, die auf das Gerät angewendet werden, ignoriert. Weitere Informationen zu Exchange ActiveSync finden Sie [unter Exchange ActiveSync in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/exchange-activesync/exchange-activesync).

## <a name="step-1-create-a-device-policy-and-deploy-to-a-test-group"></a>Schritt 1: Erstellen einer Geräterichtlinie und Bereitstellen in einer Testgruppe

Bevor Sie beginnen können, stellen Sie sicher, dass Sie Die grundlegende Mobilität und Sicherheit aktiviert und eingerichtet haben. Anweisungen finden Sie unter ["Übersicht über grundlegende Mobilität und Sicherheit".](overview.md)

1. Geben Sie in Ihrem Browser <https://protection.office.com/devicev2> .

2. Wählen Sie **Richtlinie erstellen** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Richtlinieneinstellungen für Mobilität und Sicherheit":::

3. Geben Sie auf der Seite **"Richtlinieneinstellungen"** die Anforderungen an, die auf mobile Geräte in Ihrer Organisation angewendet werden sollen.

4. **Verwalten des E-Mail-Profils erforderlich:** Wenn diese Option aktiviert ist, gelten Geräte, die nicht über ein E-Mail-Profil verfügen, das von Basic Mobility and Security verwaltet wird, als nicht konform. Ein Gerät kann nicht über ein verwaltetes E-Mail-Profil verfügen, wenn es nicht korrekt ausgerichtet ist oder wenn der Benutzer das E-Mail-Konto auf dem Gerät manuell eingerichtet hat. Wenn Sie sie **nicht aktiviert** lassen (Standardeinstellung), wird diese Einstellung nicht auf Compliance oder Nichtkonformität ausgewertet. Anweisungen dazu, wie Benutzer konform werden können, wenn diese Option ausgewählt ist, finden Sie unter [Ein vorhandenes E-Mail-Konto wurde gefunden.](/intune-user-help/existing-company-email-account-found)

5. Wählen Sie auf der Seite **Möchten Sie diese Richtlinie jetzt anwenden?** die Gruppen aus, auf die Sie diese Richtlinie anwenden möchten.

6. Wählen Sie **diese Richtlinie erstellen** aus.

Die Richtlinie wird auf das Gerät jedes Benutzers übertragen, für den die Richtlinie gilt, wenn er sich das nächste Mal bei Microsoft 365 mithilfe seines mobilen Geräts anmeldet. Wenn Benutzer zuvor nach der Bereitstellung der Richtlinie keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie eine Benachrichtigung auf ihrem Gerät, die die Schritte zum Registrieren und Aktivieren von Basic Mobility and Security enthält. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security.](enroll-your-mobile-device.md) Bis sie die Registrierung bei basic Mobility and Security abgeschlossen haben, die vom Intune-Dienst gehostet wird, ist der Zugriff auf E-Mails, OneDrive und andere Dienste eingeschränkt. Nachdem sie die Registrierung mithilfe der Intune-Unternehmensportal-App abgeschlossen haben, können sie die Dienste verwenden, und die Richtlinie wird auf ihr Gerät angewendet.

## <a name="step-2-verify-that-your-policy-works"></a>Schritt 2: Überprüfen, ob Ihre Richtlinie funktioniert

Nachdem Sie eine Geräterichtlinie erstellt haben, überprüfen Sie, ob die Richtlinie wie erwartet funktioniert, bevor Sie sie in Ihrer Organisation bereitstellen.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie **die Liste der verwalteten Geräte anzeigen** aus.
3. Überprüfen Sie den Status von Benutzergeräten, für die die Richtlinie angewendet wurde. Sie möchten, dass der **Status** der Geräte **verwaltet wird.**
4. Sie können auch eine vollständige oder selektive Zurücksetzung auf einem Gerät durchführen, indem Sie nach der Auswahl eines Geräts auf die Schaltfläche "Zurücksetzen auf **Die Werkseinstellungen"** klicken oder "Unternehmensdaten aus der Schaltfläche **"Verwalten"** **entfernen.** Anweisungen finden Sie unter [Zurücksetzen eines mobilen Geräts in Microsoft 365.

## <a name="step-3-deploy-a-policy-to-your-organization"></a>Schritt 3: Bereitstellen einer Richtlinie für Ihre Organisation

Nachdem Sie eine Geräterichtlinie erstellt und überprüft haben, dass sie wie erwartet funktioniert, stellen Sie sie in Ihrer Organisation bereit.

1. Von Ihrem Browsertyp: [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie die Richtlinie aus, die Sie bereitstellen möchten, und wählen Sie **"Bearbeiten"** neben **"Gruppen" aus, auf die sie angewendet wurden.**
3. Suchen Sie nach einer Gruppe, die hinzugefügt werden soll, und klicken Sie auf **"Auswählen".**
4. Wählen Sie **"Schließen"** und **"Einstellung ändern" aus.**
5. Wählen Sie **"Schließen"** und **"Richtlinie bearbeiten" aus.**

Die Richtlinie wird auf das mobile Gerät jedes Benutzers übertragen, für den die Richtlinie gilt, wenn er sich das nächste Mal von ihrem mobilen Gerät aus bei Microsoft 365 anmeldet. Wenn Benutzer keine Richtlinie auf ihr mobiles Gerät angewendet haben, erhalten sie eine Benachrichtigung auf ihrem Gerät mit den Schritten zum Registrieren und Aktivieren für Grundlegende Mobilität und Sicherheit. Nachdem sie die Registrierung abgeschlossen haben, wird die Richtlinie auf ihr Gerät angewendet. Weitere Informationen finden Sie unter [Registrieren Ihres mobilen Geräts mit basic Mobility and Security.](enroll-your-mobile-device.md)

## <a name="step-4-block-email-access-for-unsupported-devices"></a>Schritt 4: Blockieren des E-Mail-Zugriffs für nicht unterstützte Geräte

Um Ihre Unternehmensinformationen zu schützen, sollten Sie den App-Zugriff auf Microsoft 365 E-Mails für mobile Geräte blockieren, die von Basic Mobility and Security nicht unterstützt werden. Eine Liste der unterstützten Geräte finden Sie unter ["Unterstützte Geräte".](../../admin/basic-mobility-security/capabilities.md)

**So blockieren Sie den App-Zugriff:**

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .
2. Wählen Sie **organisationsweite Gerätezugriffseinstellungen verwalten** aus.
3. Um nicht unterstützte Geräte zu blockieren, wählen Sie **"Blockieren"** unter **"Wenn ein Gerät von Basic Mobility and Security für Microsoft 365 nicht unterstützt wird"** aus, und wählen Sie dann **"Speichern"** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-5-block-access.png" alt-text="Option &quot;Grundlegende Mobilität und Sicherheit blockieren&quot;":::

## <a name="step-5-choose-security-groups-to-be-excluded-from-conditional-access-checks"></a>Schritt 5: Auswählen von aus Überprüfungen für den bedingten Zugriff auszuschließenden Sicherheitsgruppen

Wenn Sie einige Personen aus den Überprüfungen für den bedingten Zugriff auf ihren Mobilgeräten ausschließen möchten und Sie mindestens eine Sicherheitsgruppe für diese Personen erstellt haben, fügen Sie die Sicherheitsgruppen hier hinzu. Für die Personen in diesen Gruppen werden keine Richtlinien für ihre unterstützten mobilen Geräte erzwungen. Dies ist die empfohlene Option, wenn Sie die grundlegende Mobilität und Sicherheit in Ihrer Organisation nicht mehr verwenden möchten.

1. Geben Sie in Ihrem Browser [https://protection.office.com/devicev2](https://protection.office.com/devicev2) .

2. Wählen Sie **organisationsweite Gerätezugriffseinstellungen verwalten** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-4-policy.png" alt-text="Grundlegende Mobilität und Sicherheit – Erstellen einer Richtlinienoption":::

3. Wählen Sie **"Hinzufügen"** aus, um die Sicherheitsgruppe hinzuzufügen, deren Benutzer Sie von der Sperrung des Zugriffs auf Microsoft 365 ausschließen möchten. Wenn ein Benutzer dieser Liste hinzugefügt wurde, kann er auf Microsoft 365 E-Mail zugreifen, wenn er ein nicht unterstütztes Gerät verwendet.

4. Wählen Sie im **Bereich "Gruppe auswählen"** die Sicherheitsgruppe aus, die Sie verwenden möchten.

5. Wählen Sie den Namen aus, und **fügen Sie** dann  >  **"Speichern"** hinzu.

6. Wählen Sie im **organisationsweiten Bereich "Gerätezugriffseinstellungen"** die Option **"Speichern"** aus.

   :::image type="content" source="../../media/basic-mobility-security/bms-8-allow-access.png" alt-text="Grundlegende Mobilität und Sicherheit – Zugriffsoption zulassen":::

## <a name="what-is-the-impact-of-security-policies-on-different-device-types"></a>Wie wirken sich Sicherheitsrichtlinien auf verschiedene Gerätetypen aus?

Wenn Sie eine Richtlinie auf Benutzergeräte anwenden, sind die Auswirkungen auf jedes Gerät je nach Gerätetyp unterschiedlich. In der folgenden Tabelle finden Sie Beispiele für die Auswirkung von Richtlinien auf verschiedene Geräte.

|**Sicherheitspolitik**|**Android 4 und höher**|**Samsung KNOX**|**iOS 6 und höher**|**Hinweise**|
|:-----|:-----|:-----|:-----|:-----|
|Verschlüsselte Sicherung erforderlich|Nein|Ja|Ja|iOS-verschlüsselte Sicherung erforderlich.|
|Cloudsicherung blockieren|Ja|Ja|Ja|Google-Sicherung auf Android blockieren (abgeblendet), Cloud-Sicherung auf iOS.|
|Dokumentsynchronisierung blockieren|Nein|Nein|Ja|iOS: Dokumente in der Cloud blockieren.|
|Fotosynchronisierung blockieren |Nein|Nein|Ja|iOS (systemeigen): Fotodatenstrom blockieren.|
|Screenshots blockieren |Nein|Ja|Ja|Bei Versuch blockiert.|
|Videokonferenz blockieren |Nein|Nein|Ja|FaceTime ist für iOS blockiert, nicht für Skype oder andere.|
|Senden von Diagnosedaten blockieren |Nein|Ja|Ja|Senden von Google-Absturzbericht unter Android blockieren|
|Zugriff auf den App-Store blockieren |Nein|Ja|Ja|App-Store-Symbol fehlt auf Android-Startseite, ist deaktiviert unter Windows, fehlt unter iOS.|
|Kennwort für den App-Store anfordern |Nein|Nein|Ja|iOS: Kennwort für iTunes-Käufe erforderlich.|
|Verbindung mit Wechselmedien blockieren |Nein|Ja|Nicht zutreffend|Android: SD-Karte ist in den Einstellungen abgeblendet, Windows benachrichtigt den Benutzer, installierte Apps sind nicht verfügbar|
|Bluetoothverbindung blockieren |Siehe Hinweise|Siehe Hinweise|Ja|BlueTooth kann unter Android nicht als Einstellung deaktiviert werden. Stattdessen deaktivieren wir alle Transaktionen, für die BlueTooth erforderlich ist: erweiterte Audioverteilung, Audio-/Video-Fernbedienung, freihändige Geräte, Headsets, Telefon Buchzugriff und serieller Port. Eine kleine Popupnachricht wird am unteren Rand der Seite angezeigt, wenn diese Transaktionen verwendet werden.|

## <a name="what-happens-when-you-delete-a-policy-or-remove-a-user-from-the-policy"></a>Was geschieht beim Löschen einer Richtlinie oder beim Entfernen eines Benutzers aus der Richtlinie?

Wenn Sie eine Richtlinie löschen oder einen Benutzer aus einer Gruppe entfernen, in der die Richtlinie bereitgestellt wurde, werden die Richtlinieneinstellungen Microsoft 365 E-Mail-Profils und zwischengespeicherte E-Mails möglicherweise vom Gerät des Benutzers entfernt. In der folgenden Tabelle sehen Sie, was für die verschiedenen Gerätetypen entfernt wird.

|**Entfernte Elemente**|**iOS 6 und höher**|**Android 4 und höher (einschließlich Samsung KNOX**|
|:-----|:-----|:-----|
|Verwaltete E-Mail-Profile<sup>1</sup>|Ja|Nein|
|Cloud-Sicherung blockieren|Ja|Nein|

<sup>1</sup> Wenn die Richtlinie mit der Option **"E-Mail-Profil verwaltet"** bereitgestellt wurde, werden das verwaltete E-Mail-Profil und die zwischengespeicherten E-Mails in diesem Profil vom Benutzergerät gelöscht.

Die Richtlinie wird für jeden Benutzer, für den die Richtlinie gilt, beim nächsten Einchecken des Geräts mit Basic Mobility and Security vom mobilen Gerät entfernt. Wenn Sie eine neue Richtlinie bereitstellen, die für diese Benutzergeräte gilt, werden sie aufgefordert, sich erneut bei Basic Mobility and Security zu registrieren.

Sie können ein Gerät auch vollständig oder selektiv vom Gerät löschen. Weitere Informationen finden Sie unter ["Zurücksetzen eines mobilen Geräts in Basic Mobility and Security".](wipe-mobile-device.md)

## <a name="related-content"></a>Verwandte Inhalte

[Übersicht über grundlegende Mobilität und Sicherheit](overview.md) (Artikel)\
[Funktionen der grundlegenden Mobilität und Sicherheit](capabilities.md) (Artikel)