---
title: 'Fehler: Firewall und „Keine Authentifizierung“ | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: troubleshooting
f1_keywords:
- vs.debug.error.firewall.noauth
dev_langs:
- CSharp
- VB
- FSharp
- C++
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 4a72d16869c92b1965fae8db0ae32146a3a57e67
ms.sourcegitcommit: 3fe6bed9ef8fb1478106645f655c7472009ae43a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/28/2019
ms.locfileid: "64823952"
---
# <a name="error-firewall-no-authentication"></a>Fehler: Firewall und „Keine Authentifizierung“
Die Internetverbindungsfirewall auf dem Remotecomputer wurde nicht für das Remotedebuggen eingerichtet. Für das Remotedebuggen mit `No Authentication` muss der Ausnahmenliste die Datei msvsmon.exe hinzugefügt werden. Es ist möglicherweise auch erforderlich, einige IPSEC-Anschlüsse zu öffnen.

> [!NOTE]
> Der Remotedebugger kann die Windows Firewall automatisch konfigurieren. Wenn eine andere Firewall als die Windows Firewall verwendet wird, wie z. B. eine Software- oder Hardwarefirewall eines Drittanbieters, muss die Firewall manuell konfiguriert werden, um das Remotedebugging zu ermöglichen. Lassen Sie hierzu Verkehr für die TCP/IP-Ports zu, die von msvsmon.exe abgehört werden. Standardmäßig handelt es sich hierbei um Ports 4018 und 4019, wobei 4018 auf allen Betriebssystemen und 4019 wird nur unter Windows x64 verwendet wird, um Debugging von x86-Prozessen zu ermöglichen.

 Weitere Informationen finden Sie unter [Remotedebuggen](../debugger/remote-debugging.md).