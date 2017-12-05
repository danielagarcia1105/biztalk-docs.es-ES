---
title: Con las utilidades del Kit de herramientas de ESB de BizTalk | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2dc05ac-831a-44e1-bd44-e41398552ab1
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: db4a8ef2def05e0b77d272463d7a79f937623b1a
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="using-the-biztalk-esb-toolkit-utilities"></a>Con las utilidades del Kit de herramientas de ESB de BizTalk
Esta sección describen diversas utilidades incluidas como parte de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)].  
  
 **Utilidad de importación itinerarios de ESB**  
  
 Esta utilidad se encuentra en el directorio \bin de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y se denomina EsbImportUtil.exe. Esta utilidad se puede usar para publicar o implementar el itinerario XML en la base de datos de ESBItineraryDB.  
  
 La sintaxis de la utilidad es como sigue:  
  
```  
>EsbImportUtil <Parameter1> <Value> <parameter2> <Value>...  
```  
  
 Los distintos parámetros que pueda aceptar son los siguientes:  
  
 /?: \<Mostrar la Ayuda de los parámetros\>  
  
 / f: \<ruta de acceso del archivo de xml de itinerario\>  
  
 / c: \<publicado &#124; implementado\>  
  
 / n: \<nombre itinerario predeterminado\>  
  
 / v: \<versión itinerario predeterminado (formato 'principal.secundaria')\>  
  
 / o: \<sobrescribir silenciosa\>  
  
 Los siguientes son ejemplos de cómo usar esta utilidad.  
  
 Para publicar en la base de datos de itinerario:  
  
```  
>EsbImportUtil /f:myitinerary.xml /c:published  
```  
  
 Para implementar en la base de datos de itinerario:  
  
```  
>EsbImportUtil  /f:myitinerary.xml /c:deployed  
```  
  
 **Configuración de SSO conservar utilidad**  
  
 Esta utilidad se encuentra en el directorio \bin de la [!INCLUDE[esbToolkit](../includes/esbtoolkit-md.md)] y se denomina Microsoft.Practices.ESB.PersistConfigurationTool.exe. Esta utilidad puede usarse para conservar la información de configuración de ESB en la base de datos de SSO de BizTalk. También puede usarse para ver información de configuración y quitar la información de configuración de la base de datos SSO.  
  
 La sintaxis de la utilidad es como sigue:  
  
 **Para agregar una sección de configuración:**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /P /F:app.config /S:SectionName /A:ApplicationName  
```  
  
> [!NOTE]
>  Si no se proporciona/s, se agregarán las siguientes secciones: connectionStrings, esb, esb.resolver y cachingConfiguration.  
  
 **Para quitar una sección:**  
  
```  
>Microsoft.Practices.ESB.PersistConfigurationTool  /R /S:SectionName  
```  
  
 Para ver una sección existente, utilice los modificadores de la aplicación y la sección con el modificador/v.  
  
 Para establecer al administrador de nombre de grupo, utilice el modificador AG:AdminGroupName.  
  
 Para establecer el nombre del grupo de usuario, use el modificador UG:UserGroupName.