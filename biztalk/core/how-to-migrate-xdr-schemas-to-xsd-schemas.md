---
title: "Cómo migrar esquemas XDR a esquemas XSD | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 90bde0d0-bfe6-4d6c-823c-8ed9c0e15783
caps.latest.revision: "10"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 84bbc42297a10c7d42adb8d778ba19b3b392742c
ms.sourcegitcommit: 5abd0ed3f9e4858ffaaec5481bfa8878595e95f7
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 11/28/2017
---
# <a name="how-to-migrate-xdr-schemas-to-xsd-schemas"></a>Cómo migrar esquemas XDR a esquemas XSD
Si va a migrar esquemas de una versión anterior de BizTalk Server, deberá convertir los esquemas de datos reducidos XML (XDR) a esquemas de lenguaje de definición de esquemas XML (XSD). En este tema se describe los pasos necesarios.  
  
### <a name="to-generate-an-xsd-schema-from-an-xdr-schema"></a>Para generar un esquema XSD a partir de un esquema XDR  
  
1.  En **el Explorador de soluciones**, haga clic en el proyecto de BizTalk correspondiente, seleccione **agregar**y, a continuación, haga clic en **agregar elementos generados**.  
  
2.  En el  **agregar elementos generados - \<* BizTalk ProjectName*\>** cuadro de diálogo, en la **plantillas** sección, haga clic en **generar Esquemas**y, a continuación, haga clic en **agregar**.  
  
3.  En el **generar esquemas** cuadro de diálogo, en la **tipo de documento** lista, seleccione **esquema XDR**.  
  
4.  Haga clic en **examinar**, busque el archivo de esquema XDR que desea migrar y, a continuación, haga clic en **Aceptar**.  
  
     A partir del archivo de esquema XDR especificado se crea un esquema nuevo con el mismo nombre que dicho archivo y la extensión .xsd y, a continuación, se abre en el Editor de BizTalk.  
  
> [!NOTE]
>  Evite el uso de palabras reservadas de C# y nombres de tipos y de espacios de nombres de .NET Framework (como System) en los nombres de los nodos raíz de esquema o en los nombres de archivo.  
  
## <a name="see-also"></a>Vea también  
 [Administrar esquemas en proyectos](../core/managing-schemas-within-projects.md)   
 [Migración de registros de archivo sin formato](../core/migrating-flat-file-records.md)