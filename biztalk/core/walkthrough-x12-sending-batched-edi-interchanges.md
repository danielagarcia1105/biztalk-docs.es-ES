---
title: 'Tutorial (X12): Envío de intercambios EDI por lotes | Microsoft Docs'
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: b80ea79b-6112-49bd-90e8-9a0a0e604df8
caps.latest.revision: 54
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25a17a950cf857c21fe9f7d913ba58a5a68c4512
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973221"
---
# <a name="walkthrough-x12-sending-batched-edi-interchanges"></a>Tutorial (X12): Enviar intercambios EDI por lotes
Este tutorial proporciona un conjunto de procedimientos detallados que crea una solución para enviar intercambios EDI por lotes de una entidad a otra mediante [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo de administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] o de operadores B2B de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  

## <a name="how-the-solution-sends-batched-edi-interchanges"></a>Cómo envía la solución intercambios EDI por lotes  
 La solución hará lo siguiente:  

1. La ubicación de recepción recibe un intercambio EDI desde un **entidad A**.  

   > [!NOTE]
   >  Puede que los eventos de esta lista no se produzcan en el orden mostrado.  

2. La canalización de recepción convierte el formato EDI del intercambio en formato XML interno. La canalización de recepción determina que el intercambio se va a realizar por lotes. Como resultado, el componente BatchMarkerReceivePipeline promociona las propiedades `EDI.ToBeBatched==True` y `EDI.BatchId`. Después, coloca el intercambio en el cuadro de mensajes.  

3. La orquestación de procesamiento por lotes recupera el intercambio recibido del cuadro de mensajes, porque se suscribe al mensaje basado en `EDI.ToBeBatched==True` y `EDI.BatchId==%BatchID%`.  

4. La ubicación de recepción recibe un segundo intercambio EDI de la misma entidad que envió el primer intercambio.  

5. La ubicación de recepción procesa el intercambio como en el paso 2 y, a continuación, coloca el intercambio en el cuadro de mensajes.  

6. La orquestación de procesamiento por lotes recupera el intercambio como en el paso 3.  

7. Después de cumplir con los criterios de lanzamiento (que definen cómo deben coincidir los intercambios), la orquestación de procesamiento por lotes ensambla el intercambio que contiene todos los intercambios y luego promociona las propiedades de contexto `EDI.ToBeBatched==False`, `EDI.BatchName` y `EDI.DestinationPartyName`. Coloca el intercambio por lotes en el cuadro de mensajes.  

8. El puerto de envío toma el intercambio por lotes mediante la suscripción a las propiedades de contexto `EDI.ToBeBatched`==False, `EDI.BatchName` y `EDI.DestinationPartyName`.  

9. La canalización de envío aplica propiedades adicionales sobre del intercambio por lotes y, a continuación, envía el intercambio a la entidad de destino, **entidad B**.  

    > [!NOTE]
    >  Para obtener más información, consulte [ensamblar un intercambio de EDI por lotes](../core/assembling-a-batched-edi-interchange.md).  

   La siguiente ilustración muestra la arquitectura de esta solución.  

   ![Envío de intercambios EDI por lotes](../core/media/93a09e3c-476d-4bd2-a0e3-b5b219858791.gif "93a09e3c-476d-4bd2-a0e3-b5b219858791")  

## <a name="the-functionality-in-this-solution"></a>La funcionalidad en esta solución  
 Por lo que respecta a este tutorial, se habilitará la siguiente funcionalidad:  

-   La solución está diseñada para intercambios que utilizan la codificación X12, no la codificación EDIFACT.  

    > [!NOTE]
    >  La configuración que se usa para la codificación EDIFACT e HIPAA es bastante parecida a la que usa la codificación X12.  

-   Las confirmaciones funcionales o técnicas no se devolverán en respuesta al intercambio que se recibió originalmente o a cualquier intercambio por lotes que se enviase.  

    > [!NOTE]
    >  Para obtener información acerca de cómo generar confirmaciones EDI, vea [tutorial (X12): devolución de una confirmación de envío y recepción de intercambios EDI](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md).  

-   Esta solución usa un puerto unidireccional y un puerto de envío unidireccional estático. Estos puertos se configurarán con el tipo de transporte de archivo.  

-   Se habilitarán los informes EDI.  

-   Los conjuntos de transacciones se guardarán para su visualización desde el informe de estado de intercambio.  

