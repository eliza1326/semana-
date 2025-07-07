# semana-
uso de html-css-javascript
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Pedido | Handele Perfumería Fina</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="form-container">
        <h1>Realizar Pedido en Handele Perfumería Fina</h1>
        <form id="orderForm">
            <h2>Datos del Cliente</h2>
            <div class="form-group">
                <label for="nombreCliente">Nombre Completo:</label>
                <input type="text" id="nombreCliente" name="nombreCliente" required minlength="3">
                <div class="error-message" id="nombreClienteError"></div>
            </div>

            <div class="form-group">
                <label for="emailCliente">Correo Electrónico:</label>
                <input type="email" id="emailCliente" name="emailCliente" required>
                <div class="error-message" id="emailClienteError"></div>
            </div>

            <div class="form-group">
                <label for="telefonoCliente">Teléfono:</label>
                <input type="tel" id="telefonoCliente" name="telefonoCliente" placeholder="Ej: 0987654321" required>
                <div class="error-message" id="telefonoClienteError"></div>
            </div>

            <h2>Detalles del Pedido</h2>
            <div class="form-group">
                <label for="perfumeSeleccionado">Seleccione su Perfume:</label>
                <select id="perfumeSeleccionado" name="perfumeSeleccionado" required>
                    <option value="">-- Por favor, seleccione --</option>
                    <option value="rosal-nocturno">Rosal Nocturno - Eau de Parfum (50ml)</option>
                    <option value="brisa-marina">Brisa Marina - Eau de Toilette (100ml)</option>
                    <option value="esencia-bosque">Esencia del Bosque - Perfume Unisex (75ml)</option>
                    <option value="flor-oriental">Flor Oriental - Eau de Cologne (120ml)</option>
                </select>
                <div class="error-message" id="perfumeSeleccionadoError"></div>
            </div>

            <div class="form-group">
                <label for="cantidad">Cantidad:</label>
                <input type="number" id="cantidad" name="cantidad" required min="1" max="10">
                <div class="error-message" id="cantidadError"></div>
            </div>

            <div class="form-group">
                <label for="direccionEnvio">Dirección de Envío:</label>
                <textarea id="direccionEnvio" name="direccionEnvio" rows="4" placeholder="Calle, número, ciudad, código postal, país" required minlength="10"></textarea>
                <div class="error-message" id="direccionEnvioError"></div>
            </div>

            <div class="form-buttons">
                <button type="submit" id="submitBtn" disabled>Realizar Pedido</button>
                <button type="reset" id="resetBtn">Limpiar Formulario</button>
            </div>
        </form>
    </div>

    <script src="script.js"></script>
</body>
</html>

body {
    font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif; /* Un poco más elegante */
    background-color: #f8f0e5; /* Tono crema suave */
    display: flex;
    justify-content: center;
    align-items: center;
    min-height: 100vh;
    margin: 0;
    color: #333;
}

.form-container {
    background-color: #fff;
    padding: 35px;
    border-radius: 10px;
    box-shadow: 0 4px 15px rgba(0, 0, 0, 0.1);
    width: 100%;
    max-width: 550px; /* Un poco más ancho */
    box-sizing: border-box;
    border: 1px solid #e0e0e0;
}

h1, h2 {
    text-align: center;
    color: #4a2f2b; /* Marrón oscuro */
    margin-bottom: 25px;
    font-weight: 600;
}

h2 {
    margin-top: 30px;
    border-bottom: 1px solid #e0e0e0;
    padding-bottom: 10px;
    margin-bottom: 20px;
    font-size: 1.4em;
}

.form-group {
    margin-bottom: 20px; /* Un poco más de espacio */
}

label {
    display: block;
    margin-bottom: 8px;
    font-weight: bold;
    color: #5d4037; /* Tono de marrón para etiquetas */
}

input[type="text"],
input[type="email"],
input[type="tel"], /* Añadido para el campo de teléfono */
input[type="number"],
select, /* Añadido para el select */
textarea { /* Añadido para el textarea */
    width: 100%;
    padding: 12px; /* Un poco más de padding */
    border: 1px solid #ccc;
    border-radius: 6px; /* Bordes más suaves */
    box-sizing: border-box;
    font-size: 16px;
    background-color: #fcfcfc;
    transition: border-color 0.2s ease, box-shadow 0.2s ease;
}

input:focus,
select:focus,
textarea:focus {
    border-color: #795548; /* Marrón en foco */
    box-shadow: 0 0 0 3px rgba(121, 85, 72, 0.2); /* Sombra suave */
    outline: none;
}


/* Estilos para campos válidos */
input.valid, select.valid, textarea.valid {
    border-color: #28a745; /* Verde */
    box-shadow: 0 0 5px rgba(40, 167, 69, 0.2);
}

