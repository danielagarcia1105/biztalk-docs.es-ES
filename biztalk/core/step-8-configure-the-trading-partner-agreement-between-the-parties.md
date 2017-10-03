---
title: 'Paso 8: Configurar el acuerdo de socio comercial entre las partes | Documentos de Microsoft'
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 9f532f85-3f09-4b60-b7bb-817ee3c79899
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 25e49bf5dcae7324fa3b68fe5080d094b4a2f603
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="step-8-configure-the-trading-partner-agreement-between-the-parties"></a>Paso 8: Configurar el acuerdo de socio comercial entre las partes
![Paso 8 de 9](../adapters-and-accelerators/wcf-lob-adapter-sdk/media/step-8of9.gif "Step_8of9")  
  
 En este paso, configurará un X12 comerciales de acuerdo con el socio para definir los parámetros para intercambiar X12 mensajes entre los dos socios comerciales, OrderSystem y Fabrikam.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe iniciar sesión como miembro del grupo Administradores de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
### <a name="to-configure-an-agreement"></a>Procedimiento para configurar un acuerdo  
  
1.  Haga clic en **iniciar**, haga clic en **todos los programas**, haga clic en **Microsoft BizTalk Server**y, a continuación, haga clic en **administración de BizTalk Server**.  
  
2.  En el [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] consola de administración, haga clic en **partes** en el árbol de consola y, en la **entidades y perfiles empresariales** página, haga clic en **Fabrikam_Profile**, seleccione **New**y, a continuación, haga clic en **acuerdo**.  
  
3.  En el **propiedades generales** página, para la **nombre** texto cuadro, escriba un nombre para el acuerdo.  
  
4.  Desde el **protocolo** lista desplegable, seleccione **X12**.  
  
5.  En el **segunda entidad** sección, desde el **entidad** lista desplegable, seleccione **OrderSystem**.  
  
6.  En el **segunda entidad** sección, desde el **Business** lista desplegable, seleccione **OrderSystem_Profile**.  
  
     Observará que dos pestañas nuevas se agregan junto a la **General** ficha. Cada ficha es para configurar un acuerdo unidireccional y cada acuerdo unidireccional representa una transacción completa del mensaje (incluida la transferencia del mensaje y la transferencia de la confirmación).  
  
7.  En el **General** ficha la **propiedades generales** página, en la **configuración de Host común** sección, seleccione **activar informes**y, a continuación, Seleccione **almacenar carga de mensaje para informes**.  
  
8.  Realizar las tareas siguientes en el **Fabrikam -> OrderSystem** ficha.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Calificador de remitente (ISA5)**|Seleccione **ZZ - definidos mutuamente**.|  
        |**Identificador de remitente (ISA6)**|Escriba **THEM**.|  
        |**Calificador de receptor (ISA7)**|Seleccione **ZZ - definidos mutuamente**.|  
        |**Identificador de receptor (ISA8)**|Escriba **US**.|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] necesita los campos de identificador y calificador del remitente y del receptor para realizar una resolución de acuerdo. Coincidirá con los valores de **ISA5**, **ISA6**, **ISA7**, y **ISA8** en el encabezado de intercambio con aquellos de las propiedades de un acuerdo. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]también resolverá el acuerdo haciendo coincidir el calificador de remitente y el identificador (sin el calificador de receptor y el identificador). Si [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] no puede resolver el acuerdo, usará las propiedades de acuerdo de reserva.  
  
    2.  En el **confirmaciones** página, en la **configuración de intercambio** sección, haga clic en **997 esperado**. Si se selecciona esta casilla, se solicita a la canalización de recepción que genere una confirmación 997 cuando reciba el intercambio 850.  
  
    3.  En el **validación** página en el **configuración de intercambio** sección, asegúrese de que **número de Control de intercambio (comprobar isa13 duplicados)** opción está desactivada.  
  
        > [!NOTE]
        >  Borrar el **comprobar isa13 duplicados** propiedad le permite recibir varias instancias del mismo mensaje.  
  
    4.  En el **configuración de Host Local** página, en la **configuración de intercambio** sección, desactive **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta**.  
  
        > [!NOTE]
        >  Borrar el **enrutar confirmación** propiedad es necesaria porque esta solución devuelve una confirmación asincrónica a través de otro puerto de envío, en lugar del puerto de recepción de una confirmación sincrónica mediante el puerto de envío asociado con un bidireccional.  
  
    5.  En el **configuración de Host Local** página en el **configuración del conjunto de transacciones** sección, seleccione el espacio de nombres del esquema que se va a utilizar para procesar el intercambio entrante.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Activar la casilla en la columna Predeterminado.|  
        |**Para ST1**|Seleccione **850 - pedido de compra**.|  
        |**GS2**|Escriba **THEM**.|  
        |**Target Namespace**|Seleccione **http://schemas.microsoft.com/BizTalk/EDI/X12/2006**.|  
  
        > [!NOTE]
        >  El establecimiento de las propiedades permite que [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] determine el esquema que se va a utilizar en el procesamiento del intercambio 850 entrante. Si un intercambio tiene los valores de GS02 y ST01 que se escriben en una línea de la cuadrícula, se utilizará el espacio de nombres de destino para la misma línea con el fin de determinar el esquema que se va a utilizar.  
  
