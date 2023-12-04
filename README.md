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

## Inleiding

Deze training is bedoeld om je vertrouwd te maken met Azure-dataoplossingen en biedt een praktische hands-on ervaring. We zullen elke opdracht in detail bespreken, rekening houdend met het feit dat je misschien nog nooit eerder met Azure-services hebt gewerkt.

## Opdrachten

### Opdracht 1: Aanmaken van Azure Resources

**Opdracht:** Aanmaken van twee Azure SQL Databases, een gevuld met Sample Data en de andere als de doeldatabase.

**Uit te voeren stappen:**

1. **Inloggen op de Azure Portal**
   - Ga naar [https://portal.azure.com](https://portal.azure.com) en log in met je Azure-account. Als je geen Azure-account hebt, kun je er een aanmaken.

2. **Resourcegroep maken**
   - Klik op "Resourcegroepen" in het Azure Portal-menu, en klik vervolgens op "Resourcegroep maken".
   - Volg de instructies om een nieuwe resourcegroep aan te maken.

3. **Azure SQL Databases aanmaken**
   - Klik op "SQL-databases" in het Azure Portal-menu en klik op "Nieuwe maken".
   - Volg de instructies om twee Azure SQL Databases aan te maken. Geef ze duidelijke namen en kies bij één database de optie om deze te vullen met Sample Data (bijvoorbeeld AdventureWorksLT).

4. **Toevoegen van je huidige IP-adres aan de firewallregels**
   - Ga naar de instellingen van elke database en zoek de optie "Firewall en virtueel netwerk".
   - Voeg je huidige IP-adres toe aan de lijst met toegestane IP-adressen om verbinding te maken met de databases.

### Opdracht 2: Aanmaken van Azure Data Factory

**Opdracht:** Aanmaken van een Azure Data Factory.

**Uit te voeren stappen:**

1. **Azure Data Factory maken**
   - Klik op "Data + analyse" in het Azure Portal-menu en selecteer "Azure Data Factory".
   - Klik op "Maken" en volg de instructies om een Azure Data Factory te maken. Kies de resourcegroep die je eerder hebt gemaakt.

### Opdracht 3: Configureren van Linked Services en Toegang voor Azure Data Factory

**Opdracht:** Configureren van Linked Services voor beide Azure SQL Databases en het verlenen van toegang voor Azure Data Factory.

**Uit te voeren stappen:**

1. **Azure Data Factory**
   - Ga naar de eerder gemaakte Azure Data Factory.
   - In het linkerdeelvenster, klik op "Author & Monitor" om de Azure Data Factory-editor te openen.

2. **Linked Services**
   - Klik op "Author" en ga naar "Connections".
   - Klik op "New" om Linked Services voor beide Azure SQL Databases te configureren. Zorg ervoor dat je de verbindingsreeksen correct instelt om toegang te krijgen tot de databases.

3. **Toegang verlenen aan Azure Data Factory**
   - Ga naar de Azure Portal en zoek naar de Azure SQL Databases die je in opdracht 

1 hebt aangemaakt.
   - Klik op elke database en ga naar "Firewall en virtueel netwerk".
   - Voeg het IP-adres van je Azure Data Factory toe aan de lijst met toegestane IP-adressen om verbinding te maken met de databases.

4. **Voer de volgende SQL-code uit om Azure Data Factory toegang te geven tot de databases:**

   ```sql
   CREATE USER [azure-data-factory-name] FROM EXTERNAL PROVIDER
   EXEC sp.addrolemember 'db_owner','azure-data-factory-name'
   ```

   Hiermee voeg je de Managed Identity van Azure Data Factory toe als gebruiker van de SQL Databases en ken je de `db_owner`-rol toe. Dit zorgt ervoor dat Azure Data Factory de nodige machtigingen heeft om gegevens te schrijven naar en te lezen uit de databases.

### Opdracht 4: Configureren van Datasets

**Opdracht:** Configureren van Datasets die verwijzen naar de gegevensbronnen en bestemmingen die je wilt gebruiken.

**Uit te voeren stappen:**

1. **Azure Data Factory**
   - Binnen de Azure Data Factory-editor, klik je op "Author" en ga je naar "Author".
   - Klik op "New Dataset" om Datasets te configureren die verwijzen naar de gegevensbronnen en bestemmingen die je wilt gebruiken.

### Opdracht 5: Configureren van Pipelines

**Opdracht:** Aanmaken van Pipelines en definieer gegevenstransformaties en -verplaatsingen tussen je Datasets.

**Uit te voeren stappen:**

1. **Azure Data Factory**
   - Ga naar "Author" in de Azure Data Factory-editor.
   - Klik op "New Pipeline" om Pipelines te maken en definieer gegevenstransformaties en -verplaatsingen tussen je Datasets.

### Opdracht 6: Laden van gegevens naar Azure SQL Database

**Opdracht:** Laden van gegevens vanuit je bronnen naar de doeldatabase.

**Uit te voeren stappen:**

1. **Azure Data Factory**
   - Binnen je Pipelines, configureer activiteiten om gegevens van je bronnen naar de doeldatabase te kopiëren. Gebruik gegevensverplaatsingstaken zoals de "Copy Data"-taak om de gegevens te laden.

### Opdracht 7: Verbinden van Power BI

**Opdracht:** Verbinden van Power BI met de doeldatabase van je Azure SQL Databases.

**Uit te voeren stappen:**

1. **Power BI Desktop**
   - Download en installeer [Power BI Desktop](https://powerbi.microsoft.com/nl-nl/desktop/).
   - Open Power BI Desktop.

2. **Gegevensverbinding**
   - Klik op "Gegevens ophalen" om een nieuwe gegevensverbinding te maken naar de doeldatabase van je Azure SQL Databases. Gebruik de juiste verbindingsreeks die je in opdracht 3 hebt geconfigureerd.

3. **Gegevensvisualisatie**
   - Bouw rapporten en dashboards op basis van de gegevens in je doeldatabase met behulp van Power BI Desktop.

## Bonusopdracht

**Opdracht:** Laden van CSV-bestanden van deze repository in je Azure SQL Database.

**Uit te voeren stappen:**

1. **Azure Data Factory**
   - Breid je Azure Data Factory-pijplijnen uit om CSV-bestanden van deze repository te lezen en te transformeren. Je kunt bijvoorbeeld een Blob Storage-linked service gebruiken om de bestanden op te slaan en dan een kopieeractiviteit gebruiken om de gegevens naar je doeldatabase te verplaatsen.

Dit zijn de bijgewerkte en gedetailleerde stappen voor de opdrachten. Zorg ervoor dat je alle stappen zorgvuldig volgt om de training succesvol af te ronden.
