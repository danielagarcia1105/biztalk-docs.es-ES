---
title: Cómo crear esquemas para mensajes XML | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: a0270293-fe23-42bd-b090-e877d5e9ce0b
caps.latest.revision: 12
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a22b241d002884f24be0a2972db24b8a398ee1d7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36984453"
---
# <a name="how-to-create-schemas-for-xml-messages"></a>Cómo crear esquemas para mensajes XML
Hay varios métodos para crear esquemas de mensaje de BizTalk. Este tema proporciona instrucciones paso a paso para algunos de estos métodos.  
  
### <a name="to-create-a-new-schema"></a>Para crear un nuevo esquema  
  
1. En **el Explorador de soluciones**, seleccione el proyecto de BizTalk al que desea agregar un esquema.  
  
2. En el menú **Proyecto** , haga clic en **Agregar nuevo elemento**.  
  
3. En el **Agregar nuevo elemento - \< *BizTalk ProjectName* \>**  cuadro de diálogo el **plantillas** sección, haga clic en **esquema**.  
  
4. En el **nombre** , escriba un nombre para el esquema y, a continuación, haga clic en **agregar**.  
  
5. Si es necesario, presione F4 para abrir el [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] ventana Propiedades.  
  
6. En la vista de árbol de esquema, seleccione el **esquema** nodo y, a continuación, en la ventana Propiedades, seleccione la **Target Namespace** propiedad y escriba un nombre para el espacio de nombres de destino. Es importante que establezca esta propiedad en esta fase inicial de creación de esquemas; Evite usar el valor predeterminado **Target Namespace** valor de propiedad.  
  
   > [!NOTE]
   >  Algunos de los nombres que se eligen para los archivos del proyecto, como los archivos de esquema, pueden producir más adelante errores de compilación debido a conflictos con palabras reservadas del lenguaje C# y con nombres de tipos y espacios de nombres de .NET Framework (como System). Entre los ejemplos de esquemas se incluyen schema.xsd, XmlContent y RootNodes. Esto es porque el **nombre de tipo** valores predeterminados de la propiedad a la base parte (que no sean de extensión) de la **Filename** propiedad. Puede solucionar este tipo de error de compilación cambiando explícitamente el valor de la **nombre de tipo** propiedad a algo que no entra en conflicto.  
  
   > [!NOTE]
   >  Puede que deba agregar, eliminar y modificar los registros y campos del esquema junto con las propiedades asociadas. Para obtener más información sobre esto, vea [administrar los nodos de esquema](../core/managing-the-nodes-within-a-schema.md).  
  
### <a name="to-generate-a-schema-from-a-non-xsd-source"></a>Para generar un esquema a partir de un origen no XSD  
  
1.  En **el Explorador de soluciones**, haga clic en un proyecto de BizTalk, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el **agregar elementos generados - \< *BizTalk ProjectName* \>**  cuadro de diálogo el **plantillas** sección, haga clic en **generar Esquemas**y, a continuación, haga clic en **agregar**.  
  
3.  En el **generar esquemas** cuadro de diálogo el **tipo de documento** lista desplegable, seleccione **esquema XDR**, **esquema DTD**, o **XML correcto**.  
  
     Si ve alguno **DTD (no cargado)** o **XML bien formado (no cargado)** en la lista desplegable, seleccione el tipo de documento apropiado de todos modos, y se le guiará a través del proceso de instalación de la Falta el archivo DLL. A continuación, repita estos pasos.  
  
4.  En el **generar esquemas** cuadro de diálogo, haga clic en **examinar**, busque el archivo que desea importar y, a continuación, haga clic en **abierto**. El archivo encontrado debe coincidir con el tipo de documento seleccionado en el paso anterior.  
  
     Se genera un nuevo esquema a partir del archivo especificado con el mismo nombre que el archivo con la extensión .xsd y se abre en el Editor de BizTalk.  
  
## <a name="see-also"></a>Vea también  
 [Administración de esquemas en proyectos](../core/managing-schemas-within-projects.md)