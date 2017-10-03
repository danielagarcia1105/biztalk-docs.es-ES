---
title: "Procesamiento de reparación de mensajes y nuevo envío especial | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- repairing messages, rekey verification
- repairing messages, process flow
- rekey verification
- repairing messages
- messages, templates
- messages, rekey verification
- BIC fields
- templates, messages
- BIC-12 data
- messages, process flow
- BIC-11 data
ms.assetid: 0ab729e3-4b67-47d3-84c9-f016318a4c41
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 1d77d518b080fd84b874c9bb79dedd5173d0a78b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="special-processing-in-message-repair-and-new-submission"></a>Procesamiento especial en la reparación de mensajes y nuevo envío
El [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] reparación de mensajes y nuevo envío funcionalidad permite a los clientes a desarrollar una implementación empresarial. La funcionalidad es compatible con el siguiente procesamiento especial:  
  
-   Comprobación de regeneración de claves  
  
-   Compatibilidad de flujo de trabajo específicos de departamento (para obtener más información, consulte [reparación de mensajes y enviar mensajes nuevos](../../adapters-and-accelerators/accelerator-swift/repairing-messages-and-submitting-new-messages.md).)  
  
-   Entrada de datos de 12 BIC como BIC 11  
  
-   Entrada de campos BIC como una cadena  
  
-   Analizar la reparación y reenvío de errores (para obtener más información, consulte [reparar sin analizar mensajes](../../adapters-and-accelerators/accelerator-swift/repairing-unparsed-messages.md).)  
  
-   Guardar reparaciones en curso con el comando Guardar  
  
-   Crear una nueva plantilla mediante el comando Guardar como  
  
## <a name="rekey-verification"></a>Cambiar la clave de comprobación  
 Para muchas de las instituciones financieras, el medio principal de la comprobación de trabajo es para que una segunda persona regenerar los campos más importantes de una transacción. Esta operación comprueba que la opción la segunda persona ha leído y comprendido, los datos de esos campos. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]proporciona esta capacidad para reparar o creados en los mensajes [!INCLUDE[btsBizTalkServerNoVersion](../../includes/btsbiztalkservernoversion-md.md)].  
  
 Si se requiere, un paso de regeneración de claves [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] espacios en blanco los campos regeneración en el formulario que se presentan al usuario. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Muestra el contenido del mensaje original en el panel de tareas, por lo que el Comprobador puede utilizar dicho contenido al escribir los datos. El Comprobador de no debería cambiar otros campos en el mensaje, porque esto podría permitir que los cambios sin esta comprobación. En su lugar, el Comprobador debe rechazar la reparación de mensajes si es necesario realizar otros cambios.  
  
 Después del paso de regeneración de claves, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] compara los resultados de la regeneración de claves con los resultados de la reparación. Esta comparación realiza únicamente en los campos que han sido regeneración, según un campo a campo. Si las dos versiones no coinciden en forma de carácter a carácter, necesiten ser reparado el mensaje de nuevo. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]indica que hay un error de coincidencia de comprobación de las claves y el error agrega a la parte de la colección de errores del mensaje. No se guardan los datos introducidos por el Comprobador de.  
  
 Los campos de regeneración se especifican en el archivo MrsrXpathConfig.xml en la carpeta MRSR en la [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] carpeta. Este archivo contiene los pares nombre/valor que consta del campo regeneración y la expresión xpath para el campo. Puede personalizar este archivo para cambiar qué campos se regeneración para cada mensaje. Los campos regeneración generalmente son aquéllos que representa la fecha más importante asociada con el contenido del mensaje, la moneda de la transacción y la cantidad de la transacción.  
  
 Todos los pasos de comprobación de reparación de mensajes y nuevo envío implican la comprobación de regeneración de claves. Comprobación de campo visual se realiza mediante el aprobador.  
  
## <a name="entry-of-bic-12-data-as-bic-11"></a>Entrada de datos de 12 BIC como BIC 11  
 [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]satisface las necesidades de un carácter adicional en la dirección lógica Terminal (LP) de un mensaje. La dirección de LT contiene sólo 11 caracteres de datos, pero el acceso de Alliance de SWIFT (AAS) requiere el campo LT tener una "X" en la posición 9. Este carácter adicional indica a AAS que seleccionen la LT. correcta  
  
 La dirección LT se utiliza para la transmisión del mensaje a través de la red FIN. Puede incluirse en dos campos de un mensaje de SWIFTBound (el campo de dirección de LT del bloque de encabezado básico) o el campo de dirección de destino en el bloque de encabezado de la aplicación de entrada y en dos campos de un mensaje de SWIFT (el campo de dirección de LT del bloque de encabezado básico o Dirección LT en la referencia del mensaje de entrada en el bloque de encabezado de la aplicación de salida).  
  
 Los usuarios deben escribir solo 11 caracteres cuando crea o reparar un mensaje o regenerar el campo como parte de la comprobación. Aunque la reparación o regeneración de claves un LT con 12 caracteres, un usuario debe escribir sólo 11 caracteres. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]Inserta el carácter duodécimo y valida el campo de 12 caracteres. [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]valida la dirección LT de 11 caracteres en la dirección en la base de datos BIC más.  
  
## <a name="entry-of-bic-fields-as-one-string"></a>Entrada de campos BIC como una cadena  
 Puede escribir el código BIC en un único campo [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios. El código BIC contiene cuatro subcampos, cada uno de los cuales tiene un subcampo en el [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formularios. Después de escribir la cadena BIC completa en el campo único, [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)] rellena cada uno de los cuatro subcampos.  
  
## <a name="saving-repairs-in-progress"></a>Guardar reparaciones en curso  
 Si necesita una reparación de interrupción, puede guardar un mensaje en su estado actual en la Bandeja de entrada de reparación. La forma de hacerlo es mediante el comando Guardar para proteger el mensaje. Puede cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario y compruebe el mensaje fuera más adelante u otra persona puede comprobar para continuar la reparación. Historial del mensaje indica la operación de guardar operación y un segundo taller de reparación pueden ver las reparaciones que ha realizado.  
  
 Puede ejecutar un comando Guardar como para almacenar un mensaje en su estado actual en el equipo del usuario local. Esto deja el mensaje comprobado por el usuario que realizó Guardar como. El usuario puede cerrar la [!INCLUDE[btsInpathNoVersion](../../includes/btsinpathnoversion-md.md)] formulario y volver más tarde para completar la reparación, pero otro usuario no se pueden extraer del repositorio el mensaje y repararlo.  
  
## <a name="creating-a-new-template"></a>Crear una nueva plantilla  
 Al crear un nuevo mensaje, puede crear una nueva plantilla al ejecutar un comando Guardar como. Esto le permite abrir una plantilla existente, agregar datos a los campos y, a continuación, crear una nueva plantilla basada en la plantilla existente que incluya los datos adicionales. Guarde la plantilla con un nuevo nombre, y cualquier persona con acceso a la nueva carpeta de mensaje en el sitio MRSR puede crear un nuevo mensaje basado en la plantilla. Debe guardar la plantilla en el sitio MRSR para enviar un mensaje basado en la plantilla para [!INCLUDE[btaA4SWIFT2.3abbrevnonumber](../../includes/btaa4swift2-3abbrevnonumber-md.md)]. En caso contrario, se producirán errores o no podrá abrir el formulario.