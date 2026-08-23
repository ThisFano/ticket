<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Ticket de Tienda - Hogaluz</title>
    <style>
        :root {
            --color-primario: #004481;
            --color-primario-suave: #eef3f8;
            --color-texto: #1a1a1a;
            --color-texto-secundario: #6b6b6b;
            --color-borde: #d9d9d9;
            --color-borde-fuerte: #000;
            --color-fondo-sutil: #fafafa;
        }

        * {
            box-sizing: border-box;
        }

        body {
            font-family: Arial, Helvetica, sans-serif;
            font-size: 12px;
            line-height: 1.45;
            color: var(--color-texto);
            max-width: 800px;
            margin: 0 auto;
            padding: 28px 24px;
        }

        /* ===================== ENCABEZADO ===================== */
        .header-container {
            display: flex;
            justify-content: space-between;
            align-items: flex-start;
            gap: 24px;
            padding-bottom: 14px;
            border-bottom: 2px solid var(--color-primario);
            margin-bottom: 18px;
        }

        /* Bloque de identidad (logo + datos de la empresa) */
        .company-info {
            display: flex;
            flex-direction: column;
            gap: 6px;
            max-width: 55%;
        }

        /* Contenedor del logo.
           ---------------------------------------------------------
           AQUÍ VA EL LOGO OFICIAL DE LA EMPRESA (ver instrucciones
           después del código sobre cómo insertarlo).
           Mientras tanto se muestra un placeholder de texto para no
           perder la referencia visual de la marca.
           ---------------------------------------------------------
        */
        .company-logo {
            display: flex;
            align-items: center;
            height: 40px;
            margin-bottom: 2px;
        }
        .company-logo svg,
        .company-logo img {
            height: 100%;
            width: auto;
            max-width: 220px;
            object-fit: contain;
        }
        /* Placeholder temporal: eliminar esta clase/nodo al insertar el SVG real */
        .company-logo .logo-placeholder {
            font-size: 22px;
            font-weight: bold;
            color: var(--color-primario);
            letter-spacing: 0.5px;
        }

        .company-info .info-line {
            font-size: 10px;
            color: var(--color-texto-secundario);
            margin: 0;
        }

        /* Ficha del comprobante (metadatos del documento) */
        .document-info {
            text-align: right;
            min-width: 230px;
        }

        .document-info .title {
            font-size: 15px;
            font-weight: bold;
            color: var(--color-primario);
            text-transform: uppercase;
            letter-spacing: 0.4px;
            margin: 0 0 8px 0;
        }

        .document-info .info-line {
            margin: 2px 0;
        }

        .info-line .label {
            color: var(--color-texto-secundario);
            font-size: 10.5px;
        }

        .info-line .value {
            color: var(--color-texto);
            font-weight: 600;
        }

        /* ===================== DATOS DEL CLIENTE ===================== */
        .customer-section {
            margin-bottom: 20px;
        }

        .section-label {
            font-size: 10px;
            font-weight: bold;
            color: var(--color-texto-secundario);
            text-transform: uppercase;
            letter-spacing: 0.6px;
            margin-bottom: 6px;
        }

        .customer-grid {
            display: grid;
            grid-template-columns: 1fr 1fr;
            column-gap: 24px;
            row-gap: 3px;
        }

        .customer-grid .info-line {
            margin: 0;
        }

        /* ===================== TABLA DE PRODUCTOS ===================== */
        table {
            width: 100%;
            border-collapse: collapse;
            margin-bottom: 4px;
        }

        thead {
            display: table-header-group; /* repite el encabezado en cada página impresa */
        }

        th {
            background-color: var(--color-primario);
            color: #fff;
            font-size: 10.5px;
            text-transform: uppercase;
            letter-spacing: 0.3px;
            font-weight: bold;
            padding: 8px 10px;
            text-align: left;
        }

        th.col-numerica,
        td.col-numerica {
            text-align: right;
        }

        td {
            padding: 7px 10px;
            border-bottom: 1px solid var(--color-borde);
            font-size: 11.5px;
            break-inside: avoid;
        }

        tbody tr:last-child td {
            border-bottom: 2px solid var(--color-primario);
        }

        /* ===================== TOTALES ===================== */
        .totals-container {
            display: flex;
            justify-content: flex-end;
            margin-top: 6px;
            margin-bottom: 22px;
            break-inside: avoid;
        }

        .totals-table {
            width: 44%;
            min-width: 230px;
            border-collapse: collapse;
        }

        .totals-table td {
            padding: 5px 4px;
            border: none;
            font-size: 11.5px;
        }

        .totals-table td:last-child {
            text-align: right;
        }

        .totals-table tr.row-subtotal td,
        .totals-table tr.row-descuento td {
            color: var(--color-texto-secundario);
        }

        .totals-table tr.row-total td {
            border-top: 1.5px solid var(--color-primario);
            padding-top: 8px;
            font-size: 15px;
            font-weight: bold;
            color: var(--color-primario);
        }

        /* ===================== VENDEDOR / LOCAL ===================== */
        .meta-venta {
            display: flex;
            gap: 18px;
            flex-wrap: wrap;
            font-size: 10.5px;
            color: var(--color-texto-secundario);
            padding-top: 10px;
            border-top: 1px solid var(--color-borde);
            margin-bottom: 26px;
        }

        .meta-venta .info-line {
            margin: 0;
        }

        .meta-venta .separador {
            color: var(--color-borde);
        }

        /* ===================== PIE DE PÁGINA ===================== */
        .footer {
            border-top: 1px solid var(--color-borde);
            padding-top: 14px;
            break-inside: avoid;
        }

        .legal-text {
            font-size: 8.5px;
            line-height: 1.5;
            color: var(--color-texto-secundario);
            text-align: justify;
            margin-bottom: 10px;
        }

        .legal-title {
            font-weight: bold;
            color: var(--color-texto-secundario);
            text-transform: uppercase;
            letter-spacing: 0.3px;
            font-size: 8.5px;
            margin-bottom: 2px;
            display: block;
        }

        .footer-bottom {
            display: flex;
            justify-content: space-between;
            align-items: center;
            flex-wrap: wrap;
            gap: 10px;
            margin-top: 12px;
            padding-top: 10px;
            border-top: 1px solid var(--color-borde);
        }

        .footer-contact {
            font-size: 10px;
            font-weight: bold;
            color: var(--color-texto);
        }

        /* Redes sociales */
        .footer-social {
            display: flex;
            align-items: center;
            gap: 8px;
            font-size: 10px;
            color: var(--color-texto-secundario);
        }

        .footer-social .social-icons {
            display: flex;
            align-items: center;
            gap: 6px;
        }

        .footer-social svg {
            width: 13px;
            height: 13px;
            fill: var(--color-texto-secundario);
        }

        .footer-social .social-user {
            font-weight: 600;
            color: var(--color-texto);
        }

        @media print {
            @page {
                margin: 12mm;
            }
            body {
                padding: 0;
                max-width: 100%;
            }
            tr {
                break-inside: avoid;
            }
        }
    </style>
