---
title: Gerätebilder
description: Imageanforderungen beim Sortieren neuer Geräte oder beim Wiederverwenden vorhandener Geräte
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
ms.openlocfilehash: fb3646e2ff339115d3fe6043ed45ea8f2140105a
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419511"
---
# <a name="device-images"></a>Gerätebilder


Unabhängig davon, ob Sie [neue Geräte](#new-devices) bestellen oder [vorhandene](#existing-devices) wiederverwenden, haben Sie mehrere Optionen, um sicherzustellen, dass das Bild auf dem Gerät unseren [Geräteanforderungen](device-requirements.md#check-hardware-requirements)entspricht.

## <a name="new-devices"></a>Neue Geräte
Wenn Sie ein neues Gerät von einem [genehmigten Hersteller](device-requirements.md#minimum-requirements)bestellen, führen Sie die folgenden Schritte aus, um sicherzustellen, dass geräte mit der richtigen Microsoft Managed Desktop Image- und Softwarekonfiguration ausgeliefert werden. Jedes Mal, wenn Sie ein bestimmtes Gerätemodell zum ersten Mal im Dienst registrieren möchten, sollten Sie ein Beispiel testen, um sicherzustellen, dass es die erwartete Benutzererfahrung bietet. Weitere Informationen finden Sie unter [Überprüfen neuer Geräte.](/microsoft-365/managed-desktop/get-started/validate-device)

### <a name="dell"></a>Dell
Wenden Sie sich direkt an den Dell-Vertriebsmitarbeiter, der sicherstellt, dass das von Microsoft Managed Desktop genehmigte Image auf Geräte für Ihre Bestellung angewendet wird. Wenden Sie sich bei weiteren Fragen zu Dell-Geräten, dem Image und dem Bestellvorgang an MMD_at_dell@dell.com.

### <a name="hp"></a>Hp 
Wenn Sie neue Geräte von HP bestellen, müssen Sie die spezifische SKU verwenden, die im Abschnitt "Zusätzliche Anforderungen" für jedes Modell auf der Website ["Shop Windows 10 Pro Business Devices"](https://www.microsoft.com/windowsforbusiness/view-all-devices#view-all-filter) aufgeführt ist (filtern Sie die Ansicht, um Microsoft Managed Desktop Geräte anzuzeigen).

Wenn Sie ein Gerät von HP sortieren, das als [Ausnahme](customizing.md) genehmigt wurde, aber derzeit nicht auf der Seite "Geräteliste" aufgeführt ist, stellen Sie sicher, dass Sie die SKU anfordern, die für Ihr Modell verwendet werden soll. Wir arbeiten mit HP, um Diese Informationen mithilfe Ihrer Ausnahmeanforderung abzurufen. Sie können hp auch direkt kontaktieren, um Fragen zu Geräten und Anweisungen zur Gerätereihenfolge zu erhalten, indem Sie die folgenden Adressen verwenden:
 
- Nord- und Südamerika: mmd-americas@hp.com
- Europa/Naher Osten/Afrika: mmd-emea@hp.com
- Asien-Pazifik/Japan: mmd-apj@hp.com
- Global: mmd@hp.com

### <a name="lenovo"></a>Lenovo
Wenn Sie Geräte von Lenovo für die Verwendung in Microsoft Managed Desktop bestellen, müssen Sie eine bestimmte Teilenummer angeben, die im Rahmen der Bestellung enthalten ist. Wenden Sie sich an Ihren Lenovo-Vertriebsmitarbeiter oder Lenovo Channel Partner, und bitten Sie ihn, ein *Sonderangebotsmodell* mit einem System zu erstellen, das unsere [Geräteanforderungen](device-requirements.md#minimum-requirements)erfüllt. Um ein vorinstalliertes Bild einzuschließen, das mit Microsoft Managed Desktop kompatibel ist, bitten Sie den Vertriebsmitarbeiter, auf *"Systembausteinteilnummer NV0Q94938 – MMD Enablement"* zu verweisen. Wenden Sie sich an Ihren Lenovo-Vertriebsmitarbeiter oder Lenovo Channel Partner, um empfohlene Dienste, Support und Imageerstellungsdienste zu erwerben.

### <a name="microsoft"></a>Microsoft
Alle Microsoft-Geräte, die die Geräteanforderungen erfüllen, verfügen über ein Image, das mit Microsoft Managed Desktop funktioniert. Es sind keine weiteren Schritte erforderlich.

Um das neueste Image zu erhalten, das in der Werksversion auf einem Microsoft-Gerät verfügbar ist, arbeiten Sie mit Ihrem Surface-Spezialisten an der Verwendung des Surface-Vorgangs "Bestellgeschädigt".

## <a name="existing-devices"></a>Vorhandene Geräte

Sie können vorhandene Geräte wiederverwenden, solange sie sowohl den  [Geräteanforderungen](device-requirements.md#minimum-requirements) als auch den [Softwareanforderungen](device-requirements.md#installed-software)entsprechen. Führen Sie die für Ihren Hersteller relevanten Schritte aus.

Sie können Geräte entweder mit einem Image des Herstellers oder mithilfe des Microsoft Managed Desktop "universellen Bilds" neu abbilden. Um ein entsprechendes Herstellerimage zu erhalten, können Sie mindestens ein [neues Gerät](#new-devices) des Modells bestellen, das Sie wiederverwenden. Anschließend können Sie das Bild von diesem Gerät abrufen und es auf andere Geräte desselben Modells anwenden.

> [!NOTE]
> Es liegt in Ihrer Verantwortung, Bilder zu erstellen, zu testen und bereitzustellen. Wir empfehlen außerdem, nach Möglichkeit geeignete, vom Hersteller bereitgestellte Bilder anstelle von benutzerdefinierten Bildern zu verwenden , einschließlich des "universellen Bilds".

### <a name="hp"></a>Hp

Hp Commercial PCs, die mit dem HP Corporate Ready Image ausgeliefert wurden, enthalten ein . WIM-Datei für die Wiederherstellung. Sie können dieses Image verwenden, um das Factorywiederherstellungsimage auf andere Geräte desselben Modells anzuwenden.

Durch diese Schritte werden alle Daten auf dem Gerät entfernt. Bevor Sie also beginnen, sollten Sie alle Daten sichern, die Sie beibehalten möchten.

1. [Erstellen Sie ein startbares USB-Laufwerk](/windows-hardware/manufacture/desktop/winpe-create-usb-bootable-drive) mit WinPE.
2. Kopieren Sie diese Dateien aus C: \\ SOURCES auf das USB-Laufwerk:
    - Die WIM-Datei für die Werkswiederherstellung (z. B. HP \_ EliteBook \_ 840 \_ G7 \_ Notebook PC CR \_ \_ \_ 2004.wim)
    - Bereitstellen. Cmd
    - ReCreatePartitions.txt
3. [Starten des Geräts in WinPE](https://store.hp.com/us/en/tech-takes/how-to-boot-from-usb-drive-on-windows-10-pcs) USB-Laufwerk.
4. Führen Sie an einer Eingabeaufforderung [Diskpart.exe](/windows-server/administration/windows-commands/diskpart#additional-references)aus.
5. Führen Sie in Diskpart `list disk` die primäre Speicherdatenträgernummer aus (in der Regel Datenträger 0).
6. Beenden Sie Diskpart, indem Sie `exit` .
7. Führen Sie an der Eingabeaufforderung `deploy.cmd <sys_disk> <recovery_wim>` aus, wobei *sys_disk* die Datenträgernummer des primären Speicherdatenträgers ist, den Sie gerade ermittelt haben, und *recovery_wim* der Dateiname der . WIM-Datei, die Sie zuvor kopiert haben.
8. Entfernen Sie das USB-Laufwerk, und starten Sie das Gerät neu.

### <a name="microsoft"></a>Microsoft 

Microsoft Surface-Geräte enthalten "Bare Metal [Recovery"-Images,](https://support.microsoft.com/en-us/surfacerecoveryimage) die für jedes Modell spezifisch sind. Sie können diese Bilder verwenden, um Geräte neu abzubilden.

Diese Bilder verwenden die Windows Wiederherstellungsumgebung (WinRE) und dies ist ein manueller (nicht automatisierter) Prozess. Führen Sie die Schritte zum [Erstellen und Verwenden eines USB-Wiederherstellungslaufwerks für Surface](https://support.microsoft.com/surface/creating-and-using-a-usb-recovery-drive-for-surface-677852e2-ed34-45cb-40ef-398fc7d62c07)aus.


### <a name="universal-image"></a>Universelles Bild
Microsoft Managed Desktop hat ein Bild erstellt, das Windows 10 Pro und Microsoft 365 Apps für Enterprise enthält, die Sie mit Microsoft Managed Desktop verwenden können. Es empfiehlt sich jedoch, nach Möglichkeit Bilder zu verwenden, die für Microsoft Managed Desktop vom Hersteller bereitgestellt werden, auch wenn dies eine ältere Windows Version bedeutet, die aktualisiert werden muss, sobald sich der Benutzer anmeldet. Die Verwendung des Microsoft Managed Desktop Universellen Bilds sollte eine letzte Option sein.

- Wir aktualisieren das Image alle 30 bis 60 Tage mit den neuesten Windows monatlichen Qualitätsupdates und Microsoft 365 Apps für Enterprise Updates mindestens zweimal pro Jahr.
- Das Image enthält ein Wiederherstellungsbereitstellungspaket, um sicherzustellen, dass Microsoft 365 Apps für Enterprise nach Windows Wiederherstellungsszenarien wiederhergestellt wird.
- Sie können das Image mit USB-Laufwerken bereitstellen. Es enthält einen skriptfähigen Prozess zum Einfügen von Treibern (in der im Bild enthaltenen Dokumentation beschrieben).
- Sie können die enthaltenen Skripts und Ordner für die Verwendung mit anderen Anpassungen ändern, z. B. zum Hinzufügen bestimmter kumulativer Updates, zum Kopieren von Dateien oder zum Ausführen anderer Überprüfungen.
- Treiber und Qualitätsupdates werden Windows während der Bereitstellung über das USB-Laufwerk hinzugefügt.

> [!NOTE]
> Es liegt in Ihrer Verantwortung, alle erforderlichen Treiber hinzuzufügen, alle Tests durchzuführen und sicherzustellen, dass es keine Probleme mit dem endgültigen bereitgestellten Image gibt. Wir stellen das universelle Image "wie besehen" bereit, stellen aber technische Anleitungen bereit und beantworten Fragen. Wenden Sie sich an MMDImage@microsoft.com.

Senden Sie Anforderungen für den Inhalt und die Dokumentation für universelle Bilder, indem Sie eine Änderungsanforderung im [Verwaltungsportal](../get-started/access-admin-portal.md)erstellen.