/* Estilos para campos inválidos */
input.invalid, select.invalid, textarea.invalid {
    border-color: #dc3545; /* Rojo */
    box-shadow: 0 0 5px rgba(220, 53, 69, 0.2);
}

.error-message {
    color: #dc3545; /* Rojo para mensajes de error */
    font-size: 0.88em; /* Un poco más grande */
    margin-top: 6px; /* Más espacio */
    height: 20px; /* Para mantener el espacio y evitar saltos de diseño */
    display: block;
    font-weight: 500;
}

.form-buttons {
    text-align: center; /* Centrar botones */
    margin-top: 30px;
}

button {
    padding: 12px 25px; /* Más padding */
    border: none;
    border-radius: 6px;
    cursor: pointer;
    font-size: 17px; /* Más grande */
    font-weight: bold;
    transition: background-color 0.3s ease, transform 0.2s ease;
}

#submitBtn {
    background-color: #8d6e63; /* Marrón suave */
    color: white;
}

#submitBtn:hover:not(:disabled) {
    background-color: #6d4c41; /* Marrón más oscuro al pasar el ratón */
    transform: translateY(-2px); /* Pequeño efecto de elevación */
}

#submitBtn:disabled {
    background-color: #cccccc;
    cursor: not-allowed;
    opacity: 0.7;
}

#resetBtn {
    background-color: #a1887f; /* Otro tono de marrón */
    color: white;
    margin-left: 15px; /* Más separación */
}

#resetBtn:hover {
    background-color: #8d6e63;
    transform: translateY(-2px);
}


