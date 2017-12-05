---
title: "Instalar el ejemplo de servicio de resolución | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: fce9bbeb-9377-41af-8ca7-740ce4d1f617
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4bd438725b53362cda1b041af697283e68d77ba7
ms.sourcegitcommit: 3fc338e52d5dbca2c3ea1685a2faafc7582fe23a
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 12/01/2017
---
# <a name="installing-the-resolver-service-sample"></a>Instalar el ejemplo de servicio de resolución
Esta sección describe el proceso de instalación del ejemplo de servicio de resolución. El servicio de resolución depende el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] principales de la solución. Instalar el [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] core automáticamente copia e instala los ensamblados básicos necesarios para este ejemplo en las ubicaciones correctas.  
  
 **Para instalar el ejemplo de servicio de la resolución del proyecto de la solución**  
  
1.  En el Explorador de Windows, abra la carpeta \Source\Samples\ResolverService\Install\Scripts.  
  
2.  Haga doble clic en el archivo Setup_bin.cmd.  
  
3.  Para confirmar la correcta instalación del ejemplo, o si se están produciendo problemas al ejecutar aplicaciones, puede usar la lista proporcionada en la tabla siguiente para comprobar la presencia de los ensamblados necesarios y otros artefactos.  
  
|Ubicación|Categoría|Nombre y versión del componente|  
|--------------|--------------|---------------------------------------|  
|Aplicación de BizTalk GlobalBank.ESB|Orquestaciones|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de envío|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Puertos de recepción|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Ubicaciones de recepción|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Esquemas|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Canalizaciones|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Recursos|(ninguno)|  
|Aplicación de BizTalk GlobalBank.ESB|Directivas|ResolveEndpoint|  
|||ResolveMap|  
|Aplicación de BizTalk GlobalBank.ESB|Mapas|(ninguno)|  
|Caché global de ensamblados|Ensamblados|(ninguno)|  
|% Program Files %\\componentes BizTalk Server\Pipeline|Componentes de canalización|(ninguno)|