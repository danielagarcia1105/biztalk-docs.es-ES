---
title: Pruebas unitarias | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c40e5b82-dbb2-4767-8286-88e2de4129f3
caps.latest.revision: "6"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: faa6dd215aee23f49442e614649fa33f7321d42e
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="unit-testing"></a>Pruebas unitarias
[!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)]presenta un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk. Captura de pantalla siguiente muestra el acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en la configuración de este proyecto **propiedades**.  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades**  
  
 Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones. Los temas de la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] documentación proporciona algunos métodos de ejemplo para usar la característica de pruebas unitarias. Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.  
  
|Tipo de artefacto|Clase base|  
|-------------------|----------------|  
|esquema|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|Mapa|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|Canalización|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 Para obtener más información acerca de la unidad de la característica de pruebas introducidos con [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)], vea los temas siguientes en la [!INCLUDE[btsBizTalkServer2006r3](../includes/btsbiztalkserver2006r3-md.md)] ayuda:  
  
-   [Uso de la característica con esquemas y asignaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).  
  
-   [Uso de la característica con canalizaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>Vea también  
 [Implementación de las pruebas automatizadas](../technical-guides/implementing-automated-testing.md)