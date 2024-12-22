```mermaid
sequenceDiagram
    participant navegador
    participant servidor

    navegador->>servidor: Enviar nota ['Esta es mi nueva nota'] con HTTP POST
    servidor->>navegador: Solicitar realizar HTTP GET a /notes

    Note right of servidor: Almacenar el valor de la nueva nota en 'new_notes' y redirigir el navegador a 'notes'

    navegador->>servidor: Solicitar código HTML de notes
    servidor-->>navegador: Código HTML de notes

    navegador->>servidor: Solicitar código CSS
    servidor-->>navegador: Código CSS

    navegador->>servidor: Solicitar código JS
    servidor-->>navegador: Código JS

    Note right of navegador: El navegador ejecuta el JS que solicita los datos en JSON al servidor

    navegador->>servidor: Solicitar los datos JSON
    servidor-->>navegador: Valores o contenido de cada nota
