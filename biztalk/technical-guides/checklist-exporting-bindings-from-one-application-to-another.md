---
title: "Lista de comprobación: Exportar enlaces desde una aplicación a otra | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 152924e6-da64-4db9-a852-bdb4e79687fb
caps.latest.revision: "2"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: df60a6fd1b266403a5c43b5f76bf7594cad4f41a
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-exporting-bindings-from-one-application-to-another"></a>Lista de comprobación: Exportar enlaces desde una aplicación a otra
En este tema se describe los pasos necesarios para transferir los enlaces de una aplicación a otra aplicación en el entorno de producción o desarrollo. Este proceso es similar al proceso de implementar una aplicación con un archivo MSI. Sin embargo, cuando se implementa una aplicación mediante un archivo .msi, el proceso creará automáticamente la aplicación. Cuando la transferencia de los enlaces de una aplicación a otra, por otro lado, la aplicación de destino ya debe existir.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Asegúrese de que tiene los permisos adecuados para realizar la operación de exportación.|[Permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md)|  
|Cree una aplicación de destino para importar los enlaces de la aplicación en.|-   [Crear una aplicación](../technical-guides/creating-an-application.md)<br />-Sección "Crear una aplicación de BizTalk" de [prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md)|  
|Exportar los enlaces de una aplicación de origen en un archivo de enlace.|-   [Cómo exportar enlaces a un archivo de enlace](../technical-guides/how-to-export-bindings-to-a-binding-file.md)<br />-"Exportación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"Exportación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md).|  
|Importar los enlaces en un archivo de enlace a la aplicación de destino.|-   [Cómo importar enlaces desde un archivo de enlace](../technical-guides/how-to-import-bindings-from-a-binding-file.md)<br />-"Importación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md)<br />-"Importación de una aplicación de BizTalk" sección de [problemas conocidos con la implementación de una aplicación](../technical-guides/known-issues-with-deploying-an-application.md).|