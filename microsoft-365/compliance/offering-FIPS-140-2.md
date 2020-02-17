---
title: FIPS-Publikation 140-2 (Federal Information Processing Standard)
description: Microsoft bescheinigt, dass seine kryptografischen Module dem US-Bundes Informationsverarbeitungs Standard entsprechen.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 1a1e8b19ff214d29dc8a309cce4f79de92cf8155
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42071292"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>FIPS-Publikation 140-2 (Federal Information Processing Standard)

## <a name="fips-140-2-standard-overview"></a>FIPS 140-2 Standard (Übersicht)

Die FIPS-Publikation 140-2 (Federal Information Processing Standard) ist ein US-Regierungsstandard, der Mindestanforderungen an die Sicherheit von kryptografischen Modulen in IT-Produkten definiert, wie in Abschnitt 5131 der Informationen definiert. Technology Management Reform Act vom 1996.

Das [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP), eine gemeinsame Anstrengung des US National Institute of Standards and Technology (NIST) und des kanadischen Zentrums für Cyber Security (CCCS), validiert kryptografische Module für die *Sicherheitsanforderungen für kryptografische Module* Standard (dh., FIPS 140-2) und die zugehörigen FIPS Cryptography Standards. Die FIPS 140-2-Sicherheitsanforderungen umfassen 11 Bereiche im Zusammenhang mit dem Entwurf und der Implementierung eines kryptografischen Moduls. Das NIST-Informationstechnologie Labor betreibt ein verwandtes Programm, das die FIPS-genehmigten kryptografischen Algorithmen im Modul validiert.

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Microsoft-Ansatz für die FIPS 140-2-Validierung

Microsoft hält eine aktive Verpflichtung zur Erfüllung der 140-2-Anforderungen, wobei kryptografische Module seit der Einführung des Standards in 2001 validiert wurden. Microsoft validiert seine kryptografischen Module unter dem [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP) des National Institute of Standards and Technology (NIST). Mehrere Microsoft-Produkte, einschließlich vieler Cloud-Dienste, verwenden diese kryptografischen Module.

