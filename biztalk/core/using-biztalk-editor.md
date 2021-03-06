---
title: Mediante el Editor de BizTalk | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 22021272-f028-4db3-ad8a-fb89a5340910
caps.latest.revision: 13
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 2f1f85fa69e07f252aa732d868353609ed065fbf
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37007165"
---
# <a name="using-biztalk-editor"></a>Utilizar el editor BizTalk

## <a name="overview"></a>Información general
El Editor de BizTalk reside en el shell de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Algunas de las funciones en el Editor de BizTalk se basa en elementos de interfaz de usuario existente dentro de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell. Por ejemplo, usa el **archivo**, **editar**, y **vista** menús igual que haría para otros entornos de desarrollo en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]. Información sobre esta funcionalidad común está disponible desde el **ayuda** menú.  
  
 El Editor de BizTalk se activa cuando agrega un nuevo esquema a un proyecto de BizTalk, cuando abre un esquema ya existente (archivo .xsd) en un proyecto de BizTalk, o cuando vuelve a activar un esquema haciendo clic en la pestaña correspondiente en la ventana de edición principal de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
> [!NOTE]
>  El Editor de BizTalk guarda los archivos de esquema con la codificación de caracteres UTF-16.  

## <a name="views"></a>Vistas  
 La siguiente ilustración muestra las distintas vistas dentro de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell que forman parte del Editor de BizTalk.  
  
 ![Las distintas partes del proyecto de BizTalk](../core/media/differentpartsofbiztalkserver.gif "DifferentpartsofBizTalkServer")  
  
 El Editor de BizTalk consta de las siguientes vistas dentro de Microsoft [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell y sus cuadros de diálogo asociados:  
  
- **Árbol de esquema.** Esta vista está en el lado izquierdo de los principales [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de edición. Cree el esquema de forma activa en esta vista al generar la estructura de árbol que describe la estructura del mensaje que el esquema define. Para obtener más información acerca de cómo se representan los esquemas de BizTalk en la vista de árbol de esquema, vea [representación de esquemas de BizTalk](../core/biztalk-representation-of-schemas.md).  
  
- **Vista XSD.** Esta vista está en el lado derecho de los principales [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana de edición. Muestra la estructura en el formato de lenguaje de definición de esquemas XML (XSD) que representa al esquema que está creando en la vista de árbol de esquema. Esta vista es de solo lectura y su objetivo es ayudarle a que se acostumbre a la sintaxis XSD del esquema que está creando. Si lo prefiere, puede ajustar el divisor de vistas de modo que la vista XSD únicamente se muestre de forma parcial.  
  
- **Explorador de soluciones.** Esta vista se encuentra en el lado derecho de la [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] shell. Muestra el proyecto de BizTalk y los distintos elementos que contiene. Use el Explorador de soluciones para agregar esquemas nuevos y existentes al proyecto, así como para abrir esquemas que ya son parte del proyecto. Por ejemplo, para crear un nuevo esquema, haga clic en el proyecto de BizTalk en la ventana Explorador de soluciones, haga clic en **agregar**, haga clic en **nuevo elemento**y, a continuación, utilice el **Agregar nuevo elemento** cuadro de diálogo cuadro para nombrar y crear un nuevo esquema.  
  
- [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)]  **Ventana Propiedades.** Utilice esta vista para examinar y establecer la mayoría de las propiedades de los esquemas y nodos. Al seleccionar un nodo en la vista de árbol de esquema o un esquema en la ventana Explorador de soluciones, las propiedades correspondientes de ese nodo o esquema se muestran en la ventana Propiedades con los paradigmas estándar de Visual Studio. Por ejemplo, las propiedades se agrupan en categorías y pueden mostrarse según estas categorías o alfabéticamente. Para obtener información detallada sobre los distintos conjuntos de propiedades que están disponibles cuando se seleccionan los distintos tipos de nodos o el esquema, vea el **referencia de esquema de propiedad** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
  Además de estas vistas, puede interactuar con varios cuadros de diálogo. Normalmente abrirá estos cuadros de diálogo cuando edite una propiedad compleja, como una colección.  
  
  Esta sección proporciona información acerca de las vistas, los comandos y las teclas de método abreviado disponibles en el Editor de BizTalk.  
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Cómo administrar la vista de árbol de esquema](../core/how-to-manage-the-schema-tree-view.md)  
  
-   [Cómo administrar la vista XSD](../core/how-to-manage-the-xsd-view.md)  
  
-   [Cómo administrar la ventana Propiedades](../core/how-to-manage-the-properties-window.md)  
  
-   [Cómo administrar otras Windows de Visual Studio](../core/how-to-manage-other-visual-studio-windows.md)  
  
-   [Uso de los comandos del Editor de BizTalk](../core/using-biztalk-editor-commands.md)  
  
-   [Trabajar con esquemas grandes](../core/working-with-large-schemas.md)