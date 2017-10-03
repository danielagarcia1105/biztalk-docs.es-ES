---
title: Configurar un puerto para recibir mensajes EDI y confirmaciones | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c043e648-b7f5-40aa-b7b5-0172fbea7b31
caps.latest.revision: "18"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 16d3add143cdac1926b89cf137b5ccfcebe77be3
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="configuring-a-port-to-receive-edi-messages-and-acknowledgments"></a>Configurar un puerto para recibir mensajes y confirmaciones EDI
Para recibir un intercambio EDI, puede crear un puerto de recepción unidireccional o un puerto de recepción de solicitud-respuesta (bidireccional) para recibir el intercambio.  
  
-   Cree un puerto de recepción unidireccional si también va a crear un puerto de envío unidireccional para enviar confirmaciones EDI (si está habilitado). También tendrá que desactivar la **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** propiedad del acuerdo.  
  
-   Cree una ubicación y un puerto de recepción de solicitud-respuesta para devolver confirmaciones EDI (si esta opción está habilitada) a través de la canalización de envío asociada. También tendrá que seleccionar la **puerto de recepción de enrutar confirmación para la canalización de envío de solicitud-respuesta** propiedad del acuerdo.  
  
## <a name="creating-a-one-way-receive-port"></a>Crear un puerto de recepción unidireccional  
 Cree la ubicación y el puerto de recepción con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de recepción: General**|Tipo de puerto|Unidireccional|  
|**Propiedades de puerto de recepción: General**|Autenticación|Establecido en **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** para autenticar la entidad que envió el mensaje recibido.<br /><br /> Establecido en **sin autenticación** para deshabilitar la autenticación de la entidad que envió el mensaje recibido.<br /><br /> Si establece en **eliminar mensajes si hay errores de autenticación**, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] suspenderá un mensaje si se produce un error en la autenticación de su remitente.<br /><br /> Si establece en **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación**, el mensaje debe resolverse en un acuerdo. No se permite el uso de las propiedades de acuerdo de reserva. Si no se ha determinado ningún acuerdo para un mensaje entrante, [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] tratará el mensaje como si se hubiese producido un error en la autenticación y lo suspenderá.|  
|**Propiedades de la ubicación de recepción: General**|Tipo de transporte|Puede ser cualquier número de tipos de transporte.|  
|**Propiedades de la ubicación de recepción: General**|Controlador de recepción|BizTalkServerApplication|  
|**Propiedades de la ubicación de recepción: General**|Canalización de recepción|EdiReceive|  
|**Propiedades de transporte de archivo: autenticación**|Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red (con nombre de usuario y contraseña)|Definir si se requiere autenticación.|  
|**Propiedades de transporte de archivo: procesamiento por lotes**|Número de mensajes en un lote|Definir si el intercambio se va a procesar por lotes.|  
|**Propiedades de transporte de archivo: procesamiento por lotes**|Tamaño máximo del lote (en bytes)|Definir si el intercambio se va a procesar por lotes.|  
  
## <a name="creating-a-request-response-receive-port"></a>Crear un puerto de recepción de solicitud-respuesta  
 Cree la ubicación y el puerto de recepción con la siguiente configuración:  
  
|Ubicación|Propiedad|Configuración|  
|--------------|--------------|-------------|  
|**Propiedades de puerto de recepción: General**|Tipo de puerto|Respuesta de solicitud|  
|**Propiedades de puerto de recepción: General**|Autenticación|Establecido en **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación** para autenticar la entidad que envió el mensaje recibido.<br /><br /> Establecido en **sin autenticación** para deshabilitar la autenticación de la entidad que envió el mensaje recibido.<br /><br /> **Nota:** si establece en **eliminar mensajes si hay errores de autenticación** o **conservar mensajes si hay errores de autenticación**, el mensaje debe resolverse en un acuerdo.|  
|**Propiedades de la ubicación de recepción: General**|Tipo de transporte|Puede ser cualquier número de tipos de transporte, excepto de archivos, que no está disponible en la lista desplegable.<br /><br /> **Nota:** puede producirse un problema de seguridad si crea una ubicación de recepción que usa la canalización EDIReceive y tenga un tipo de transporte de HTTP. La canalización EdiReceive no generará una confirmación HTTP “200 OK”. Si no se devuelve una confirmación EDI, la conexión permanecerá abierta hasta que se agote el tiempo de espera.|  
|**Propiedades de la ubicación de recepción: General**|Controlador de recepción|BizTalkServerApplication|  
|**Propiedades de la ubicación de recepción: General**|Canalización de recepción|EdiReceive|  
|**Propiedades de la ubicación de recepción: General**|Canalización de envío|EdiSend|  
|**Propiedades de transporte de archivo: autenticación**|Usar estas credenciales cuando el host no tenga acceso al recurso compartido de red (con nombre de usuario y contraseña)|Definir si se requiere autenticación.|  
|**Propiedades de transporte de archivo: procesamiento por lotes**|Número de mensajes en un lote|Definir si el intercambio se va a procesar por lotes.|  
|**Propiedades de transporte de archivo: procesamiento por lotes**|Tamaño máximo del lote (en bytes)|Definir si el intercambio se va a procesar por lotes.|  
  
## <a name="setting-agreement-properties"></a>Establecimiento de las propiedades del acuerdo  
 Tras la creación de la ubicación y el puerto de recepción, es necesario establecer las propiedades de acuerdo requeridas para que funcione la canalización de recepción. Estas propiedades se establecen en las distintas páginas de la **propiedades del acuerdo de** cuadro de diálogo. Para obtener una lista de las propiedades que debe tener el Desensamblador EDI para recibir un intercambio EDI en el EdiReceive de proceso de canalización, consulte [cómo funciona el de desensamblador de EDI](../core/how-the-edi-disassembler-works.md).  
  
## <a name="see-also"></a>Vea también  
 [Configurar puertos para una solución EDI](../core/configuring-ports-for-an-edi-solution.md)   
 [Cómo funciona el Desensamblador EDI](../core/how-the-edi-disassembler-works.md)   
 [Cómo crear un puerto de recepción](../core/how-to-create-a-receive-port.md)