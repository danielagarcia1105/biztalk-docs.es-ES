---
title: Información general sobre el proceso de desarrollo de BAM | Documentos de Microsoft
ms.custom: ''
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: ''
ms.suite: ''
ms.tgt_pltfrm: ''
ms.topic: article
ms.assetid: 098db3f6-2a61-4cc8-88c7-2299c2e2a55e
caps.latest.revision: 14
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: 78ae5f1c61f2a00359e88acd75c093e2b6c2fb91
ms.sourcegitcommit: 8418b1a8f38b7f56979cd6e203f0b591e2f40fe1
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 03/28/2018
ms.locfileid: "25972506"
---
# <a name="overview-of-the-bam-development-process"></a>Información general sobre el proceso de desarrollo con BAM
En este tema se describen el proceso de desarrollo, así como las bases de datos y tablas que almacenan los datos de BAM.  
  
## <a name="prerequisites-for-developing-with-bam"></a>Requisitos previos para desarrollar con BAM  
 Tenga en cuenta los siguientes requisitos previos antes de desarrollar con BAM:  
  
-   Para instrumentar una aplicación, es preciso tener una actividad implementada.  
  
-   Debe tener derechos DBO en las bases de datos de SQL Server y ser miembro del contexto de seguridad de la función de escritor de eventos de BAM.  
  
-   Debe usar Microsoft .NET 4 para desarrollar la aplicación. Puede usar cualquier lenguaje .NET, aunque recomendamos que use C#.  
  
-   Debe tener la biblioteca Microsoft.BizTalk.BAM.EventObservation.dll instalada en el equipo. Puede obtener el archivo DLL de dos maneras:  
  
    -   Utilice el administrador de configuración de BizTalk Server para instalar las herramientas de BAM. Recomendamos utilizar el administrador de configuración porque coloca las entradas apropiadas en el Registro, lo que facilita las actualizaciones. Para obtener más información sobre la configuración de BAM, consulte [configurar herramientas de BAM mediante el Administrador de configuración](http://go.microsoft.com/fwlink/?LinkId=70561) (http://go.microsoft.com/fwlink/?LinkId=70561).  
  
    -   Copie el archivo DLL desde un equipo donde ya estén instaladas. El archivo DLL reside en Microsoft BizTalk Server \<versión\>carpeta \Tracking.  
  
## <a name="bam-development-process"></a>Proceso de desarrollo con BAM  
 En la ilustración siguiente se describe el flujo de desarrollo con BAM.  
  
 ![Flujo de trabajo de desarrollo de BAM](../core/media/dwb-bamdevelopmentflowc.gif "dwb_bamdevelopmentflowc")  
  
 En el procedimiento siguiente se enumeran los pasos básicos para desarrollar una solución con BAM.  
  
#### <a name="to-develop-a-bam-enabled-solution"></a>Para desarrollar una solución habilitada para BAM  
  
1.  Cree un modelo de observación con el complemento BAM para Excel.  
  
    > [!NOTE]
    >  Ejemplos de los pasos de este procedimiento pueden encontrarse en la API de BAM (ejemplo de BizTalk Server) en [ http://go.microsoft.com/fwlink/?LinkId=69968 ](http://go.microsoft.com/fwlink/?LinkId=69968).  
  
2.  Utilice la utilidad de administración de BAM para implementar la actividad en la base de datos de importación principal (BDIP).  
  
3.  Instrumente la aplicación agregando su propio código de EventStream de BAM.  
  
4.  Ejecute la aplicación. Al hacerlo, el código hará lo siguiente:  
  
    -   Agregar un registro de marcador de posición a la tabla BAM_\<*nombre de la actividad*\>_especifique tabla.  
  
    -   Actualizar los elementos de datos del registro.  
  
    -   Finalizar la actividad y mover el registro a la tabla BAM_\<* nombre de actividad **\>tabla _completed.  
  
## <a name="where-bam-data-is-stored"></a>¿Dónde se guardan los datos de BAM?  
 BAM proporciona el espacio de nombres EventObservation que contiene las clases EventStream usadas para controlar los eventos de BAM.  
  
 Los datos de seguimiento de BAM se almacenan en la base de datos de importación principal (BDIP) de BAM. Al implementar un modelo de observación mediante la utilidad de administración de BAM, se crean las siguientes cinco tablas en la base de datos de importación principal.  
  
|Nombre|Description|  
|----------|-----------------|  
|Tabla activa|Denominado bam_\<*nombre de la actividad*\>_especifique, esta tabla contiene las actividades de este tipo que aún no se han completado.|  
|Tabla de relaciones activas|Denominado bam_\<*nombre de la actividad*\>_ActiveRelationships, esta tabla contiene las actividades relacionadas con la actividad que aún no se han completado.|  
|Tabla de continuaciones|Denominado bam_\<*nombre de la actividad*\>_continuations, esta tabla se muestran las actividades de continuaciones para la actividad.|  
|Tabla de actividades completadas|Denominado bam_\<*nombre de la actividad*\>_completed.|  
|Tabla de relaciones completadas|Denominado bam_\<*nombre de la actividad*\>_CompletedRelationships, esta tabla contiene las actividades relacionadas completadas para la actividad.|  
  
 En una actividad de BAM se capturan cuatro tipos de datos:  
  
-   String  
  
-   Date/Time (normalmente denominados hitos)  
  
-   Integer  
  
-   Float