---
title: Orquestación PIPAutomation de acción doble | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 9159f7b1-cb83-41f1-8637-39c5ddcc63ae
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4f04b04d20189307c3d42e60c43c2c4c9254ffb7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37008429"
---
# <a name="double-action-pipautomation-orchestration"></a>Orquestación PIPAutomation de acción doble
El ejemplo DoubleAction.odx muestra cómo implementar una orquestación para generar automáticamente las respuestas para los procesos de interfaz de socio (PIP) de doble acción 0c2, 0c4, 3A2 y 3A4. Puede extender este proyecto de ejemplo para admitir PIP de doble acción adicionales.  
  
> [!NOTE]
>  Las asignaciones proporcionadas en la carpeta de ejemplo son ejemplos. Para poder utilizarlos, debes cambiarlos según sus requisitos específicos.  
  
> [!NOTE]
>  Se debe extender este proyecto de ejemplo para admitir PIP únicamente, no de acción única PIP de doble acción. Esta orquestación devolverá un error si ampliarlo para procesar una sola acción PIP. Para asegurarse de que esta orquestación no procesará el PIP de acción única, consulte la siguiente sección de filtrado horizontal mensajes de acción única.  
  
 De forma predeterminada, el Microsoft® [!INCLUDE[BTARN_CurrentVersion_FirstRef](../../includes/btarn-currentversion-firstref-md.md)] programa de instalación instala este ejemplo en \< *unidad*\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction.  
  
 Este proyecto de ejemplo incluye:  
  
