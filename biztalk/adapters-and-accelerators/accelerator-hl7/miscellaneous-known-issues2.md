---
title: Varios problemas2 conocidos | Microsoft Docs
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
ms.openlocfilehash: 7d0e845a6a178b66d2a817414666455eb20b5bb4
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007861"
---
# <a name="miscellaneous-known-issues"></a>Problemas conocidos varios
Esta sección contiene información útil sobre varios errores.  
  
## <a name="duplicate-errors-logged-for-the-same-message-segment-sequence-and-field-number"></a>Duplicar los errores registrados para el mismo segmento de mensaje, la secuencia y el número de campo  
 Si hay errores en los componentes de un campo de datos complejos tipos de Acelerador de Microsoft BizTalk para HL7 ([!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]) notificará un error para cada error de ese tipo. El identificador de segmento y el número de campo serán idéntico. El número de error y la descripción pueden ser diferentes porque el error HL7 mecanismo de notificación no admite informes de errores en el nivel de componente y del subcomponente.  
  
## <a name="segment-sequence-errors"></a>Errores de secuencia de segmento  
 Si es necesario el mensaje faltan los segmentos, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] informa de un mensaje "Error en la secuencia (fin inesperado del cuerpo del mensaje se encuentra) de segmento" en el último segmento correcto por el motor puede analizado.  
  
## <a name="invalid-error-can-be-recorded-when-the-msh3-header-field-is-structurally-incorrect"></a>Se puede grabar error no válido cuando el campo de encabezado MSH3 es estructuralmente incorrecto  
 Si un campo de encabezado MSH3 es estructuralmente incorrecto, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador no puede copiar el contenido del campo MSH3 en el encabezado de MSH5 y [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] no se puede enviar una confirmación (ACK). Esto puede indicar que el problema era con el campo MSH5, no en el campo MSH3.  
  
## <a name="access-database-errors"></a>Errores de base de datos de Access  
 Las bases de datos de acceso de HL7 contenían los errores siguientes:  
  
- 27 de campo del segmento OBR en la base de datos de HL7 V2.3 acceso incorrectamente se marcó como no repetibles y necesarias. Se ha producido un cambio en este [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] campo esquemas a los valores correctos de repetible y opcionales.  
  
- Field 2 del segmento en la base de datos se ha marcado incorrectamente como el HL7 V2.3 acceso OBX necesarios y campo 10 del segmento en la base de datos de acceso de HL7 V2.3 OBX se ha marcado incorrectamente como no repetibles. En el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] esquemas, campo 2 está marcado como opcional y campo 10 está marcado como repetible.  
  
- Field 4 del segmento OBX en la base de datos se ha marcado incorrectamente como el HL7 V2.3.1 acceso requerido. Este campo en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] esquemas está marcada correctamente como opcionales.  
  
## <a name="logging-service-account-may-not-have-access-to-databases-that-are-not-created-by-the-setup-program"></a>Cuenta de servicio de registro no puede tener acceso a bases de datos que no se crean mediante el programa de instalación  
 Al configurar el almacén de registro para que apunte a una base de datos recién creada, que no ha creado el programa de instalación, la nueva base de datos que no tenga enumerada para el acceso a la cuenta de servicio de registro. Asegúrese de que la cuenta de servicio de registro tiene acceso a todas las bases de datos de registro recién creados.  
  
## <a name="leading-spaces-not-allowed-in-nm-and-si-data-types"></a>Los espacios que no se permite en NM y SI los tipos de datos iniciales  
 [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] rechaza las instancias de los tipos de datos NM y SI tienen espacios iniciales y finales.  
  
## <a name="btahl7-accepts-a-value-of-0-for-hl7-v21-si-data-type"></a>BTAHL7 acepta un valor de "0" para el tipo de datos de HL7 V2.1 SI  
 En el estándar HL7 para HL7 V2.1, no es aceptable en una instancia del tipo de datos SI un valor de "0". Sin embargo, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] acepta "0" como un valor válido en una instancia del tipo de datos SI.  
  
