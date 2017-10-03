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
ms.openlocfilehash: b06c7383dee805612a3f599148f1d631891ace79
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
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
|% Program Files %\\[!INCLUDE[prague](../includes/prague-md.md)]\Pipeline componentes|Componentes de canalización|(ninguno)|