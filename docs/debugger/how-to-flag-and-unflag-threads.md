---
title: 'Vorgehensweise: Kennzeichnen von Threads und Aufheben der Kennzeichnung | Microsoft-Dokumentation'
ms.date: 11/04/2016
ms.topic: conceptual
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
author: mikejo5000
ms.author: mikejo
manager: jillfra
ms.workload:
- multiple
ms.openlocfilehash: 68a2ce8b6ec429b3f7f5cd782c3dac52602eff16
ms.sourcegitcommit: 5f6ad1cefbcd3d531ce587ad30e684684f4c4d44
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/22/2019
ms.locfileid: "72733234"
---
# <a name="how-to-flag-and-unflag-threads-c-visual-basic-c"></a>Vorgehensweise: Kennzeichnen von Threads und Aufheben der Kennzeichnung (C#, Visual Basic, C++)

Sie können einen Thread, dem Sie besondere Aufmerksamkeit widmen möchten, kennzeichnen, indem Sie ihn in den Fenstern **Threads**, **Parallele Stapel** (Threadansicht), **Parallele Überwachung** und **GPU-Threads** mit einem Symbol versehen. Anhand dieses Symbols können Sie gekennzeichnete Threads von anderen Threads unterscheiden.

Gekennzeichnete Threads werden auch in der Liste **Thread** auf der Symbolleiste **Debugspeicherort** und in den anderen Multithreaddebugfenstern gesondert behandelt. Sie können alle Threads oder nur gekennzeichnete Threads in der Liste **Thread** oder in den anderen Fenstern anzeigen.

### <a name="to-flag-or-unflag-a-thread"></a>So Kennzeichnen Sie einen Thread bzw. haben die Kennzeichnung auf

- Suchen Sie in den Fenstern **Threads** oder **Parallele Überwachung** den gewünschten Thread, und klicken Sie auf das Flagsymbol, um das Flag auszuwählen oder zu löschen.
- Klicken Sie im Fenster **Parallele Stapel** mit der rechten Maustaste auf einen einzelnen Thread oder eine Gruppe von Threads, und klicken Sie dann entweder auf **Kennzeichnen / \<Thread>** oder auf **Kennzeichnung aufheben / \<Thread>** .

### <a name="to-unflag-all-threads"></a>So heben Sie die Kennzeichnung aller Threads auf

- Klicken Sie im Fenster **Threads** mit der rechten Maustaste auf einen Thread, und klicken Sie anschließend auf **Kennzeichnung aller Threads aufheben**.
- Wählen Sie im Fenster **Parallele Überwachung** alle gekennzeichneten Threads aus, klicken Sie mit der rechten Maustaste, und klicken Sie anschließend auf **Kennzeichnung aufheben**.

### <a name="to-display-only-flagged-threads"></a>So zeigen Sie nur gekennzeichnete Threads an

- Klicken Sie in einem der Multithreaddebugfenster auf die Schaltfläche **Nur gekennzeichnete Threads anzeigen**.

### <a name="to-flag-just-my-code"></a>So kennzeichnen Sie nur eigenen Code

1. Klicken Sie auf der Symbolleiste am oberen Rand des Fensters **Threads** auf das Kennzeichnungssymbol.

2. Klicken Sie in der Dropdownliste auf **Nur eigenen Code kennzeichnen**.

### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>So kennzeichnen Sie Threads, die ausgewählten Modulen zugeordnet sind

1. Klicken Sie auf der Symbolleiste des Fensters **Threads** auf das Kennzeichnungssymbol.

2. Klicken Sie in der Dropdownliste auf **Benutzerdefinierte Modulauswahl kennzeichnen**.

3. Wählen Sie im Dialogfeld **Module auswählen** die gewünschten Module aus.

4. (Optional) Geben Sie Im Feld **Suchen** eine Suchzeichenfolge für bestimmte Module ein.

5. Klicken Sie auf **OK**.

## <a name="see-also"></a>Siehe auch
- [Debuggen von Multithreadanwendungen](../debugger/debug-multithreaded-applications-in-visual-studio.md)
- [Debuggen von Multithreadanwendungen in Visual Studio](../debugger/get-started-debugging-multithreaded-apps.md)
- [Exemplarische Vorgehensweise: Debuggen einer Multithread-App mithilfe des Fensters „Threads“ (C#, Visual Basic, C++)](../debugger/how-to-use-the-threads-window.md)