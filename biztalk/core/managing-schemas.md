---
title: Administrar esquemas | Microsoft Docs
description: Use Administración de BizTalk para trabajar con esquemas en BizTalk Server, incluidos mostrando y ocultando las propiedades, ver la XSD, habilitar el seguimiento
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: c5632e79-b182-41c9-9138-eb88b44e3172
caps.latest.revision: 11
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 400d6946235c2137a389b22f639159c9f92d6f4a
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36973157"
---
# <a name="manage-schemas"></a>Administrar esquemas

## <a name="overiew"></a>Información general
En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar esquemas. Las canalizaciones y orquestaciones usan esquemas para representar el mensaje que se procesará.  
  
 Los esquemas se crean en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk. No es posible agregar un esquema a una aplicación de manera individual; un esquema se agrega a una aplicación del modo que se especifica a continuación:  
  
- Cuando agrega un ensamblado de BizTalk que contiene un esquema a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
- Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un esquema, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
- Cuando un programador implementa en una aplicación un ensamblado que contiene un esquema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
  Para obtener información general acerca de los esquemas, vea [esquemas](../core/schemas.md). Para obtener información sobre cómo desarrollar esquemas, vea [crear esquemas utilizando BizTalk Editor](../core/creating-schemas-using-biztalk-editor.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar los scripts que automatizan las tareas administrativas. Para obtener información sobre el uso de WMI, vea el **referencia de clases WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Mostrar y ocultar esquemas de propiedades](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [Ver la definición de esquemas (XSD) de un esquema](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [Configurar el seguimiento de un esquema](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [Quitar un esquema de una aplicación](../core/how-to-remove-a-schema-from-an-application.md)