---
title: Cómo trabajar con tipos de puertos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- deleting, port types
- port types, deleting
- port types, Web
- port types, request-response
- orchestrations, ports
- port types, modifier
- port types
- ports, port types
- port types, one-way
ms.assetid: 78ac731e-c330-4888-a9ee-10523fef8ed0
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4e3b4307cb9d48679ae1b90f7e02dd0288ec2957
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257132"
---
# <a name="how-to-work-with-port-types"></a>Cómo trabajar con tipos de puerto
Un tipo de puerto consta de un patrón de comunicación, un conjunto de operaciones (solicitudes o respuestas) y los tipos de mensaje con los que pueden trabajar esas operaciones. El patrón puede ser unidireccional o de solicitud-respuesta (bidireccional), y todas las operaciones definidas en ese tipo de puerto deben utilizar el mismo patrón. Tenga en cuenta que los tipos de puerto son independientes de la dirección: la dirección se especifica en cada puerto.  
  
 El ámbito de un tipo de puerto se define mediante la **modificador de tipo** propiedad. Un tipo de puerto puede ser público, privado o interno. Si es público, estará visible para cualquiera que interactúe con la orquestación. Si es privado, estará visible para otras orquestaciones dentro del mismo proyecto y el mismo espacio de nombres. Si es interno, el tipo de puerto estará visible solo dentro del proyecto. Puesto que una definición de tipo de puerto incluye tipos de mensaje, el ámbito del tipo de mensaje deberá incluir el de cualquier tipo de puerto que lo utilice.  
  
> [!NOTE]
>  Un tipo de puerto se puede aplicar a cualquier número de puertos. Un puerto puede considerarse como una instancia de un tipo de puerto.  
  
> [!NOTE]
>  Un tipo de puerto no tiene una dirección de comunicación de forma inherente; la dirección se establece en cada puerto.  
  
### <a name="to-add-a-request-response-port-type"></a>Para agregar un tipo de puerto de solicitud-respuesta  
  
1.  En la ventana Vista orquestación, haga clic en **tipos de puerto** y, a continuación, haga clic en **tipo de puerto de solicitud-respuesta nuevo**.  
  
     El **tipos de puerto** expande el nodo, si se contrae, y se agrega un nuevo tipo de puerto de solicitud-respuesta con una operación predeterminada.  
  
2.  Especifique un nombre para el tipo de puerto.  
  
3.  Defina una o más operaciones de puerto.  
  
     Puede asignar un nombre a las operaciones de puerto, pero cuando las seleccione desde otro proyecto, aparecerán únicamente como "Solicitud" y "Respuesta" Si selecciona una operación de puerto desde otro proyecto, compruebe que tiene el tipo de mensaje correcto.  
  
### <a name="to-add-a-one-way-port-type"></a>Para agregar un tipo de puerto unidireccional  
  
1.  En la ventana Vista orquestación, haga clic en **tipos de puerto** y, a continuación, haga clic en **nuevo tipo de puerto unidireccional**.  
  
     El **tipos de puerto** expande el nodo, si se contrae y se agrega un nuevo tipo de puerto unidireccional con una operación predeterminada.  
  
2.  Especifique un nombre para el tipo de puerto.  
  
3.  Defina una o más operaciones de puerto.  
  
### <a name="to-add-a-web-port-type"></a>Para agregar un tipo de puerto Web  
  
-   Agregue una referencia de proyecto a un ensamblado que contenga una clase de proxy para un servicio Web. Para obtener más información, consulte [crear puertos Web](../core/creating-web-ports.md).  
  
### <a name="to-remove-a-port-type"></a>Para quitar un tipo de puerto  
  
-   En la ventana Vista orquestación, haga clic en eliminar y, a continuación, haga clic en el tipo de puerto **eliminar**.  
  
    > [!NOTE]
    >  Si el tipo de puerto está en uso, su eliminación afectará a la configuración de los puertos que estén configurados para utilizarlo.  
  
    > [!NOTE]
    >  Los elementos que aparecen como de solo de lectura se definen en otra orquestación.  
  
### <a name="to-set-the-type-modifier-for-a-port-type"></a>Para establecer el modificador de tipo para un tipo de puerto  
  
-   En la ventana Propiedades, establezca la siguiente propiedad:  
  
    |Propiedad|Description|  
    |--------------|-----------------|  
    |Modificador de tipo|Determina el ámbito del tipo de puerto:<br /><br /> Privado: acceso a este tipo de puerto está limitado al módulo contenedor.<br /><br /> Público: acceso a este tipo de puerto no está limitado.<br /><br /> Interno: el acceso a este tipo de puerto está limitado a los módulos dentro del mismo proyecto.|  
  
## <a name="see-also"></a>Vea también  
 [Patrón de comunicación](../core/communication-pattern.md)   
 [Cómo ejecutar al Asistente para configuración de puertos](../core/how-to-run-the-port-configuration-wizard.md)   
 [Uso de puertos en orquestaciones](../core/using-ports-in-orchestrations.md)