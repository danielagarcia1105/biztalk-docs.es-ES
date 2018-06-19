---
title: Cómo copiar los datos en el contexto del mensaje como campos de propiedades | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 4fdfe475-d9b4-4cf9-898f-dbd7e719c27c
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 18242f30f32974cc32ab5d39a4a9c63650f27ffa
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22249988"
---
# <a name="how-to-copy-data-to-the-message-context-as-property-fields"></a>Cómo copiar los datos en el contexto del mensaje como campos de propiedades
Puede promocionar una propiedad como un **campo de propiedad** de la misma manera como promocionar una propiedad como un **campo distintivo**, y también puede usar el **promoción rápida** característica a simplificar el proceso.  
  
 Puede elegir **campo de propiedad** promoción sobre **campo distintivo** promoción por las razones siguientes:  
  
-   Los valores que desea promocionar tienen menos caracteres que la limitación de 255 caracteres que se aplica a **campos de propiedades**.  
  
-   Necesita que sea posible el acceso a los valores promocionados desde fuera de las orquestaciones; por ejemplo, desde canalizaciones o puertos.  
  
 Este tema proporciona instrucciones paso a paso para promocionar una propiedad como un **campo de propiedad** en ambas de estas maneras.  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-promote-properties-dialog-box"></a>Para promocionar una propiedad como un campo de propiedades mediante el cuadro de diálogo Promocionar propiedades  
  
1.  Si es necesario, cree un esquema de propiedades adecuado para promocionar una propiedad. Para obtener instrucciones paso a paso para crear esquemas de propiedades, vea [crear esquemas de propiedad](../core/how-to-create-property-schemas.md).  
  
    > [!NOTE]
    >  Este paso no sea necesario si ya ha creado un esquema de propiedad e inserta adecuado **elemento de campo** nodos como nodos secundarios de la **esquema** nodo.  
  
2.  En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo de la propiedad**.  
  
    > [!NOTE]
    >  Solo puede promocionar **registro** nodos si se han configurado para incluir únicamente contenido simple manteniendo su **Content Type** propiedad establecida en **SimpleContent**.  
  
3.  Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **mostrar promociones**.  
  
     El **promocionar propiedades** abre el cuadro de diálogo con la muestra el nodo seleccionado en el árbol de esquema en el lado izquierdo del cuadro de diálogo.  
  
4.  En el **promocionar propiedades** cuadro de diálogo, seleccione la **campos de propiedades** ficha.  
  
5.  Confirme que el esquema de propiedad en la que desea promocionar una propiedad está presente en el **lista de esquemas de propiedad** en la pestaña campos de propiedades. Si está presente, vaya al paso 8.  
  
6.  En el **lista de esquemas de propiedad** sección, haga clic en el **carpeta** icono. El **selector de tipos de BizTalk** aparece el cuadro de diálogo.  
  
7.  En el **selector de tipos de BizTalk** diálogo cuadro, vaya al esquema de propiedades adecuado (que haya creado en el paso 1), seleccione dicho esquema y, a continuación, haga clic en **Aceptar**.  
  
    > [!NOTE]
    >  Si lo desea, puede cambiar el prefijo de espacio de nombres asociado al esquema de propiedad cambiando la cadena en la correspondiente **prefijo** campo de la columna.  
  
8.  Con el nodo para promocionar todavía seleccionado en el árbol de esquema en el lado izquierdo de la **promocionar propiedades** cuadro de diálogo, haga clic en **agregar**.  
  
     Si se permite, el nodo seleccionado se agrega al final de la **lista de campos de propiedades** en el **campos de propiedades** ficha. En caso de no permitirse, un cuadro de mensajes proporciona una explicación. Si no se permite la **agregar** botón no está habilitado.  
  
9. Haga doble clic en **propiedad** celda de la columna de la fila que acaba de agregar a la **lista de campos de propiedades**y, a continuación, en la lista desplegable, seleccione la **esquema de propiedad** y correspondiente **elemento de campo** nodo en el que desea promocionar el nodo seleccionado. Valores de lista desplegable tienen el formato x: y, donde X es el prefijo de espacio de nombres de un esquema de propiedad de la **lista de esquemas de propiedad**, e Y es el nombre del nodo de un **elemento de campo** nodo en ese esquema de propiedad.  
  
     El valor predeterminado en la lista desplegable es el primer esquema de propiedad **(elemento de campo)** nodo que no se ha promocionado, por orden alfabético de todos los esquemas de propiedad correspondiente. En raras ocasiones será el nodo de esquema de propiedades en el que pretende promocionar un nodo de esquema específico.  
  
10. Puede seleccionar nodos adicionales para promocionarlos en el árbol de esquema en el lado izquierdo del cuadro de diálogo, haga clic en **agregar** y, a continuación, realizar el paso 9 después de cada selección.  
  
11. Cuando haya terminado, haga clic en **Aceptar**.  
  
     Los nodos seleccionados para promocionar son ahora **campos de propiedades** y están asociados a un determinado **elemento de campo** nodo en un esquema de propiedad.  
  
### <a name="to-promote-a-property-as-a-property-field-using-the-quick-promotion-command"></a>Para promocionar una propiedad como un campo de propiedades mediante el comando Promoción rápida  
  
1.  En el Editor de BizTalk, abra el esquema para el que desea promocionar una o varias propiedades y, a continuación, seleccione el (primer) **elemento de campo**, **atributo de campo**, o **registro** nodo que desea promover como un **campo de la propiedad**.  
  
    > [!NOTE]
    >  Solo puede promocionar **registro** nodos si se han configurado para incluir únicamente contenido simple manteniendo su **Content Type** propiedad establecida en **SimpleContent**.  
  
2.  Haga clic en el nodo seleccionado, haga clic en **promover**y, a continuación, haga clic en **promoción rápida**.  
  
     Si el esquema de propiedad predeterminado, tal como se define por la **nombre del esquema de propiedad predeterminado** propiedad en el **páginas de propiedades** para el esquema correspondiente, no existe, debe hacer clic en **Aceptar**en el cuadro de diálogo de confirmación para crear el esquema de propiedad predeterminado y configurarlo con un adecuado **elemento de campo** nodo para dar cabida a la promoción de propiedades.  
  
> [!NOTE]
>  Puede ver y administrar las propiedades promocionadas mediante la **promociones rápidas** característica abriendo el **promocionar propiedades** cuadro de diálogo y, a continuación, haga clic en el **campos de propiedades** pestaña. Para obtener instrucciones paso a paso para abrir el **promocionar propiedades** cuadro de diálogo, vea [abrir el cuadro de diálogo Promocionar propiedades](../core/how-to-open-the-promote-properties-dialog-box.md).  
  
## <a name="see-also"></a>Vea también  
 [Promoción de propiedades](../core/promoting-properties.md)   
 [Cómo crear esquemas de propiedades](../core/how-to-create-property-schemas.md)   
 [Formas de usar el contenido de mensaje para el procesamiento de mensajes de Control](../core/ways-to-use-message-content-to-control-message-processing.md)