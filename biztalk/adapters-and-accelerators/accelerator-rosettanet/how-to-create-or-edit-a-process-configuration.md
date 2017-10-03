---
title: "Cómo crear o editar una configuración de procesos | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- process configuration, modifying
- process configuration, creating
- authorization properties
- non-repudiation, properties
- creating, process configuration
- modifying, process configuration
ms.assetid: ef6160f1-f2f0-42ff-a516-7818c9d79d26
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: e4c9c9be5e9f3361683e495febbd98a05156399d
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-create-or-edit-a-process-configuration"></a>Cómo crear o editar una configuración de procesos
En este tema se describe cómo crear o editar una configuración de procesos.  
  
 En la siguiente tabla se muestran las opciones de configuración de procesos, organizadas por pestaña. Los procedimientos para crear y editar una configuración de procesos aparecen después de la tabla.  
  
 Las propiedades de autorización y sin repudio son interdependientes. Para obtener más información acerca de cómo establecer estas propiedades, vea [autorización y sin repudio propiedades](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md).  
  
|Pestaña|Configuración|Uso|  
|---------|-------------|-----------|  
|**General**|**Mostrar el código**|Código para mostrar del Proceso de interfaz de socio (PIP). Puede ser la designación de PIP de RosettaNet o el nombre de un esquema personalizado. Se recomienda usar una convención de nomenclatura estándar, como un nombre que incluya el código de proceso y la versión, por ejemplo, "STD_3A2_R02.00.00A". Así resultará más fácil mantener las distintas versiones del mismo PIP.<br /><br /> Campo obligatorio.|  
|**General**|**Código de proceso**|Código PIP de tres dígitos. Por ejemplo, "3A2".<br /><br /> Campo obligatorio.|  
|**General**|**Versión**|Versión del PIP. Por ejemplo, "V02.02" o "R02.00.00A".<br /><br /> Campo obligatorio.|  
|**General**|**Nombre de proceso**|Nombre del PIP. Por ejemplo, "Precio y acción de solicitud de disponibilidad".<br /><br /> Campo obligatorio.|  
|**General**|**Description**|Descripción de los mensajes que cumplen el PIP.|  
|**General**|**Standard**|Tipo de estándar.<br /><br /> Valores posibles: RosettaNet (valor predeterminado) o CIDX.|  
|**General**<br /><br /> (Área de contenido que no es de RosettaNet)|**Mensaje estándar**|Para contenido que no es de RosettaNet, se trata del nombre del estándar que no es de RosettaNet. Use esta opción si no usa un PIP de RosettaNet, pero definió un esquema personalizado. Use esta opción solo para RNIF 2.0, no para RNIF 1.1 o CIDX.|  
|**General**<br /><br /> (Área de contenido que no es de RosettaNet)|**Versión estándar**|Para contenido que no es de RosettaNet, se trata de la versión del estándar que no es de RosettaNet. Use esta opción si no usa un PIP de RosettaNet, pero definió un esquema personalizado. Use esta opción solo para RNIF 2.0, no para RNIF 1.1 o CIDX.|  
|**General**<br /><br /> (Área de contenido que no es de RosettaNet)|**Id. de enlace de carga**|Para contenido que no es de RosettaNet, se trata del número de identificación del contenido de carga. Use esta opción si no usa un PIP de RosettaNet, pero definió un esquema personalizado. La parte que implementa el PIP personalizado debe definir este valor. Use esta opción solo para RNIF 2.0, no para RNIF 1.1 o CIDX.|  
|**Actividad**<br /><br /> (Área Confirmación de recepción)|**Sin repudio necesario**|Determina si los mensajes de señal deben firmarse (con una síntesis del mensaje incluida en el mensaje de confirmación) y se almacena en su forma original por la entidad de destino de la tabla MessageStorageIn o MessageStorageOut de la [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]base de datos de archivo para fines sin repudio. La parte receptora debe almacenar las señales durante el período designado en la propiedad **Sin repudio del origen** en la configuración del socio comercial.<br /><br /> Los valores posibles: `True` (valor predeterminado) o`False`<br /><br /> Si es `False`, los mensajes de señal no se almacenarán para fines sin repudio. Los mensajes de señal pueden estar firmados o no.<br /><br /> Si es `True`, los mensajes de señal entrantes se almacenarán en su forma original en la tabla MessageStorageIn. Los mensajes de señal salientes se almacenarán en su forma original en la tabla MessageStorageOut. Los mensajes de señal deben estar firmados.<br /><br /> Para obtener más información, consulte [autorización y sin repudio propiedades](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md).|  
|**Actividad**<br /><br /> (Área Confirmación de recepción)|**Tiempo de confirmación (segundos)**|Tiempo, en segundos, en el que el iniciador debe recibir la confirmación. Si el iniciador no la recibe transcurrido este tiempo, volverá a intentarlo si los reintentos no superaron el número indicado en **Reintento** (en la sección **Comportamiento** de esta pestaña).<br /><br /> [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]las medidas el **tiempo de confirmación** valor desde el momento en que el iniciador enviado correctamente el mensaje de acción. El valor se incluye en el encabezado de entrega. El valor no puede ser menor que cero o mayor que el valor de **Tiempo de ejecución** establecido en la misma página.<br /><br /> Esta configuración se usa para los mensajes de señal (confirmaciones de aplicación) que se devuelven en el procesamiento de RNIF 1.1 y 2.01. Esta configuración también se puede usar para las confirmaciones de aceptación que se devuelven en el procesamiento de RNIF 1.1.<br /><br /> El valor predeterminado es 7200 segundos (dos horas).|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Se necesita autorización**|Determina si los mensajes entrantes de acción o señal deben estar firmados. [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)]no aceptará un documento empresarial si el usuario o el rol no está autorizado para realizar la actividad.<br /><br /> Los valores posibles: `True` (valor predeterminado) o`False`<br /><br /> Si es `False`, los mensajes salientes de acción y señal no estarán firmados. Los mensajes entrantes de acción y señal pueden estar firmados. Si no están firmados, el sistema autorizará al socio comercial que use el encabezado de entrega.<br /><br /> Si es `True`, los mensajes entrantes deben estar firmados. Los mensajes salientes pueden estar firmados. Los mensajes salientes están firmados solo si el valor de **Sin repudio del origen y del contenido** está establecido en `True`.<br /><br /> Para obtener más información, consulte [autorización y sin repudio propiedades](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md).|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Es necesita confidencialidad persistente**|Determina si el cifrado es obligatorio.<br /><br /> Valores posibles: **Ninguno** (valor predeterminado) indica que el cifrado no es necesario. **Carga** indica que es necesario el cifrado del contenido del servicio y los datos adjuntos. **Contenedor de carga** indica que es necesario el cifrado del contenido del servicio, los datos adjuntos y el encabezado de servicio.<br /><br /> En RNIF 2.0, nunca se cifran el preámbulo y el encabezado de entrega. En RNIF 1.1, no se cifran las partes del mensaje. Únicamente se firman.|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Es necesario el transporte seguro**|Determina si se necesita el transporte HTTPS.<br /><br /> Los valores posibles: `True` (valor predeterminado) o`False`|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Es la única acción**|Determina si los mensajes son de una sola acción o de acción doble.<br /><br /> Los valores posibles: `True` (valor predeterminado) o`False`<br /><br /> Los mensajes de una sola acción son Distribución de información o Notificación. Los mensajes de acción doble son Transacción empresarial, Confirmación de solicitud, Solicitud/Respuesta o Consulta/Respuesta.<br /><br /> Si el estándar es CIDX, **Es de una sola acción** debe ser **True**.|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Es sincrónico**|Determina si los socios comerciales intercambiarán mensajes de acción sincrónica o asincrónicamente.<br /><br /> Valoes posibles: `True` o `False`(valor predeterminado).<br /><br /> No se usa para RNIF 1.1.|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Sin repudio del origen y del contenido**|Determina si la parte receptora debe firmar y almacenar los mensajes de acción en la forma en que se reciben originalmente en la tabla MessageStorageIn o MessageStorageOut de la base de datos de archivo de BTARN para fines sin repudio. La parte receptora debe almacenar los mensajes de acción durante el período designado en la propiedad **Sin repudio del origen** en la configuración del socio comercial para fines sin repudio. Si es necesario, los mensajes de acción deben estar firmados.<br /><br /> Los valores posibles: `True` (valor predeterminado) o`False`<br /><br /> Si es `False`, los mensajes de acción no se almacenarán para fines sin repudio. Los mensajes de acción pueden estar firmados o no.<br /><br /> Si es `True`, los mensajes de acción entrantes se almacenarán en su forma original en la tabla MessageStorageIn. Los mensajes de acción salientes se almacenarán en su forma original en la tabla MessageStorageOut. Los mensajes de acción deben estar firmados.<br /><br /> Para obtener más información, consulte [autorización y sin repudio propiedades](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md).|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Número de reintentos**|Número de veces que el proceso debe reintentar la actividad si se produce un error en el transporte o el procesamiento. Si el número de reintentos es 3, el proceso intentará la actividad cuatro veces.<br /><br /> El valor predeterminado es 3.<br /><br /> Si la comunicación es sincrónica, [!INCLUDE[btaBTARN3.3abbrevnonumber](../../includes/btabtarn3-3abbrevnonumber-md.md)] no utiliza este campo, porque los reintentos no se aplican en transacciones sincrónicas.|  
|**Actividad**<br /><br /> (Área Comportamiento)|**Tiempo para realizar**|Período (en segundos) en el que el proceso debe completar la actividad. El período comienza cuando el iniciador envía el primer documento. El iniciador (no el respondedor) debe asegurarse de que la actividad se completa en este período. Este valor se encuentra en el encabezado de entrega.<br /><br /> El valor predeterminado es de 86400 segundos (24 horas).<br /><br /> El valor de **Tiempo de ejecución** debe ser mayor que el valor de **Tiempo de confirmación** establecido en la sección **Confirmación de recepción** de la misma página.|  
|**Actividad**<br /><br /> (Área General)|**Tipo**|Determina el tipo de la actividad.<br /><br /> Valores posibles: **Transacción empresarial**, **Distribución de información** (valor predeterminado), **Notificación**, **Consulta/Respuesta**, **Solicitud/Confirmación**o **Solicitud/Respuesta**|  
|**Iniciador**<br /><br /> (Área Documento empresarial)|**Description**|Descripción del documento empresarial de la acción del iniciador.|  
|**Iniciador**<br /><br /> (Área Documento empresarial)|**Nombre**|Nombre del documento empresarial de la acción del iniciador. Por ejemplo, "Precio y solicitud de disponibilidad".|  
|**Iniciador**<br /><br /> (Área Documento empresarial)|**Versión**|Versión del documento empresarial. Por ejemplo, "V02_02_00" o "R02.00.00A".<br /><br /> Puede encontrar este número de versión al principio del archivo .htm Directrices de los mensajes XML de RosettaNet que se descarga con el archivo .doc de especificación de PIP y la DTD de PIP de la organización RosettaNet.|  
|**Iniciador**<br /><br /> (Área General)|**Acción**|Descripción de la acción del iniciador. Por ejemplo, "Acción de consulta sincrónica de prueba".|  
|**Iniciador**<br /><br /> (Área General)|**Rol**|Rol del iniciador. Por ejemplo, "Comprador" o "Pagador".<br /><br /> El valor predeterminado es "Iniciador".|  
|**Iniciador**<br /><br /> (Área General)|**Descripción de la función**|Descripción del rol del iniciador. Por ejemplo, "Entidad emisora del pago".|  
|**Iniciador**<br /><br /> (Área General)|**Tipo de rol**|Tipo de rol del iniciador.<br /><br /> Valores posibles: **Organizativo**, **Empleado**o **Funcional** (valor predeterminado).|  
|**Iniciador**<br /><br /> (Área General)|**ssNoVersion**|Servicio iniciador. Por ejemplo, "Servicio comprador" o "Servicio pagador".|  
|**Iniciador**<br /><br /> (Área General)|**Clasificación de servicio**|Tipo de servicio iniciador. Por ejemplo, "Servicio empresarial".|  
|**Servicio de respuesta**<br /><br /> (Área Documento empresarial)|**Description**|Descripción del documento empresarial de la acción del respondedor. Por ejemplo, "Confirma formalmente el estado de los elementos de línea de un pedido".|  
|**Servicio de respuesta**<br /><br /> (Área Documento empresarial)|**Nombre**|Nombre del documento empresarial de la acción del respondedor. Por ejemplo, "Confirmación de pedido".|  
|**Servicio de respuesta**<br /><br /> (Área Documento empresarial)|**Versión**|Versión del documento empresarial. Por ejemplo, "V02.02.00" o "R02.00.00A". Puede encontrar este número de versión al principio del archivo .htm Directrices de los mensajes XML de RosettaNet que se descarga con el archivo .doc de especificación de PIP y la DTD de PIP de la organización RosettaNet.|  
|**Servicio de respuesta**<br /><br /> (Área General)|**Acción**|Descripción de la acción del respondedor. Por ejemplo, "Acción de confirmación de pedido".|  
|**Servicio de respuesta**<br /><br /> (Área General)|**Rol**|Rol del respondedor. Por ejemplo, "Vendedor".<br /><br /> El valor predeterminado es "Respondedor".|  
|**Servicio de respuesta**<br /><br /> (Área General)|**Descripción de la función**|Descripción del rol del respondedor. Por ejemplo, "Entidad receptora del pago".|  
|**Servicio de respuesta**<br /><br /> (Área General)|**Tipo de rol**|Tipo de rol del respondedor.<br /><br /> Valores posibles: **Organizativo** (valor predeterminado), **Empleado**o **Funcional**.|  
|**Servicio de respuesta**<br /><br /> (Área General)|**ssNoVersion**|Servicio del respondedor. Por ejemplo, "Servicio vendedor".|  
|**Servicio de respuesta**<br /><br /> (Área General)|**Clasificación de servicio**|Tipo de servicio del respondedor. Por ejemplo, "Servicio empresarial".|  
  
