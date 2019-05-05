# M300_LB3


## Kriterien 1:

Die ersten Kriterien sind zur Toolumgebung.
Dabei hat sich seit der LB2 bei mir nichts geändert und konnte deshalb so übernommen werden.

Siehe [LB2 - Kriterium 1](https://github.com/DeleonDuncan/M300_LB2/blob/master/README.md#kriterien-1
) 


## Kriterien 2



## Docker for Windows (Kriterien 3)

Für die LB3 habe ich mich für Docker for Windows entschieden.

Es wäre für mich zu unübersichtlich geworden mit Vagrant. 
Denn bekanntlich wird mir mehreren Schichten alles komplexer. Deshalb werde ich den Vagrant Teil überspringen,
und direkt Container von Docker ausführen.

Wir starten mit dem installieren von Docker.

Dazu muss man sich bei [Docker Hub](https://hub.docker.com/) eine Docker-ID erstellen, 
und danach Docker herunterladen. Wichtig dabei ist, dass man Hyper-V aktiviert hat oder währen der Installation aktiviert.
Dabei muss man beachten das VirtualBox mit der Aktivierung von Hyper-V nicht mehr funktioniert


Hat man Docker installiert, loggt man sich mit der Docker-ID ein und started Docker von CMD oder Powershell.

      docker run hello-world

Lädt ein Image herunter welches erklärt wie der Docker Client und Daemon miteinander agieren.

# Docker Befehle

Befehl         |  Beschreibung
-------------- |----------
docker run 	   |  Führt einen Befehl in einem neuen Container aus
docker start 	 |  Startet einen oder mehrere Container
docker stop 	 |  Stoppt einen oder mehrere Container
docker build 	 | Baut eine Image aus dem Dockerfile
docker pull 	 |  Lädt Image aus einer Repository herunter
docker push 	 |  Lädt Image in eine Repository hoch

# Einrichten von Kubernetes

Unter den Docker Settings gibt es die Option Kubernetes zu enablen.





