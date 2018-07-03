---
title: Flujo de trabajo BAM | Microsoft Docs
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- monitoring business activities [BAM], collecting business data
- XML files
- orchestrations, XML files
- business activities, business data
- infrastructure, managing [BAM]
- business activities, monitoring
- monitoring business activities [BAM], monitoring flow
- managing [BAM], infrastructure
- monitoring business activities [BAM], viewing business data
- managing [orchestrations], mapping XML to orchestrations
ms.assetid: 8b4ae145-3e16-4bb8-bfba-09b9f666218d
caps.latest.revision: 9
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 4c925e1b77b53bc2ec30a7f42b2446ee410ffef7
ms.sourcegitcommit: 266308ec5c6a9d8d80ff298ee6051b4843c5d626
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 06/27/2018
ms.locfileid: "36989941"
---
# <a name="bam-workflow"></a>Flujo de trabajo de BAM
En la siguiente ilustración se muestran los cuatro roles de usuario que funcionan con Supervisión de la actividad económica, así como las herramientas que usan.  
  
 ![](../core/media/ebiz-tut-bamworkflow.gif "ebiz_tut_bamworkflow")  
Roles de BAM  
  
 Los pasos siguientes proporcionan información general de alto nivel sobre el flujo de trabajo para usar Supervisión de la actividad económica.  
  
## <a name="specifying-the-business-data-to-collect"></a>Especificar los datos económicos que se desea recopilar  
 Los datos económicos se recopilan de la manera siguiente:  
  
-   El analista de negocios usa el Asistente para actividad de BAM para especificar los datos que se deben recopilar para todos los usuarios empresariales.  
  
-   El analista de negocios usa el Asistente para vistas de BAM para definir la vista de cada categoría de usuario empresarial.  
  
-   Cuando termina, guarda las actividades y las vistas en un libro de trabajo de Microsoft® Excel llamado Libro de trabajo de definiciones de BAM.  
  
-   El analista de negocios exporta el Libro de trabajo de definiciones de BAM a XML.  
  
-   El administrador del sistema y el programador usan el archivo XML para desempeñar sus roles.  
  
-   Instrucciones para usar el libro de definición de BAM se encuentran en [definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md).  
  
## <a name="managing-the-bam-infrastructure"></a>Administrar la infraestructura de BAM  
 Una vez que el analista haya definido la vista de BAM que desea, el administrador del sistema usa la utilidad de administración de BAM (BM.EXE), una herramienta de línea de comandos, para implementar la infraestructura de BAM desde el Libro de trabajo de definiciones de BAM o el XML exportado desde dicho libro.  
  
 La utilidad de administración de BAM crea dinámicamente las tablas, los desencadenadores, los paquetes DTS y los cubos de OLAP necesarios para que funcione la vista de BAM.  
  
 Cada vez que el analista de negocios defina una vista de BAM distinta o cambie una existente, el administrador del sistema deberá volver a implementar el Libro de trabajo de definiciones de BAM.  
  
## <a name="mapping-the-xml-to-an-orchestration"></a>Asignar el archivo XML a una orquestación  
 Una vez que el analista de negocios haya exportado el Libro de trabajo de definiciones de BAM a XML, el programador importa el archivo XML al Editor de perfiles de seguimiento. El programador implementa los requisitos de información del analista de negocios, y asigna el archivo XML a una orquestación.  
  
 Mediante el Editor de perfiles de seguimiento, el programador asigna el archivo XML a una orquestación del modo siguiente:  
  
- Carga el ensamblado implementado que se encuentra almacenado en la base de datos de administración de BizTalk (también llamada base de datos de configuración). El ensamblado implementado contiene una o más orquestaciones correspondientes a los requisitos especificados por el analista de negocios en el paso 1.  
  
- Define los datos que deben extraerse de una orquestación. Para ello, coloca elementos de los esquemas de mensaje y de las formas de orquestación en el hito económico (evento) y las carpetas de elementos de datos correspondientes.  
  
- Cuando termina, guarda el perfil como un archivo de seguimiento de BizTalk® Server (.btt) en una base de datos de almacenamiento, tal como Visual SourceSafe.  
  
  El programador implementa el archivo .btt en una base de datos de prueba y comprueba el resultado mediante la prueba de integración.  
  
## <a name="deploying-the-tracking-profile"></a>Implementar el perfil de seguimiento  
 Mediante el Editor de perfiles de seguimiento, el administrador del sistema implementa el perfil en una o varias bases de datos de administración de BizTalk.  
  
 Cada vez que el programador cambie la orquestación o cambien los requisitos de los usuarios empresariales y estos últimos desean someter más datos a seguimiento, el administrador del sistema deberá volver a implementar el perfil de seguimiento mediante la utilidad de línea de comandos bttdeploy.exe.  
  
## <a name="viewing-the-business-data"></a>Ver los datos económicos  
 El usuario empresarial usa el libro de trabajo _LiveData, generado por la utilidad BM.exe. Cada vez que el usuario empresarial abra el libro de trabajo _LiveData, recibirá una nueva versión en directo de los datos recopilados para supervisar un aspecto específico del proceso empresarial.  
  
-   Para ver los datos que se definen como agregación en tiempo real, el usuario empresarial solo tiene que hacer clic en **actualizar** en el libro para ver los datos.  
  
-   Si los datos de la agregación no son de tiempo real, el usuario empresarial ve una instantánea tomada en el momento de ejecutarse el paquete DTS programado.  
  
-   Si la organización tiene requisitos de colaboración, el usuario empresarial puede tener acceso a los datos activos desde el sitio web de BAS.  
  
## <a name="see-also"></a>Vea también  
 [Definir actividades económicas y vistas en Excel](../core/defining-business-activities-and-views-in-excel.md)   
 [Supervisión de actividades económicas con BAM](../core/monitoring-business-activities-with-bam.md)