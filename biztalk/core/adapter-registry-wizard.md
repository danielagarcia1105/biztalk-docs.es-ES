---
title: Asistente para registro del adaptador | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- utilities, Adapter Registration Wizard
- Adapter Registration Wizard
ms.assetid: bd15d0c7-01bb-41f9-9157-cdcf4bb4e39a
caps.latest.revision: "8"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f07ef6adc96a4f5819cd5438b4a5d24ce6fc0770
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="adapter-registry-wizard"></a>Asistente para registro del adaptador
Usar al Asistente para registro del adaptador para crear los archivos de registro necesarios para configurar y registrar un adaptador personalizado.  
  
## <a name="location-in-sdk"></a>Ubicación en SDK  
 *\<Ruta de acceso de instalación >*\SDK\Utilities\AdapterRegistryWizard\  
  
## <a name="to-run-this-utility"></a>Para ejecutar esta utilidad  
 Inicie el asistente mediante la ejecución de AdapterRegistryWizard.exe. Las páginas siguientes solicitan información acerca del adaptador y de las propiedades que admite. Las páginas del Asistente para el Registro del adaptador se describen en las secciones siguientes.  
  
### <a name="generic-adapter-properties-page"></a>Página de propiedades de adaptador  
 Utilice la página de propiedades de adaptador para especificar las propiedades del adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Tipo de adaptador de transporte**|Especificar el tipo de adaptador.|  
|**Espacio de nombres de propiedad**|Especifique el espacio de nombres de adaptador. [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)]almacena propiedades específicas del adaptador en el contexto del mensaje en este espacio de nombres.|  
|**Adaptador puede recibir mensajes y enviarlos a BizTalk Server**|Identificar patrones de comunicación compatibles con el adaptador. Se usa para calcular la entrada de Registro Restricciones del adaptador.|  
|**Adaptador puede enviar mensajes de BizTalk Server**|Identificar patrones de comunicación compatibles con el adaptador. Se usa para calcular la entrada de Registro Restricciones del adaptador.|  
  
### <a name="inbound-part-page"></a>Parte entrante (página)  
 Utilice la página Parte entrante para especificar la lógica de recepción entrante del adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Examinar**|Seleccionar el ensamblado que implementa la lógica de recepción entrante del adaptador. Aparece una lista de los tipos públicos expuestos por el ensamblado en la lista desplegable. Seleccionar el tipo en el ensamblado específico que implementa la lógica entrante del adaptador de la lista desplegable.|  
|**Adaptador es compatible con el protocolo de solicitudes y respuestas**|Especificar las capacidades de recepción del adaptador. Se usa para calcular la entrada de registro de restricciones para el adaptador.|  
|**Adaptador está aislado (que se hospeda en un proceso diferente)**|Especificar las capacidades de recepción del adaptador. Se usa para calcular la entrada de registro de restricciones para el adaptador.|  
  
### <a name="outbound-part-page"></a>Parte saliente (página)  
 Utilice la página Parte saliente para especificar la lógica de recepción saliente del adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Examinar**|Seleccionar el ensamblado que implementa la lógica de recepción saliente del adaptador. Aparece una lista de los tipos públicos expuestos por el ensamblado en la lista desplegable. Seleccionar el tipo de ensamblado específico que implementa la lógica saliente del adaptador de la lista desplegable. Además, debe escribir una lista de alias separados por comas para identificar el protocolo usado por este adaptador (por ejemplo, submit://).|  
|**Adaptador es compatible con el protocolo de petición-respuesta**|Identificar las capacidades de transmisión del adaptador. Estos valores se usan para calcular la entrada de Registro Restricciones del adaptador.|  
  
### <a name="adapter-management-page"></a>Administración de adaptador (página)  
 Utilice la página Administración de adaptador para especificar la lógica de administración en tiempo de diseño del adaptador.  
  
|Use|Para|  
|--------------|----------------|  
|**Examinar**|Seleccionar el ensamblado que implementa la lógica de administración del adaptador en tiempo de diseño para el adaptador. Aparece una lista de los tipos públicos expuestos por este ensamblado en la lista desplegable. Seleccionar el tipo para el ensamblado específico que implementa la lógica de administración de adaptador para este adaptador de la lista desplegable.|  
  
### <a name="output-file-name"></a>Archivo de salida (nombre)  
 Utilice la página de nombre de Archivo de salida para especificar el nombre y la ubicación de un archivo de salida.  
  
|Use|Para|  
|--------------|----------------|  
|**Examinar**|Seleccionar un nombre y una ubicación del archivo de salida. El Registro del adaptador se escribe en este archivo.|  
  
## <a name="remarks"></a>Comentarios  
 La utilidad Asistente para el Registro del adaptador rellena las propiedades de almacén de configuración Inicio de sesión único empresarial (SSO) con valores predeterminados. Si el adaptador no utiliza las páginas de propiedades estándar proporcionadas por el marco de trabajo de adaptadores para el controlador y la ubicación de las propiedades de adaptador, debe editar el archivo de Registro de forma manual para modificar estos valores. Para obtener más información acerca de estas opciones, consulte "Registro de propiedades de adaptador de almacén de configuración de SSO" en el tema [registrar un adaptador](../core/registering-an-adapter.md).  
  
## <a name="see-also"></a>Vea también  
 [Utilidades del SDK de](../core/utilities-in-the-sdk.md)   
 [Registrar un adaptador](../core/registering-an-adapter.md)