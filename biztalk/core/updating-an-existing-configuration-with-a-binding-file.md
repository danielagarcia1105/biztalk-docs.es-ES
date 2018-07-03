---
title: Actualizar una configuración existente con un archivo de enlace | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- binding files, updating
- binding files, rules
- artifacts, binding files
- binding files, unbinding
- binding files, customizing
- artifacts, updating
ms.assetid: 11580e59-7147-42d0-a976-f6b5e6933d24
caps.latest.revision: 10
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18b198690860489c16bf60b167b19eecdb34f529
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37022258"
---
# <a name="updating-an-existing-configuration-with-a-binding-file"></a>Actualizar una configuración que ya existe con un archivo de enlace
La información de un archivo de enlace sustituye la información de configuración existente. Si el nombre de un artefacto en un archivo de enlace coincide con el nombre de un artefacto en la configuración existente, el artefacto del archivo de enlace actualizará el artefacto de la configuración existente al importar el archivo de enlace.  
  
 Al actualizar los artefactos existentes con los artefactos del archivo de enlace, se siguen una serie de reglas. En este tema se tratan las reglas que se siguen al actualizar artefactos de una configuración que ya existe con los artefactos de un archivo de enlace.  
  
 En esta sección se da por hecho que existen valores válidos presentes en el archivo de enlace cuando se importa el archivo, y no se aborda ningún escenario en que el archivo de enlace contiene valores no válidos.  
  
## <a name="rules-followed-by-biztalk-server-when-updating-a-configuration-with-a-binding-file"></a>Reglas que sigue BizTalk Server al actualizar una configuración con un archivo de enlace  
 BizTalk Server sigue una serie de reglas al actualizar los artefactos existentes con sus homólogos de un archivo de enlace. En general, se aplican las reglas siguientes:  
  
- Los cuadros de texto y las casillas de verificación que se exponen al configurar un artefacto mediante la interfaz de usuario de BizTalk Server (por ejemplo, en la consola de administración de BizTalk Server o el Explorador de BizTalk) deberán estar establecidos en un valor específico o vacíos. Los valores proporcionados para los artefactos en un archivo de enlace establecerán en consecuencia el valor de la interfaz de usuario correspondiente al elemento actualizado.  
  
- Los cuadros de lista desplegable que se exponen al configurar un artefacto mediante la interfaz de usuario de BizTalk Server deberán estar establecidos en "Ninguno". Los valores proporcionados para los artefactos en un archivo de enlace establecerán en consecuencia el valor de la interfaz de usuario correspondiente al elemento actualizado.  
  
- Las vistas de cuadrícula de datos que se exponen al configurar un artefacto mediante la interfaz de usuario de BizTalk Server se actualizan con listas del elemento correspondiente en el archivo de enlace. La lista asociada a una vista de cuadrícula de datos siempre se sobrescribe con la lista del archivo de enlace, a no ser que la lista de la vista de cuadrícula de datos esté asociada a un puerto o una ubicación de recepción. En este caso, la lista del archivo de enlace se combina con la lista de la vista de cuadrícula de datos existente.  
  
- Los artefactos del archivo de enlace se identifican mediante un valor de clave primaria. El valor asociado a la clave primaria de un artefacto no se puede establecer nunca en NULL en la interfaz de usuario y, por consiguiente, todos los artefactos de un archivo de enlace deben tener establecido el valor de la clave primaria. Si el valor asociado a la clave primaria de un artefacto del archivo de enlace coincide con el valor asociado a la clave primaria de un artefacto de la configuración existente, ambos artefactos se considerarán idénticos o coincidentes. Si el artefacto del archivo de enlace y el artefacto existente son idénticos, entonces el existente se actualiza con el contenido en el archivo de enlace, como se describe en la tabla siguiente. Si un artefacto del archivo de enlace contiene un valor de clave primaria único, se creará un artefacto nuevo en la configuración de BizTalk Server al importar el archivo de enlace.  
  
  En la tabla siguiente se describe el comportamiento esperado al actualizar los artefactos de una configuración que ya existe con sus artefactos coincidentes al importar un archivo de enlace.  
  
