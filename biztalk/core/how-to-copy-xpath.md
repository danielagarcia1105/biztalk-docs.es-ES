---
title: Cómo copiar XPath | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 404599d4-0fb3-4c7c-91e6-1295d9d0965e
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: bb282c5c32d8da62a9da6d7a9c900c798e44eee7
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22248532"
---
# <a name="how-to-copy-xpath"></a>Copia de XPath
El lenguaje de definición de esquemas XML (XSD) proporciona la sintaxis subyacente de los esquemas de mensaje definidos en BizTalk Server. Aunque las vistas de árbol del Asignador de BizTalk utilizan una jerarquía gráfica específica de BizTalk para los nodos de registro y de campo (entre otros tipos de nodos), cada uno con su propio conjunto de propiedades, dichas jerarquías se crean y mantienen como XSD.  
  
 En escenarios donde las asignaciones son complejas y abarcan varias páginas de cuadrícula, localizar el principal de un nodo de esquema puede resultar complicado. La ruta de acceso XSD será útil aquí. Puede usar la ruta de acceso XSD para obtener información acerca de la profundidad de los nodos de esquema. Además, puede volver a usar esta ruta de acceso en otra página de cuadrícula para identificar la relación.  
  
## <a name="prerequisites"></a>Requisitos previos  
 Estas instrucciones requieren que se está ejecutando el asignador de BizTalk.  
  
### <a name="to-copy-the-xsd-path-xpath"></a>Para copiar la ruta de acceso XSD (XPath)  
  
1.  Haga clic en el nodo de esquema para el que desea que la ruta de acceso XSD y, a continuación, haga clic en **Copiar XPath**.  
  
2.  Abra un editor de texto. En el menú **Editar** , haga clic en **Pegar**. Ahora puede ver la ruta de acceso XSD.  
  
    > [!NOTE]
    >  Como alternativa, puede presionar CTRL+V para pegar la ruta de acceso en un editor de texto.  
  
     El siguiente código muestra la ruta de acceso XSD para el nodo de esquema seleccionado.  
  
    ```  
    /*[local-name()='<Schema>']/*[local-name()='Shipment']/*[local-name()='DataCollection']  
    ```  
  
## <a name="see-also"></a>Vea también  
 [Uso de características mejoradas en el asignador de BizTalk](../core/using-enhanced-features-in-biztalk-mapper.md)   
 [Cómo reemplazar esquemas](../core/how-to-replace-schemas.md)   
 [Cómo expandir y contraer los árboles de esquema](https://msdn.microsoft.com/library/ee253802(v=bts.10).aspx)