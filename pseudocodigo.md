Creación de Usuario

INICIO CrearUsuario
    INPUT nombre, email
    saldo_inicial = 1000000.00
    usuario = CrearObjeto(Usuario, nombre, email, saldo_inicial)
    inversor = CrearObjeto(Inversor, usuario.id_usuario, perfil_inversor)
    OUTPUT "Usuario creado con éxito", usuario, inversor
FIN

Consulta de Cotizaciones


INICIO ConsultarCotizaciones
    cotizaciones = ObtenerCotizaciones()
    PARA cada cotizacion EN cotizaciones
        IMPRIMIR "Símbolo:", cotizacion.simbolo
        IMPRIMIR "Nombre de la Empresa:", cotizacion.nombre_empresa
        IMPRIMIR "Último Operado:", cotizacion.ultimo_operado
        IMPRIMIR "Cantidad Compra Diaria:", cotizacion.cantidad_compra_diaria
        IMPRIMIR "Precio Compra Actual:", cotizacion.precio_compra_actual
        IMPRIMIR "Precio Venta Actual:", cotizacion.precio_venta_actual
        IMPRIMIR "Cantidad Venta Diaria:", cotizacion.cantidad_venta_diaria
        IMPRIMIR "Apertura:", cotizacion.apertura
        IMPRIMIR "Mínimo Diario:", cotizacion.minimo_diario
        IMPRIMIR "Máximo Diario:", cotizacion.maximo_diario
        IMPRIMIR "Último Cierre:", cotizacion.ultimo_cierre
    FIN 
FIN

Compra de Acciones

INICIO ComprarAcciones
    INPUT id_usuario, simbolo_accion, cantidad
    usuario = ObtenerUsuarioPorId(id_usuario)
    cotizacion = ObtenerCotizacionPorSimbolo(simbolo_accion)
    precio_total = cotizacion.precio_venta_actual * cantidad
    comision = precio_total * 0.015
    costo_total = precio_total + comision
    
    SI usuario.saldo >= costo_total ENTONCES
        usuario.saldo = usuario.saldo - costo_total
        transaccion = CrearObjeto(Transaccion, "compra", fecha_actual, cotizacion.id_accion, cantidad, cotizacion.precio_venta_actual, comision, usuario.id_usuario)
        ActualizarPortafolio(usuario.id_usuario, cotizacion.id_accion, cantidad, costo_total)
        OUTPUT "Compra exitosa", transaccion
    SINO
        OUTPUT "Saldo insuficiente para realizar la compra"
    FIN SI
FIN

Venta de Acciones

INICIO VenderAcciones
    INPUT id_usuario, simbolo_accion, cantidad
    usuario = ObtenerUsuarioPorId(id_usuario)
    cotizacion = ObtenerCotizacionPorSimbolo(simbolo_accion)
    portafolio = ObtenerPortafolioPorUsuarioYAccion(id_usuario, cotizacion.id_accion)
    
    SI portafolio.cantidad >= cantidad ENTONCES
        precio_total = cotizacion.precio_compra_actual * cantidad
        comision = precio_total * 0.015
        ganancia_total = precio_total - comision
        
        usuario.saldo = usuario.saldo + ganancia_total
        transaccion = CrearObjeto(Transaccion, "venta", fecha_actual, cotizacion.id_accion, cantidad, cotizacion.precio_compra_actual, comision, usuario.id_usuario)
        ActualizarPortafolio(usuario.id_usuario, cotizacion.id_accion, -cantidad, -ganancia_total)
        OUTPUT "Venta exitosa", transaccion
    SINO
        OUTPUT "No tiene suficientes acciones para vender"
    FIN SI
FIN

Gestión del Portafolio

INICIO MostrarPortafolio
    INPUT id_usuario
    portafolio = ObtenerPortafolioPorUsuario(id_usuario)
    total_invertido = 0
    ganancia_perdida = 0

    PARA cada item EN portafolio
        cotizacion = ObtenerCotizacionPorId(item.id_accion)
        valor_actual = cotizacion.precio_compra_actual * item.cantidad
        total_invertido = total_invertido + item.total_invertido
        ganancia_perdida = ganancia_perdida + (valor_actual - item.total_invertido)
        IMPRIMIR "Símbolo:", cotizacion.simbolo
        IMPRIMIR "Cantidad:", item.cantidad
        IMPRIMIR "Valor Actual:", valor_actual
    FIN PARA
    
    IMPRIMIR "Total Invertido:", total_invertido
    IMPRIMIR "Ganancia/Pérdida:", ganancia_perdida
    IMPRIMIR "Saldo de la Cuenta:", usuario.saldo
FIN