---
title: Cómo crear esquemas de propiedad | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 24086dea-62b8-4ef6-8af8-eb4ab7c3c018
caps.latest.revision: 6
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: ee97f4cb3065fdb201ec19f88a79e7899f03ac49
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
ms.locfileid: "25970482"
---
# <a name="how-to-create-property-schemas"></a>Cómo crear esquemas de propiedades
Si elige promocionar los campos como campos de propiedades, primero deberá definir un esquema de propiedades. Este esquema de propiedades especifica una colección no estructurada de campos en la puede promocionar los campos desde un mensaje de instancia definido por un esquema asociado con el esquema de propiedades.  
  
> [!IMPORTANT]
>  No copie ni edite un esquema de propiedades existente para crear un nuevo esquema. El esquema de propiedades contiene datos internos específicos del esquema.  
  
> [!NOTE]
>  No es necesario que cree un esquema de propiedades para promocionar campos distintivos.  
  
### <a name="to-create-a-property-schema"></a>Para crear un esquema de propiedades  
  
1.  En **el Explorador de soluciones**, haga clic en un proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **nuevo elemento**.  
  
2.  En el **Agregar nuevo elemento** cuadro de diálogo, en la **plantillas** sección, haga clic en **esquema de propiedades**.  
  
3.  En el **nombre** , escriba un nombre para el esquema y, a continuación, haga clic en **agregar**.  
  
     Se abre el nuevo esquema de propiedad, y que ya contenga un **elemento de campo** nodo denominado Property1.  
  
4.  En el árbol de esquema, haga clic en que **elemento de campo** nodo, haga clic en **cambiar el nombre de**, escriba un nombre descriptivo para la primera propiedad del esquema y, a continuación, presione ENTRAR.  
  
5.  Establecer el **tipo de datos** y otras propiedades relevantes, según corresponda, para el **elemento de campo** nodo en la ventana Propiedades.  
  
6.  Si desea insertar **elemento de campo** nodos para las propiedades adicionales, haga clic en el \<esquema\> nodo, haga clic en **Insertar nodo de esquema**y, a continuación, haga clic en  **Elemento de campo secundario**y, a continuación, repita los pasos 4 y 5. Repita según sea necesario para crear el conjunto necesario de **elemento de campo** nodos en el que se va a promover los valores de los mensajes de instancia.  
  
## <a name="see-also"></a>Vea también  
 [Administración de esquemas en proyectos](../core/managing-schemas-within-projects.md)