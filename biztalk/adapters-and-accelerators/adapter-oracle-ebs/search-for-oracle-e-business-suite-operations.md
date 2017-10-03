---
title: Busque las operaciones de Oracle E-Business Suite | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 2970ddd4-a534-4da4-9bd5-28bb9da4deca
caps.latest.revision: "5"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 797f89b5032d6bcfdb1a4d16f5a83d53d01f1c7f
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="search-for-oracle-e-business-suite-operations"></a>Busque las operaciones de Oracle E-Business Suite
Puede usar el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] para buscar artefactos específicos en Oracle E-Business Suite. Este tema proporciona información sobre cómo se admite la búsqueda para distintas vistas y lo que pueden usar caracteres comodín para buscar artefactos de Oracle. En este tema también proporciona información sobre cómo buscar mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)].  


  
> [!NOTE]
>  El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] presentes básicamente la misma interfaz al examinar y buscar las operaciones, por lo que ambos componentes se tratan en los temas de la mismos.  
  
 Para obtener más información, consulte [utilizar el adaptador de Oracle E-Business Suite con SharePoint](../../adapters-and-accelerators/adapter-oracle-ebs/use-the-oracle-e-business-suite-adapter-with-sharepoint.md).  
  
## <a name="prerequisites"></a>Requisitos previos  
 Debe conectarse a Oracle E-Business Suite antes de poder buscar metadatos para las operaciones de destino. Para obtener información acerca de cómo conectar con Oracle con la base de datos cuando se usa el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], consulte [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md).  
  
## <a name="support-for-wildcard-characters"></a>Compatibilidad con caracteres comodín  
 Al buscar metadatos de Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)], el [!INCLUDE[adapteroraclebusinessshort](../../includes/adapteroraclebusinessshort-md.md)] admite caracteres comodín y escape en la expresión de búsqueda.  
  
|Carácter especial|Interpretación|  
|-----------------------|--------------------|  
|_ (carácter de subrayado)|Coincide exactamente con un carácter<br /><br /> Por ejemplo, coincide con A_ AB, CA, AD.|  
|% (porcentaje)|Coincide con cero o más caracteres.<br /><br /> Por ejemplo, un % coincide con A, AB ABC.|  
|\ (escape)|Convierte el significado especial de % y _<br /><br /> Por ejemplo, un\\_B coincide con A_B.|  
  
> [!NOTE]
>  Carácter de escape es un carácter que se coloca delante de un carácter comodín para indicar que el carácter comodín debe interpretarse como un carácter normal y no como un carácter comodín.  
  
## <a name="searching-under-different-views"></a>Buscar en distintas vistas  
 El [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] y [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)] clasifica los datos en tres vistas: vista basada en la aplicación y vista basada en el artefacto, vista de esquema. Uno de los motivos para clasificar los artefactos en estas tres vistas es facilitar la búsqueda en función de lo que está buscando. En la tabla siguiente describe cómo puede diferir la búsqueda a través de estas vistas.  
  
|Ver|Cómo buscar|  
|----------|-------------------|  
|**Vista basada en la aplicación**|Esta vista está clasificada por los nombres de la aplicación de Oracle E-Business Suite. Debe utilizar esta vista cuando se sabe que la aplicación que contiene los artefactos que desea trabajar.<br /><br /> Los usuarios con esta visualización estarán familiarizados con las aplicaciones de Oracle y son compatibles con la aplicación que desean usar. Por lo tanto, la búsqueda en esta vista solo se admite en el nivel de inmediato. Por ejemplo, si la **vista basada en la aplicación** nodo está seleccionado, los usuarios pueden buscar una aplicación de Oracle E-Business Suite. De forma similar, si la **tabla de interfaz** nodo está seleccionado, los usuarios pueden buscar una tabla de interfaz en una aplicación de Oracle E-Business.|  
|**Vista de artefacto**|Esta vista está clasificada por los artefactos de Oracle E-Business Suite. Al trabajar con artefactos de la aplicación de Oracle E-Business Suite, los usuarios deben usar esta vista cuando sepan qué artefactos de Oracle E-Business Suite va a trabajar y pero no están seguro de qué aplicación al que pertenece el artefacto.<br /><br /> Con esta vista, los usuarios pueden buscar un artefacto específico en todas las aplicaciones de Oracle E-Business Suite. Por ejemplo, los usuarios pueden seleccionar la **tablas de interfaz** nodo y usando la cadena de búsqueda `AR%`. Se trata cómo se realizará la búsqueda:<br /><br /> -Dado que las tablas de interfaz se clasifican en las aplicaciones, se mostrarán todas las aplicaciones que se inicie con AR.<br />-Se enumerarán todas las tablas de interfaz a partir de AR. Estas tablas pueden pertenecer a cualquier aplicación de Oracle E-Business suite.<br /><br /> Al trabajar con artefactos de base de datos de Oracle mediante esta vista, los usuarios pueden buscar un artefacto específico, ya sea en el esquema actual con el que inicia sesión o todos los esquemas. Por ejemplo, si los usuarios desean utilizar un procedimiento CREATE_ACCOUNT pero que no tenga en cuenta qué esquema al que pertenece el procedimiento, se puede seleccionar la **todos los esquemas** nodo y, a continuación, busque mediante la cadena de `CREATE%`.|  
|**Vista de esquema**|Esta vista está clasificada por los esquemas disponibles en la base de datos de Oracle subyacente. Debe utilizar esta vista cuando se sabe qué esquema tiene los artefactos que desea trabajar.<br /><br /> Los usuarios con esta visualización estarán familiarizados con el esquema que tiene el artefacto que desean trabajar. Por lo tanto, la búsqueda en esta vista solo se admite en el nivel de inmediato. Por ejemplo, si la **vista basada en el esquema** nodo está seleccionado, los usuarios pueden buscar un esquema en la base de datos de Oracle. De forma similar, si la **tabla** nodo está seleccionado, los usuarios pueden buscar una tabla en una aplicación de Oracle E-Business.|  
  