## <a name="mismatch-of-source-and-destination-party-namespaces"></a>Error de coincidencia de espacios de nombres de entidad de origen y destino  
 Si configura el espacio de nombres en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración en el **validación** ficha no coincide con el espacio de nombres de origen en el esquema para un V2 HL7. X mensaje, el serializador puede generar mensajes de error que no identifique claramente el problema. Los mensajes de error podrían indicar que se encuentra errores de secuencia de segmento o un final inesperado del cuerpo del mensaje. Si no se pueda explicar la causa del error, es posible que busque una falta de coincidencia del espacio de nombres de entidad.  
  
## <a name="lack-of-segments-fts-or-bts-results-in-error-but-the-message-still-parses"></a>Falta de segmentos FTS o BTS produce error, pero el mensaje todavía analiza  
 Cuando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Desensamblador analiza un mensaje por lotes que contiene los segmentos FHS o BHS, pero no tiene la correspondiente segmentar FTS o BTS, [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] genera un error, pero todavía analiza el mensaje.  
  
## <a name="modifying-a-message-header-tag-results-in-multiple-errors"></a>Modificación de un mensaje encabezado etiqueta da como resultado varios errores  
 Si el Diseñador de orquestaciones se modifica una etiqueta de encabezado de mensaje, es posible que vea errores que no son comprensibles, como "primer segmento no válido" o "error de secuencia de segmento".  
  
## <a name="configuration-data-can-be-affected-by-other-biztalk-server-applications"></a>Datos de configuración pueden verse afectados por otras aplicaciones de BizTalk Server  
 Si escribe los datos personalizados en el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] Explorador de configuración o la configuración del conjunto de datos mediante programación a través de la configuración de aplicación Interfaces de programación (API), los datos personalizados se almacenan en la base de datos de configuración.  Puede usar la base de datos de configuración para otra información específica de la entidad desde otras aplicaciones de BizTalk. Si otra aplicación almacena datos en la misma ubicación que el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] datos de configuración, el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] datos no se pueden almacenar correctamente. Si esto ocurre, cambie la ubicación de almacenamiento de datos de la otra aplicación y guarde el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] nuevamente los datos de configuración.  
  
## <a name="errors-might-not-be-logged-in-the-error-log-due-to-a-size-limitation-of-the-event-log-store"></a>No se podrían registrar errores en el registro de errores debido a una limitación de tamaño del almacén del registro de eventos  
 Cuando el [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] serializador genera un número significativo de errores, [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] no es posible que registre algunos de los errores, debido a una limitación de tamaño del almacén del registro de eventos. Puede ver todos los errores en la herramienta de mantenimiento y seguimiento de actividad (HAT), pero no es posible que pueda ver todos ellos en el registro de errores.  
  
## <a name="reinstalling-btahl7-under-a-different-folder-will-cause-the-default-receive-locations-not-to-work"></a>Reinstalación de BTAHL7 en una carpeta diferente se causa el valor predeterminado las ubicaciones de recepción no funcione  
 Reinstalación de BTAHL7 en una carpeta diferente hará que la ubicación predeterminada de BatchControlPort o los puertos creados por el Tutorial de inicio no funcione porque el URI (según lo dispuesto en la instalación anterior) para estos puertos no coincidirán con las nuevas carpetas creadas por el programa de instalación. Para que estos puertos para que funcione, deberá actualizar la ruta de acceso de carpeta en el cuadro de diálogo Propiedades de transporte de archivo para estos puertos.  
  
 Si uno o varios puertos MLLP existen en BizTalk al desinstalar BTAHL7, no se quitará el adaptador de MLLP. Una vez que se produce, si instala el producto en una ubicación diferente, todos los puertos MLLP nueva o antiguos dejará de funcionar. Para que MLLP funcione, tendrá que desinstalar y reinstalar el adaptador de MLLP. Para obtener más información, vea "no se quita el adaptador MLLP durante la desinstalación" en [solucionar otros problemas](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-other-issues.md).  
  
## <a name="see-also"></a>Vea también  
 [Problemas conocidos](../../adapters-and-accelerators/accelerator-hl7/known-issues1.md)