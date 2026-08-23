<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ticket de Tienda - Hogaluz</title>
    <style>
        body {
            font-family: Arial, sans-serif;
            font-size: 12px;
            color: #000;
            max-width: 800px; 
            margin: 0 auto;
            padding: 20px;
        }
        .header-container {
            display: flex;
            justify-content: space-between;
            margin-bottom: 20px;
        }
        .customer-info, .company-info {
            width: 48%;
        }
        .company-info {
            text-align: center;
        }
        .company-info h1 {
            color: #004481;
            margin: 0;
            font-size: 32px;
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 10px;
        }
        .title {
            font-weight: bold;
            font-size: 14px;
            text-decoration: underline;
            margin-bottom: 10px;
        }
        .info-line {
            margin: 3px 0;
        }
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 20px;
        }
        th, td {
            padding: 8px;
            text-align: left;
        }
        th {
            border-top: 2px solid #000;
            border-bottom: 2px solid #000;
            font-weight: bold;
        }
        .totals-container {
            display: flex;
            justify-content: flex-end;
            margin-bottom: 20px;
        }
        .totals-table {
            width: 30%;
            border-collapse: collapse;
        }
        .totals-table td {
            padding: 5px;
            border-bottom: 1px solid #ccc;
        }
        .totals-table tr:last-child td {
            font-weight: bold;
            border-bottom: none;
        }
        .footer-info {
            margin-bottom: 20px;
        }
        .legal-text {
            font-size: 9px;
            text-align: justify;
            margin-bottom: 10px;
        }
        .legal-title {
            font-weight: bold;
            text-decoration: underline;
            margin-bottom: 3px;
        }
        
        @media print {
            @page { margin: 10mm; }
            body { padding: 0; }
        }
    </style>
