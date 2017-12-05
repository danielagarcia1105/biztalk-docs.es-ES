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
ms.openlocfilehash: d5f792adf73fb1e3791f0dfe6c8c5f60a3bb81e6
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="unit-testing"></a>Pruebas unitarias
BizTalk Server introduce un característica que se puede habilitar en de pruebas unitarias la **implementación** página de propiedades de un proyecto de BizTalk. Captura de pantalla siguiente muestra el acceso desde el Diseñador de proyectos cuando haga clic en un proyecto y haga clic en la configuración de este proyecto **propiedades**.  
  
 ![](../core/media/projectdesignerenableunittesting.gif "ProjectDesignerEnableUnitTesting")  
  
 **Captura de pantalla de la pestaña implementación en el Diseñador de proyectos que expone la propiedad de proyecto habilitar pruebas de unidades**  
  
 Esta característica permite crear pruebas de unidades para los esquemas, asignaciones y canalizaciones. Los temas de la documentación de BizTalk Server proporciona algunos métodos de ejemplo para usar la característica de pruebas unitarias. Si se habilita esta característica y se vuelve a generar el proyecto, las clases de artefacto se derivan de las siguientes clases base para admitir las pruebas de unidades.  
  
|Tipo de artefacto|Clase base|  
|-------------------|----------------|  
|esquema|**Microsoft.BizTalk.TestTools.Schema.TestableSchemaBase**|  
|Mapa|**Microsoft.BizTalk.TestTools.Mapper.TestableMapBase**|  
|Canalización|**Microsoft.BizTalk.TestTools.Pipeline.TestablePipelineBase**|  
  
 Para obtener más información acerca de la característica que se introdujo con BizTalk Server de pruebas unitarias, vea los temas siguientes en la Ayuda de BizTalk Server:  
  
-   [Uso de la característica con esquemas y asignaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150482) (http://go.microsoft.com/fwlink/?LinkId=150482).  
  
-   [Uso de la característica con canalizaciones de pruebas de unidades](http://go.microsoft.com/fwlink/?LinkId=150483) (http://go.microsoft.com/fwlink/?LinkId=150483)  
  
## <a name="see-also"></a>Vea también  
 [Implementación de pruebas automatizadas](../technical-guides/implementing-automated-testing.md)