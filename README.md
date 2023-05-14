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
Per prima cosa scarichiamo il db tramite questo link: https://www.sqlitetutorial.net/wp-content/uploads/2018/03/chinook.zip , lo dezippiamo e:

  - Per MAUI: Copia il file `chinook.db` nella cartella "App/Assets" del progetto MAUI.
  - Per WPF: Copia il file `chinook.db` nella cartella "Assets" del progetto WPF.

### 8) Per accedere al database appena aggiunto è necessario il seguente codice: 
   
   ```csharp
using System;
using System.IO;

namespace YourNamespace
{
    public class DatabaseAccess
    {
        private string dbFileName = "chinook.db";
        private string dbFilePath;

        public void AccessDatabase()
        {
            // Percorso del file nella cartella "raw"
            string rawFolderPath = Path.Combine(AppDomain.CurrentDomain.BaseDirectory, "raw");
            string rawFilePath = Path.Combine(rawFolderPath, dbFileName);

            // Percorso della directory "Local Data"
            string localDataFolderPath = Path.Combine(Environment.GetFolderPath(Environment.SpecialFolder.LocalApplicationData), "LocalData");

            // Percorso completo del file nella directory "Local Data"
            dbFilePath = Path.Combine(localDataFolderPath, dbFileName);

            // Copia il file dalla cartella "raw" alla directory "Local Data" se non esiste già
            if (!File.Exists(dbFilePath))
            {
                Directory.CreateDirectory(localDataFolderPath);
                File.Copy(rawFilePath, dbFilePath);
            }

            // Ora puoi utilizzare il file "chinook.db" nella directory "Local Data" per le operazioni di database
            // Esempio:
            using (var connection = new SQLite.SQLiteConnection(dbFilePath))
            {
                // Esegui query e operazioni sul database qui
            }
        }
    }
}

   




