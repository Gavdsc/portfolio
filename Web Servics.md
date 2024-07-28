# Pantheon Web Services

All code, no pictures, more text :(

### Overview

Pantheon Web Services was developed as a solution for importing and exporting data to and from the Oculus databases. 

This service is designed to facilitate seamless data integration by connecting clients with data from third-party REST APIs. 
By acting as an intermediary, Pantheon Web Services enables efficient data exchange between external APIs and the Oculus databases. 
Clients can easily retrieve data from various external sources or send data to these sources using the web services provided by Pantheon. 
This approach simplifies the process of data integration and ensures that clients have access to up-to-date and accurate information from multiple external providers.

### Structure

Writing and maintaining RPG programs for IBM i systems can be challenging, particularly when it comes to integrating modern
web technologies. To address these challenges, PHP was used for accessing and structuring calls to third party
REST API services, leveraging PHP cURL.

Using an intermediary database, RPG programs call a PHP program to make and handle requests. 
The intermediary database acts as a communication hub where RPG programs can place requests that need to 
be processed by PHP. When an RPG program has a task that requires interaction with a third party API or service,
it inserts a request into the database. The PHP program is then passed the request over command line,
retrieves it from the database, processes and runs it (often in batches), and then updates the database with the results.

Once a request has been completed, PHP triggers the correct RPG programs using prepared stored procedure calls via PDO (PHP Data Objects) and SQL.
To achieve this, the program passes along any necessary information such as the database name, library, batch ID, and any error messages. 
This structured approach ensures that the RPG program is correctly informed and can proceed with its next steps.

### Contributions

I was the sole developer responsible for maintaining and building the PHP services for Pantheon Web Services. My role involved designing, coding, and troubleshooting the PHP scripts.

To ensure successful integrations, I worked closely with the backend RPG developers