</head>
<body>

    <div class="header-container">
        <!-- Datos del Cliente -->
        <div class="customer-info">
            <div class="title">TICKET DE TIENDA</div>
            <div class="info-line">Nro. de Ticket: <span id="ticket">000000</span></div>
            <div class="info-line">Fecha: <span id="fecha">--/--/----</span></div>
            <div class="info-line">Tipo de documento: <span id="documento">Nota de Venta</span></div>
            <div class="info-line">Cliente: <span id="cliente">-</span></div>
            <div class="info-line">DNI/RUC: <span id="dni">-</span></div>
            <div class="info-line">Dirección: <span id="direccion">-</span></div>
            <div class="info-line">Teléfono: <span id="telefono">-</span></div>
        </div>
        
        <!-- Datos de la Empresa -->
        <div class="company-info">
            <h1>Hogaluz</h1> 
            <div class="info-line">RUC: 10024374896</div>
            <div class="info-line">URB. CERCADO, JULIACA, PUNO</div>
            <div class="info-line">Jr. 8 de noviembre Nro. 575 Urb. Cercado / Jr. Tupac Amaru</div>
            <div class="info-line">Nro 1476, Juliaca 21104, Provincia San Román, Departamento</div>
            <div class="info-line">de Puno, Perú</div>
        </div>
    </div>

    <!-- Tabla de Productos (Related VENTASs) -->
    <table>
        <thead>
            <tr>
                <th>Cantidad</th>
                <th>Descripción</th>
                <th>Precio</th>
                <th>Subtotal</th>
            </tr>
        </thead>
        <tbody id="lista-productos">
            <tr>
                <td colspan="4" style="text-align:center;">Cargando productos...</td>
            </tr>
        </tbody>
    </table>

    <!-- Totales -->
    <div class="totals-container">
        <table class="totals-table">
            <tr>
                <td>Subtotal</td>
                <td>S/ <span id="subtotal">0.00</span></td>
            </tr>
            <tr>
                <td>Descuento</td>
                <td>S/ <span id="descuento">0.00</span></td>
            </tr>
            <tr>
                <td>Total</td>
                <td>S/ <span id="total">0.00</span></td>
            </tr>
        </table>
    </div>

    <!-- Info del Vendedor / Local -->
    <div class="footer-info">
        <div class="info-line">Vendedor: <span id="vendedor">-</span></div>
        <div class="info-line">Local: <span id="local">-</span></div>
    </div>

    <!-- Textos Legales -->
    <div class="legal-text">
        <div class="legal-title">Política de Cambios y Devoluciones</div>
        Garantizamos el correcto funcionamiento de todos nuestros productos al momento de salir de tienda. En caso de que el producto no haya sido probado previamente antes de su entrega, el cliente podrá solicitar un cambio dentro de un plazo máximo de 48 horas desde realizada la compra. Los cambios se efectuarán únicamente si el producto es devuelto en perfecto estado o en las mismas condiciones en las que fue vendido, conservando todos sus empaques, accesorios y etiquetas. No realizamos devoluciones de dinero en efectivo bajo ninguna circunstancia. Para productos que cuentan con garantía, ésta será informada al momento de la venta y se respetará dentro del plazo establecido, aplicándose únicamente para fallas de fábrica. La empresa no se hace responsable por daños incidentales o indirectos derivados del uso del producto.
    </div>
    <div class="legal-text">
        <div class="legal-title">Aviso al Cliente</div>
        Este ticket corresponde a la constancia de la operación realizada en nuestra tienda y NO constituye Boleta de Venta, Factura ni Comprobante de Pago válido ante SUNAT. La Boleta de Venta Electrónica o Factura Electrónica correspondiente a esta operación se encuentra pendiente de emisión y será enviada al cliente utilizando los datos proporcionados al momento de realizar la compra.
        <br><br>
        Importante: Verifique que sus datos personales y/o tributarios registrados en este ticket sean correctos. En caso de existir algún error o requerir alguna modificación, comuníquese a la brevedad a los números de contacto indicados en este ticket.
    </div>
    <div class="info-line" style="text-align:center; font-weight:bold;">
        Tel. 961 011 400 - 912 906 262
    </div>

    <script>
        // Capturar parámetros de la URL
        const params = new URLSearchParams(window.location.search);

        // Mapear los datos de la tabla COMPROBANTE
        const campos = ['fecha', 'documento', 'dni', 'cliente', 'direccion', 'telefono', 'subtotal', 'descuento', 'ticket', 'local', 'vendedor'];
        
        campos.forEach(campo => {
            if(params.has(campo) && params.get(campo) !== "") {
                document.getElementById(campo).innerText = params.get(campo);
            }
        });

        // Calcular y mostrar el Total (Subtotal - Descuento)
        const valSubtotal = parseFloat(params.get('subtotal')) || 0;
        const valDescuento = parseFloat(params.get('descuento')) || 0;
        document.getElementById('total').innerText = (valSubtotal - valDescuento).toFixed(2);

        // Lógica para inyectar los productos de la tabla [Related VENTASs]
        const itemsParam = params.get('items');
        const listaProductos = document.getElementById('lista-productos');

        if (itemsParam) {
            listaProductos.innerHTML = ''; 
            
            // Separar cada producto por el asterisco (*)
            const productos = itemsParam.split('*'); 
            
            productos.forEach(prod => {
                // Separar (UNIDADES | DESCRIPCIÓN | PRECIO | SUBTOTAL) por la barra vertical (|)
                const detalles = prod.split('|'); 
                if(detalles.length === 4) {
                    const tr = document.createElement('tr');
                    tr.innerHTML = `
                        <td>${detalles[0]}</td>
                        <td>${detalles[1]}</td>
                        <td>S/ ${parseFloat(detalles[2]).toFixed(2)}</td>
                        <td>S/ ${parseFloat(detalles[3]).toFixed(2)}</td>
                    `;
                    listaProductos.appendChild(tr);
                }
            });
        } else {
            listaProductos.innerHTML = '<tr><td colspan="4" style="text-align:center;">No se registraron productos.</td></tr>';
        }

        // Ejecutar impresión automática
        window.onload = function() {
            setTimeout(() => { window.print(); }, 500);
        }
    </script>
</body>
</html>
