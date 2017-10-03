---
title: Fase de desensamblado (procesamiento de intercambio recuperable) | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 552b1e90-f75d-4713-8c7b-155a52819308
caps.latest.revision: "4"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: f36dd7a9d8bb10180d4af0562ba1e869957415d8
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="disassembly-stage-recoverable-interchange-processing"></a>Fase de desensamblado (procesamiento de intercambio recuperable)
Los intercambios se procesan en la fase de desensamblado de dos modos distintos:  
  
-   **Modo estándar.** cuando el componente de desensamblador de una canalización de recepción está configurado para realizar el desensamblado estándar, los mensajes contenidos en un intercambio se extraen, se procesan con la canalización de recepción, se asignan y se publican como una unidad de trabajo transaccional. Es decir, el intercambio completo y los mensajes que contiene se procesan completamente y se publican en la base de datos de cuadro de mensajes, o bien, el intercambio se coloca en la cola de suspensión.  
  
-   **Modo recuperable.** Cuando el componente de desensamblador de una canalización de recepción está configurado para realizar **procesamiento de intercambio recuperable**, los mensajes contenidos en un intercambio se extraen independientemente entre sí. Los mensajes que se extraen correctamente se propagan más abajo en la canalización de recepción. Los mensajes identificados dentro de un intercambio que no se extraen correctamente se sitúan en la cola de suspensión.  
  
## <a name="examples"></a>Ejemplos  
 Los ejemplos siguientes ilustran escenarios de procesamiento de intercambio.  
  
### <a name="example-1"></a>Ejemplo 1  
 En este ejemplo, el siguiente pseudointercambio se envía en una ubicación de recepción de intercambio estándar. Es decir, el componente de desensamblador de la canalización de recepción está configurado para el procesamiento de intercambio estándar.  
  
```  
<Interchange>  
<Document1>...</Document1>  
<Document2 failure=”routing”>...</Document2>  
<Document3>...</Document3>  
<Document4 failure=”pipeline” recoverableError=”true”>...</Document4>  
<Document5>...</Document5>  
</Interchange>  
```  
  
 Este intercambio contiene cinco mensajes y el desensamblador los extrae correctamente del intercambio. Se procesan del siguiente modo:  
  
-   El primero, el segundo y el tercer mensaje se propagan a través de la canalización y están listos para ser publicados.  
  
-   El cuarto mensaje genera un error de procesamiento en la fase de desensamblado de la canalización. Esto hace que se deshagan todos los mensajes ya procesados y que se suspenda el mensaje de intercambio original como reanudable.  
  
 El resultado del envío es:  
  
-   No se publica nada. En el procesamiento de intercambio estándar, el intercambio original se suspende porque cuando alguno de los mensajes extraídos genera un error en algún punto del procesamiento de intercambio o después del mismo, hace que todos los mensajes extraídos se descarten y que el intercambio original se coloque en la cola de suspensión como reanudable.  
  
### <a name="example-2"></a>Ejemplo 2  
 Este ejemplo utiliza el mismo escenario de procesamiento de intercambio y de propagación que el ejemplo anterior, salvo que aquí la fase de desensamblado está configurada para realizar un procesamiento de intercambio recuperable.  
  
 El resultado del envío es que los mensajes extraídos se procesan y se descarta el intercambio original. Los mensajes individuales se procesan del siguiente modo:  
  
-   El primero, el segundo y el tercer mensaje se propagan a través de la canalización y están listos para ser publicados.  
  
-   El cuarto mensaje genera un error en el procesamiento de desensamblado (es decir, algo va mal después de su extracción) y está listo para ser suspendido.  
  
-   El quinto mensaje se propaga a través de la canalización y está listo para ser publicado.  
  
-   Después de extraer todos los mensajes del intercambio, los mensajes 1, 2, 3 y 5 se publican en la base de datos de cuadro de mensajes y el mensaje 4 se coloca en la cola de suspensión. El mensaje 2 también se redirige a la cola de suspensión debido a un error de enrutamiento al no encontrar un suscriptor coincidente.  
  
## <a name="configuring-recoverable-interchange-processing"></a>Configurar el procesamiento de intercambio recuperable  
 El procesamiento de intercambio recuperable es una propiedad del componente de desensamblador de una canalización de recepción. No todos los componentes de desensamblador permiten especificar el procesamiento de intercambio recuperable; por ejemplo, el desensamblador nativo de BizTalk Framework no lo permite. Si un desensamblador admite el procesamiento de intercambio recuperable, especifique este comportamiento en el Diseñador de canalizaciones de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] al agregar el componente de desensamblador a la fase de desensamblado de la canalización que se está diseñada. Después de arrastrar el Desensamblador seleccionado en la fase de desensamblado de la canalización, establezca la propiedad de ese componente de desensamblador de procesamiento de intercambio recuperable `true`.  
  
### <a name="party-resolution"></a>Resolución de entidades  
 Los mensajes que se extraen correctamente durante el procesamiento de intercambio recuperable tienen identificada su entidad de envío según la entidad configurada para el puerto de recepción al que llegó el intercambio primario. Si se genera un error en alguno de los mensajes extraídos de un intercambio dado, se considera que la resolución de entidades ha dado error en todo el intercambio.  
  
### <a name="restrictions"></a>Restricciones  
  
-   Cuando un intercambio genera errores en el desensamblador, el intercambio se suspende como reanudable. No obstante, si el intercambio se reanuda mediante administración, tendrá de nuevo errores porque los tipos de errores que provocan el error de desensamblado se deben al contenido del intercambio, que permanece inalterado cuando se reanuda el intercambio. Dicho intercambio con errores debe modificarse y volver a enviarse a través de una ubicación de recepción.  
  
-   Si un mensaje que se extrajo correctamente de un intercambio no se propaga posteriormente mediante mensajería porque no hay un suscriptor coincidente, el mensaje se suspende como reanudable. Este mensaje se puede reanudar mediante administración si se corrige la causa del error de enrutamiento.  
  
-   El componente de desensamblador sigue extrayendo mensajes de un intercambio a pesar de los siguientes errores en los componentes de desensamblador:  
  
    -   Esquema no encontrado  
  
    -   Ambigüedad de esquema no resuelta (es decir, existe más de un esquema para el mismo tipo de mensaje)  
  
    -   Error al validar XML  
  
    -   Error al analizar archivo sin formato  
  
-   El componente de desensamblador **no** continuar extrayendo mensajes de un intercambio si se produce el siguiente error en componentes de desensamblador:  
  
    -   Los datos del documento no tienen un formato XML correcto; cualquier propiedad del documento que provoque un error en System.Xml.XmlReader  
  
## <a name="see-also"></a>Vea también  
 [Cómo configurar el componente de canalización de desensamblador XML](../core/how-to-configure-the-xml-disassembler-pipeline-component.md)   
 [Cómo configurar el componente de canalización de desensamblador de archivos sin formato](../core/how-to-configure-the-flat-file-disassembler-pipeline-component.md)