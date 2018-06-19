---
title: Varios problemas2 conocidos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- known issues
ms.assetid: 01cd896f-6c7f-4734-b953-81a92195a5c0
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: af644ead6ecb825d6d6960145958c176946e844c
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207068"
---
# <a name="miscellaneous-known-issues"></a>Varios problemas conocidos
Esta sección contiene información útil sobre varios errores.  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>Duplicar errores registrados para el mismo segmento de mensaje, la secuencia y el número de campo  
 Si hay errores en los componentes de un campo de tipos de datos complejos, [!INCLUDE[btsCoName](../../includes/btsconame-md.md)] Acelerador de BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) notificará un error para cada error de ese tipo. El identificador de segmento y el número de campo serán idéntico. El número de error y la descripción pueden ser diferentes porque el error HL7 mecanismo de notificación no admite la notificación de errores en el nivel de componente y del subcomponente.  
  
## <a name="segment-sequence-errors"></a>Errores de secuencia de segmento  
 Si faltan segmentos de mensaje necesarios [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] informa de un mensaje "Error en la secuencia (fin inesperado del cuerpo de mensaje que se encuentra) de segmento" en el último segmento correcto analizado por el motor.  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>Se puede grabar error no válido cuando el campo de encabezado de MSH3 es estructuralmente incorrecto  
 Si un campo de encabezado de MSH3 es estructuralmente incorrecto, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador no puede copiar el contenido del campo MSH3 en el encabezado de MSH5 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se puede enviar una confirmación (ACK). Esto puede indicar que el problema se debía con el campo MSH5, no en el campo MSH3.  
  
## <a name="access-database-errors"></a>Errores de base de datos de Access  
 Las bases de datos de Access HL7 incluye los siguientes errores:  
  
-   27 de campo del segmento OBR en la base de datos de HL7 V2.3 acceso incorrectamente se marcó como no repetibles y necesarias. Se ha producido un cambio en este [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] campo de esquemas a los valores correctos de repetible y opcionales.  
  
-   Campo 2 del segmento OBX en la base de datos se ha marcado incorrectamente como HL7 el acceso de V2.3 necesario y campo 10 del segmento OBX en la base de datos de HL7 V2.3 acceso incorrectamente se marcó como no repetibles. En el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] esquemas, campo 2 se marca como opcional y se marca como repeatable campo 10.  
  
-   Se requiere el 4 de campo del segmento OBX en el acceso de V2.3.1 HL7 incorrectamente marcada como base de datos. Este campo en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] esquemas se marca correctamente como opcionales.  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>Cuenta de servicio de registro no puede tener acceso a bases de datos que no se crean mediante el programa de instalación  
 Al configurar el almacén de registro para que señale a una base de datos recién creada, el programa de instalación no ha creado, la nueva base de datos no puede tener la cuenta de servicio de registro enumerada para access. Asegúrese de que la cuenta de servicio de registro tiene acceso a todas las bases de datos de registro recién creados.  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>No se permite en tipos de datos NM y SI de espacios iniciales  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]instancias de los tipos de datos NM y SI tienen los espacios iniciales y finales se rechaza.  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 acepta un valor de "0" para el tipo de datos de HL7 V2.1 SI  
 En el estándar HL7 para HL7 V2.1, no es aceptable en una instancia del tipo de datos SI un valor de "0". Sin embargo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acepta "0" como un valor válido en una instancia del tipo de datos SI.  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>Error de coincidencia de espacios de nombres de entidad de origen y destino  
 Si el espacio de nombres configurado en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración en el **validación** ficha no coincide con el espacio de nombres de origen en el esquema para un V2 HL7. X mensaje, el serializador puede generar mensajes de error que no se identifique claramente el problema. Estos mensajes de error pudieron indicar que se encuentra errores de secuencia de segmento o un fin inesperado del cuerpo del mensaje. Si no se pueda explicar la causa de un error, podría comprobar un error de coincidencia del espacio de nombres de entidad.  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>Falta de segmentos FT o BTS da lugar a errores, pero el mensaje todavía analiza  
 Cuando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Desensamblador analiza un mensaje por lotes que contiene los segmentos FHS o BHS, pero no contiene el correspondiente segmento FT o BTS, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera un error, pero todavía analiza el mensaje.  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>Modificar un resultados de etiqueta de encabezado de mensaje en varios errores  
 Si el Diseñador de orquestaciones se modifica una etiqueta de encabezado de mensaje, puede ver errores que no son comprensibles, como "primer segmento de no válido" o "error de secuencia de segmento".  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>Datos de configuración pueden verse afectados por otras aplicaciones de BizTalk Server  
 Si escribe los datos personalizados en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] configuración del explorador o configuración de conjunto de datos mediante programación a través de la configuración de programación Interfaces de aplicaciones (API), los datos personalizados se almacenan en la base de datos de configuración.  Puede usar la base de datos de configuración de otra información específica de la entidad de otras aplicaciones de BizTalk. Si otra aplicación almacena los datos en la misma ubicación que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] datos de configuración, la [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] datos no se almacenan correctamente. Si esto ocurre, cambiar la ubicación de almacenamiento de datos de la otra aplicación y guarde el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] datos de configuración de nuevo.  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>No se pueden registrar errores en el registro de errores debido a una limitación de tamaño del almacén del registro de eventos  
 Cuando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador genera un número significativo de errores, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no es posible que registre algunos de los errores, debido a una limitación de tamaño del almacén del registro de eventos. Puede ver todos los errores en la herramienta de mantenimiento y seguimiento de actividad (HAT), pero es posible que no pueda ver todas ellas en el registro de errores.  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>Volver a instalar BTAHL7 en una carpeta diferente se causa el valor predeterminado ubicaciones de recepción no se comporte  
 Volver a instalar BTAHL7 en una carpeta diferente hará que la ubicación predeterminada de BatchControlPort o puertos creados por iniciar Tutorial no funcionará porque el URI (según lo dispuesto en la instalación anterior) para estos puertos no coincide con las nuevas carpetas creadas por el programa de instalación. Para que estos puertos para que funcione, tendrá que actualizar la ruta de acceso de carpeta en el cuadro de diálogo Propiedades de transporte de archivo para estos puertos.  
  
 Si uno o varios puertos MLLP existen en BizTalk al desinstalar BTAHL7, no se quitará el adaptador MLLP. Después de que se produzca, si se instala el producto en una ubicación diferente, todos los puertos MLLP nuevos o antiguos dejará de funcionar. Para que MLLP para que funcione, tendrá que desinstalar y reinstalar el adaptador MLLP. Para obtener más información, vea "no se quita el adaptador MLLP durante la desinstalación" en [solución de problemas de otros](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md).  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)