### <a name="to-implement-a-new-process-configuration"></a>Para implementar una nueva configuración de procesos  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic con el botón derecho en **Opciones de configuración de procesos**, seleccione **Nuevo**y haga clic en **Configuración de procesos**.  
  
4.  En el cuadro de diálogo Propiedades de configuración de proceso nuevo, en las pestañas **General**, **Actividad**, **Iniciador**y **Respondedor** , escriba los valores de las opciones indicadas en la tabla anterior y, a continuación, haga clic en **Aceptar**.  
  
### <a name="to-edit-a-process-configuration"></a>Para editar una configuración de procesos  
  
1.  Haga clic en **iniciar**, seleccione **todos los programas**, seleccione **Microsoft** [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)]y, a continuación, haga clic en [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)] **consola de administración de**.  
  
2.  En la consola de administración de BTARN, expanda [!INCLUDE[btaBTARNNoVersionui](../../includes/btabtarnnoversionui-md.md)].  
  
3.  Haga clic en **Opciones de configuración de procesos**.  
  
4.  Haga clic con el botón derecho en la configuración de procesos que desea editar y, a continuación, haga clic en **Propiedades**.  
  
5.  En el  *\<configuración del proceso >* cuadro de diálogo de propiedades de la **General** y **póngase en contacto con propiedades** pestañas, cambiar la configuración según sea necesario. Para obtener información acerca de estas opciones de configuración, consulte la tabla anterior.  
  
6.  Haga clic en **Aceptar**.  
  
## <a name="see-also"></a>Vea también  
 [Mediante la especificación de PIP para crear una configuración de procesos](../../adapters-and-accelerators/accelerator-rosettanet/using-the-pip-specification-to-create-a-process-configuration.md)   
 [Propiedades de autorización y sin repudio](../../adapters-and-accelerators/accelerator-rosettanet/authorization-and-non-repudiation-properties.md)   
 [Normas europeas de configuración seguridad CIDX intercambio de mensajes](../../adapters-and-accelerators/accelerator-rosettanet/setting-up-cidx-estandards-message-exchange.md)   
 [Administrar la configuración de BTARN](../../adapters-and-accelerators/accelerator-rosettanet/administering-the-btarn-configuration.md)