## <a name="configuring-and-testing-the-walkthrough"></a>Configuración y prueba del tutorial  
 Los procedimientos necesarios para esta solución son:  

- Agregar los esquemas de mensaje necesarios a un proyecto de BizTalk y, a continuación, genere e implemente el proyecto, de modo que los esquemas estén disponibles para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] los utilice a la hora de procesar los mensajes.  

- Actualizar el intervalo de sondeo del adaptador de SQL en el **BatchControlMessageReccvLoc** ubicación de recepción, para que la orquestación por lotes se activará inmediatamente al hacer clic en el **iniciar** botón a enviar el mensaje de control que activará una instancia de orquestación por lotes.  

- Crear un puerto de recepción para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] reciba los mensajes de EDI entrada .txt con codificación X12 procedentes de una entidad.  

- Cree una entidad (socio comercial) para la Entidad A y la Entidad B.  

- Crear un perfil de negocio para cada uno de los socios comerciales.  

- Crear un acuerdo entre los dos perfiles configurando las propiedades de EDI para que se reciba el mensaje. Configurar las propiedades de EDI para el mensaje por lotes que se debe enviar. Para esta solución, configure los acuerdos de forma que BizTalk Server envíe un lote a la Entidad B siempre que se reciban dos intercambios 850.  

- Crear un puerto de envío para que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] envíe el intercambio EDI por lotes al socio comercial. Este puerto de envío será un puerto de envío unidireccional estático.  

- Asociar el puerto de envío al acuerdo que procesa los intercambios y crea los lotes.  

- Colocar dos intercambios EDI de prueba en la carpeta local asociada a la ubicación de recepción, así como verificar que BizTalk Server haya colocado un intercambio por lotes en la carpeta asociada al puerto de envío.  

### <a name="configuring-the-walkthrough"></a>Configuración del tutorial  
 En esta sección se describen los procedimientos para configurar el tutorial.  

##### <a name="to-deploy-the-message-schema"></a>Para implementar el esquema de mensajes  

