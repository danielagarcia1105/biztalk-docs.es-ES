---
title: "Solución de problemas de la < adaptador 2 | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- wildcard characters, in send port properties
- troubleshooting adapter
- Get.xml
- send ports, using wildcards in properties
ms.assetid: e9e0408f-5a12-4f05-83a6-37dc519ae4c5
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 991278813d2183795239d1a75c08e474b2f8159a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="troubleshooting-the-adapter"></a>Solucionar problemas del adaptador
Este tema contiene información para ayudarle a identificar y resolver los problemas que pueda tener mientras usa el adaptador de Microsoft BizTalk para PeopleSoft Enterprise.  
  
## <a name="cannot-use-wildcard-characters-in-send-port-properties"></a>No se pueden usar caracteres comodín en las propiedades de puertos de envío  
 El adaptador de BizTalk para PeopleSoft Enterprise no admite el uso de caracteres comodín en los siguientes campos de propiedades de puertos de envío:  
  
-   Nombre de usuario  
  
-   Ruta de acceso del servidor de aplicación  
  
-   Java_Home  
  
-   Archivos JAR de personas  
  
## <a name="getxml-data-assigns-0001-01-01-value-for-null-dates"></a>Los datos Get.xml asignan el valor 0001-01-01 para fechas nulas  
 Get.xml asigna incorrectamente el valor 0001-01-01 para fechas nulas. Debe usar la herramienta Asignador de BizTalk si desea reemplazar 0001-01-01 por un valor nulo.  
  
## <a name="creating-and-updating-properties-with-collections-fails"></a>Se produce un error al crear y actualizar propiedades con colecciones  
 Al usar el adaptador con la versión 8.17.02 de PeopleSoft, el adaptador puede leer datos del servidor de PeopleSoft correctamente. Sin embargo, se produce un error al crear y actualizar propiedades con colecciones. Este un problema conocido de PeopleSoft que se corregirá en un futuro release de PeopleSoft.  
  
## <a name="see-also"></a>Vea también  
 [Solución de problemas de PeopleSoft](../core/troubleshooting-peoplesoft.md)