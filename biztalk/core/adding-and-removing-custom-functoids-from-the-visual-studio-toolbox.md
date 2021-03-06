---
title: Agregar y quitar Functoids personalizados del cuadro de herramientas de Visual Studio | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 28f798cc-da97-4332-a842-ba87ac7b13b8
caps.latest.revision: 20
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8a0ddbab8a116369b6edb39623cd73a16362a3db
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "37013093"
---
# <a name="adding-and-removing-custom-functoids-from-the-visual-studio-toolbox"></a>Adición y eliminación de functoids personalizados del cuadro de herramientas de Visual Studio
En este tema se describe cómo agregar functoids personalizados y quitarlos del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
## <a name="adding-custom-functoids-to-visual-studio"></a>Agregar functoids personalizados a Visual Studio  
 Los functoids personalizados se deben agregar al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] antes de que se puedan usar en una asignación. Utilice el procedimiento siguiente para agregar functoids personalizados.  
  
#### <a name="to-add-a-custom-functoid"></a>Para agregar un functoid personalizado  
  
1. Agregue el functoid al cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
   1. Mediante el Explorador de Windows, busque el ensamblado que implemente su functoid personalizado.  
  
   2. Copie el ensamblado en el \< *carpeta de instalación de BizTalk Server*\>**\Developer Tools\Mapper extensiones** directory. Aquí es donde el Asignador de BizTalk busca functoids personalizados.  
  
   3. Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.  
  
   4. En el **elementos del cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.  
  
   5. Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**. Este proceso podría tardar varios minutos.  
  
       Su functoid personalizado debería aparecer ahora en el cuadro de herramientas en las fichas que coinciden con su categoría.  
  
      \- O BIEN  
  
   6. Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.  
  
   7. En el **elementos del cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.  
  
   8. Haga clic en **restablecer**y, a continuación, haga clic en **Aceptar**.  
  
      > [!NOTE]
      >  Si el functoid personalizado no expone ningún código en línea, asegúrese de que su ensamblado está disponible en la caché global de ensamblados.  
  
   9. En el **archivo** menú, haga clic en **Exit** para cerrar [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
   10. Iniciar **símbolo del sistema de Visual Studio**.  
  
   11. En el símbolo del sistema, escriba **devenv /setup**.  
  
   12. Iniciar **Microsoft Visual Studio**.  
  
        El functoid personalizado debería aparecer en la ficha correspondiente.  
  
2. Agregue el ensamblado a la caché de ensamblados global. Si su ensamblado contiene sólo functoids en línea, puede omitir este paso.  
  
   1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
   2.  Pase a la carpeta que contiene su ensamblado.  
  
   3.  En el símbolo del sistema, escriba **gacutil /if < assembly_path >**. Por ejemplo, si el nombre del ensamblado es FunctoidLibrary.dll, a continuación, escriba **gacutil /if FunctoidLibrary.dll**.  
  
   4.  Cuando haya terminado, escriba **salir**.  
  
## <a name="removing-custom-functoids-from-visual-studio"></a>Quitar functoids personalizados de Visual Studio  
 Utilice el procedimiento siguiente para quitar functoids personalizados.  
  
#### <a name="to-remove-a-custom-functoid"></a>Para quitar un functoid personalizado  
  
1. Quite el functoid del cuadro de herramientas de [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)].  
  
   1. Desde un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, en el **herramientas** menú, haga clic en **elegir elementos del cuadro de herramientas**.  
  
   2. En el **elementos del cuadro de herramientas elija** cuadro de diálogo, haga clic en el **Functoids del asignador de BizTalk** ficha.  
  
   3. Busque el functoid personalizado en la lista, seleccione el **quitar** casilla de verificación y, a continuación, haga clic en **Aceptar**.  
  
      \- O BIEN  
  
   4. Mientras edita una asignación en un [!INCLUDE[btsVStudioNoVersion](../includes/btsvstudionoversion-md.md)] proyecto de BizTalk, haga clic en el **cuadro de herramientas** tab para abrir la paleta de cuadro de herramientas.  
  
   5. Haga clic en el grupo de functoids que contiene su functoid personalizado.  
  
   6. Haga clic en el functoid que desea quitar y, a continuación, haga clic en **eliminar** o presione la tecla SUPR.  
  
2. Quitar el ensamblado de functoid el **Programador\extensiones** directory.  
  
   > [!CAUTION]
   >  Si un ensamblado contiene functoids activos, no los quite. Si lo hace, se interrumpirán otras asignaciones.  
  
   1. Inicie el Explorador de Windows y navegue hasta la **Programador\extensiones** directorio de [!INCLUDE[btsBizTalkServerNoVersion](../includes/btsbiztalkservernoversion-md.md)].  
  
   2. Haga clic en el ensamblado que contiene el functoid que ha quitado y, a continuación, haga clic en **eliminar** para quitar el archivo.  
  
3. Quitar el ensamblado de functoid de la caché de ensamblados global. Si su ensamblado contiene sólo functoids en línea, puede omitir este paso.  
  
   > [!CAUTION]
   >  Si un ensamblado contiene functoids activos, no los quite de la caché de ensamblados global. Si lo hace, se interrumpirán otras asignaciones.  
  
   1.  Iniciar **símbolo del sistema de Visual Studio**.  
  
   2.  En el símbolo del sistema, escriba **gacutil /u < assembly_display_name >**. Por ejemplo, si el nombre del ensamblado es FunctoidLibrary.dll, a continuación, escriba **gacutil /if Functoidlibrary.dll**.  
  
   3.  Cuando haya terminado, escriba **salir**.  
  
## <a name="see-also"></a>Vea también  
 [Desarrollo de functoids personalizados](../core/developing-custom-functoids.md)