---
title: "Cómo crear esquemas para mensajes XML | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: "12"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 6396d4607e93298961e6691ded2ca8d4566d819c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-create-schemas-for-xml-messages"></a>Cómo crear esquemas para mensajes XML
Hay varios métodos para crear esquemas de mensaje de BizTalk. Este tema proporciona instrucciones paso a paso para algunos de estos métodos.  
  
### <a name="to-create-a-new-schema"></a>Para crear un nuevo esquema  
  
1.  En **el Explorador de soluciones**, seleccione el proyecto de BizTalk al que desea agregar un esquema.  
  
2.  En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
3.  En el  **Agregar nuevo elemento - \<* BizTalk ProjectName*\>** cuadro de diálogo, en la **plantillas** sección, haga clic en **esquema**.  
  
4.  En el **nombre** , escriba un nombre para el esquema y, a continuación, haga clic en **agregar**.  
  
5.  Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.  
  
6.  En la vista de árbol de esquema, seleccione la **esquema** nodo y, a continuación, en la ventana Propiedades, seleccione la **Target Namespace** propiedad y escriba un nombre para el espacio de nombres de destino. Es importante que establezca esta propiedad en esta fase inicial de creación de esquemas; Evite utilizar el valor predeterminado **Target Namespace** valor de propiedad.  
  
    > [!NOTE]
    >  Algunos de los nombres que se eligen para los archivos del proyecto, como los archivos de esquema, pueden producir más adelante errores de compilación debido a conflictos con palabras reservadas del lenguaje C# y con nombres de tipos y espacios de nombres de .NET Framework (como System). Entre los ejemplos de esquemas se incluyen schema.xsd, XmlContent y RootNodes. Esto es porque el **nombre de tipo** valores predeterminados de la propiedad a la parte (no es una extensión) base de la **Filename** propiedad. Puede solucionar este tipo de error de compilación, cambie explícitamente el valor de la **nombre de tipo** propiedad a algo que no entra en conflicto.  
  
    > [!NOTE]
    >  Puede que deba agregar, eliminar y modificar los registros y campos del esquema junto con las propiedades asociadas. Para obtener más información al respecto, consulte [administrar los nodos de un esquema](../core/managing-the-nodes-within-a-schema.md).  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>Para generar un esquema a partir de un origen no XSD  
  
1.  En **el Explorador de soluciones**, haga clic en un proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el  **agregar elementos generados - \<* BizTalk ProjectName*\>** cuadro de diálogo, en la **plantillas** sección, haga clic en  **Generar esquemas**y, a continuación, haga clic en **agregar**.  
  
3.  En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista desplegable, seleccione **esquema XDR**, **esquema DTD**, o **XML correcto**.  
  
     Si ve alguno **DTD (no cargado)** o **XML bien formado (no cargado)** en la lista desplegable, seleccione el tipo de documento correcto de todas formas, y se le guiará a través del proceso de instalación de la Falta el archivo DLL. A continuación, repita estos pasos.  
  
4.  En el **generar esquemas** cuadro de diálogo, haga clic en **examinar**, busque el archivo que desea importar y, a continuación, haga clic en **abiertos**. El archivo encontrado debe coincidir con el tipo de documento seleccionado en el paso anterior.  
  
     Se genera un nuevo esquema a partir del archivo especificado con el mismo nombre que el archivo con la extensión .xsd y se abre en el Editor de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Administración de esquemas en proyectos](../core/managing-schemas-within-projects.md)