---
title: "Plattformübergreifendes Remotedebuggen mit Python in Visual Studio | Microsoft-Dokumentation"
ms.custom: 
ms.date: 7/12/2017
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-python
ms.devlang: python
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: aa667357-763f-4ce6-8e47-48f9337658a8
caps.latest.revision: 1
author: kraigb
ms.author: kraigb
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 1e017806ca7bf3d23410ba3a2f999dca0b78f240
ms.openlocfilehash: 2711238ccc6d90b34df748c6b59e4130c74de69b
ms.contentlocale: de-de
ms.lasthandoff: 09/26/2017

---

# <a name="remotely-debugging-python-code-on-linux"></a>Remotedebuggen von Python-Code in Linux

Visual Studio kann Python-Anwendungen sowohl lokal als auch remote (siehe [Remotedebuggen](../debugger/remote-debugging.md)) auf einem Windows-Computer starten und debuggen. Mithilfe der [ptvsd-Bibliothek](https://pypi.python.org/pypi/ptvsd) kann PTVS das Remotedebuggen auch auf einem anderen Betriebssystem, einem anderen Gerät oder in einer anderen Python-Implementierung als CPython ausführen.

Beim Verwenden von ptvsd hostet der Python-Code, für den das Debuggen ausgeführt werden soll, den Debugserver, an den Visual Studio angefügt werden kann. Für dieses Hosting ist eine kleine Änderung an Ihrem Code erforderlich, um den Server zu importieren und zu aktivieren. Auf dem Remotecomputer müssen möglicherweise Netzwerk- oder Firewallkonfigurationen geändert werden, sodass TCP-Verbindungen zulässig sind.

Eine Einführung zum Remotedebuggen sehen Sie in diesem Video: [Deep Dive: Cross-Platform Remote Debugging](https://youtu.be/y1Qq7BrV6Cc) (youtube.com, 6 Minuten, 22 Sekunden).

> [!VIDEO https://www.youtube.com/embed/y1Qq7BrV6Cc]

## <a name="setting-up-a-linux-computer"></a>Einrichten eines Linux-Computers

Die folgenden Elemente sind für diese exemplarische Vorgehensweise nötig:

- Einen Remotecomputer, auf dem Python unter einem Betriebssystem wie Mac OSX oder Linux ausgeführt wird.
- Einen geöffneten Port 5678 (eingehend) auf der Firewall dieses Computers. Dies ist die Standardeinstellung für das Remotedebuggen.

Sie können problemlos [virtuelle Linux-Computer in Azure](https://docs.microsoft.com/azure/virtual-machines/linux/creation-choices) erstellen und von Windows aus [darauf über Remotedesktop zugreifen](https://docs.microsoft.com/azure/virtual-machines/linux/use-remote-desktop). Es ist praktisch, für den virtuellen Computer Ubuntu zu verwenden, da Python standardmäßig installiert ist; andernfalls finden Sie eine Liste mit weiteren Python-Downloadspeicherorten unter [Installieren Sie einen Python-Interpreter Ihrer Wahl](python-environments.md#selecting-and-installing-python-interpreters).

Weitere Informationen zum Erstellen einer Firewallregel für einen virtuellen Azure-Computer finden Sie unter [Öffnen von Ports für einen virtuellen Computer in Azure mithilfe des Azure-Portals](https://docs.microsoft.com/azure/virtual-machines/windows/nsg-quickstart-portal).

## <a name="preparing-the-script-for-debugging"></a>Vorbereiten des Skripts für das Debuggen

1. Erstellen Sie auf dem Remotecomputer eine Python-Datei mit dem Namen `guessing-game.py` mit dem folgenden Code:

  ```python
  import random

  guesses_made = 0
  name = input('Hello! What is your name?\n')
  number = random.randint(1, 20)
  print('Well, {0}, I am thinking of a number between 1 and 20.'.format(name))

  while guesses_made < 6:
      guess = int(input('Take a guess: '))
      guesses_made += 1
      if guess < number:
          print('Your guess is too low.')
      if guess > number:
          print('Your guess is too high.')
      if guess == number:
          break
  if guess == number:
      print('Good job, {0}! You guessed my number in {1} guesses!'.format(name, guesses_made))
  else:
      print('Nope. The number I was thinking of was {0}'.format(number))
  ```
 
1. Installieren Sie mithilfe von `pip3 install ptvsd` das `ptvsd`-Paket in Ihrer Umgebung. (Hinweis: Es ist eine gute Idee, die Version von ptvsd zu erfassen, die installiert wird, falls Sie sie für die Problembehandlung benötigen; die [ptvsd-Liste](https://pypi.python.org/pypi/ptvsd) zeigt auch die verfügbaren Versionen.)

1. Aktivieren Sie das Remotedebuggen, indem Sie den untenstehenden Code am frühestmöglichen Punkt in `guessing-game.py` einfügen, also vor jedem anderen Code. (Dies ist zwar nicht zwingend erforderlich, aber es ist unmöglich, Hintergrundthreads zu debuggen, die vor dem Aufruf der Funktion `enable_attach` erzeugt werden.)

   ```python
   import ptvsd
   ptvsd.enable_attach('my_secret')
   ```

   Das erste Argument, das an `enable_attach` (als „geheimer Schlüssel“ bezeichnet) übergeben wird, schränkt den Zugriff auf das ausgeführte Skript ein, und Sie geben diesen geheimen Schlüssel ein, wenn Sie den Remotedebugger anfügen. (Obwohl dies nicht empfohlen wird, können Sie allen Benutzern das Herstellen einer Verbindung erlauben, und `enable_attach(secret=None)` verwenden.)

1. Speichern Sie die Datei, und führen Sie `python3 guessing-game.py` aus. Der Aufruf von `enable_attach` wird im Hintergrund ausgeführt und wartet auf eingehende Verbindungen, da Sie andernfalls mit dem Programm interagieren. Bei Bedarf kann die Funktion `wait_for_attach` nach `enable_attach` aufgerufen werden, um das Programm zu blockieren, bis der Debugger angefügt wurde.

> [!Tip]
> Zusätzlich zu `enable_attach` und `wait_for_attach` bietet ptvsd auch die Hilfsfunktion `break_into_debugger`, die als programmgesteuerter Haltepunkt fungiert, wenn der Debugger angefügt wird. Es gibt auch eine `is_attached`-Funktion, die `True` zurückgibt, wenn der Debugger angefügt wird (das Ergebnis muss vor dem Aufrufen anderer `ptvsd`-Funktionen nicht geprüft werden).

## <a name="attaching-remotely-from-python-tools"></a>Remoteanfügen über Python Tools

In diesen Schritten legen wir einen einfachen Haltepunkt fest, um den Remoteprozess anzuhalten.

1. Erstellen Sie eine Kopie der Remotedatei auf dem lokalen Computer, und öffnen Sie diese in Visual Studio. Es spielt keine Rolle, wo die Datei gespeichert wird, der Name muss aber dem Namen des Skripts auf dem Remotecomputer entsprechen.

1. (Optional) Um auf dem lokalen Computer über IntelliSense für ptvsd zu verfügen, können Sie das ptvsd-Paket in Ihrer Python-Umgebung installieren.

1. Klicken Sie auf **Debuggen > An den Prozess anhängen**.

1. Legen Sie im nun angezeigten Dialogfeld **An den Prozess anhängen** den **Verbindungstyp** auf **Python remote (ptvsd)** fest. (In älteren Versionen von Visual Studio werden diese Befehle als **Transport** und **Python-Remotedebuggen** bezeichnet.)

1. Geben Sie in das Feld **Verbindungsziel** (in älteren Versionen als **Qualifizierer** bezeichnet) `tcp://<secret>@<ip_address>:5678` ein, wobei `<secret>` für die übergebene Zeichenfolge `enable_attach` im Python-Code, `<ip_address>` für den Remotecomputer (entweder eine explizite Adresse oder ein Name wie myvm.cloudapp.net) und `:5678` für die Portnummer beim Remotedebuggen steht.

    > [!Warning]
    > Wenn Sie eine Verbindung über das öffentliche Internet herstellen, sollten Sie stattdessen `tcps` verwenden und die nachstehende Anweisung unten [Sichern der Debuggerverbindung mit SSL](#securing-the-debugger-connection-with-ssl) befolgen.

1. Drücken Sie die EINGABETASTE, um die Liste der auf diesem Computer verfügbaren ptvsd-Prozesse aufzufüllen:

    ![Eingeben des Verbindungsziels und Auflisten von Prozessen](media/remote-debugging-qualifier.png)

    Wenn Sie nach dem Auffüllen dieser Liste ein anderes Programm auf dem Remotecomputer starten, klicken Sie auf die Schaltfläche **Aktualisieren**.

1. Wählen Sie den Prozess zum Debuggen und dann **Anfügen** aus, oder doppelklicken Sie auf den Prozess.

1. Visual Studio wechselt dann in den Debugmodus, während das Skript weiterhin auf dem Remotecomputer ausgeführt wird, und bietet alle üblichen Funktionen zum [Debuggen](debugging.md). Setzen Sie zum Beispiel einen Haltepunkt in die `if guess < number:`-Zeile, wechseln Sie dann zum Remotecomputer, und geben Sie einen anderen Schätzwert ein. Danach stoppt Visual Studio auf dem lokalen Computer an diesem Haltepunkt, zeigt lokale Variablen an usw.:

    ![Haltepunkt wird erreicht](media/remote-debugging-breakpoint-hit.png)

1. Wenn Sie das Debuggen beenden, wird Visual Studio vom Programm getrennt, das weiterhin auf dem Remotecomputer ausgeführt wird. ptvsd ist ebenfalls weiterhin für das Anfügen von Debuggern bereit, sodass Sie den Prozess jederzeit wiederaufnehmen können.

### <a name="connection-troubleshooting"></a>Problembehandlung bei der Verbindung

1. Stellen Sie sicher, dass Sie **Python remote (ptvsd)** als **Verbindungstyp** ausgewählt haben (in älteren Versionen **Python-Remotedebuggen** bei **Transport**).
1. Überprüfen Sie, ob der geheime Schlüssel im **Verbindungsziel** (oder **Qualifizierer**) mit dem geheimen Schlüssel im Remotecode genau übereinstimmt.
1. Überprüfen Sie, ob die IP-Adresse im **Verbindungsziel** (oder **Qualifizierer**) der des Remotecomputers entspricht.
1. Stellen Sie sicher, dass Sie den Port für das Remotedebuggen auf dem Remotecomputer geöffnet haben, und das Suffix des Ports wie z.B. `:5678` im Verbindungsziel enthalten ist.
    - Wenn Sie einen anderen Port verwenden möchten, können Sie ihn im `enable_attach`-Aufruf mithilfe des `address`-Arguments angeben wie z.B. in `ptvsd.enable_attach(secret = 'my_secret', address = ('0.0.0.0', 8080))`. Öffnen Sie in diesem Fall diesen Port in der Firewall.
1. Überprüfen Sie, ob die auf dem Remotecomputer installierte ptvsd-Version wie von `pip3 list` zurückgegeben mit der der Version der Python-Tools aus der untenstehenden Tabelle übereinstimmt, die Sie in Visual verwenden. Aktualisieren Sie bei Bedarf ptvsd auf dem Remotecomputer.

    | Visual Studio-Version | Python-Tools/ptvsd-Version |
    | --- | --- |
    | 2017 15.3 | 3.2.0 |
    | 2017 15.2 | 3.1.0 |
    | 2017 15.0, 15.1 | 3.0.0 |
    | 2015 | 2.2.6 |
    | 2013 | 2.2.2 |
    | 2012, 2010 | 2.1 |


## <a name="securing-the-debugger-connection-with-ssl"></a>Sichern der Debuggerverbindung mit SSL

In der Standardeinstellung ist die Verbindung mit dem ptvsd-Remotedebugserver nur durch den geheimen Schlüssel geschützt, und alle Daten werden als Nur-Text übergeben. Für eine sicherere Verbindung unterstützt ptvsd SSL, das folgendermaßen eingerichtet wird:

1. Generieren Sie auf dem Remotecomputer ein eigenständiges selbstsigniertes Zertifikat und Schlüsseldateien mit OpenSSL:
    
    ```bash
    openssl req -new -x509 -days 365 -nodes -out cert.cer -keyout cert.key
    ```

    Verwenden Sie den Hostnamen oder die IP-Adresse (je nachdem, was Sie beim Verbinden verwenden) als **gemeinsamen Namen**, wenn Sie von OpenSSL dazu aufgefordert werden.

    (Weitere Informationen finden Sie unter [Self-signed certificates (Selbstsignierte Zertifikate)](http://docs.python.org/3/library/ssl.html#self-signed-certificates) im Python-Modul `ssl`. Beachten Sie, dass der Befehl in dieser Dokumentation nur eine einzige kombinierte Datei generiert.)

1. Ändern Sie im Code den Aufruf von `enable_attach` so, dass er `certfile`- und `keyfile`-Argumente mit den Dateinamen als Werte enthält (diese Argumente haben dieselbe Bedeutung wie bei der standardmäßigen Python-Funktion `ssl.wrap_socket`):

    ```python
    ptvsd.enable_attach(secret='my_secret', certfile='cert.cer', keyfile='cert.key')
    ```
    
    Sie können die gleiche Änderung auch in der Codedatei auf dem lokalen Computer vornehmen, aber da dieser Code nicht tatsächlich ausgeführt wird, ist dies nicht zwingend erforderlich.    

1. Starten Sie das Python-Programm auf dem Remotecomputer neu, damit es zum Debuggen bereit ist.

1. Sichern Sie den Kanal, indem Sie das Zertifikat der vertrauenswürdigen Stammzertifizierungsstelle auf dem Windows-Computer mit Visual Studio hinzufügen:

    1. Kopieren Sie die Zertifikatdatei vom Remotecomputer auf den lokalen Computer.
    1. Öffnen Sie die Systemsteuerung, und navigieren Sie zu **Verwaltung > Computerzertifikate verwalten**.
    1. Erweitern Sie im daraufhin angezeigten Fenster auf der linken Seite **Vertrauenswürdige Stammzertifizierungsstellen**, klicken Sie mit der rechten Maustaste auf **Zertifikate**, und wählen Sie **Alle Aufgaben > Importieren** aus.
    1. Wählen Sie die `.cer`-Datei aus, die vom Remotecomputer kopiert wurde, und klicken Sie sich dann durch den Dialog, um den Import abzuschließen.

1. Wiederholen Sie den Anfügungsprozess wie zuvor beschrieben in Visual Studio, und verwenden Sie nun `tcps://` als Protokoll für das **Verbindungsziel** (oder **Qualifizierer**).

    ![Auswählen des Transports für das Remotedebuggen über SSL](media/remote-debugging-qualifier-ssl.png)

### <a name="warnings"></a>Warnungen

Visual Studio meldet Ihnen beim Herstellen einer Verbindung über SSL mögliche Zertifikatsprobleme, wie unten beschrieben. Sie können die Warnungen ignorieren und fortfahren, aber obwohl der Kanal dann noch immer gegen Lauschangriffe verschlüsselt ist, kann er für Man-in-the-Middle-Angriffe geöffnet sein.

1. Wenn die untenstehende Warnung „Das Remotezertifikat ist nicht vertrauenswürdig“ angezeigt wird, bedeutet dies, dass Sie das Zertifikat nicht ordnungsgemäß der vertrauenswürdigen Stammzertifizierungsstelle hinzugefügt haben. Überprüfen Sie diese Schritte, und versuchen Sie es erneut.

    ![SSL-Zertifikatwarnung Vertrauenswürdigkeit](media/remote-debugging-ssl-warning.png)

1. Wenn die untenstehende Warnung „Der Name des Remotezertifikats stimmt nicht mit dem Hostnamen überein“ angezeigt wird, bedeutet dies, dass Sie bei der Erstellung des Zertifikats als **gemeinsamen Namen** nicht den richtigen Hostnamen oder nicht die richtige IP-Adresse eingegeben haben.

    ![SSL-Zertifikatwarnung Hostname](media/remote-debugging-ssl-warning2.png)

> [!Warning]
> Derzeit hängt sich Visual Studio 2017 auf, wenn Sie diese Warnungen ignorieren. Achten Sie darauf, dass Sie alle Probleme beheben, bevor Sie versuchen, eine Verbindung herzustellen.