## <a name="searching-for-operations"></a>Búsqueda de operaciones  
 Buscar metadatos en Oracle E-Business Suite utilizando el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)], realice los pasos siguientes.  
  
#### <a name="to-search-metadata-in-oracle-e-business-suite"></a>Buscar metadatos en Oracle E-Business Suite  
  
1.  Conectarse a Oracle E-Business Suite mediante el [!INCLUDE[consumeadapterservshort](../../includes/consumeadapterservshort-md.md)] o [!INCLUDE[addadapterservrefshort](../../includes/addadapterservrefshort-md.md)]. Vea [conectarse a Oracle E-Business Suite en Visual Studio](../../adapters-and-accelerators/adapter-oracle-ebs/connect-to-the-oracle-e-business-suite-in-visual-studio.md) para obtener instrucciones.  
  
2.  Desde el **seleccione el tipo de contrato** , seleccione el tipo de contrato en función de si está buscando las operaciones de entrada o salidas.  
  
3.  En el **seleccione una categoría de** cuadro, haga clic en el nodo de categoría en la que desea buscar un artefacto específico. Por ejemplo, para buscar una aplicación de Oracle, haga clic en el **vista basada en la aplicación** nodo.  
  
    > [!NOTE]
    >  Para buscar una aplicación puede especificar el nombre descriptivo o el nombre corto de la aplicación. Por ejemplo, para buscar el **cuentas por cobrar** aplicación puede especificar la cadena de búsqueda como `Receive%` o `AR`. AR es el nombre corto de aplicación.  
  
4.  En el **búsqueda en la categoría** , escriba una expresión de búsqueda para buscar un artefacto específico. Por ejemplo, para buscar las aplicaciones de Oracle que tiene "Cliente" en su nombre, escriba `%Customer%`.  
  
    > [!NOTE]
    >  La cadena de búsqueda distingue mayúsculas de minúsculas.  
  
5.  Para iniciar la búsqueda, haga clic en el botón con el icono de flecha derecha. Una vez completada, la búsqueda del **categorías y operaciones disponibles** cuadro muestra los artefactos que cumplen los criterios de búsqueda.  
  
     La siguiente ilustración muestra las tablas de las aplicaciones de Oracle que contienen a "Cliente" en su nombre.  
  
     ![Buscar metadatos en Oracle E &#45; Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/media/e6278992-a475-4a35-8371-db862f25a720.gif "e6278992-a475-4a35-8371-db862f25a720")  
  
    > [!NOTE]
    >  Para buscar un programa simultáneo puede especificar el nombre descriptivo o el nombre real del programa simultáneo. Por ejemplo, para buscar el **interfaz cliente** programa simultáneo puede especificar la cadena de búsqueda como `%Customer Interface%` o `%RACUST%`. RACUST es el nombre real del programa simultáneo.  
    >   
    >  Además, el resultado de la búsqueda siempre contendrá los programas simultáneos estándares independientemente de si su nombre coincide con la cadena de búsqueda especificado.  
  
## <a name="see-also"></a>Vea también  
 [Examinar, buscar y obtener los metadatos de las operaciones de Oracle E-Business Suite](../../adapters-and-accelerators/adapter-oracle-ebs/browse-search-and-get-metadata-for-oracle-e-business-suite-operations.md)