# Oggi vedremo come creare un progetto per visualizzare i dati di una tabella del DB Chinook.db usando una app MAUI oppure WPF

### 1) Apriamo Visual Studio e clicchiamo su "Crea un nuovo progetto"

### 2) Si aprirà una pagina dove Visual Studio offre una vasta gamma di modelli per sviluppare, per creare una app MAUI selezioniamo dalle tendine in alto queste caratteristiche:

![image](https://github.com/giovimori/GUIDb/assets/116790906/4bd0c4d5-46a8-480f-98e2-910407ec71b7)

e clicchiamo sul primo risultato, poi su "Avanti".

### 3) Per creare una app WPF invece selezioniamo dalle tendine in alto queste caratteristiche:

![image](https://github.com/giovimori/GUIDb/assets/116790906/66989f44-c065-4f08-834f-971e7a184869)

infine premiamo su "Applicazione WPF", poi su "Avanti".

### 4) In entrambi i casi bisogna inserire il nome del progetto, che sarà cognome.nome.4h.GUIDb.

### 5) Selezioniamo NET 6.0 dalla tendina e clicchiamo su crea.

### 6) Dopo pochi secondi si aprirà il nuovo progetto, per prima cosa, sia in MAUI che in WPF, aggiungiamo la libreria sqlite-net-pcl nel seguente modo:

Fare clic con il pulsante destro del mouse sul progetto nella finestra Solution Explorer e selezionare "Manage NuGet Packages".
   - Nella finestra di dialogo NuGet Package Manager, cercare "sqlite-net-pcl" e selezionarlo.
   
   ![image](https://github.com/giovimori/GUIDb/assets/116790906/22ef9971-a951-499e-ade1-9c28e0f82cb9)

   - Fare clic sul pulsante "Install" per installare la libreria nel progetto.

### 7) Per aggiungere il database chinook.db al progetto procediamo nel seguente modo:
Per prima cosa scarichiamo il db tramite questo link: https://www.sqlitetutorial.net/wp-content/uploads/2018/03/chinook.zip , lo dezippiamo e per accedervi saranno necessari questi passaggi:
   
Nel tuo progetto WPF, crea una nuova cartella chiamata "Data" o "Database" (o qualsiasi nome tu preferisca) all'interno dell'esploratore della soluzione.

Fai clic con il pulsante destro del mouse sulla cartella "Data" o "Database" appena creata e seleziona "Aggiungi" > "Elemento esistente" dal menu contestuale.

Nella finestra di dialogo di selezione file, naviga e seleziona il file "chinook.db" e fai clic su "Aggiungi".

Nel file di progetto (.csproj) del tuo progetto WPF, aggiungi manualmente la seguente riga di codice all'interno dell'elemento ItemGroup:
```
<Content Include="Data\chinook.db">
  <CopyToOutputDirectory>PreserveNewest</CopyToOutputDirectory>
</Content>
   ```
Questo codice indica a Visual Studio di copiare il file "chinook.db" nella directory di output del tuo progetto durante la compilazione.

Una volta completati questi passaggi, il file "chinook.db" sarà incluso nel tuo progetto WPF e verrà copiato nella directory di output durante la compilazione

## Tabella artists di chinook.db:

![image](https://github.com/giovimori/GUIDb/assets/116790906/61e8e57e-d729-47b7-9697-eacf7f953770)

   




