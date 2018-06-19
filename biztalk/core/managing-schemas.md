---
title: Administrar esquemas | Documentos de Microsoft
description: Usar administración de BizTalk para trabajar con esquemas en BizTalk Server, incluida la presentación y ocultación de propiedades, vea el esquema XSD, habilitar el seguimiento
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
ms.openlocfilehash: f0d7fe3eee97cf81c668ffe90fd9c0897af23cc1
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22262604"
---
# <a name="manage-schemas"></a>Administrar esquemas

## <a name="overiew"></a>Información
En esta sección, se proporcionan instrucciones acerca de la utilización de la consola de administración de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)] para administrar esquemas. Las canalizaciones y orquestaciones usan esquemas para representar el mensaje que se procesará.  
  
 Se crean esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] y se compilan en ensamblados de BizTalk. No es posible agregar un esquema a una aplicación de manera individual; un esquema se agrega a una aplicación del modo que se especifica a continuación:  
  
-   Al agregar un ensamblado de BizTalk que contiene un esquema a la aplicación, como se describe en [cómo agregar un ensamblado de BizTalk a una aplicación](../core/how-to-add-a-biztalk-assembly-to-an-application.md).  
  
-   Al importar un archivo .msi en una aplicación que incluye un ensamblado de BizTalk que contiene un esquema, como se describe en [cómo importar una aplicación de BizTalk](../core/how-to-import-a-biztalk-application.md).  
  
-   Cuando un programador implementa en una aplicación un ensamblado que contiene un esquema de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)], tal y como se describe en [implementar ensamblados de BizTalk desde Visual Studio en una aplicación de BizTalk](../core/deploying-biztalk-assemblies-from-visual-studio-into-a-biztalk-application.md).  
  
 Para obtener información general acerca de los esquemas, vea [esquemas](../core/schemas.md). Para obtener información acerca de cómo desarrollar esquemas, vea [crear esquemas de uso del Editor BizTalk](../core/creating-schemas-using-biztalk-editor.md).  
  
> [!NOTE]
>  Puede usar el modelo de objetos de Microsoft Windows Management Instrumentation (WMI) para crear y ejecutar scripts que automatizan las tareas administrativas. Para obtener información acerca del uso de WMI, consulte el **referencia de clase WMI** [!INCLUDE[ui-guidance-developers-reference](../includes/ui-guidance-developers-reference.md)].
  
## <a name="next-steps"></a>Pasos siguientes 
  
-   [Mostrar u ocultar esquemas de propiedades](../core/how-to-show-and-hide-property-schemas.md)  
  
-   [Ver la definición de esquema (XSD) de un esquema](../core/how-to-view-the-schema-definition-xsd-of-a-schema.md)  
  
-   [Configurar el seguimiento de un esquema](../core/how-to-configure-tracking-for-a-schema.md)  
  
-   [Quitar un esquema de una aplicación](../core/how-to-remove-a-schema-from-an-application.md)