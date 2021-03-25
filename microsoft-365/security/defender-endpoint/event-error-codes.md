---
title: Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige
description: Erhalten Sie Beschreibungen und weitere Schritte zur Problembehandlung (falls erforderlich) für alle Ereignisse, die vom Microsoft Defender for Endpoint-Dienst gemeldet wurden.
keywords: Problembehandlung, Ereignisanzeige, Protokollzusammenfassung, Fehlercode, Fehler, Microsoft Defender for Endpoint-Dienst, kann nicht gestartet, unterbrochen, nicht gestartet werden
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068583"
---
# <a name="review-events-and-errors-using-event-viewer"></a>Überprüfen von Ereignissen und Fehlern mithilfe der Ereignisanzeige

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**Gilt für:**
- Ereignisanzeige
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

Sie können Ereignis-IDs in der [Ereignisanzeige auf](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) einzelnen Geräten überprüfen.

Wenn Geräte beispielsweise nicht in der Liste Geräte angezeigt **werden,** müssen Sie möglicherweise nach Ereignis-IDs auf den Geräten suchen. Anschließend können Sie diese Tabelle verwenden, um weitere Schritte zur Problembehandlung zu ermitteln.

**Öffnen Sie die Ereignisanzeige, und suchen Sie das Microsoft Defender for Endpoint-Dienstereignisprotokoll:**

1. Klicken **Sie im** Menü Windows auf Start, geben Sie **Ereignisanzeige ein,** und drücken Sie die **EINGABETASTE.**

2. Führen Sie in der Protokollliste unter **Protokollzusammenfassung** einen Bildlauf durch, bis **Microsoft-Windows-SENSE/Operational angezeigt wird.** Doppelklicken Sie auf das Element, um das Protokoll zu öffnen.

   a.  Sie können auch auf das Protokoll zugreifen, indem Sie **Anwendungen und Dienstprotokolle** Microsoft Windows SENSE erweitern  >    >    >   und auf **Betriebs klicken.**

   > [!NOTE]
   > SENSE ist der interne Name, der verwendet wird, um auf den Verhaltenssensor zu verweisen, der Microsoft Defender for Endpoint unterstützt.

3. Vom Dienst aufgezeichnete Ereignisse werden im Protokoll angezeigt. Eine Liste der vom Dienst aufgezeichneten Ereignisse finden Sie in der folgenden Tabelle.

<table>
<tbody style="vertical-align:top;">
<tr>
<th>Ereigniskennung</th>
<th>Message</th>
<th>Beschreibung</th>
<th>Aktion</th>
</tr>
<tr>
<td>1</td>
<td>Microsoft Defender for Endpoint Service gestartet (Version <code>variable</code> ).</td>
<td>Tritt während des Start-, Herunterfahrens und während des Onbboardings auf.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>2</td>
<td>Herunterfahren des Microsoft Defender for Endpoint-Diensts.</td>
<td>Tritt auf, wenn das Gerät heruntergefahren oder offboarded wird.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>3</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte nicht gestartet werden. Fehlercode: <code>variable</code> .</td>
<td>Der Dienst wurde nicht gestartet.</td>
<td>Überprüfen Sie andere Nachrichten, um mögliche Ursachen und Schritte zur Problembehandlung zu ermitteln.</td>
</tr>
<tr>
<td>4 </td>
<td>Der Microsoft Defender for Endpoint-Dienst hat den Server unter <code>variable</code> kontaktiert.</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Diese URL ist mit der In der Firewall- oder Netzwerkaktivität übereinstimmend.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>5 </td>
<td>Microsoft Defender for Endpoint-Dienst konnte keine Verbindung mit dem Server unter <code>variable</code> herstellen.</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</td>
<td>Überprüfen Sie die Verbindung zur URL. Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</td>
</tr>
<tr>
<td>6 </td>
<td>Der Microsoft Defender for Endpoint-Dienst ist nicht onboarded, und es wurden keine Onboardingparameter gefunden.</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Das Onboarding muss vor dem Starten des Diensts ausgeführt werden.<br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>7 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte die Onboardingparameter nicht lesen. Fehler: <code>variable</code> .</td>
<td>Variable = detaillierte Fehlerbeschreibung. Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>8 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte seine Konfiguration nicht bereinigen. Fehlercode: <code>variable</code> .</td>
<td><b>Während des Onboardings:</b> Fehler beim Bereinigen der Konfiguration während des Onboardings durch den Dienst. Der Onboardingprozess wird fortgesetzt. <br><br> <b>Während des Offboardings:</b> Der Dienst konnte seine Konfiguration während des Offboardings nicht bereinigen. Der Offboardingvorgang wurde abgeschlossen, der Dienst wird jedoch weiterhin ausgeführt.
 </td>