1. En [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], cree o abra un proyecto de BizTalk.  

   > [!NOTE]
   >  Este tema presupone que ya ha agregado una referencia de su aplicación a la aplicación EDI de BizTalk, que contiene esquemas, canalizaciones y orquestaciones EDI. Si no, consulte [cómo agregar una referencia a la aplicación EDI de BizTalk Server](http://msdn.microsoft.com/library/7af066fb-372f-4709-b566-c8d6b4a9d782).  

2. Haga clic en el proyecto, elija **agregar**y, a continuación, haga clic en **elemento existente**. Vaya a [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]XSD_Schema\EDI\X12\00401 y, a continuación, haga doble clic en el esquema correspondiente al mensaje de prueba.  

   > [!NOTE]
   >  Si los esquemas EDI no se han descomprimido en las carpetas \XSD_Schema\EDI, ejecute el **MicrosoftEdiXSDTemplates.exe** archivo en la carpeta \XSD_Schema\EDI para descomprimir los esquemas en la carpeta predeterminada.  
   > 
   > [!NOTE]
   >  En el caso de un mensaje de prueba, se puede usar el mensaje de ejemplo 850 usado en el tutorial de programadores de la interfaz EDI. Este archivo es SamplePO.txt en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\. Si lo hace, debe usar el esquema x12_00401_850.xsd ubicado en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.  

3. Defina el archivo de clave de ensamblado y, a continuación, genere e implemente el ensamblado.  

##### <a name="to-update-the-polling-interval"></a>Para actualizar el intervalo de sondeo  

1. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, abra el **grupo de BizTalk**, **aplicaciones**, **aplicación EDI de BizTalk** nodos, y **ubicaciones de recepción**  nodos. En el **ubicaciones de recepción** nodo, haga clic en **BatchControlMessageRecvLoc**y, a continuación, haga clic en **propiedades**.  

2. Para el tipo de transporte SQL, haga clic en **configurar**.  

3. En el **propiedades de transporte SQL** diálogo cuadro, establezca el intervalo de sondeo con un valor menor. Por ejemplo, se puede cambiar **unidad de sondeo de medida** a **segundos**, en lugar de minutos, para cambiar el intervalo de sondeo a 5 segundos.  

   > [!NOTE]
   >  El cambio del intervalo de sondeo garantiza que la orquestación de procesamiento por lotes se active rápidamente.  

4. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  

##### <a name="to-create-a-one-way-receive-port-to-receive-the-edi-messages-to-be-batched"></a>Para crear un puerto de recepción unidireccional para recibir los mensajes EDI que se van a procesar por lotes  

1. Cree una carpeta local para recibir los mensajes EDI que se van a procesar por lotes.  

2. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de recepción** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Unidireccional puerto de recepción.**  

3. Nombre del puerto de recepción y, a continuación, haga clic en **ubicaciones de recepción** en el árbol de consola.  

4. Haga clic en **Nueva**.  

5. Nombre de la ubicación de recepción, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

6. Especifique una carpeta para **carpeta recepción**y una máscara para **máscara de archivo**, tales como  **\*.txt**.  

7. Haga clic en **Aceptar**.  

8. Para **canalización de recepción**, seleccione **EdiReceive**.  

9. Haga clic en **Aceptar**y, a continuación, haga clic en **Aceptar** nuevo.  

10. En el árbol de consola, haga clic en **ubicaciones de recepción**. En el **ubicaciones de recepción** panel, haga clic en la ubicación de recepción y, a continuación, haga clic en **habilitar**.  

##### <a name="to-create-a-party-and-a-business-profile-for-party-a"></a>Para crear una entidad y un perfil de negocio para la Entidad A  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **PartyA_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-a-party-and-a-business-profile-for-party-b"></a>Para crear una entidad y un perfil de negocio para la Entidad B  

1. Haga clic en el **partes** nodo en el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, seleccione **New**y, a continuación, haga clic en **entidad**.  

2. Escriba un nombre para la entidad en el **nombre** cuadro de texto y, a continuación, haga clic en **Aceptar**.  

   > [!NOTE]
   >  Si selecciona el **BizTalk Local procesa mensajes recibidos por el admite las partes o enviar mensajes desde esta entidad** casilla de verificación, puede especificar que la entidad que se va a crear es para la misma organización que también hospeda [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]. En función de ello, algunas propiedades estarán habilitadas o deshabilitadas cuando se crea un acuerdo. Sin embargo, para este tutorial, puede dejar activada esta casilla.  

3. Haga clic en el nombre de la entidad, seleccione **New**y, a continuación, haga clic en **perfil de negocio**.  

4. En el **propiedades de perfil** cuadro de diálogo el **General** , escriba **PartyB_Profile** en el **nombre** cuadro de texto.  

   > [!NOTE]
   >  Cuando se crea una entidad, también se crea un perfil. Puede cambiar el nombre y usar ese perfil en lugar de crear uno nuevo. Para cambiar el nombre de un perfil, haga clic en el perfil y seleccione **propiedades**. En el **General** , especifique un nombre para el perfil.  

##### <a name="to-create-an-agreement-between-the-two-business-profiles"></a>Para crear un acuerdo entre los dos perfiles de negocio  

1. Haga clic en **PartyA_Profile**, apunte a **New**y, a continuación, haga clic en **contrato**.  

2. En el **propiedades generales** página, para el **nombre** texto, escriba un nombre para el acuerdo.  

3. Desde el **protocolo** lista desplegable, seleccione **X12**.  

4. En el **segundo socio** sección, desde el **nombre** lista desplegable, seleccione **PartyB**.  

5. En el **segundo socio** sección, desde el **perfil** lista desplegable, seleccione **PartyB_Profile**.  

    Observará que las dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha es para configurar un acuerdo unidireccional y cada acuerdo unidireccional representa una transacción completa del mensaje (incluida la transferencia del mensaje y la transferencia de la confirmación).  

6. En el **General** ficha la **propiedades generales** página, en el **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **carga de mensaje de Store para el informe**.  

7. Realizar las tareas siguientes en el **entidad a -> PartyB** ficha.  

   1. En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Lo hará coincidir los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado del intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador e identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
      > 
      > [!NOTE]
      >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **THEM**, **ISA7** a **ZZ**, y **ISA8** a **US**.  

   2. En el **validación** página bajo la **configuración de intercambio** sección, asegúrese de que **comprobación de duplicado ISA13** opción está desactivada.  

      > [!NOTE]
      >  Borrar el **comprobación de duplicado ISA13** propiedad le permite recibir varias instancias del mismo mensaje.  

   3. En el **juego de caracteres y separadores** página bajo la **configuración de intercambio** sección, seleccione el **CR LF** opción.  

   4. En el **configuración por lotes** página bajo la **configuración de intercambio** sección, realice lo siguiente:  

      1.  Haga clic en **nuevo lote**.  

      2.  En el **identificación** sección, para **nombre de lote** texto, escriba `Batch1`.  

      3.  En el **filtro** sección, haga clic en el **filtro** botón y en el **filtro por lotes** diálogo cuadro, realice lo siguiente:  

          1.  Haga clic en la celda vacía bajo la **propiedad** columna y seleccione **BTS. ReceivePortName**.  

          2.  Haga clic en la celda vacía bajo la **operador** columna y seleccione **==**.  

          3.  Haga clic en la celda vacía bajo la **valor** columna y escriba el nombre del puerto de recepción que creó anteriormente.  

          4.  Haga clic en **Aceptar**.  

      4.  En el **versión** sección, seleccione el **establece el número máximo de transacciones** opción, en la lista desplegable, seleccione **intercambio**y en el cuadro de texto, escriba el número de intercambios que se procesarán por lotes. En esta solución, se procesará por lotes dos intercambios, por lo tanto, en el cuadro de texto, escriba `2`.  

      5.  En el **activación** sección, seleccione **iniciar inmediatamente**.  

   5. En el **sobres** página bajo la **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  


      |       Use       |                                                                                                                                    Para                                                                                                                                    |
      |----------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
      |     **Default**      |   Seleccione **predeterminado**. **Nota:** al seleccionar esta fila de forma predeterminada, los valores de **GS1**, **GS2**, **GS3**, **GS7**, y  **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el mensaje.    |
      | **Tipo de transacción** |                                                                                                     Seleccione el tipo de mensaje del mensaje de prueba, **850 - Purchase Order**.                                                                                                      |
      | **Versión y lanzamiento**  |                                                                                                                        Especifique la versión EDI, **00401**.                                                                                                                         |
      | **Espacio de nombres de destino** |                                                                                                         Seleccione **<http://schemas.microsoft.com/BizTalk/Edi/X12/2006>**.                                                                                                          |
      |       **GS1**        |                                                                                           Compruebe que está seleccionado el tipo de mensaje del mensaje de prueba, **PO - Purchase Order (850)**.                                                                                           |
      |       **GS2**        |                                                                                                      Escriba un valor para el remitente de aplicación, por ejemplo, **Purchasing**.                                                                                                      |
      |       **GS3**        |                                                                                                    Escriba un valor para el receptor de la aplicación, por ejemplo, **OrderControl**.                                                                                                    |
      |       **GS4**        | Seleccionar el formato de fecha que desee. **Nota:** tiene que seleccionar el valor en la lista desplegable, haga clic en no solo en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente. |
      |       **GS5**        |                                                                                                                      Seleccione el formato de hora que desee.                                                                                                                       |
      |       **GS7**        |                                                                                                                Seleccione **X - Accredited Standards Committee X12**.                                                                                                                |
      |       **GS8**        |                                                                                                             Compruebe que se ha especificado la versión de EDI, **00401**.                                                                                                             |

      > [!NOTE]
      >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] establecerá los valores para GS01, GS02, GS03, GS04, GS05, GS07 y GS08 de las confirmaciones salientes según los valores especificados para **tipo de transacción**, **versión**, y **destino espacio de nombres**. La canalización de envío intenta hacer coincidir el tipo de conjunto de transacciones, la versión X12 y el espacio de nombres de destino con los valores correspondientes del encabezado del mensaje. Si es correcta, usa los valores de GS asociados con el **tipo de transacción**, **versión**, y **espacio de nombres de destino** valores.  

