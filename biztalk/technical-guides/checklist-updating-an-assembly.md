---
title: "Lista de comprobación: Actualizar un ensamblado | Documentos de Microsoft"
ms.custom: 
ms.date: 06/08/2017
ms.prod: biztalk-server
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 5afcb78a-333b-46ff-8681-42362ce5aaad
caps.latest.revision: "3"
author: MandiOhlinger
ms.author: mandia
manager: anneta
ms.openlocfilehash: d9b20aa7d1b0b901176f090ab7636ef0b3eccfa9
ms.sourcegitcommit: cb908c540d8f1a692d01dc8f313e16cb4b4e696d
ms.translationtype: MT
ms.contentlocale: es-ES
ms.lasthandoff: 09/20/2017
---
# <a name="checklist-updating-an-assembly"></a>Lista de comprobación: Actualización de un ensamblado
La siguiente lista de comprobación describe el proceso de actualización de artefactos de uno o más de una aplicación que ya se ha implementado y, a continuación, volver a implementar la aplicación.  
  
> [!NOTE]  
>  Si no se puede programar el tiempo de inactividad o tiene instancias de ejecución muy prolongada que no se puede finalizar, actualice con control de versiones en paralelo.  
  
|Pasos|Referencia|  
|-----------|---------------|  
|Revise las consideraciones importantes para actualizar artefactos en una aplicación.|-   [Consideraciones importantes para actualizar las aplicaciones](http://go.microsoft.com/fwlink/?LinkId=154823) (http://go.microsoft.com/fwlink/?LinkId=154823).<br />-   [Prácticas recomendadas para actualizar las aplicaciones](../technical-guides/best-practices-for-updating-applications.md)|  
|Asegúrese de que tiene permisos apropiados para realizar la implementación.|[Permisos para administrar una aplicación](../technical-guides/permissions-for-managing-an-application.md)|  
|Realice los cambios necesarios para los ensamblados, agregar, quitar o volver a configurar artefactos según sea necesario.<br /><br /> Implementar los ensamblados desde Visual Studio en una aplicación de BizTalk en el entorno de desarrollo.|-   [Cómo actualizar un ensamblado](../technical-guides/how-to-update-an-assembly.md)<br />-   [Actualizar un artefacto](../technical-guides/updating-an-artifact.md)<br />-"Actualizar un artefacto" y "Actualizar un ensamblado" secciones de [prácticas recomendadas para actualizar aplicaciones](../technical-guides/best-practices-for-updating-applications.md)<br />-   [Cómo implementar un ensamblado de BizTalk desde Visual Studio](http://go.microsoft.com/fwlink/?LinkId=154824) (http://go.microsoft.com/fwlink/?LinkId=154824).|  
|Pruebe todos los artefactos nuevos o modificados y asegúrese de probar también todos aquéllos que dependan de los nuevos o modificados. **Nota:** al realizar pruebas, debe tener en cuenta las dependencias que puedan existir entre esta aplicación y otras aplicaciones.|[Tareas de prueba para la implementación de aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154825) (http://go.microsoft.com/fwlink/?LinkId=154825).|  
|En la consola de administración de BizTalk Server, agregar, quitar o volver a configurar los artefactos de la aplicación según sea necesario.|-   [Cómo crear o agregar un artefacto](http://go.microsoft.com/fwlink/?LinkID=154724) (http://go.microsoft.com/fwlink/?LinkID=154724).<br />-   [Cómo quitar un artefacto de una aplicación](http://go.microsoft.com/fwlink/?LinkID=154688) (http://go.microsoft.com/fwlink/?LinkID=154688).<br />-   [Administrar artefactos](http://go.microsoft.com/fwlink/?LinkID=154725) (http://go.microsoft.com/fwlink/?LinkID=154725).<br />-   [Actualizar un artefacto](../technical-guides/updating-an-artifact.md)<br />-Sección "Actualizar un artefacto" de [prácticas recomendadas para actualizar aplicaciones](../technical-guides/best-practices-for-updating-applications.md).|  
|Exporte la aplicación que contiene los artefactos nuevos o modificados a un archivo .msi.|-   [Exportar aplicaciones de BizTalk, los enlaces y directivas](http://go.microsoft.com/fwlink/?LinkId=154826) (http://go.microsoft.com/fwlink/?LinkId=154826).<br />-   [Cómo exportar una aplicación a un archivo .msi](../technical-guides/how-to-export-an-application-to-an-msi-file.md)<br />-"Exportación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md).|  
|Si la actualización va a interferir con la aplicación mientras se ejecuta, programe el tiempo de inactividad y detener la aplicación que desea actualizar.|-   [Cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154729) (http://go.microsoft.com/fwlink/?LinkID=154729).<br />-La sección "Iniciar o detener una aplicación" de [prácticas recomendadas para actualizar aplicaciones](../technical-guides/best-practices-for-updating-applications.md).|  
|Importar los artefactos modificados o actualizados desde el archivo .msi en la aplicación que se va a actualizar, instalar la aplicación. **Nota:** al actualizar un ensamblado de BizTalk, debe detener y dar de baja artefactos antes de importar desde el archivo MSI. Debe volver a dar de alta y, a continuación, iniciar los artefactos de BizTalk después de importar desde el archivo .msi.|-   [Cómo importar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkId=154827) (http://go.microsoft.com/fwlink/?LinkId=154827).<br />-   [Cómo importar una aplicación desde un archivo .msi](../technical-guides/how-to-import-an-application-from-an-msi-file.md)<br />-"Importación de una aplicación de BizTalk" sección de [prácticas recomendadas para implementar una aplicación](../technical-guides/best-practices-for-deploying-an-application.md).<br />-   [Cómo instalar una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154728) (http://go.microsoft.com/fwlink/?LinkID=154728).<br />-   [Cómo instalar un ensamblado en la GAC](http://go.microsoft.com/fwlink/?LinkId=154828) (http://go.microsoft.com/fwlink/?LinkId=154828).|  
|Inicie la aplicación, reanudar la publicación de mensajes. Reinicie todas las instancias de host de BizTalk.|-   [Cómo iniciar y detener una aplicación de BizTalk](http://go.microsoft.com/fwlink/?LinkID=154729) (http://go.microsoft.com/fwlink/?LinkID=154729).|  
|Después de importar un ensamblado que contiene una orquestación, si la aplicación a la que lo va a importar ya contiene un ensamblado con los mismos nombre, token de clave pública y versión, detenga e inicie las instancias de host del host al que esté enlazada la orquestación. De este modo se garantiza que BizTalk Server use la nueva versión del ensamblado.|-   [Cómo detener una instancia de Host](http://go.microsoft.com/fwlink/?LinkId=154829) (http://go.microsoft.com/fwlink/?LinkId=154829).<br />-   [Cómo iniciar una instancia de Host](http://go.microsoft.com/fwlink/?LinkId=154830) (http://go.microsoft.com/fwlink/?LinkId=154830).|