document.addEventListener('DOMContentLoaded', () => {
    // Obtener referencias a los elementos del formulario
    const form = document.getElementById('orderForm');
    const nombreClienteInput = document.getElementById('nombreCliente');
    const emailClienteInput = document.getElementById('emailCliente');
    const telefonoClienteInput = document.getElementById('telefonoCliente');
    const perfumeSeleccionadoInput = document.getElementById('perfumeSeleccionado');
    const cantidadInput = document.getElementById('cantidad');
    const direccionEnvioInput = document.getElementById('direccionEnvio');
    const submitBtn = document.getElementById('submitBtn');
    const resetBtn = document.getElementById('resetBtn');

    // Obtener referencias a los divs de mensajes de error
    const nombreClienteError = document.getElementById('nombreClienteError');
    const emailClienteError = document.getElementById('emailClienteError');
    const telefonoClienteError = document.getElementById('telefonoClienteError');
    const perfumeSeleccionadoError = document.getElementById('perfumeSeleccionadoError');
    const cantidadError = document.getElementById('cantidadError');
    const direccionEnvioError = document.getElementById('direccionEnvioError');

    // Mapeo de campos a sus funciones de validación
    const fields = [
        { input: nombreClienteInput, errorDiv: nombreClienteError, validator: validateNombreCliente },
        { input: emailClienteInput, errorDiv: emailClienteError, validator: validateEmailCliente },
        { input: telefonoClienteInput, errorDiv: telefonoClienteError, validator: validateTelefonoCliente },
        { input: perfumeSeleccionadoInput, errorDiv: perfumeSeleccionadoError, validator: validatePerfumeSeleccionado },
        { input: cantidadInput, errorDiv: cantidadError, validator: validateCantidad },
        { input: direccionEnvioInput, errorDiv: direccionEnvioError, validator: validateDireccionEnvio }
    ];

    // --- Funciones Auxiliares ---

    function displayError(inputElement, errorDiv, message) {
        errorDiv.textContent = message;
        if (message) {
            inputElement.classList.remove('valid');
            inputElement.classList.add('invalid');
        } else {
            inputElement.classList.remove('invalid');
            inputElement.classList.add('valid');
        }
    }

    // --- Funciones de Validación Específicas ---

    function validateNombreCliente() {
        const value = nombreClienteInput.value.trim();
        if (value.length < 3) {
            displayError(nombreClienteInput, nombreClienteError, 'El nombre debe tener al menos 3 caracteres.');
            return false;
        }
        displayError(nombreClienteInput, nombreClienteError, '');
        return true;
    }

    function validateEmailCliente() {
        const value = emailClienteInput.value.trim();
        // Expresión regular para validar formato de correo electrónico
        const emailRegex = /^[^\s@]+@[^\s@]+\.[^\s@]+$/;
        if (!emailRegex.test(value)) {
            displayError(emailClienteInput, emailClienteError, 'Ingrese un formato de correo electrónico válido (ej. usuario@dominio.com).');
            return false;
        }
        displayError(emailClienteInput, emailClienteError, '');
        return true;
    }

    function validateTelefonoCliente() {
        const value = telefonoClienteInput.value.trim();
        // Expresión regular para números de teléfono (ej. 10 dígitos numéricos)
        // Puedes ajustar esta regex a un formato específico de país si es necesario.
        const phoneRegex = /^\d{7,15}$/; // Acepta de 7 a 15 dígitos numéricos
        if (!phoneRegex.test(value)) {
            displayError(telefonoClienteInput, telefonoClienteError, 'Ingrese un número de teléfono válido (7-15 dígitos numéricos).');
            return false;
        }
        displayError(telefonoClienteInput, telefonoClienteError, '');
        return true;
    }

    function validatePerfumeSeleccionado() {
        const value = perfumeSeleccionadoInput.value;
        if (value === '') { // Si no ha seleccionado ninguna opción real
            displayError(perfumeSeleccionadoInput, perfumeSeleccionadoError, 'Por favor, seleccione un perfume.');
            return false;
        }
        displayError(perfumeSeleccionadoInput, perfumeSeleccionadoError, '');
        return true;
    }

    function validateCantidad() {
        const value = parseInt(cantidadInput.value, 10);
        if (isNaN(value) || value < 1 || value > 10) { // Asumimos un máximo de 10 unidades por pedido
            displayError(cantidadInput, cantidadError, 'La cantidad debe ser entre 1 y 10 unidades.');
            return false;
        }
        displayError(cantidadInput, cantidadError, '');
        return true;
    }

    function validateDireccionEnvio() {
        const value = direccionEnvioInput.value.trim();
        if (value.length < 10) {
            displayError(direccionEnvioInput, direccionEnvioError, 'Ingrese una dirección de envío detallada (mínimo 10 caracteres).');
            return false;
        }
        displayError(direccionEnvioInput, direccionEnvioError, '');
        return true;
    }

    // --- Función para verificar la validez general del formulario ---
    function checkFormValidity() {
        // Ejecuta todas las validaciones y verifica si todas son true
        const allValid = fields.every(field => field.validator());
        submitBtn.disabled = !allValid; // Habilita/deshabilita el botón de envío
    }

    // --- Event Listeners para validación en tiempo real ---
    fields.forEach(({ input, validator }) => {
        // Para inputs de texto/número/textarea, valida al escribir y al perder el foco
        if (input.type === 'text' || input.type === 'email' || input.type === 'tel' || input.type === 'number' || input.tagName === 'TEXTAREA') {
            input.addEventListener('input', () => {
                validator();
                checkFormValidity();
            });
            input.addEventListener('blur', () => {
                validator();
                checkFormValidity();
            });
        }
        // Para el select, valida al cambiar la selección
        if (input.tagName === 'SELECT') {
            input.addEventListener('change', () => {
                validator();
                checkFormValidity();
            });
            input.addEventListener('blur', () => { // También al perder el foco
                validator();
                checkFormValidity();
            });
        }
    });

    // --- Event Listener para el botón de Reiniciar ---
    resetBtn.addEventListener('click', () => {
        // Limpiar mensajes de error y clases de validación
        fields.forEach(field => {
            field.errorDiv.textContent = '';
            field.input.classList.remove('valid', 'invalid');
        });
        submitBtn.disabled = true; // Deshabilitar el botón de envío
    });

    // --- Event Listener para el envío del formulario ---
    form.addEventListener('submit', (event) => {
        event.preventDefault(); // Prevenir el envío por defecto del formulario

        // Re-validar todos los campos antes del envío final (seguridad y última comprobación)
        const isFormValid = fields.every(field => field.validator());

        if (isFormValid) {
            const perfumeElegido = perfumeSeleccionadoInput.options[perfumeSeleccionadoInput.selectedIndex].text;
            const mensajeConfirmacion = ¡Pedido de ${cantidadInput.value} unidades de "${perfumeElegido}" realizado con éxito!\n\n +
                                        Datos del cliente:\n +
                                        Nombre: ${nombreClienteInput.value}\n +
                                        Email: ${emailClienteInput.value}\n +
                                        Teléfono: ${telefonoClienteInput.value}\n\n +
                                        Dirección de envío: ${direccionEnvioInput.value}\n\n +
                                        Pronto recibirás un correo de confirmación. ¡Gracias por elegir Handele Perfumería Fina!;
            
            alert(mensajeConfirmacion);
            
            form.reset(); // Reiniciar el formulario después del envío exitoso
            resetBtn.click(); // Simular clic en reiniciar para limpiar estados visuales
        } else {
            alert('Por favor, corrija los errores del formulario antes de enviar su pedido.');
        }
    });

    // Validar el formulario al cargar la página inicialmente (para deshabilitar el botón si no cumple al inicio)
    checkFormValidity();
});
