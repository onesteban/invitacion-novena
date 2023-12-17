<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title> Invitación a la Novena realizada por Maria de los Angeles y Juan Esteban </title>
    <style>
        body {
            display: flex;
            align-items: center;
            justify-content: center;
            height: 100vh;
            margin: 0;
            font-family: Arial, sans-serif;
            background-color: #870404; /* Cambia el color de fondo del cuerpo aquí */
        }

        #content {
            text-align: center;
            background-color: #ffffff; /* Cambia el color de fondo del contenido aquí */
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
        }

        h1 {
            margin-bottom: 10px; /* Añade un espacio entre el título y el párrafo */
        }

        p {
            font-size: 14px;
            margin-bottom: 10px;
        }

        button {
            margin: 10px;
            padding: 10px;
            font-size: 16px;
            background-color: #4CAF50; /* Cambia el color de fondo del botón aquí */
            color: #fff; /* Cambia el color del texto del botón aquí */
        }

        #mensaje {
            margin-top: 20px;
            font-weight: bold;
        }
    </style>
</head>
<body>

    <div id="content">
        <h1>Invitación a la Novena realizada por Maria de los Angeles y Juan Esteban.</h1>
        <p>Blanca,Manchas,copo,Loba,Negro y trebol te queremos invitar a nuestra novena ¿te gustaria asistir? </p>

        <form>
            <button type="button" onclick="responder('Sí')">Sí</button>
            <button type="button" onclick="responder('No')">No</button>

            <div id="mensaje"></div>
        </form>
    </div>

    <script>
        var contadorSi = 0;

        function responder(respuesta) {
            var mensajeContainer = document.getElementById("mensaje");

            switch (respuesta) {
                case "Sí":
                    contadorSi++;

                    if (contadorSi === 1) {
                        mensajeContainer.innerHTML = "no te veo muy convencido ¿seguro quiere ir?";
                    } else if (contadorSi === 2) {
                        mensajeContainer.innerHTML = "creo que puedes aprovechar ese tiempo en algo mejor ¿estas seguro de que te gustaria ir?";
                    } else if (contadorSi === 3) {
                        mensajeContainer.innerHTML = "es enserio  ¿piensalo una vez más?";
                    } else if (contadorSi === 4) {
                        mensajeContainer.innerHTML = "es tu última oportunidad ¿estas seguro?.";
                    } else if (contadorSi === 5) {
                        mensajeContainer.innerHTML = "Lo sentimos, pero despues de meditarlo hemos decidido que ya no vamos a hacer la novena.";
                        disableButtons();
                    }
                    break;
                case "No":
                    mensajeContainer.innerHTML = "bueno muchas gracias por participar ";
                    disableButtons();
                    break;
                default:
                    mensajeContainer.innerHTML = "";
            }
        }

        function disableButtons() {
            var buttons = document.querySelectorAll('button');
            buttons.forEach(function(button) {
                button.disabled = true;
            });
        }
    </script>

</body>
</html>
