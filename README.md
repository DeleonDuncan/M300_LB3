# M300_LB3


## Kriterien 1:

Die ersten Kriterien sind zur Toolumgebung.
Dabei hat sich seit der LB2 bei mir nichts geändert und konnte deshalb so übernommen werden.

Siehe [LB2 - Kriterium 1](https://github.com/DeleonDuncan/M300_LB2/blob/master/README.md#kriterien-1
) 


## Kriterien 2

### 1. GitHub Account erstellt

![GitHub DeleonDuncan](https://github.com/deleonduncan)


### 2. Git-Client verwendet

Ich habe die Git-Bash benutzt für die Befehle in den Kriterien 3, und für die Navigation im Explorer.


### 3. Dokumentation als Markdown
 
Ich habe keinen Makrdown editor benutzt, sondern sondern direkt die README.md datei editiert. Diese Dokumentation sollte als Beweis ausreichen, dass ich sie in Markdown geschrieben habe.


### 4. Persönlicher Wissenstand

Themen            | Wissen
----------------- | -------------
VirtualBox        | Ich kannte VirtualBox als hypervisor. Ich wusste das es Open-Source ist. Trotzdem habe ich vorher immer VMWare             Workstation benutzt
VisualStudio-Code | Ich kannte und bentutze VSCode bereits als Editor. Vor allem wegen den Extensions finde ich ihn extrem mächtig. Man kann am einen Tag Powershell und am anderen mit Python ohne probleme, und mit Syntax Highlighting arbeiten.
Git-Client        | Git Client kannte ich vor diesem Modul, und ich hatte es auch schon mal installiert. Jedoch habe ich es nie aktiv genutzt.
SSH Keys          | Mit SSh-Keys habe ich schon im Geschäft zu tun gehabt. Sie sind etwas komplett vertrautes.
Minikube	  | Ich habe anstatt Kubernetes Minikube verwendet. Minikube primär für die Entwicklung verwendet. Ich habe es benutzt, weil es lokal einfacher ist mit Minikube als Kubernetes.

### 5. Wichtige Lernschritte

Minikube/Kubernetes:
        
		Zuvor haben wir uns nur mit Vagrant und Docker beschäftigt. In der LB3 bin ich dann auf Kubernetes gestossen.
            Mit Kubernetes hat sich mein Verständnis im Thema automatisierung sehr verbessert. Ich habe verstanden, dass es darauf abzielt eine Plattform                     zu sein, die automatisiert Anwendungen in Container verpackt und diese auf virtuellen Hosts, sogenannte Pods, auszuführen. Spannend finde ich die           implementation von Docker. So hat man anscheinen grenzenlose Mäglichkeiten Software auszuführen und managen.



## Minkube

Minikube ist ein Tool, mit dem Kubernetes lokal einfach ausgeführt werden kann. Minikube führt einen Kubernetes-Cluster mit Einzelknoten in einer VM auf Ihrem Laptop aus, damit Benutzer Kubernetes ausprobieren oder täglich damit entwickeln können.

[Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/) habe ich nach dem Download mit [Chocolatey](https://chocolatey.org/) installiert. Chocolatey ist ein Software Verwaltungstool für Windows. Es ähnelt Linux Software Managern

Mit dem folgenden Befehl kann man Chocolatey per CMD oder Powershell mit Adminrechten installieren.

      @"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None     -ExecutionPolicy Bypass -Command "iex ((New-Object    System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"

Nachdem Chocolatey installiert ist, installieren wir minikube und kubernetes-cli

      choco install minikube kubernetes-cli

Nach der installation starte ich minikube und führe das Dashboard aus.

      minikube start
      minikube dashboard
      
Nun sollte man zum Dashboard kommen

<img src="https://github.com/DeleonDuncan/M300_LB3/blob/master/images/dashboard%20m300.PNG" alt="Dashboard minikube" title="" />

## Web Service erstellen.

Nachdem wir zum Dashboard gelangen, erstellen wir den ersten Webservice.
Dazu müssen wir ein Minikube addon enablen.

      minikube addons enable ingress

Als nächstes prüfen wir ob das Addon wirklich aktiviert wurde mit:

      minikube addons list

Danach führen wir den Webservice aus mit:

      kubectl run web --image=gcr.io/google-samples/hello-app:1.0 --port=8080
      deployment.apps "web" created

Nachdem wir es ausgeführt haben, müssen wir noch den Port 8080 erreichbar machen.

      kubectl expose deployment web --target-port=8080 --type=NodePort
      
Danach müssen wir überprüfen, ob der Service läuft. Anschliessend geben wir die URL aus auf die wir Verbinden können.

      kubectl get service web
      minikube service web --url
      
In meinem Fall ist der Webserver unter der Adresse http://192.168.99.100:31409 erreichbar.

<img src="https://github.com/DeleonDuncan/M300_LB3/blob/master/images/webt.PNG">
      






     