|Tipo de artefacto|Property|Apariciones posibles de la propiedad especificada|Campo de la interfaz de usuario|Impacto de la importación de un artefacto coincidente del archivo de enlace.|  
|-------------------|--------------|------------------------------------------------|--------------------------|--------------------------------------------------------------|  
|**Entidad**|Nombre|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Clave principal|  
||Alias|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de alias con la lista de alias del archivo de enlace.|  
||Puertos de envío|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Se combina la lista de puertos de esta entidad existente con la lista de puertos de esta entidad del archivo de enlace.|  
||Nombre común y Huella digital del certificado|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: 1<br /><br /> (por propiedad)|Cuadro de texto|Sobrescribe estos valores con los valores especificados en el archivo de enlace. Si estos valores no existen en el archivo de enlace, se establecen en NULL.|  
|**orquestación**|Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Host|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribe este valor con el valor especificado en el archivo de enlace. Si este valor no existe en el archivo de enlace, se establece en NULL.|  
||Puertos de entrada y puertos de salida|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadro de lista desplegable|Enlaza un puerto lógico a un puerto físico existente. El puerto físico puede existir en las siguientes ubicaciones:<br /><br /> -En el grupo.<br />-En la aplicación.<br />-En el archivo de enlace.<br /><br /> Opcionalmente, establezca el puerto en **ninguno**. Si establece en **ninguno** , a continuación, el puerto lógico no está enlazado a ningún recurso.|  
||Casillas de verificación de las propiedades de seguimiento|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1<br /><br /> (por propiedad)|casilla|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
|**Grupo de puertos de envío**|Nombre|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Clave principal|  
||Los puertos de envío|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Se combina la lista de puertos de este grupo de puertos de envío existente con la lista de puertos de este grupo de puertos de envío especificada en el archivo de enlace.|  
||Filtros|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de filtros de este grupo de puertos de envío existente con la lista de filtros de este grupo de puertos de envío especificada en el archivo de enlace.|  
|**Puerto de envío**|Nombre|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Clave principal|  
||Transporte - Tipo|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Transporte – Controlador de envío|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Canalización de envío|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Número de reintentos, Intervalo de reintento y Prioridad|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1<br /><br /> (por propiedad)|Cuadro de desplazamiento|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
||Entrega ordenada|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Habilitar enrutamiento para mensajes con errores|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Habilitar ventana de servicio|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Hora de inicio y Hora de finalización en la ventana de servicio|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de desplazamiento|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
||Mapas|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de asignaciones de puerto de envío existente con la lista de asignaciones de este puerto de envío especificada en el archivo de enlace.|  
||Filter|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de filtros de este puerto de envío existente con la lista de filtros de este puerto de envío especificada en el archivo de enlace.|  
||Nombre común del certificado|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Huella digital de certificado|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Seguimiento|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Tipo (transporte de reserva)|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||URI (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace. solo es válido si se ha establecido el Tipo del transporte de reserva.|  
||Controlador de envío (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace. solo es válido si se ha establecido el Tipo del transporte de reserva.|  
||Número de reintentos (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de desplazamiento|Sobrescribir este valor con el valor especificado en el archivo de enlace. solo es válido si se ha establecido el Tipo del transporte de reserva.|  
||Intervalo de reintentos (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de desplazamiento|Sobrescribir este valor con el valor especificado en el archivo de enlace. solo es válido si se ha establecido el Tipo del transporte de reserva.|  
||Habilitar ventana de servicio (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace. solo es válido si se ha establecido el Tipo del transporte de reserva.|  
||Hora de inicio y Hora de finalización en la ventana de servicio (transporte de reserva)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de desplazamiento|Sobrescribir estos valores con los valores especificados en el archivo de enlace. solo es válido si se ha establecido el Tipo y Habilitar ventana de servicio para el transporte de reserva.|  
|**Puerto de recepción**|Nombre|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Clave principal|  
||Configuración de autenticación (botones de opción)|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Botón de opción|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Habilitar enrutamiento para mensajes con errores|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Ubicaciones de recepción|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de ubicaciones de recepción de este grupo de puertos de recepción existente con la lista de ubicaciones de recepción de este grupo de puertos de recepción especificada en el archivo de enlace. Si todas las ubicaciones de recepción del archivo de enlace ya existen en el grupo, se produce un error al importar.|  
||Mapas|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Cuadrícula de datos|Sobrescribe la lista de asignaciones de puerto de recepción existente con la lista de asignaciones de este puerto de recepción especificada en el archivo de enlace.|  
||Seguimiento - Seguimiento de partes de mensaje y Seguimiento de propiedades de mensaje|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1<br /><br /> (por casilla de verificación)|casilla|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
|**Ubicación de recepción**|Nombre|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Clave principal|  
||Tipo de transporte|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Controlador de recepción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Canalización|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de lista desplegable|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Casillas de verificación y cuadros de lista desplegable de fecha de inicio y fecha de finalización de la programación.|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Casilla de verificación y cuadro de lista desplegable.|Sobrescribir estos valores con los valores especificados en el archivo de enlace. Los valores de datos se importan aunque las casillas de verificación no estén activadas.|  
||Casilla de verificación Habilitar ventana de servicio|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Hora de inicio y Hora de finalización en la ventana de servicio|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de desplazamiento|Sobrescribir estos valores con los valores especificados en el archivo de enlace. solo es válido si se ha establecido Habilitar ventana de servicio.|  
|**Esquema**|Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Seguimiento - Hacer siempre el seguimiento de todas las propiedades|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Seguimiento - Seleccionar todas las propiedades de mensajes|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|casilla|Sobrescribir este valor con el valor especificado en el archivo de enlace. Si este valor está activado, todas las propiedades de mensaje que se puedan activar también se activarán.|  
||Seguimiento – propiedades individuales|Número mínimo de instancias: 0<br /><br /> Número máximo de instancias: *|Casillas de verificación|Sobrescribe la lista de propiedades sometidas a seguimiento de este esquema existente con la lista de propiedades sometidas a seguimiento de este esquema especificada en el archivo de enlace.<br /><br /> Si se importa un archivo de enlace que hace referencia a propiedades sometidas a seguimiento que no están disponibles para el esquema existente, se genera un error.|  
|**Mapa**|Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
|**Canalización**|Descripción|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1|Cuadro de texto|Sobrescribir este valor con el valor especificado en el archivo de enlace.|  
||Seguimiento de eventos|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1<br /><br /> (por casilla de verificación)|casilla|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
||Realizar seguimiento de partes de mensaje|Número mínimo de instancias: 1<br /><br /> Número máximo de instancias: 1<br /><br /> (por casilla de verificación)|casilla|Sobrescribir estos valores con los valores especificados en el archivo de enlace.|  
|**Directiva**|No aplicable. Las directivas no se exportan a un archivo de enlace.|No aplicable|No aplicable|No aplicable|  
|**Vínculo de función**|No aplicable. Los vínculos de rol no se exportan a un archivo de enlace.|No aplicable|No aplicable|No aplicable|  
  
## <a name="unbinding-behavior-when-updating-existing-artifacts-with-matching-artifacts-in-a-binding-file"></a>Comportamiento de desenlace al actualizar artefactos existentes con sus homólogos de un archivo de enlace  
 Los artefactos del archivo de enlace suelen estar configurados de modo que hagan referencia a otros artefactos, por ejemplo, normalmente un puerto de recepción se configura de modo que haga referencia a una ubicación de recepción. En este escenario, el puerto de recepción es el artefacto principal, y la ubicación de recepción es el artefacto secundario. Es el puerto de recepción **explícitamente** configurado para hacer referencia a la ubicación de recepción y la ubicación de recepción, a continuación, **implícitamente** hace referencia el puerto de recepción. Si un archivo de enlace contiene artefactos principales que no se han configurado completamente, por ejemplo, un puerto de recepción que no se haya configurado con su ubicación de recepción, quedarán configurados de manera incompleta después de importar el archivo de enlace, independientemente de su estado en la configuración existente. Por ejemplo, si dispone de una recepción myRP puerto configurado con ubicación de recepción myRL y puerto de recepción idéntico myRP del archivo de enlace es **no** configurado con ubicación de recepción myRL, a continuación, toma la entrada del archivo de enlace prioridad. Para la recepción de este ejemplo myRP del puerto no se configurarán con una ubicación de recepción después de importar el archivo de enlace, por lo que tendrá eficazmente **independiente** myRL de myRP.  
  
 Esta regla solo se aplica a la importación de artefactos que realizan referencias explícitas, no a los que tienen referencias implícitas. De modo que si ha importado una asignación que hace referencia implícitamente otros 10 artefactos (que hacen referencia a la asignación de manera explícita), no debe temer que la asignación se desenlace de los artefactos a los que hace referencia implícitamente.  
  
## <a name="see-also"></a>Vea también  
 [Personalización de archivos de enlace](../core/customizing-binding-files.md)