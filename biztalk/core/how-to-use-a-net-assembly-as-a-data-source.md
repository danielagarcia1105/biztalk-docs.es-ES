---
title: Cómo usar un ensamblado .NET como origen de datos | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- Business Rule Composer, data sources
ms.assetid: 14dbec48-acc9-4c3c-bd7f-737dabf29543
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 8fa56370cf894d0d18a36320ca97c4d028fee487
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="how-to-use-a-net-assembly-as-a-data-source"></a>Cómo utilizar un ensamblado .NET como origen de datos
Puede especificar un ensamblado .NET como origen de datos. A continuación, puede seleccionar una clase o miembro de clase del ensamblado y arrastrarla hasta una definición de vocabulario o regla.  
  
### <a name="to-specify-a-net-assembly-as-a-data-source"></a>Para especificar un ensamblado .NET como origen de datos  
  
1.  En la ventana Explorador de hechos, haga clic en el **clases .NET** ficha.  
  
2.  Haga clic en el **módulos** nodo.  
  
3.  Seleccione un ensamblado .NET de entre los disponibles.  
  
    > [!NOTE]
    >  Los ensamblados tienen que estar en la caché de ensamblados global (GAC). El Compositor de reglas de negocio carga un ensamblado .NET al buscar el ensamblado de .NET en el **Explorador de hechos** ventana o en la **clase .NET o una definición de miembro de clase** página de la **vocabulario Definición de** ventana.  Si actualiza el ensamblado en la GAC, cierre el Compositor de reglas de negocios y reinícielo para cargar el ensamblado .NET actualizado. El Compositor de reglas de negocio no actualiza el ensamblado de forma automática.  
  
     ![Captura de pantalla del explorador de árbol de definición y hechos. ] (../core/media/ebiz-netbrowse.gif "ebiz_netbrowse")