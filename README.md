# Fortezza Azure Data Fundamentals Training

Dit GitHub-project bevat alle benodigde informatie en bronnen voor de Fortezza Azure Data Fundamentals Training. In deze training leer je hoe je Azure-services kunt gebruiken om een end-to-end gegevensoplossing te bouwen. De belangrijkste opdrachten omvatten het aanmaken van Azure-resources, het configureren van Azure Data Factory, het laden van gegevens en het integreren van Power BI met je Azure SQL Databases.

## Inhoudsopgave

1. [Inleiding](#inleiding)
2. [Opdrachten](#opdrachten)
    - [Opdracht 1: Aanmaken van Azure Resources](#opdracht-1-aanmaken-van-azure-resources)
    - [Opdracht 2: Aanmaken van Azure Data Factory](#opdracht-2-aanmaken-van-azure-data-factory)
    - [Opdracht 3: Configureren van Linked Services en Toegang voor Azure Data Factory](#opdracht-3-configureren-van-linked-services-en-toegang-voor-azure-data-factory)
    - [Opdracht 4: Configureren van Datasets](#opdracht-4-configureren-van-datasets)
    - [Opdracht 5: Configureren van Pipelines](#opdracht-5-configureren-van-pipelines)
    - [Opdracht 6: Laden van gegevens naar Azure SQL Database](#opdracht-6-laden-van-gegevens-naar-azure-sql-database)
    - [Opdracht 7: Verbinden van Power BI](#opdracht-7-verbinden-van-power-bi)
3. [Bonusopdracht](#bonusopdracht)
4. [Bijdragen](#bijdragen)
5. [Licentie](#licentie)

## Inleiding

Deze training is bedoeld om je vertrouwd te maken met Azure-dataoplossingen en biedt een praktische hands-on ervaring. We zullen elke opdracht in detail bespreken, rekening houdend met het feit dat je misschien nog nooit eerder met Azure-services hebt gewerkt.

## Opdrachten

### Opdracht 1: Aanmaken van Azure Resources

#### Stap 1: Inloggen op de Azure Portal
Ga naar [https://portal.azure.com](https://portal.azure.com) en log in met je Azure-account. Als je geen Azure-account hebt, kun je er een aanmaken.

#### Stap 2: Resourcegroep maken
Een resourcegroep helpt je om al je Azure-resources te organiseren. Klik op "Resourcegroepen" in het Azure Portal-menu, en klik vervolgens op "Resourcegroep maken". Volg de instructies om een nieuwe resourcegroep aan te maken.

#### Stap 3: Azure SQL Databases aanmaken
- Klik op "SQL-databases" in het Azure Portal-menu en klik op "Nieuwe maken".
- Volg de instructies om twee Azure SQL Databases aan te maken. De ene database moet gevuld worden met Sample Data, terwijl de andere de doeldatabase wordt.
- Voeg bij het aanmaken van de databases je huidige IP-adres toe aan de firewallregels om toegang te krijgen tot de databases.

### Opdracht 2: Aanmaken van Azure Data Factory

#### Stap 1: Azure Data Factory maken
- Klik op "Data + analyse" in het Azure Portal-menu en selecteer "Azure Data Factory".
- Klik op "Maken" en volg de instructies om een Azure Data Factory te maken. Kies de resourcegroep die je eerder hebt gemaakt.

### Opdracht 3: Configureren van Linked Services en Toegang voor Azure Data Factory

#### Stap 1: Azure Data Factory
- Ga naar de eerder gemaakte Azure Data Factory.
- In het linkerdeelvenster, klik op "Author & Monitor" om de Azure Data Factory-editor te openen.

#### Stap 2: Linked Services
- Klik op "Author" en ga naar "Connections".
- Klik op "New" om Linked Services voor beide Azure SQL Databases te configureren. Je moet de verbindingsreeksen correct instellen om toegang te krijgen tot de databases.

#### Stap 3: Toegang verlenen aan Azure Data Factory
- Ga naar de Azure Portal en zoek naar de Azure SQL Databases die je in opdracht 1 hebt aangemaakt.
- Klik op elke database en ga naar "Firewall en virtueel netwerk".
- Voeg het IP-adres van je Azure Data Factory toe aan de lijst met toegestane IP-adress

en om verbinding te maken met de databases.

### Opdracht 4: Configureren van Datasets

#### Stap 1: Azure Data Factory
- Binnen de Azure Data Factory-editor, klik je op "Author" en ga je naar "Author".
- Klik op "New Dataset" om Datasets te configureren die verwijzen naar de gegevensbronnen en bestemmingen die je wilt gebruiken.

### Opdracht 5: Configureren van Pipelines

#### Stap 1: Azure Data Factory
- Ga naar "Author" in de Azure Data Factory-editor.
- Klik op "New Pipeline" om Pipelines te maken en definieer gegevenstransformaties en -verplaatsingen tussen je Datasets.

### Opdracht 6: Laden van gegevens naar Azure SQL Database

#### Stap 1: Azure Data Factory
- Binnen je Pipelines, configureer activiteiten om gegevens van je bronnen naar de doeldatabase te kopiëren. Je kunt gegevensverplaatsingstaken gebruiken om de gegevens te laden.

### Opdracht 7: Verbinden van Power BI

#### Stap 1: Power BI Desktop
- Download en installeer [Power BI Desktop](https://powerbi.microsoft.com/nl-nl/desktop/).
- Open Power BI Desktop.

#### Stap 2: Gegevensverbinding
- Klik op "Gegevens ophalen" om een nieuwe gegevensverbinding te maken naar de doeldatabase van je Azure SQL Database. Gebruik de juiste verbindingsreeks die je in opdracht 3 hebt geconfigureerd.

#### Stap 3: Gegevensvisualisatie
- Bouw rapporten en dashboards op basis van de gegevens in je doeldatabase met behulp van Power BI Desktop.

## Bonusopdracht

Voor de bonusopdracht om CSV-bestanden in deze repository te laden in je Azure SQL Database, kun je de volgende stappen volgen:

#### Stap 1: Azure Data Factory
- Breid je Azure Data Factory-pijplijnen uit om CSV-bestanden van deze repository te lezen en te transformeren. Je kunt bijvoorbeeld een Blob Storage-linked service gebruiken om de bestanden op te slaan en dan een kopieeractiviteit gebruiken om de gegevens naar je doeldatabase te verplaatsen.

Dit zijn de bijgewerkte stappen voor de opdrachten. Zorg ervoor dat je alle stappen zorgvuldig volgt om de training succesvol af te ronden.