9. Realizar las tareas siguientes en el **OrderSystem -> Fabrikam** ficha.  
  
    1.  En el **identificadores** página en el **configuración de intercambio** sección, especifique valores para los campos de calificador e identificador (**ISA5**, **ISA6**, **ISA7**, y **ISA8**) que corresponden a los valores de esos campos de encabezado de mensaje de prueba.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Calificador de remitente (ISA5)**|Seleccione **ZZ - definidos mutuamente**.|  
        |**Identificador de remitente (ISA6)**|Escriba **US**.|  
        |**Calificador de receptor (ISA7)**|Seleccione **ZZ - definidos mutuamente**.|  
        |**Identificador de receptor (ISA8)**|Escriba **THEM**.|  
  
    2.  En el **juego de caracteres y separadores** página, en la **configuración de intercambio** sección, seleccione **CR LF** para el **sufijo** propiedad.  
  
    3.  En el **puertos de envío** página en el **configuración de intercambio** sección, asocie el puerto de envío que van a enviar la confirmación de vuelta a Fabrikam. En el **puertos de envío** cuadrícula, en la **nombre** columna, haga clic en una celda vacía y, en la lista desplegable, seleccione el puerto de envío (**toTHEM_997**) creado para enviar el 997 confirmación a Fabrikam.  
  
    4.  En el **sobres** página en el **configuración del conjunto de transacciones** sección, especifique valores para todas las columnas de la primera línea de la cuadrícula.  
  
        |Use|Para|  
        |--------------|----------------|  
        |**Default**|Seleccione la casilla de la **predeterminado** columna. **Nota:** al seleccionar esta fila como valor predeterminado, los valores de **GS1**, **GS2**, **GS3**, **GS7**y **GS8** se usan incluso si los valores de **tipo de transacción**, **versión**, y **espacio de nombres de destino** no son una coincidencia para el Mensaje.|  
        |**Tipo de transacción**|Seleccione el tipo de mensaje del mensaje de prueba, **850 - pedido de compra**.|  
        |**Versión y lanzamiento**|Especifique la versión EDI, **00401**.|  
        |**Espacio de nombres de destino**|Seleccione **http://schemas.microsoft.com/Edi/X12**.|  
        |**GS1**|Compruebe que **PO - Purchase Order (850)** está seleccionada.|  
        |**GS2**|Escriba **1234567**.<br /><br /> **Identificador de la aplicación remitente.**|  
        |**GS3**|Escriba **0000000**.<br /><br /> **Identificador de la aplicación receptora.**|  
        |**GS4**|Seleccione **SSAAMMDD**. **Nota:** tiene que seleccionar el valor en la lista desplegable, no basta con hacer clic en el campo para mostrar el valor predeterminado. Si hace clic en el campo sin seleccionar el valor de la lista desplegable, el valor no se seleccionará realmente.|  
        |**GS5**|Seleccione **HHMM**.|  
        |**GS7**|Seleccione **X - Accredited Standards Committee X12**.|  
        |**GS8**|Compruebe que **00401** se ha especificado.|  
  
        > [!NOTE]
        >  [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]Para establecer los valores de GS01, GS02, GS03, GS04, GS05, GS07 y GS08 de las confirmaciones salientes basados en los valores especificados para **tipo de transacción**, **versión**, y **destino espacio de nombres**. La canalización de envío intenta hacer coincidir el tipo de conjunto de transacciones, la versión X12 y el espacio de nombres de destino con los valores correspondientes del encabezado del mensaje. Si es correcta, usa los valores de GS asociados a la **tipo de transacción**, **versión**, y **espacio de nombres de destino** valores.  
  
10. Haga clic en **Aplicar**.  
  
11. Haga clic en **Aceptar**. El acuerdo recién agregado se muestra en el **contratos** sección de la **entidades y perfiles empresariales** panel. El acuerdo recién agregado está habilitado de forma predeterminada.  
  
12. Reiniciar el servicio de BizTalk. En la consola de administración de BizTalk Server, en **configuración de plataforma**, haga clic en **instancias de Host**, haga clic en **BizTalkServerApplication**y, a continuación, haga clic en  **Reinicie**.  
  
    > [!NOTE]
    >  El servicio de BizTalk necesita reiniciarse después de que se haya activado o desactivado el informe de estado de EDI para que se aplique el cambio.  
  
## <a name="next-steps"></a>Pasos siguientes  
 Probar la solución EDI tal y como se describe en [paso 9: probar la solución EDI](../core/step-9-test-the-edi-solution.md)  
  
## <a name="see-also"></a>Vea también  
 [Configurar propiedades del acuerdo de codificación](../core/configuring-encoding-agreement-properties.md)