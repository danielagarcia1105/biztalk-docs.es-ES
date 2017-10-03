---
title: Exportar Bindings6 | Documentos de Microsoft
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- bindings, exporting
- exporting, bindings
ms.assetid: 052a429e-3237-44d4-8933-00aa5edfb212
caps.latest.revision: "22"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 3362984eca1dcec4fb68bfbac92c30da81de8a3b
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="exporting-bindings"></a>Exportar enlaces
En los temas de esta sección se describe cómo exportar enlaces para un grupo, un ensamblado o una aplicación de BizTalk a un archivo .xml. (Los enlaces definen cómo se asocian los hosts, puertos de envío, grupos de puertos de envío, puertos de recepción, ubicaciones de recepción y entidades con las orquestaciones, las canalizaciones, las asignaciones y los esquemas.) A continuación podrá importar los enlaces desde el archivo .xml a otro grupo o aplicación. Al importar enlaces se sobrescriben los enlaces existentes del mismo nombre en el grupo o la aplicación. También puede agregar enlaces a una aplicación, con lo que no se sobrescriben los enlaces existentes. Los enlaces que se agregan no se aplican hasta que se importa la aplicación.  
  
 En los siguientes escenarios, podrá ver que el uso de archivos de enlace acelera la implementación, al evitar la necesidad de configurar los enlaces de forma manual:  
  
-   Mover una aplicación desde un entorno de implementación a otro.  
  
-   Actualizar un ensamblado.  
  
-   Implementar un ensamblado junto con sus enlaces en varios grupos de BizTalk.  
  
 Para obtener más información acerca del uso de archivos de enlace para estos fines, vea [archivos de enlace y la implementación de aplicaciones](../core/binding-files-and-application-deployment.md).  
  
 Para obtener más información sobre cómo importar y agregar enlaces, vea [cómo importar enlaces en un grupo de BizTalk](../core/how-to-import-bindings-into-a-biztalk-group.md), [cómo importar enlaces en una aplicación de BizTalk](../core/how-to-import-bindings-into-a-biztalk-application.md), y [cómo agregar un enlace Archivo a una aplicación](../core/how-to-add-a-binding-file-to-an-application2.md).  
  
> [!IMPORTANT]
>  El archivo de enlace puede contener datos confidenciales. Asegúrese de seguir los pasos necesarios proteger el archivo.  
  
> [!NOTE]
>  Por motivos de seguridad, cuando exporte un archivo de enlace, BizTalk Server quita las contraseñas de los enlaces del archivo. Después de importar los enlaces, deberá volver a configurar las contraseñas para que funcionen los puertos de envío y las ubicaciones de recepción. Configure las contraseñas en el cuadro de diálogo Propiedades de transporte de la consola de administración de BizTalk Server para el puerto de envío o la ubicación de recepción. Para obtener instrucciones, consulte [cómo crear un puerto de envío](../core/how-to-create-a-send-port2.md). Vea también [cómo crear una ubicación de recepción](../core/how-to-create-a-receive-location.md).  
  
## <a name="in-this-section"></a>En esta sección  
  
-   [Cómo exportar enlaces para un grupo de BizTalk](../core/how-to-export-bindings-for-a-biztalk-group.md)  
  
-   [Cómo exportar enlaces para una aplicación de BizTalk](../core/how-to-export-bindings-for-a-biztalk-application.md)  
  
-   [Cómo exportar enlaces para un ensamblado de BizTalk](../core/how-to-export-bindings-for-a-biztalk-assembly.md)  
  
-   [Cómo exportar enlaces para una solución EDI y AS2](../core/how-to-export-bindings-for-an-edi-as2-solution.md)