Technische Informationen zu Microsoft Windows Cryptographic Modules, die Sicherheitsrichtlinie für jedes Modul und den Katalog mit CMVP-Zertifikatdetails finden Sie unter [Windows und Windows Server FIPS 140-2-Inhalt](https://aka.ms/AA6ehud).

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft-Clouddienste im Leistungsumfang

Während der aktuelle CMVP FIPS 140-2-Implementierungsleitfaden eine FIPS 140-2-Validierung für einen clouddienst selbst ausschließt; Cloud-Dienstanbieter können sich dafür entscheiden, FIPS 140 validierte kryptografische Module für die Datenverarbeitungs Elemente, die ihren clouddienst umfassen, zu erhalten und zu betreiben. Zu den Microsoft Online Services, die Komponenten enthalten, die FIPS 140-2 validiert wurden, gehören unter anderem:

- [Azure und Azure Government](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 und Dynamics 365 Government](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Worin besteht der Unterschied zwischen "FIPS 140 validiert" und "FIPS 140 konform"?**

"FIPS 140 validiert" bedeutet, dass das kryptografische Modul oder ein Produkt, das das Modul einbettet, vom CMVP validiert ("zertifiziert") wurde, da die Anforderungen für FIPS 140-2 erfüllt sind. "FIPS 140-konform" ist ein Branchenbegriff für IT-Produkte, die auf FIPS 140 validierte Produkte für kryptografische Funktionen basieren.

**Wann übernimmt Microsoft eine FIPS 140-Validierung?**

Die Kadenz für das Starten einer Modul Überprüfung richtet sich nach den Funktionsupdates von Windows 10 und Windows Server. Wenn sich die Softwareindustrie entwickelt hat, werden Betriebssysteme häufiger mit monatlichen Softwareupdates veröffentlicht. Microsoft unternimmt die Validierung für Feature-Releases, aber zwischen den Versionen versucht, die Änderungen an den kryptografischen Modulen zu minimieren.

**Welche Computer sind in einer FIPS 140-Validierung enthalten?**

Microsoft validiert kryptografische Module in einer repräsentativen Stichprobe von Hardwarekonfigurationen mit Windows 10 und Windows Server. Es ist gängige branchenübliche Praxis, diese FIPS 140-2-Validierung zu akzeptieren, wenn eine Umgebung Hardware verwendet, die den für den Validierungsprozess verwendeten Beispielen ähnelt.

**Auf der NIST-Website sind viele Module aufgeführt. Woher weiß ich, welche Anwendung für meine Agentur gilt?**

Wenn Sie kryptografische Module verwenden müssen, die über FIPS 140-2 validiert wurden, müssen Sie überprüfen, ob die verwendete Version in der Überprüfungsliste angezeigt wird. Die CMVP und Microsoft führen eine Liste validierter kryptografischer Module nach Produktversion zusammen mit Anweisungen zum Identifizieren der auf einem Windows-System installierten Module aus. Weitere Informationen zum Konfigurieren von Systemen, die kompatibel sein sollen, finden Sie unter [Windows und Windows Server FIPS 140-2-Inhalt](https://aka.ms/AA6ehud).

**Was bedeutet "bei Betrieb im FIPS-Modus" auf einem Zertifikat?**

Dieser Vorbehalt informiert den Leser darüber, dass die erforderlichen Konfigurations-und Sicherheitsregeln befolgt werden müssen, um das kryptografische Modul auf eine Art und Weise zu verwenden, die mit der FIPS 140-2-Sicherheitsrichtlinie übereinstimmt. Jedes Modul verfügt über eine eigene Sicherheitsrichtlinie – eine genaue Spezifikation der Sicherheitsregeln, unter denen es ausgeführt wird – und verwendet genehmigte kryptografische Algorithmen, kryptografische Schlüsselverwaltung und Authentifizierungstechniken. Die Sicherheitsregeln sind in der Sicherheitsrichtlinie für jedes Modul definiert. Weitere Informationen, einschließlich Links zur Sicherheitsrichtlinie für jedes Modul, das über das CMVP validiert wurde, finden Sie unter [Windows-und Windows Server FIPS 140-2-Inhalt](https://aka.ms/AA6ehud).

**Ist für FedRAMP die FIPS 140-2-Validierung erforderlich?**

Ja, das Bundes Risiko-und Autorisierungs Verwaltungsprogramm (FedRAMP) basiert auf den von der [NIST SP 800-53 Revision 4](https://nvd.nist.gov/800-53/Rev4/)definierten Steuerbasis Linien, einschließlich des [SC-13 Cryptographic Protection](https://nvd.nist.gov/800-53/Rev4/control/SC-13) , der die Verwendung von FIPS-validierter Kryptografie oder von NSA genehmigter Kryptografie erfordert.

**Wie unterstützt Microsoft Azure FIPS 140-2?**

Azure wurde mit einer Kombination aus Hardware, kommerziell verfügbaren Betriebssystemen (Linux und Windows) und Azure-spezifischer Windows-Version erstellt. Über den Microsoft [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/) (SDL) verwenden alle Azure-Dienste FIPS 140-2-zugelassene Algorithmen für die Datensicherheit, da das Betriebssystem FIPS 140-2-zugelassene Algorithmen verwendet, während es in einer Hyper Scale-Cloud funktioniert.

**Kann ich die Einhaltung von Microsoft für FIPS 140-2 im Zertifizierungsprozess meiner Agentur verwenden?**

Zur Einhaltung von FIPS 140-2 muss Ihr System so konfiguriert sein, dass es in einem FIPS-genehmigten Betriebsmodus ausgeführt wird, wodurch sichergestellt ist, dass ein kryptografisches Modul nur FIPS-geprüfte Algorithmen verwendet. Weitere Informationen zum Konfigurieren von Systemen, die kompatibel sein sollen, finden Sie unter [Windows und Windows Server FIPS 140-2-Inhalt](https://aka.ms/AA6ehud).

**Was ist die Beziehung zwischen FIPS 140-2 und allgemeinen Kriterien?**

Es handelt sich um zwei separate Sicherheitsstandards mit unterschiedlichen, aber komplementären Zwecken. FIPS 140-2 wurde speziell für die Validierung von Software-und Hardware kryptografischen Modulen entwickelt, während die allgemeinen Kriterien dazu dienen, Sicherheitsfunktionen in IT-Software und Hardwareprodukten zu evaluieren. Häufige Bewertungs Bewertungen basieren häufig auf FIPS 140-2-Validierungen, um sicherzustellen, dass die grundlegende kryptografische Funktionalität ordnungsgemäß implementiert ist.

## <a name="resources"></a>Ressourcen

- [FIPS PUB 140-2 Sicherheitsanforderungen für kryptografische Module](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [NIST Cryptographic Module Validation Program](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows, Windows Server und FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Hintergrundinformationen zum Angebot herunterladen

Benötigen Sie das Dokument mit Hintergrundwissen für dieses Angebot? Laden Sie die [PDF-Datei](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf) herunter.
