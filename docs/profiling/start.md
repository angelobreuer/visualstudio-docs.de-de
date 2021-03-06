---
title: Start | Microsoft-Dokumentation
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: b85d0fe9-f67a-4b7c-8d48-7eecf3f2dfe9
author: mikejo5000
ms.author: mikejo
manager: jillfra
monikerRange: vs-2017
ms.workload:
- multiple
ms.openlocfilehash: df3ccda9730be02bafb7f7d069a26193a4528d1e
ms.sourcegitcommit: cc841df335d1d22d281871fe41e74238d2fc52a6
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/18/2020
ms.locfileid: "74778270"
---
# <a name="start"></a>Starten
Die **Start**-Option ist eine *VSPerfCmd.exe*-Option, die den Profiler mit der angegebenen Profilerstellungsmethode initialisiert.

## <a name="syntax"></a>Syntax

```cmd
VSPerfCmd.exe /Start:Method /Output:FileName [Options]
```

#### <a name="parameters"></a>Parameter
 `Method` muss einem der folgenden Schlüsselwörter entsprechen:

- **TRACE**: Gibt die Instrumentationsmethode an.

- **SAMPLE**: Gibt die Samplingmethode an.

- **COVERAGE**: Gibt die Abdeckung des Codes an.

- **CONCURRENCY**: Gibt die Ressourcenkonfliktmethode an.

## <a name="required-options"></a>Erforderliche Optionen
 Die Option **Ausgabe** muss angegeben werden, wenn **Start** auf der Befehlszeilen angegeben wird.

 **Ausgabe:** `filename` gibt den Ausgabedateinamen an.

## <a name="exclusive-options"></a>Ausschließende Optionen
 Die folgenden Optionen können nur mit der Option **Start** in einer Befehlszeile verwendet werden.

 **CrossSession**&#124;**CS** ermöglicht die prozessübergreifende Profilerstellung. Die Optionsnamen **CrossSession** und **CS** werden beide unterstützt.

 **User:** [`domain\`]`username`: ermöglicht dem Client Zugriff auf den Monitor vom angegebenen Konto aus.

 **WinCounter:** `Path` [**Automark**:`n`] **WinCounter** gibt einen Windows-Leistungsindikator an, der als Markierung in die Profilerstellungs-Datendatei aufgenommen werden soll. **AutoMark** gibt das Intervall in Millisekunden zwischen dem Erfassen der Datendatei an.

## <a name="invalid-options"></a>Ungültige Optionen
 Die folgenden Optionen können nicht mit der Option **Start** in einer Befehlszeile verwendet werden.

 **Status** gilt für die Prozesse, für die ein Profil erstellt wurde. Prozesse und Threads und der aktuelle Zustand der Profile (ein/aus) wird hier aufgeführt. Wenn beispielsweise ein Prozess beendet wird, gibt **Status** dies nicht im Bericht an. **Status** zeigt an, ob vom Prozess ein Profil erstellt wird.

 **Shutdown**[ **:** `Timeout`] deaktiviert den Profiler.

## <a name="example"></a>Beispiel
 Das folgende Beispiel veranschaulicht, wie die *VSPerfCmd.exe*-Option **Start** den Profiler initialisiert.

```cmd
VSPerfCmd.exe /Start:Sample /Output:TestApp.exe.vsp
VSPerfCmd.exe /Launch:TestApp.exe
```

## <a name="see-also"></a>Siehe auch
- [VSPerfCmd](../profiling/vsperfcmd.md)
- [Profilerstellung für eigenständige Anwendungen](../profiling/command-line-profiling-of-stand-alone-applications.md)
- [Profilerstellung für ASP.NET-Webanwendungen](../profiling/command-line-profiling-of-aspnet-web-applications.md)
- [Profilerstellung für Dienste](../profiling/command-line-profiling-of-services.md)
