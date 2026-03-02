async function crearContrato(primaryControl) {
    const formContext = primaryControl;
    
    // 1. Obtener los valores de los campos (cambia los nombres lógicos aquí)
    const idContrato = formContext.getAttribute("ol_idcontrato").getValue();
    const nombreEmpleado = formContext.getAttribute("ol_empleadocontratado").getValue();
    const recordId = formContext.data.entity.getId().replace("{", "").replace("}", "");
    const entityName = formContext.data.entity.getEntityName();

    // 2. VALIDACIÓN: Verificar si están rellenos
    if (!idContrato || !nombreEmpleado) {
        Xrm.Navigation.openErrorDialog({ 
            message: "Error: Los campos 'Id Contrato' y 'Nombre Empleado' deben estar rellenos para continuar." 
        });
        return; // Detiene la ejecución
    }

    // 3. Confirmación del usuario
    const confirmStrings = { 
        text: "¿Ha revisado los campos para generar el contrato? ¿Está seguro de continuar?", 
        title: "Confirmar proceso" 
    };
    const confirmOptions = { height: 200, width: 450 };

    Xrm.Navigation.openConfirmDialog(confirmStrings, confirmOptions).then(async function (success) {
        if (success.confirmed) {
            try {
                // 4. Mostrar indicador de carga
                Xrm.Utility.showProgressIndicator("Actualizando estado  y creando contrato...");

                // 5. Actualizar el estado (Status Reason / statuscode)
                // Cambia 'statuscode' por tu campo y el número por el valor del estado deseado
                let data = {
                    "statuscode": 125250001 // Valor numérico de tu estado (ej: 'Enviado')
                };

                await Xrm.WebApi.updateRecord(entityName, recordId, data);

                // 6. Refrescar el formulario y cerrar indicador
                formContext.data.refresh(false);
                Xrm.Utility.closeProgressIndicator();

                // Notificación de éxito
                Xrm.Navigation.openAlertDialog({ text: "El estado se ha actualizado. Generando contrato." });

            } catch (error) {
                Xrm.Utility.closeProgressIndicator();
                Xrm.Navigation.openErrorDialog({ message: "Error en la actualización: " + error.message });
            }
        }
    });
}