</head>
<body>

    <!-- ===================== ENCABEZADO ===================== -->
    <div class="header-container">
        <!-- Identidad de la empresa -->
        <div class="company-info">
            <div class="company-logo">
                <!--
                    INSERTAR AQUÍ EL LOGO OFICIAL (ver instrucciones al final).
                    Opción 1 (preferida): pegar el código <svg>...</svg> del logo directamente en este div.
                    Opción 2: <img src="ruta/local/logo.svg" alt="Hogaluz">
                    Mientras tanto se usa un placeholder de texto:
                -->
                <span class="logo-placeholder">Hogaluz</span>
            </div>
            <div class="info-line">RUC: 10024374896</div>
            <div class="info-line">URB. CERCADO, JULIACA, PUNO</div>
            <div class="info-line">Jr. 8 de noviembre Nro. 575 Urb. Cercado / Jr. Tupac Amaru Nro 1476</div>
            <div class="info-line">Juliaca 21104, Provincia San Román, Departamento de Puno, Perú</div>
        </div>

        <!-- Datos del comprobante -->
        <div class="document-info">
            <div class="title">Ticket de Tienda</div>
            <div class="info-line"><span class="label">Nro. de Ticket:</span> <span class="value" id="ticket">000000</span></div>
            <div class="info-line"><span class="label">Fecha:</span> <span class="value" id="fecha">--/--/----</span></div>
            <div class="info-line"><span class="label">Tipo de documento:</span> <span class="value" id="documento">Nota de Venta</span></div>
        </div>
    </div>

    <!-- ===================== DATOS DEL CLIENTE ===================== -->
    <div class="customer-section">
        <div class="section-label">Datos del Cliente</div>
        <div class="customer-grid">
            <div class="info-line"><span class="label">Cliente:</span> <span class="value" id="cliente">-</span></div>
            <div class="info-line"><span class="label">DNI/RUC:</span> <span class="value" id="dni">-</span></div>
            <div class="info-line"><span class="label">Dirección:</span> <span class="value" id="direccion">-</span></div>
            <div class="info-line"><span class="label">Teléfono:</span> <span class="value" id="telefono">-</span></div>
        </div>
    </div>

    <!-- Tabla de Productos (Related VENTASs) -->
    <table>
        <thead>
            <tr>
                <th>Cantidad</th>
                <th>Descripción</th>
                <th class="col-numerica">Precio</th>
                <th class="col-numerica">Subtotal</th>
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
            <tr class="row-subtotal">
                <td>Subtotal</td>
                <td>S/ <span id="subtotal">0.00</span></td>
            </tr>
            <tr class="row-descuento">
                <td>Descuento</td>
                <td>S/ <span id="descuento">0.00</span></td>
            </tr>
            <tr class="row-total">
                <td>Total</td>
                <td>S/ <span id="total">0.00</span></td>
            </tr>
        </table>
    </div>

    <!-- Info del Vendedor / Local -->
    <div class="meta-venta">
        <div class="info-line"><span class="label">Vendedor:</span> <span class="value" id="vendedor">-</span></div>
        <span class="separador">•</span>
        <div class="info-line"><span class="label">Local:</span> <span class="value" id="local">-</span></div>
    </div>

    <!-- ===================== PIE DE PÁGINA ===================== -->
    <div class="footer">
        <div class="legal-text">
            <span class="legal-title">Política de Cambios y Devoluciones</span>
            Garantizamos el correcto funcionamiento de todos nuestros productos al momento de salir de tienda. En caso de que el producto no haya sido probado previamente antes de su entrega, el cliente podrá solicitar un cambio dentro de un plazo máximo de 48 horas desde realizada la compra. Los cambios se efectuarán únicamente si el producto es devuelto en perfecto estado o en las mismas condiciones en las que fue vendido, conservando todos sus empaques, accesorios y etiquetas. No realizamos devoluciones de dinero en efectivo bajo ninguna circunstancia. Para productos que cuentan con garantía, ésta será informada al momento de la venta y se respetará dentro del plazo establecido, aplicándose únicamente para fallas de fábrica. La empresa no se hace responsable por daños incidentales o indirectos derivados del uso del producto.
        </div>
        <div class="legal-text">
            <span class="legal-title">Aviso al Cliente</span>
            Este ticket corresponde a la constancia de la operación realizada en nuestra tienda y NO constituye Boleta de Venta, Factura ni Comprobante de Pago válido ante SUNAT. La Boleta de Venta Electrónica o Factura Electrónica correspondiente a esta operación se encuentra pendiente de emisión y será enviada al cliente utilizando los datos proporcionados al momento de realizar la compra.
            <br><br>
            Importante: Verifique que sus datos personales y/o tributarios registrados en este ticket sean correctos. En caso de existir algún error o requerir alguna modificación, comuníquese a la brevedad a los números de contacto indicados en este ticket.
        </div>

        <div class="footer-bottom">
            <div class="footer-contact">Tel. 961 011 400 - 912 906 262</div>

            <div class="footer-social">
                <span class="social-icons">
                    <!-- Instagram -->
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-label="Instagram">
                        <path d="M12 2.2c3.2 0 3.6 0 4.9.07 1.2.06 2 .24 2.5.42.6.24 1.1.55 1.6 1.05.5.5.8 1 1.05 1.6.18.5.36 1.3.42 2.5.06 1.3.07 1.7.07 4.9s0 3.6-.07 4.9c-.06 1.2-.24 2-.42 2.5-.24.6-.55 1.1-1.05 1.6-.5.5-1 .8-1.6 1.05-.5.18-1.3.36-2.5.42-1.3.06-1.7.07-4.9.07s-3.6 0-4.9-.07c-1.2-.06-2-.24-2.5-.42-.6-.24-1.1-.55-1.6-1.05-.5-.5-.8-1-1.05-1.6-.18-.5-.36-1.3-.42-2.5C2.2 15.6 2.2 15.2 2.2 12s0-3.6.07-4.9c.06-1.2.24-2 .42-2.5.24-.6.55-1.1 1.05-1.6.5-.5 1-.8 1.6-1.05.5-.18 1.3-.36 2.5-.42C8.4 2.2 8.8 2.2 12 2.2zm0 1.8c-3.15 0-3.5 0-4.75.07-1 .04-1.55.2-1.9.34-.48.19-.82.4-1.18.76-.36.36-.58.7-.76 1.18-.14.35-.3.9-.34 1.9C3 9.5 3 9.85 3 13s0 3.5.07 4.75c.04 1 .2 1.55.34 1.9.19.48.4.82.76 1.18.36.36.7.58 1.18.76.35.14.9.3 1.9.34 1.25.06 1.6.07 4.75.07s3.5 0 4.75-.07c1-.04 1.55-.2 1.9-.34.48-.19.82-.4 1.18-.76.36-.36.58-.7.76-1.18.14-.35.3-.9.34-1.9.06-1.25.07-1.6.07-4.75s0-3.5-.07-4.75c-.04-1-.2-1.55-.34-1.9-.19-.48-.4-.82-.76-1.18-.36-.36-.7-.58-1.18-.76-.35-.14-.9-.3-1.9-.34C15.5 4 15.15 4 12 4zm0 3.6a4.4 4.4 0 1 1 0 8.8 4.4 4.4 0 0 1 0-8.8zm0 1.8a2.6 2.6 0 1 0 0 5.2 2.6 2.6 0 0 0 0-5.2zm4.6-2.05a1.03 1.03 0 1 1 0 2.06 1.03 1.03 0 0 1 0-2.06z"/>
                    </svg>
                    <!-- TikTok -->
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-label="TikTok">
                        <path d="M16.5 2h-3.1v13.4c0 1.4-1.1 2.6-2.6 2.6a2.6 2.6 0 0 1-2.6-2.6 2.6 2.6 0 0 1 2.6-2.6c.25 0 .5.03.73.1V9.7a5.7 5.7 0 0 0-.73-.05A5.75 5.75 0 0 0 5 15.4 5.75 5.75 0 0 0 10.75 21a5.75 5.75 0 0 0 5.75-5.6V8.9c1.1.8 2.45 1.28 3.9 1.28V7.05c-1.9 0-3.5-1.35-3.9-2.9z"/>
                    </svg>
                    <!-- Facebook -->
                    <svg viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg" aria-label="Facebook">
                        <path d="M13.5 21v-8.1h2.7l.4-3.1h-3.1V7.8c0-.9.25-1.5 1.55-1.5H16.7V3.5c-.3-.04-1.3-.13-2.45-.13-2.4 0-4.05 1.47-4.05 4.15v2.3H7.5v3.1h2.7V21h3.3z"/>
                    </svg>
                </span>
                <span class="social-user">@hogaluz</span>
            </div>
        </div>
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
                        <td class="col-numerica">S/ ${parseFloat(detalles[2]).toFixed(2)}</td>
                        <td class="col-numerica">S/ ${parseFloat(detalles[3]).toFixed(2)}</td>
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