- Un procedimiento almacenado (`PipAutomationGetAction)` para recuperar los mensajes de acción nueva para el PIP 0c2, 0c4, 3A2 y 3A4.  
  
- Una ubicación de recepción (MessagesToLOB_Receive_Location) se enlaza al procedimiento almacenado de SQL.  
  
- Una orquestación (DoubleAction.odx) que procesa cada PIP, genera la respuesta adecuada en función de una asignación para cada PIP y guarda la respuesta en la tabla MessagesFromLOB de la base de datos BTARNDATA. La orquestación utiliza la `RNIFSubmit` método desde Microsoft.Solutions.BTARN.Shared.dll para enviar el mensaje.  
  
- Un archivo de enlace (DoubleActionBinding.xml) que usa el archivo Setup.bat para crear el MessagesToLOB_Receive_Port para su uso con la orquestación de DoubleAction.  
  
- Un archivo de instalación para crear e inicializar el ejemplo. Si BizTalk Server se está ejecutando en un equipo de 32 bits, ejecute el archivo setup.bat el \<unidad\>: Acelerador de BizTalk para RosettaNet \SDK\PIPAutomation\DoubleAction carpeta \Program Files\Microsoft. Si BizTalk Server se está ejecutando en un equipo de 64 bits, ejecute setupx64.bat en la misma carpeta.  
  
  La orquestación recibe mensajes mediante el procedimiento PipAutomationGetAction almacenado en la base de datos BTARNData (el archivo de origen es DoubleAction.sql en el directorio de DoubleAction). Este procedimiento almacenado recupera los mensajes de la tabla MessagesToLOB.  
  
  Para extender este proyecto de ejemplo para admitir PIP de doble acción adicionales, agregue una ruta de acceso en la orquestación para el PIP de doble acción. Esta ruta de acceso incluirá un mapa que se va a construir un mensaje de respuesta a un mensaje de solicitud. Por ejemplo, mapas, consulte el [solicitud 3A2 al ejemplo de asignación de respuesta de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md) y [solicitud de 3A4 al ejemplo de asignación de respuesta de 3A4 &#91;RN3&#93;](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md).  
  
### <a name="to-build-and-initialize-this-sample"></a>Para generar e inicializar el ejemplo  
  
1. En un símbolo del sistema, busque el  *\<unidad\>*: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction carpeta.  
  
   > [!NOTE]
   >  Antes de ejecutar el programa de instalación, abra el archivo DoubleAction.sql (en la carpeta anterior) en el Bloc de notas. En el menú **Archivo** , haga clic en **Guardar como**. En el **Encoding** lista, seleccione **ANSI**y, a continuación, haga clic en **guardar**. Seleccione **Sí** para sobrescribir el archivo existente.  
  
2. Si el servidor BizTalk Server se está ejecutando en un equipo de 32 bits, ejecute el archivo setup.bat el \<unidad\>: \Program Files\Microsoft BizTalk Accelerator for RosettaNet\SDK\PIPAutomation\DoubleAction carpeta. Si la instalación de BizTalk Server se está ejecutando en un equipo de 64 bits, ejecute setupx64.bat en la misma carpeta. El archivo por lotes realizará las acciones siguientes:  
  
   - Crea un procedimiento almacenado de SQL (`PipAutomationGetAction`) en la base de datos BTARNDATA para recuperar el mensaje de acción de la tabla MessagesToLOB. Esto también garantiza que los registros recuperados no se leerá a intentarlo.  
  
   - Compila el HeaderHelper [!INCLUDE[btsDotNet](../../includes/btsdotnet-md.md)] del proyecto y registra el ensamblado en la caché global de ensamblados.  
  
   - Crea y enlaza el SQL Server de BizTalk (MessagesToLOB_Receive_Port) del puerto de recepción.  
  
   - Habilita la ubicación de recepción (MessagesToLOB_Receive_Location).  
  
   - Compila e implementa la orquestación PIPAutomation de doble acción (DoubleAction.odx).  
  
   - Enlaza e inicia la orquestación de BizTalk Server.  
  
     > [!NOTE]
     >  El ejemplo muestra algunas advertencias durante la compilación. Puede omitir estas advertencias.  
  
     > [!NOTE]
     >  El ejemplo usa el nombre de host predeterminado **BizTalkServerApplication** al implementar el proyecto. Si desea ejecutar el ejemplo en un host diferente, deberá modificar los nombres de host de forma predeterminada se encuentra en DoubleActionBinding.xml en \<SDK\>\PIPAutomation\DoubleAction carpeta.  
  
### <a name="to-run-the-double-action-pipautomation-sample"></a>Para ejecutar el ejemplo PIPAutomation de doble acción  
  
1. Crear un acuerdo de 3A4 donde el rol principal es un iniciador. Establezca GBI de la organización propia a 123456789 y GBI para el socio comercial a 987654321. Esto le permite usar los ejemplos proporcionados en la carpeta SampleInstances en la carpeta LOBApplication en el SDK.  
  
2. Mediante la utilidad de creación de reflejo de acuerdo de bucle invertido, cree un reflejo para el PIP de 3A4 creado en el paso 1.  
  
3. Mediante la utilidad LOBApplication.exe del SDK, envíe un mensaje de solicitud de PIP de 3A4. El [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] SDK incluye un ejemplo de entrada en la carpeta \< *directorio de instalación*\>\SDK\LOBApplication\SampleInstances\3A4_Request.xml.  
  
4. Ejecute la siguiente consulta en la base de datos BTARNDATA:  
  
   ```  
   Select * from MessagesToLOB  
   ```  
  
5. Transcurridos unos segundos, cuatro nuevos mensajes aparecen en esta tabla. Dos de ellos son las señales de confirmación. Una señal es el mensaje de solicitud de 3A4 Async. Una señal es el mensaje de respuesta de 3A4 asincrónico.  
  
   > [!NOTE]
   >  Para deshacer los cambios realizados por Setup.bat, ejecute Cleanup.bat. Debe ejecutar Cleanup.bat antes de ejecutar Setup.bat de nuevo.  
  
## <a name="remarks"></a>Notas  
 La orquestación pública genera automáticamente las confirmaciones (ACK y NACK mensajes de señal). La aplicación de línea de negocio (LOB) no es necesario generarlos.  
  
 El formato del mensaje que se enruta a la tabla MessagesFromLOB se denomina LOBMessage. El esquema está disponible en C:\Program Files\Microsoft BizTalk Accelerator para RosettaNet\SDK\RNIFSchemas\GlobalSchemas\LOBMessage.xsd. Si usas el `RNIFSubmit` método, es necesario para que funcione con el formato del mensaje. Solo tiene que enviar el ServiceContent con la información adicional. `RNIFSubmit` rellena el registro de la tabla MessagesFromLOB.  
  
## <a name="filtering-out-single-action-messages"></a>Filtrado de mensajes de acción única  
 Esta orquestación debería recibir sólo mensajes de acción doble. No deben ampliar este proyecto de ejemplo para admitir PIP de acción única. BTARN registrará errores si utiliza esta orquestación para procesar los mensajes de acción única. Con el fin de evitar que la orquestación reciba un mensaje de acción única, cambie la línea siguiente en el procedimiento almacenado de PIPAutomationGetAction:  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB  
```  
  
 En la línea anterior, agregue una cláusula WHERE que filtrará los mensajes de acción única. Incluir todos los mensajes de acción única que se van a procesar en la cláusula WHERE. La línea debería ser como sigue:  
  
```  
SELECT PIPInstanceID,DestinationPartyName,SourcePartyName,PIPCode,PIPVersion,ServiceContent FROM MessagesToLOB WHERE PIPCode NOT IN ( '0A1', '3B2', '3C3', '0C1', '0C3' )  
```  
  
## <a name="see-also"></a>Vea también  
 [Solicitud de 3A2 al ejemplo de asignación de respuesta de 3A2](../../adapters-and-accelerators/accelerator-rosettanet/3a2-request-to-3a2-response-map-sample.md)   
 [Solicitud de 3A4 al ejemplo de asignación de respuesta de 3A4](../../adapters-and-accelerators/accelerator-rosettanet/3a4-request-to-3a4-response-map-sample.md)   
 [Ejemplos de orquestación](../../adapters-and-accelerators/accelerator-rosettanet/orchestration-samples.md)