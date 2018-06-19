---
title: Solución de problemas de errores | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- errors, troubleshooting
- troubleshooting, errors
ms.assetid: 08cc95a3-4be9-450f-a015-e031011158f7
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ae7ad99b699da29d4d8680375f88e4d4a74ff66a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22207172"
---
# <a name="troubleshooting-errors"></a>Solución de problemas de errores
Esta sección trata sobre los problemas relacionados con [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] generado errores.  
  
## <a name="the-mllp-adapter-can-run-only-on-a-single-host-instance"></a>El adaptador MLLP sólo puede ejecutarse en una instancia de host  
  
### <a name="symptom"></a>Síntoma  
 No se puede habilitar una ubicación de recepción con un tipo de transporte de MLLP y un controlador de recepción diferente a otra ubicación de recepción existente. Además, no se puede dar de alta e iniciar un puerto de envío con un controlador de envío diferente de puerto de envío existente de otro.  
  
**Causa posible** : sólo se puede utilizar una MLLP recepción (o envío) controlador en un único servidor. Además, designa el URI de la ubicación de recepción (o el puerto de envío) (el nombre de Host en las propiedades de transporte de MLLP) debe ser "localhost" o el nombre del servidor donde la instancia del host para el controlador de adaptador (envío o recepción) se está ejecutando.  
  
**Resolución** : designar el mismo controlador de recepción (o envío) de MLLP todas las ubicaciones de recepción (o puertos de envío) en un único servidor.  
  
## <a name="msh-and-ack-schemas-must-be-added-to-only-one-project"></a>Esquemas de confirmación y MSH deben agregarse a un solo proyecto  
  
### <a name="symptom"></a>Síntoma  
 Al intentar compilar un proyecto, obtendrá uno de los siguientes errores:  
  
`Error: Cannot locate document specification as multiple schemas match the message type "http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF"`
  
`Schema http://microsoft.com/HealthCare/HL7/2X#MSH_24_GLO_DEF not found`
  
**Causa posible** : esquemas de confirmación y el MSH (MSH_25_GLO_DEF.xsd y ACK_24_GLO_DEF.xsd) se han implementado en varios proyectos.  
  
**Resolución** : asegúrese de que se han agregado a un solo proyecto MSH_25_GLO_DEF.xsd y ACK_24_GLO_DEF.xsd.  
  
## <a name="exception-of-type-systemoutofmemoryexception-has-thrown-an-error-in-the-event-log"></a>Excepción de tipo System.OutOfMemoryException produce un error en el registro de eventos  
  
### <a name="symptom"></a>Síntoma  
 Obtiene el error siguiente o uno similar en el registro de eventos:  
  
`Exception of type System.OutOfMemoryException has thrown an error.`
  
**Causa posible** : al procesar un gran número de mensajes, algunos [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] componentes del motor pueden producir pérdidas de memoria.  
  
**Resolución** : reinicie [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
## <a name="header-serialization-generates-an-error-in-the-event-viewer"></a>Serialización de encabezado, genera un error en el Visor de eventos  
  
### <a name="symptom"></a>Síntoma  
 Obtendrá el error siguiente o uno similar en el registro de eventos, aunque el mensaje en la herramienta de mantenimiento y seguimiento de actividad (HAT) indica una ejecución correcta:  
  
`An error happened in the header during serialization.`
  
**Causa posible** : el valor de transformación del encabezado de mensaje no está correctamente establecido en [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
**Resolución** : mapa de MSH comprobar valores de [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)] el Explorador de configuración.  
  
## <a name="duplicate-event-id-4133-serializer-errors-are-logged"></a>Se registran los errores de serializador 4133 de Id. de evento duplicados  
  
### <a name="symptom"></a>Síntoma  
 Id. de evento 4133: "Error se produjo en encabezado durante la serialización" se produce dos veces para cada instancia de un mensaje con un valor de MSH11 que no es válido.  
  
**Causa posible** : se produjo un error al procesar dos confirmaciones (confirmación y confirmaciones de aplicación) sin errores duplicados en el registro de eventos. En su lugar, recibirá un 4133 de Id. de evento para cada una de las dos confirmaciones. [!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]crea una entrada de registro para cada confirmación genera.  
  
**Resolución** : asegúrese de que los mensajes tienen un campo de MSH11 correctamente formateado y rellenado.  
  
## <a name="send-pipeline-generates-an-error-when-using-the-2-way-mllp-adapter"></a>Enviar canalización genera un error cuando se usa el adaptador MLLP de 2 vías  
  
### <a name="symptom"></a>Síntoma  
 Obtiene el error siguiente o uno similar en el registro de eventos:  
  
`There was a failure executing the send pipeline: "[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XPipelines.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)]2XSendPipeline" Source: "[!INCLUDE[btsCoName](../../includes/btsconame-md.md)].Solutions.[!INCLUDE[btaBTAHL71.3abbrevnonumber](../../includes/btabtahl71-3abbrevnonumber-md.md)].HL72fAsm" Send Port: "<*host name: port number*>" Reason: Message does not contain a part with name MSHSegment.`
  
**Causa posible** : la aplicación receptora no responde con una confirmación y [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)] se espera una respuesta de la aplicación receptora.  
  
**Resolución** : Esto es así por diseño, y puede pasar por alto el mensaje de error.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas y problemas conocidos de HL7](../../adapters-and-accelerators/accelerator-hl7/troubleshooting-and-known-issues-in-hl7.md)