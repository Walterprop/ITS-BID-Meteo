# Weather App 🌤️

Una semplice applicazione Spring Boot per visualizzare i dati meteorologici delle città italiane utilizzando l'API di OpenMeteo.

## Funzionalità

- ✅ Selezione da una lista di città italiane
- ✅ Recupero dati meteorologici delle ultime 2 settimane tramite API OpenMeteo
- ✅ Visualizzazione grafico a barre interattivo con Chart.js
- ✅ Responsive design con Bootstrap
- ✅ Containerizzazione con Docker

## Requisiti

- Java 21
- Maven 3.6+
- Docker (opzionale, per la containerizzazione)

## Come Avviare l'Applicazione
### 1. Esecuzione in PowerSchell o VS Code (Per aprirlo su PowerShell Tasto destro del mouse all'interno della cartella -- Apri Terminale)

```bash
# Costruisce l'immagine Docker
docker build -t weather-app .

# Avvia il container
docker run -p 8080:8080 weather-app

### 2. Esecuzione Locale (solo se si posside MVNW)

```bash
# Compila l'applicazione
mvnw clean package

# Avvia l'applicazione
mvnw spring-boot:run
```

L'applicazione sarà disponibile su: `http://localhost:8080`



## Utilizzo

1. Apri il browser e vai su `http://localhost:8080`
2. Seleziona una città dalla lista a tendina
3. Clicca su "Visualizza Grafico"
4. Visualizza il grafico a barre con le temperature delle ultime 2 settimane

## Città Disponibili

- Roma
- Milano  
- Napoli
- Torino
- Palermo
- Genova
- Bologna
- Firenze
- Bari
- Catania

## Tecnologie Utilizzate

- **Backend**: Spring Boot 3.3.0, Spring WebFlux
- **Database**: H2 (in-memory)
- **Frontend**: Thymeleaf, Bootstrap 5, Chart.js
- **API**: OpenMeteo (https://api.open-meteo.com)
- **Containerizzazione**: Docker

## Struttura del Progetto

```
src/
├── main/
│   ├── java/com/cavaliere/
│   │   ├── config/          # Configurazioni
│   │   ├── controller/      # Controller REST e Web
│   │   ├── model/          # Entità e DTO
│   │   ├── repository/     # Repository JPA
│   │   └── service/        # Servizi business
│   └── resources/
│       ├── static/css/     # File CSS
│       └── templates/      # Template Thymeleaf
└── test/                   # Test unitari
```

## API Endpoints

- `GET /` - Pagina principale con selezione città
- `POST /weather` - Visualizza dati meteorologici
- `GET /api/weather/{cityId}` - API REST per dati JSON

## Note

- L'applicazione utilizza un database H2 in-memory che si resetta ad ogni riavvio
- I dati meteorologici vengono recuperati in tempo reale dall'API OpenMeteo
- Il grafico mostra temperatura massima, minima e media per ogni giorno
