---
title: "Usar IntelliSense para crear un archivo de configuración de Interceptor | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 349ea1bf-a5d1-4464-bf4b-d8746c622377
caps.latest.revision: "14"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: a7be3f79545db81a0127fc8d004d71c758069a55
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="using-intellisense-to-create-an-interceptor-configuration-file"></a>Uso de IntelliSense para crear un archivo de configuración de interceptor
Puede usar IntelliSense y la validación de esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] para que le ayuden a construir archivos de configuración de interceptor válidos en términos de esquemas. La utilidad de administración de BAM valida el archivo de configuración del interceptor con respecto al esquema de configuración del interceptor base y, si el archivo no es válido, no implementa el esquema. Si el archivo pasa la validación con respecto al esquema de configuración del interceptor base, se valida en relación a los esquemas específicos de la tecnología, como el esquema de [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] o el de [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)], durante el tiempo de ejecución. Si no se encuentran errores, no se producirá ninguna intercepción. Puede prevenir estos errores usando la validación de esquemas en [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] al construir su archivo de configuración de interceptor.  
  
> [!NOTE]
>  Los archivos XSD de configuración de interceptor DE BAM de ejemplo se instalan con archivos SDK. Pueden encontrarse en [!INCLUDE[btsBiztalkServerPath](../includes/btsbiztalkserverpath-md.md)]SDK\Samples\BAM\InterceptorXSDs:  
>   
>  -   CommonInterceptorConfiguration.xsd  
> -   WcfInterceptorConfiguration.xsd  
> -   WorkflowInterceptorConfiguration.xsd  
  
### <a name="to-obtain-a-copy-of-the-interceptor-schemas"></a>Para obtener una copia de los esquemas del interceptor  
  
1.  Abra el Bloc de notas u otro procesador de texto.  
  
2.  Navegue hasta la [esquema de configuración de Interceptor](../core/interceptor-configuration-schema.md) tema.  
  
3.  Pegue el contenido en un nuevo documento en el editor de texto abierto y, a continuación, guarde el archivo como un archivo de texto con el nombre **CommonInterceptorConfiguration.xsd** (o uno de su propia elección) en el disco duro.  
  
4.  Repita estos pasos para la [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] esquema y [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] temas del esquema con los nombres de archivo **WorkflowInterceptorConfiguration.xsd** y **WcfInterceptorConfiguration.xsd** o nombres de su propia elección.  
  
### <a name="to-use-intellisense-with-your-interceptor-configuration-file"></a>Procedimiento para usar IntelliSense con su archivo de configuración de interceptor  
  
1.  Abra [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
2.  Haga clic en **archivo**, haga clic en **New**y, a continuación, haga clic en **archivo**.  
  
3.  En el **nuevo archivo** cuadro de diálogo, seleccione **archivo XML** y, a continuación, haga clic en **abiertos**.  
  
4.  Ver el panel de propiedades haciendo clic en el panel de edición y, a continuación, haga clic en **propiedades**.  
  
5.  En el panel Propiedades, haga clic en **esquemas**y, a continuación, haga clic en el botón de puntos suspensivos (**...** ).  
  
6.  En el **esquemas XML** cuadro de diálogo, haga clic en **agregar** y, a continuación, navegue hasta la ubicación de los esquemas y seleccione **CommonInterceptorConfiguration.xsd** y  **WcfInterceptorConfiguration.xsd** si está trabajando con un [!INCLUDE[firstref_btsWinCommFoundation](../includes/firstref-btswincommfoundation-md.md)] archivo de configuración de interceptor, o **WorkflowInterceptorConfiguration.xsd** si está trabajando con un [!INCLUDE[firstref_btsWinWorkflowFoundation](../includes/firstref-btswinworkflowfoundation-md.md)] archivo de configuración de interceptor.  
  
    > [!NOTE]
    >  Si ha guardado los archivos con nombres diferentes, seleccione esos archivos en su lugar.  
  
7.  [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] validará su archivo de configuración de interceptor cuando éste se abra, y le proporcionará ayuda de IntelliSense cuando cree y vaya modificando el archivo.  
  
## <a name="see-also"></a>Vea también  
 [Esquema de Windows Workflow Foundation](../core/windows-workflow-foundation-schema.md)   
 [Esquema de Windows Communication Foundation](../core/windows-communication-foundation-schema.md)