<td><b>Onboarding:</b> Keine Aktion erforderlich. <br><br> <b>Offboarding:</b> Starten Sie das System neu.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>9 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte seinen Starttyp nicht ändern. Fehlercode: <code>variable</code> .</td>
<td><b>Während des Onboardings:</b> Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal. <br><br><b>Während des Offboardings:</b> Fehler beim Ändern des Dienststarttyps. Der Offboardingprozess wird fortgesetzt. </td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>10  </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte die Onboardinginformationen nicht beibehalten. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert und meldet nicht an das Portal.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>11</td>
<td>Onboarding oder erneutes Onboarding des Defender for Endpoint-Diensts abgeschlossen.</td>
<td>Das Gerät wurde ordnungsgemäß onboardiert.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.<br>
Es kann mehrere Stunden dauern, bis das Gerät im Portal angezeigt wird.</td>
</tr>
<tr>
<td>12 </td>
<td>Microsoft Defender for Endpoint konnte die Standardkonfiguration nicht anwenden.</td>
<td>Der Dienst konnte die Standardkonfiguration nicht anwenden.</td>
<td>Dieser Fehler sollte nach kurzer Zeit behoben werden.</td>
</tr>
<tr>
<td>13</td>
<td>Microsoft Defender for Endpoint-Geräte-ID berechnet: <code>variable</code> .</td>
<td>Normaler Betriebsprozess.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>15 </td>
<td>Microsoft Defender for Endpoint kann den Befehlskanal nicht mit DER URL starten: <code>variable</code> .</td>
<td>Variable = URL der Defender for Endpoint-Verarbeitungsserver.<br>
Der Dienst konnte die externen Verarbeitungsserver unter dieser URL nicht kontaktieren.</td>
<td>Überprüfen Sie die Verbindung zur URL. Weitere Informationen finden Sie unter <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and internet connectivity</a>.</td>
</tr>
<tr>
<td>17 </td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Speicherort des Diensts für verbundene Benutzererfahrungen und Telemetrie nicht ändern. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>18 </td>
<td>OOBE (Windows Welcome) ist abgeschlossen.</td>
<td>Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>19</td>
<td>OOBE (Windows Welcome) wurde noch nicht abgeschlossen.</td>
<td>Der Dienst wird erst gestartet, nachdem alle Windows-Updates installiert wurden.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.<br>
Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</td>
</tr>
<tr>
<td>20</td>
<td>Kann nicht warten, bis OOBE (Windows Welcome) abgeschlossen ist. Fehlercode: <code>variable</code> .</td>
<td>Interner Fehler.</td>
<td>Wenn dieser Fehler nach einem Systemneustart weiterhin auftritt, stellen Sie sicher, dass alle Windows-Updates vollständig installiert sind.</td>
</tr>
<tr>
<td>25</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Integritätsstatus in der Registrierung nicht zurücksetzen. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert.
Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>26</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den Onboardingstatus in der Registrierung nicht festlegen. Fehlercode: <code>variable</code> .</td>
<td>Das Gerät wurde nicht ordnungsgemäß onboardiert.<br>
Er wird dem Portal gemeldet, der Dienst wird jedoch möglicherweise nicht in SCCM oder der Registrierung registriert angezeigt.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>27</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-bewussten Modus in Microsoft Defender Antivirus nicht aktivieren. Fehler beim Onboardingprozess. Fehlercode: <code>variable</code> .</td>
<td>Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a><br>
Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</td>
</tr>
<tr>
<td>28</td>
<td>Fehler bei der Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>29</td>
<td>Fehler beim Lesen der offboarding-Parameter. Fehlertyp: %1, Fehlercode: %2, Beschreibung: %3 </td>
<td>Dieses Ereignis tritt auf, wenn das System&#39;offboarding-Parameter nicht lesen kann.</td>
<td>Stellen Sie sicher, dass das Gerät über Internetzugriff verfügt, und führen Sie dann den gesamten Offboardingvorgang erneut aus. Stellen Sie sicher, dass das offboarding-Paket nicht abgelaufen ist.</td>
</tr>
<tr>
<td>30</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte den SENSE-benachrichtigungsmodus in Microsoft Defender Antivirus nicht deaktivieren. Fehlercode: <code>variable</code> .</td>
<td>Normalerweise wird Microsoft Defender Antivirus in einen speziellen passiven Zustand ein, wenn ein anderes Antischasoftwareprodukt in Echtzeit ordnungsgemäß auf dem Gerät ausgeführt wird und das Gerät an Defender for Endpoint meldet.</td>
<td>Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Siehe <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboarding von Windows 10-Geräten</a><br>
Stellen Sie sicher, dass der Antischalwareschutz in Echtzeit ordnungsgemäß ausgeführt wird.</td>
</tr>
<tr>
<td>31</td>
<td>Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist fehlgeschlagen. Fehlercode: <code>variable</code> .</td>
<td>Beim Onboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten. Der Offboardingprozess wird fortgesetzt.</td>
<td><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Überprüfen Sie mit dem Windows-Telemetriedienst auf Fehler.</a></td>
</tr>
<tr>
<td>32</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte nicht anfordern, dass er sich nach dem Offboardingvorgang selbst beendet. Fehlercode: %1</td>
<td>Beim Offboarding ist ein Fehler aufgetreten.</td>
<td>Starten Sie das Gerät neu.</td>
</tr>
<tr>
<td>33</td>
<td>Microsoft Defender for Endpoint-Dienst konnte die SENSE-GUID nicht beibehalten. Fehlercode: <code>variable</code> .</td>
<td>Ein eindeutiger Bezeichner wird verwendet, um jedes Gerät zu repräsentieren, das an das Portal meldet.<br>
Wenn der Bezeichner nicht beibehalten wird, wird das gleiche Gerät möglicherweise zweimal im Portal angezeigt.</td>
<td>Überprüfen Sie die Registrierungsberechtigungen auf dem Gerät, um sicherzustellen, dass der Dienst die Registrierung aktualisieren kann.</td>
</tr>
<tr>
<td>34</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie hinzufügen, wodurch der Onboardingprozess fehlschlagen konnte. Fehlercode: <code>variable</code> .</td>
<td>Beim Windows-Telemetriedienst ist ein Fehler aufgetreten.</td>
<td><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Stellen Sie sicher, dass der Diagnosedatendienst aktiviert ist.</a><br>
Überprüfen Sie, ob die Onboardingeinstellungen und Skripts ordnungsgemäß bereitgestellt wurden. Versuchen Sie, die Konfigurationspakete erneut zu bereitstellen.<br>
Weitere <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Informationen finden Sie unter Onboarding von Windows 10-Geräten.</a></td>
</tr>
<tr>
<td>35</td>
<td>Der Microsoft Defender for Endpoint-Dienst konnte sich nicht selbst als Abhängigkeit vom Dienst für verbundene Benutzererfahrungen und Telemetrie entfernen. Fehlercode: <code>variable</code> .</td>
<td>Beim Offboarding ist beim Windows-Telemetriedienst ein Fehler aufgetreten. Der Offboardingprozess wird fortgesetzt.
</td>
<td>Überprüfen Sie beim Windows-Diagnosedatendienst auf Fehler.</td>
</tr>
<tr>
<td>36</td>
<td>Die Registrierung des Microsoft Defender for Endpoint Connected User Experiences and Telemetry Service ist erfolgreich. Fertigstellungscode: <code>variable</code> .</td>
<td>Die Registrierung von Defender for Endpoint beim Dienst für verbundene Benutzererfahrungen und Telemetrie wurde erfolgreich abgeschlossen.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>37</td>
<td>Microsoft Defender for Endpoint A module is about to exceed its quota. Modul: %1, Kontingent: {%2} {%3}, Prozentsatz der Kontingentauslastung: %4.</td>
<td>Das gerät hat fast das zugewiesene Kontingent des aktuellen 24-Stunden-Fensters verwendet. Es wird gedrosselt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>38</td>
<td>Die Netzwerkverbindung wird als niedrig identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</td>
<td>Das Gerät verwendet ein gemessenes/kostenpflichtiges Netzwerk und kontaktiert den Server seltener.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>39</td>
<td>Die Netzwerkverbindung wird als normal identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Gemessene Verbindung: %2, Internet verfügbar: %3, kostenloses Netzwerk verfügbar: %4.</td>
<td>Das Gerät verwendet keine gemessene/kostenpflichtige Verbindung und kontaktiert den Server wie gewohnt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>40</td>
<td>Der Akkuzustand wird als niedrig gekennzeichnet. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Akkuzustand: %2.</td>
<td>Das Gerät hat einen niedrigen Akkustand und kontaktiert den Server seltener.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>41</td>
<td>Der Akkuzustand wird als normal identifiziert. Microsoft Defender for Endpoint kontaktiert den Server alle %1 Minuten. Akkuzustand: %2.</td>
<td>Das Gerät hat keinen niedrigen Akkustand und kontaktiert den Server wie gewohnt.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>42</td>
<td>Microsoft Defender for Endpoint WDATP-Komponente konnte keine Aktion ausführen. Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmemeldung: %4</td>
<td>Interner Fehler. Der Dienst konnte nicht gestartet werden.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>43</td>
<td>Microsoft Defender for Endpoint WDATP-Komponente konnte keine Aktion ausführen. Komponente: %1, Aktion: %2, Ausnahmetyp: %3, Ausnahmefehler: %4, Ausnahmemeldung: %5</td>
<td>Interner Fehler. Der Dienst konnte nicht gestartet werden.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>44</td>
<td>Offboarding des Defender for Endpoint-Diensts abgeschlossen.</td>
<td>Der Dienst wurde offboarded.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>45</td>
<td>Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1]. Fehlercode: %2</td>
<td>Beim Starten des Diensts beim Erstellen einer ETW-Sitzung ist ein Fehler aufgetreten. Dies führte zu einem Fehler beim Starten des Diensts.</td>
<td>Wenn dieser Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
<tr>
<td>46</td>
<td>Fehler beim Registrieren und Starten der Ereignisverfolgungssitzung [%1] aufgrund fehlender Ressourcen. Fehlercode: %2. Dies liegt wahrscheinlich daran, dass zu viele aktive Ereignisverfolgungssitzungen sind. Der Dienst wird in 1 Minute erneut versuchen.</td>
<td>Fehler beim Starten des Diensts beim Erstellen einer ETW-Sitzung aufgrund fehlender Ressourcen. Der Dienst wurde gestartet und wird ausgeführt, berichtet aber erst, wenn die ETW-Sitzung gestartet wurde.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich. Der Dienst versucht, die Sitzung jede Minute zu starten.</td>
</tr>
<tr>
<td>47</td>
<td>Die Ereignisverfolgungssitzung wurde erfolgreich registriert und gestartet – nach vorherigen fehlgeschlagenen Versuchen wiederhergestellt.</td>
<td>Dieses Ereignis folgt dem vorherigen Ereignis nach dem erfolgreichen Starten der ETW-Sitzung.</td>
<td>Normale Betriebsbenachrichtigung; keine Aktion erforderlich.</td>
</tr>
<tr>
<td>48</td>
<td>Fehler beim Hinzufügen eines Anbieters [%1] zur Ereignisverfolgungssitzung [%2]. Fehlercode: %3. Dies bedeutet, dass Ereignisse von diesem Anbieter nicht gemeldet werden.</td>
<td>Fehler beim Hinzufügen eines Anbieters zur ETW-Sitzung. Aus diesem Grund werden die Anbieterereignisse nicht gemeldet.</td>
<td>Überprüfen Sie den Fehlercode. Wenn der Fehler weiterhin auftritt, wenden Sie sich an den Support.</td>
</tr>
</tr>
</tbody>
</table>

>Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a>Verwandte Themen
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
- [Konfigurieren von Geräteproxy- und Internetverbindungseinstellungen](configure-proxy-internet.md)
- [Problembehandlung für Microsoft Defender for Endpoint](troubleshoot-onboarding.md)
