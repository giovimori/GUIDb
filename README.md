Oggi vedremo come creare un progetto per visualizzare i dati di una tabella del DB Chinook.db usando una app MAUI oppure WPF

1) Apriamo Visual Studio e clicchiamo su "Crea un nuovo progetto"

2) Si aprirà una pagina dove Visual Studio offre una vasta gamma di modelli per sviluppare, per creare una app MAUI selezioniamo dalle tendine in alto queste caratteristiche:

![image](https://github.com/giovimori/GUIDb/assets/116790906/4bd0c4d5-46a8-480f-98e2-910407ec71b7)

e clicchiamo sul primo risultato, poi su "Avanti".

3) Per creare una app WPF invece selezioniamo dalle tendine in alto queste caratteristiche:

![image](https://github.com/giovimori/GUIDb/assets/116790906/66989f44-c065-4f08-834f-971e7a184869)

infine premiamo su "Applicazione WPF", poi su "Avanti".

4) In entrambi i casi bisogna inserire il nome del progetto, che sarà cognome.nome.4h.GUIDb.

5) Selezioniamo NET 6.0 dalla tendina e clicchiamo su crea.

6) Dopo pochi secondi si aprirà il nuovo progetto, per prima cosa, sia in MAUI che in WPF, aggiungiamo la libreria sqlite-net-pcl nel seguente modo:

Fare clic con il pulsante destro del mouse sul progetto nella finestra Solution Explorer e selezionare "Manage NuGet Packages".
   - Nella finestra di dialogo NuGet Package Manager, cercare "sqlite-net-pcl" e selezionarlo.
   - Fare clic sul pulsante "Install" per installare la libreria nel progetto.




