---
title: Cómo ver ensamblados y tipos en el servidor Local | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 6ddf6f60-9fef-4997-8b42-24eefd7ab0d1
caps.latest.revision: 8
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 37c0f49559de7c4b1a13982578478cf249520479
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
ms.locfileid: "22257324"
---
# <a name="how-to-view-assemblies-and-types-on-the-local-server"></a>Cómo ver ensamblados y tipos en el servidor local
Puede utilizar el Visor de ensamblado de BizTalk para examinar todos los ensamblados y tipos de BizTalk instalados en el servidor local.  
  
### <a name="to-view-all-biztalk-server-assemblies-installed-in-the-gac"></a>Para ver todos los ensamblados de servidor BizTalk Server instalados en la GAC  
  
-   Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
     Aparecerán todos los ensamblados instalados en la caché de ensamblados global (GAC) del equipo.  
  
     ![](../core/media/ebiz-deply-asblyvieweropenpage.gif "ebiz_deply_asblyvieweropenpage")  
Página abierta del Visor de ensamblado  
  
### <a name="to-view-types-attributes-and-references-for-a-biztalk-assembly"></a>Para ver los tipos, los atributos y las referencias de un ensamblado de BizTalk  
  
1.  Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
2.  Haga doble clic en el ensamblado correspondiente.  
  
     Aparecerán los tipos de ensamblado de BizTalk en el panel derecho. Los atributos y tipos aparecen en el panel de la izquierda.  
  
     También puede desplazarse a la ubicación de la instalación del ensamblado haciendo clic en el **Codebase** vínculo en la sección superior izquierda del panel de tareas. (Este vínculo no puede verse cuando el Explorador de Windows está en vista de carpetas ya que el panel de tareas se sustituye por la lista de carpetas.)  
  
### <a name="to-view-the-contents-of-a-type-in-a-biztalk-assembly"></a>Para ver el contenido de un tipo en un ensamblado de BizTalk  
  
1.  Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
2.  Haga doble clic en el ensamblado correspondiente.  
  
3.  En el panel derecho, haga doble clic en el tipo correspondiente.  
  
     El **Visor de contenido de tipo** ventana se abre y aparece la definición XML.  
  
### <a name="to-add-a-biztalk-assembly-in-the-gac"></a>Para agregar un ensamblado de BizTalk en la GAC  
  
1.  Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
2.  Utilice el Explorador de Windows para desplazarse al ensamblado que desea agregar a la GAC.  
  
3.  Arrastre el ensamblado y colóquelo en el Visor de ensamblado de BizTalk.  
  
     Éste solo acepta ensamblados de BizTalk Server. Si coloca un ensamblado que no es de BizTalk en el visor, se ignorará.  
  
### <a name="to-remove-a-biztalk-assembly-from-the-gac"></a>Para quitar un ensamblado de BizTalk de la GAC  
  
1.  Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
2.  Haga clic en el ensamblado que desea quitar de la GAC y haga clic en **eliminar**.  
  
### <a name="to-search-for-a-type-in-all-biztalk-assemblies"></a>Para buscar un tipo en todos los ensamblados de BizTalk  
  
1.  Para abrir el Visor de ensamblado de BizTalk, haga doble clic en **Mi PC**y, a continuación, haga doble clic en **ensamblados de BizTalk Server**.  
  
2.  En la barra de menús, haga clic en el **Biz Talk Server Search** icono.  
  
3.  En la ventana Buscar, especifique el tipo en el **buscar tipos** lista desplegable.  
  
4.  En el **buscar en los ensamblados de BizTalk Server** lista desplegable, seleccione los ensamblados que se va a buscar.  
  
5.  Para limitar la búsqueda de modo que incluya únicamente los tipos a los que hace referencia un tipo concreto, lleve a cabo lo siguiente:  
  
    1.  Haga clic en el **criterios de búsqueda avanzada** vínculo.  
  
    2.  En el **que hace referencia** lista desplegable, seleccione el tipo.  
  
    3.  Haga clic en **Buscar**.  
  
         Los tipos especificados aparecerán en los resultados de la búsqueda.  
  
         ![](../core/media/ebiz-depl-asblyviewtypes.gif "ebiz_depl_asblyviewtypes")  
Tipos de ensamblados de BizTalk  
  
## <a name="see-also"></a>Vea también  
 [Ver ensamblados con el Visor de ensamblado de BizTalk](../core/viewing-assemblies-with-the-biztalk-assembly-viewer.md)