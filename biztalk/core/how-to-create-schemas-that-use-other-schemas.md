---
title: Cómo crear esquemas que usan otros esquemas | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: ff0bcd9a-6c66-4c3b-bd41-64047a7c8392
caps.latest.revision: 7
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 51fdc5e7601eebca7cc8193757cc909784ab828f
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36987813"
---
# <a name="how-to-create-schemas-that-use-other-schemas"></a>Cómo crear esquemas que usan otros esquemas
El lenguaje de definición de esquemas XML (XSD) proporciona tres mecanismos diferentes pero relacionados entre sí para utilizar un esquema dentro de otro. Estos mecanismos son importar un esquema, incluir un esquema y redefinir un esquema. Para obtener un resumen breve de estos mecanismos y cómo se diferencian, consulte [esquemas que usan otros esquemas](../core/schemas-that-use-other-schemas.md). Para obtener información detallada, consulte [recursos XSD en Internet](../core/xsd-resources-on-the-web.md) para obtener vínculos a las especificaciones y manual de XSD.  
  
 En este tema se describen los pasos necesarios para importar, incluir y redefinir otros esquemas en el esquema que esté desarrollando.  
  
### <a name="to-import-include-or-redefine-one-schema-within-another-schema"></a>Para importar, incluir o redefinir un esquema dentro de otro esquema  
  
1. En el Editor de BizTalk, abra el esquema en el que desea importar, incluir o redefinir otro esquema. Para abrir un esquema, haga doble clic en él en el Explorador de soluciones.  
  
2. Seleccione el **esquema** nodo en la parte superior de la vista de árbol de esquema.  
  
3. Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.  
  
4. En la ventana Propiedades, en el **avanzadas** categoría, en la parte del valor de la **importaciones** propiedad, haga clic en el botón de puntos suspensivos (**...** ) botón.  
  
5. En el **importaciones** cuadro de diálogo el **importar un esquema nuevo como** lista, seleccione **XSD Import**, **XSD Include**, o **XSD Redefinir**, según corresponda y, a continuación, haga clic en **agregar**.  
  
6. En el **selector de tipos de BizTalk** cuadro de diálogo, expanda el **esquema** nodo en el árbol del proyecto, seleccione el esquema que desea importar, incluir, o volver a definir y, a continuación, haga clic en **Aceptar**.  
  
7. En el **importaciones** cuadro de diálogo, haga clic en **Aceptar**.  
  
    Las directivas XSD adecuadas para implementar la importación, inclusión o redefinición de la operación se agregan a la **esquema** elemento en la vista XSD, incluido un nuevo **importar**, **incluyen**, o **redefinir** elemento según corresponda.  
  
> [!IMPORTANT]
>  Asegúrese de que entiende las distintas finalidades de estos tres mecanismos, por ejemplo, en qué difieren con respecto a los requisitos de espacios de nombres. Siempre puede eliminar un esquema importado, incluido o redefinido anteriormente y, posteriormente, utilizar uno de los otros dos mecanismos. No obstante, según el grado de exhaustividad con el que haya hecho referencia a dicho esquema, podría tener que modificarlo en consecuencia.  
  
> [!IMPORTANT]
>  El mecanismo XSD para importar, incluir y redefinir un esquema dentro de otro esquema utiliza una referencia al esquema importado, incluido o redefinido. Esto significa que, si hace algún cambio al esquema importado, incluido o redefinido, este cambio se verá reflejado en el esquema que contiene la referencia de importación, inclusión o redefinición.  
  
## <a name="see-also"></a>Vea también  
 [Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md)   
 [Cómo crear referencias a otro nodo o tipo](../core/how-to-create-references-to-another-node-or-type.md)