8. Realizar las tareas siguientes en el **PartyB -> entidad a** ficha.  

   > [!NOTE]
   >  En este tutorial, especificamos el valor necesario en la ficha para que se pueda crear un acuerdo correctamente. Para crear correctamente un acuerdo, ambas fichas de acuerdo unidireccional deben tener valores definidos para **ISA5**, **ISA6**, **ISA7**, y **ISA8**.  

   1.  En el **identificadores** página bajo la **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  

       > [!NOTE]
       >  Si está utilizando el archivo SamplePO.txt de "EDI Interface Developer Tutorial" como mensaje de prueba, establecer **ISA5** a **ZZ**, **ISA6** a **US**, **ISA7** a **ZZ**, y **ISA8** a **THEM**.  

9. Haga clic en **Aplicar**.  

10. Haga clic en **Aceptar**. El acuerdo recién agregado aparece en la **acuerdos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  

##### <a name="to-create-a-static-one-way-send-port-to-send-the-batched-edi-interchange"></a>Para crear un puerto de envío estático unidireccional para enviar el intercambio EDI por lotes  

1. Cree una carpeta local a la que enviar el mensaje EDI por lotes.  

2. En [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en el **puertos de envío** nodo bajo el **BizTalk Application 1** nodo, seleccione **New**y, a continuación, haga clic en **Puerto de envío unidireccional estático.**  

3. En el **propiedades de puerto de envío** cuadro de diálogo, nombre el puerto de envío.  

4. En el **transporte** sección, seleccione **archivo** para **tipo**y, a continuación, haga clic en **configurar**.  

5. Especifique una carpeta para **carpeta de destino**y un **nombre de archivo**, tales como **%MessageID%.txt**.  

6. Haga clic en **Aceptar**.  

7. En **canalización de envío**, seleccione **EdiSend**.  

8. En el árbol de consola, seleccione **filtros**. En el **filtros** página, realice lo siguiente:  

   1.  En la primera línea de la cuadrícula, seleccione **EDI. DestinationPartyName** para **propiedad**, **==** para **operador**, el nombre que ha seleccionado para que la entidad enviar el lote para  **Valor**, y **y** para **Agrupar por**.  

   2.  En la segunda línea, seleccione **EDI. ToBeBatched** para **propiedad**, **==** para **operador**, y **False** para  **Valor**, y **y** para **Agrupar por**.  

   3.  En la tercera línea, seleccione **EDI. BatchName** para **propiedad**, **==** para **operador**y el nombre del lote para **valor**.  

9. Haga clic en **Aceptar**.  

10. En el árbol de consola, haga clic en **puertos de envío**. En el **puertos de envío** panel, haga clic en el puerto de envío y, a continuación, haga clic en **iniciar**.  

##### <a name="to-associate-the-send-port-with-the-agreement-created-for-batching"></a>Para asociar el puerto de envío al acuerdo creado para el procesamiento por lotes  

1.  Haga clic en el acuerdo que creó anteriormente y haga clic en **propiedades**.  

2.  En el **las propiedades del acuerdo** cuadro de diálogo el **entidad a -> PartyB** , haga clic **puertos de envío** en el panel izquierdo.  

3.  En el **puertos de envío** página bajo la **configuración de intercambio** sección, asocie el puerto de envío que creó anteriormente. En el **puertos de envío** cuadrícula, en el **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío.  

4.  Haga clic en **Aceptar**.  

### <a name="testing-the-walkthrough"></a>Probar el tutorial  
 Esta sección proporciona información acerca de cómo probar el tutorial.  

##### <a name="to-test-the-walkthrough"></a>Para probar el tutorial  

1. En el Explorador de Windows, abra la carpeta local asociada a la ubicación de recepción y coloque un intercambio EDI de prueba en la carpeta.  

   > [!NOTE]
   >  En el caso de un mensaje de prueba, se puede usar el mensaje de ejemplo 850 usado en el tutorial de programadores de la interfaz EDI. Este archivo es SamplePO.txt en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\\. Si lo hace, debe usar el esquema x12_00401_850.xsd ubicado en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\EDI Interface Developer Tutorial\Inbound_EDI.  

2. Coloque una segunda copia del intercambio EDI de prueba en la carpeta.  

3. Abra la carpeta asociada al puerto de envío para los intercambios y abra el intercambio por lotes. Verifique si el intercambio contiene un conjunto de encabezados ISA y GS, y dos conjuntos de transacciones.  

## <a name="see-also"></a>Vea también  
 [Desarrollar y configurar soluciones EDI de BizTalk Server](../core/developing-and-configuring-biztalk-server-edi-solutions.md)   
 [Configuración de un lote saliente](../core/configuring-an-outgoing-batch.md)   
 [Ensamblar un intercambio EDI por lotes](../core/assembling-a-batched-edi-interchange.md)   
 [Ensamblar un intercambio EDI por lotes](../core/assembling-a-batched-edi-interchange.md)   
 [Tutorial (X12): Recepción de intercambios EDI y devolución de una confirmación](../core/walkthrough-x12--receive-edi-interchanges-and-send-back-an-acknowledgement.md)   
 [Tutorial (X12): Envío de intercambios EDI](../core/walkthrough-x12-sending-edi-interchanges.md)